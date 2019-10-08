## Kubernetes ハンズオン 第2回 pod を作成する


### 1. namespace `app` を作成する

``` bash

~$ minikube start -p k8s_hands_on
😄  minikube v1.1.0 on darwin (amd64)
🔥  Creating virtualbox VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
🐳  Configuring environment for Kubernetes v1.14.2 on Docker 18.09.6
🚜  Pulling images ...
🚀  Launching Kubernetes ... 
⌛  Verifying: apiserver proxy etcd scheduler controller dns
🏄  Done! kubectl is now configured to use "k8s_hands_on"

~$ kubectl get namespaces
NAME              STATUS   AGE
default           Active   2m19s
kube-node-lease   Active   2m23s
kube-public       Active   2m23s
kube-system       Active   2m23s

~$ kubectl create namespace app
namespace/app created

~$ kubectl get namespaces
NAME              STATUS   AGE
app               Active   3s
default           Active   2m42s
kube-node-lease   Active   2m46s
kube-public       Active   2m46s
kube-system       Active   2m46s

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


### 3. 作成した nginx の pod で `wget` コマンドを実行
```
~$ kubectl -n app exec -it nginx -- sh -c "wget localhost"
Connecting to localhost (127.0.0.1:80)
index.html           100% |********************************|   612  0:00:00 ETA
```

### 4. pod `nginx` を削除

```bash
~$ kubectl get po nginx -n app 
NAME    READY   STATUS    RESTARTS   AGE
nginx   1/1     Running   0          4m17s

~$ kubectl delete po nginx -n app
pod "nginx" deleted

~$ kubectl get po nginx -n app 
Error from server (NotFound): pods "nginx" not found
```
