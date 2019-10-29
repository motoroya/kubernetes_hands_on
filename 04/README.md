## Kubernetes ハンズオン 第5回 service の作成

### 1. namespace `app` を作成する

``` bash

~$  minikube start -p koujou04
There is a newer version of minikube available (v1.5.0).  Download it here:
https://github.com/kubernetes/minikube/releases/tag/v1.5.0

To disable this notification, run the following:
minikube config set WantUpdateNotification false
😄  minikube v1.1.0 on darwin (amd64)
🔥  Creating virtualbox VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
🐳  Configuring environment for Kubernetes v1.14.2 on Docker 18.09.6
🚜  Pulling images ...
🚀  Launching Kubernetes ... 
⌛  Verifying: apiserver proxy etcd scheduler controller dns
🏄  Done! kubectl is now configured to use "koujou04"

~$ kubectl get namespaces
NAME              STATUS   AGE
default           Active   4m8s
kube-node-lease   Active   4m11s
kube-public       Active   4m11s
kube-system       Active   4m11s

~$ kubectl create namespace app
namespace/app created

~$ kubectl get namespaces
NAME              STATUS   AGE
app               Active   2s
default           Active   5m3s
kube-node-lease   Active   5m6s
kube-public       Active   5m6s
kube-system       Active   5m6s

```

### 2. namespace `app` を指定して deployment を作成
```

nginx_deployment.yml は第4回で作成したものを使用する

~$ kubectl -n app apply -f nginx_deployment.yml
deployment.apps/nginx created

```

### 3. namespace `app` を指定して configmap 作成

nginx_config.yml は第3回で作成したものを使用する

```bash
# kubectl apply -f で nginx_deployment.yml を指定し実行

~$ kubectl -n app apply -f nginx_config.yml 
configmap/nginx-config created

```

### 4. deployment `nginx` を公開する service を追加する

```
~$ kubectl -n app get deployment
NAME    READY   UP-TO-DATE   AVAILABLE   AGE
nginx   3/3     3            3           73s

~$ kubectl -n app expose deployment nginx --type=NodePort --name=nginx-service --port=8080
service/nginx-service exposed

~$ kubectl -n app get services
NAME            TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
nginx-service   NodePort   10.108.116.87   <none>        8080:32602/TCP   56s
```

### 5. 確認方法１

```bash
~$ kubectl -n app get service nginx-service
NAME            TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
nginx-service   NodePort   10.108.116.87   <none>        8080:32602/TCP   2m30s
```


### 6. 確認方法２

```bash
~$ kubectl -n app get deployment nginx
NAME    READY   UP-TO-DATE   AVAILABLE   AGE
nginx   3/3     3            3           7m59s

```


### 7. 確認方法３

```bash
# curl インストール

~$ minikube ip -p koujou04
192.168.99.111

~$ curl -I $(minikube ip -p koujou04):8080
curl: (7) Failed to connect to 192.168.99.111 port 8080: Connection refused

# --portに付いて確認し、接続ポートを修正すべく一旦削除

~$ kubectl -n app delete service nginx-service
service "nginx-service" deleted

# 再度 port 80で作成

~$ kubectl -n app expose deployment nginx --type=NodePort --name=nginx-service --port=80
service/nginx-service exposed

# NodePort何番で公開されているか確認

~$ kubectl -n app describe service/nginx-service
Name:                     nginx-service
Namespace:                app
Labels:                   <none>
Annotations:              <none>
Selector:                 app=nginx
Type:                     NodePort
IP:                       10.101.130.218
Port:                     <unset>  80/TCP
TargetPort:               80/TCP
NodePort:                 <unset>  31569/TCP
Endpoints:                172.17.0.5:80,172.17.0.6:80,172.17.0.7:80
Session Affinity:         None
External Traffic Policy:  Cluster
Events:                   <none>

# 応答確認

~$ curl -I $(minikube ip -p koujou04):31569
HTTP/1.1 302 Moved Temporarily
Server: nginx/1.17.5
Date: Tue, 29 Oct 2019 17:12:23 GMT
Content-Type: text/html
Content-Length: 145
Connection: keep-alive
Location: https://www.google.com

```

### 8. service, deployment を削除する

```bash
~$ kubectl -n app delete service nginx-service
service "nginx-service" deleted

~$ kubectl -n app get services
No resources found in app namespace.

~$ kubectl -n app delete deployment nginx
deployment.extensions "nginx" deleted

~$ kubectl -n app get deployment nginx
Error from server (NotFound): deployments.extensions "nginx" not found

~$ kubectl -n app get po -l app=nginx
No resources found in app namespace.

```
