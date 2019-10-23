## Kubernetes ハンズオン 第4回 deployment の作成

### 1. namespace `app` を作成する

``` bash

~$ $ minikube start -p koujou03
There is a newer version of minikube available (v1.4.0).  Download it here:
https://github.com/kubernetes/minikube/releases/tag/v1.4.0

To disable this notification, run the following:
minikube config set WantUpdateNotification false
😄  minikube v1.1.0 on darwin (amd64)
🔥  Creating virtualbox VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
🐳  Configuring environment for Kubernetes v1.14.2 on Docker 18.09.6
🚜  Pulling images ...
🚀  Launching Kubernetes ... 
⌛  Verifying: apiserver proxy etcd scheduler controller dns
🏄  Done! kubectl is now configured to use "koujou03"

~$ kubectl get namespaces
NAME              STATUS   AGE
default           Active   110s
kube-node-lease   Active   113s
kube-public       Active   113s
kube-system       Active   113s

~$ kubectl create namespace app
namespace/app created

~$ kubectl get namespaces
NAME              STATUS   AGE
app               Active   3s
default           Active   2m1s
kube-node-lease   Active   2m4s
kube-public       Active   2m4s
kube-system       Active   2m4s

```

### 2. namespace `app` を指定して deployment を作成


nginx_deployment.yml
以下は第3回の nginx_alpine.yml からコピー
 - spec.template.spec.volume
 - spec.template.spec.containers 

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx
  namespace: app
spec:
  replicas: 2
  template:
    metadata:
      labels:
        app: nginx
    spec:
      volumes:
      - name: nginx-config
        configMap:
          name: nginx-config
      containers:
        - name: nginx
          image: nginx:alpine
          command: []
          args: [
            "nginx", "-c", "/etc/nginx/custom/custom.conf", "-g", "daemon off;"
          ]
          volumeMounts:
            - name: nginx-config
              mountPath: /etc/nginx/custom
```

### 3. deployment, configmap 作成

nginx_config.yml は第3回で作成したものを使用する

```bash
# kubectl apply -f で nginx_deployment.yml を指定し実行

~$ kubectl -n app apply -f nginx_deployment.yml
deployment.apps/nginx created

~$ kubectl -n app apply -f nginx_config.yml 
configmap/nginx-config created

```

### 4. 確認方法１

```bash
~$ kubectl -n app get deployment nginx
NAME    READY   UP-TO-DATE   AVAILABLE   AGE
nginx   3/3     3            3           11m
```


### 5. 確認方法２

```bash
~$ kubectl -n app get po -l app=nginx
NAME                     READY   STATUS    RESTARTS   AGE
nginx-677967c667-6752s   1/1     Running   0          12m
nginx-677967c667-z8hjk   1/1     Running   0          12m
nginx-677967c667-zbgl9   1/1     Running   0          12m

```


### 6. 確認方法３

```bash
# curl インストール

~$ kubectl -n app exec -it nginx-677967c667-6752s ash

# 以下 container 内での実行内容 

/ # which curl 

/ # which apk
/sbin/apk

/ # apk --no-cache add curl
fetch http://dl-cdn.alpinelinux.org/alpine/v3.10/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.10/community/x86_64/APKINDEX.tar.gz
(1/4) Installing ca-certificates (20190108-r0)
(2/4) Installing nghttp2-libs (1.39.2-r0)
(3/4) Installing libcurl (7.66.0-r0)
(4/4) Installing curl (7.66.0-r0)
Executing busybox-1.30.1-r2.trigger
Executing ca-certificates-20190108-r0.trigger
OK: 30 MiB in 41 packages

/ # which curl
/usr/bin/curl

/ # curl -I localhost
HTTP/1.1 302 Moved Temporarily
Server: nginx/1.17.4
Date: Tue, 15 Oct 2019 16:48:40 GMT
Content-Type: text/html
Content-Length: 145
Connection: keep-alive
Location: https://www.google.com

```

### 10. deployment `nginx` を削除する

```bash
~$ kubectl -n app delete deployment nginx
deployment.extensions "nginx" deleted

~$ kubectl -n app get deployment nginx
Error from server (NotFound): deployments.extensions "nginx" not found

~$ kubectl -n app get po -l app=nginx
No resources found in app namespace.

```
