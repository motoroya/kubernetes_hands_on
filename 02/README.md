## Kubernetes ハンズオン 第3回 configmap の作成と適用

### 1. namespace `app` を作成する

``` bash

~$ minikube start -p koujou02
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
🏄  Done! kubectl is now configured to use "koujou02"

~$ kubectl get namespaces
NAME              STATUS   AGE
default           Active   8m6s
kube-node-lease   Active   8m9s
kube-public       Active   8m9s
kube-system       Active   8m9s

~$ kubectl create namespace app
namespace/app created

~$ kubectl get namespaces
NAME              STATUS   AGE
app               Active   2s
default           Active   8m42s
kube-node-lease   Active   8m45s
kube-public       Active   8m45s
kube-system       Active   8m45s

```

### 2. namespace `app` を指定して pod を作成


nginx_alpine.yml
```yml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  namespace: app
spec:
  containers:
    - name: nginx
      image: nginx:alpine
```

```bash
# kubectl create -f で nginx_alpine.yml を指定し実行

~$ kubectl create -f nginx_alpine.yml -n app
pod/nginx created

~$ kubectl get po nginx -n app 
NAME    READY   STATUS    RESTARTS   AGE
nginx   1/1     Running   0          64s

```


### 3. コンテナ `nginx` から設定ファイルダウンロード

```bash
~$ kubectl exec -it nginx -n app -- ls -l /etc/nginx | grep conf
drwxr-xr-x    2 root     root          4096 Sep 24 23:33 conf.d
-rw-r--r--    1 root     root          1077 Sep 24 16:01 fastcgi.conf
-rw-r--r--    1 root     root           646 Sep 24 16:01 nginx.conf

~$ kubectl -n app cp nginx:/etc/nginx/nginx.conf custom.conf

~$ ls -l
total 24
-rw-r--r--  1 jiraffe40095  staff  2884 10 16 00:26 README.md
-rw-r--r--  1 jiraffe40095  staff   646 10 16 00:33 custom.conf
-rw-r--r--  1 jiraffe40095  staff   131 10 16 00:35 nginx_alpine.yml

```


### 4. ダウンロードした設定ファイルを修正
以下の差分となるように custom.conf を修正する

```diff 
31c31,41
<     include /etc/nginx/conf.d/*.conf;
---
>     server {
>         listen       80;
>         server_name  localhost;
> 
>         #charset koi8-r;
>         #access_log  /var/log/nginx/host.access.log  main;
> 
>         location / {
>             return 302 https://www.google.com;
>         }
>     }

```

### 5. ファイルから ConfigMap `nginx-config` 作成

```bash
~$ kubectl -n app create configmap nginx-config --from-file=custom.conf
configmap/nginx-config created

~$ kubectl -n app get configmaps
NAME           DATA   AGE
nginx-config   1      6s

```


### 6. configmap `nginx-config` を参照するよう pod 用 yml ファイル修正
参照したファイルを使用するように nginx の実行時オプションを指定

```yml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  namespace: app
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


### 7. pod `nginx` を一旦削除し、(6.) の修正を行なったymlファイルで再度作成する

```bash
~$ kubectl -n app delete pod nginx
pod "nginx" deleted

~$ kubectl -n app create -f nginx_alpine.yml 
pod/nginx created

~$ kubectl -n app get pods
NAME    READY   STATUS              RESTARTS   AGE
nginx   0/1     ContainerCreating   0          8s

```


### 8. container にログインし、curl コマンドをインストールする

```bash
~$ kubectl -n app exec -it nginx -- ash

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

``` 

### 9. localhost にアクセスし動作確認
(8.) に引き続き container 内での実行内容です。

```
/ # curl -I localhost
HTTP/1.1 302 Moved Temporarily
Server: nginx/1.17.4
Date: Tue, 15 Oct 2019 16:48:40 GMT
Content-Type: text/html
Content-Length: 145
Connection: keep-alive
Location: https://www.google.com

```

### 10. pod `nginx` を削除する

```bash
~$ kubectl -n app delete pod nginx
pod "nginx" deleted

~$ kubectl -n app get pods
No resources found in app namespace.

```
