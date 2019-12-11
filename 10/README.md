# Kubernetes ハンズオン 第10回 GCPでクラスタを作成する

### アカウント確認

``` 
~$ gcloud auth list
    Credentialed Accounts
ACTIVE  ACCOUNT
        fXkXmXtX@jXrXfXe.cX.jX
*       mXpXrXoXaXtX@gXaXlXcXm

To set the active account, run:
    $ gcloud config set account `ACCOUNT`

```

### 作業プロジェクト指定

``` 
~$ gcloud config set project iron-dynamics-XXXXXXX
Updated property [core/project].
```

### ゾーン設定

``` 
~$ gcloud config set compute/zone asia-northeast1-a
Updated property [compute/zone].
```

### クラスタ作成

``` 
$ gcloud container clusters create hands-on-10
WARNING: Currently VPC-native is not the default mode during cluster creation. In the future, this will become the default mode and can be disabled using `--no-enable-ip-alias` flag. Use `--[no-]enable-ip-alias` flag to suppress this warning.
WARNING: Newly created clusters and node-pools will have node auto-upgrade enabled by default. This can be disabled using the `--no-enable-autoupgrade` flag.
WARNING: Starting in 1.12, default node pools in new clusters will have their legacy Compute Engine instance metadata endpoints disabled by default. To create a cluster with legacy instance metadata endpoints disabled in the default node pool, run `clusters create` with the flag `--metadata disable-legacy-endpoints=true`.
WARNING: Your Pod address range (`--cluster-ipv4-cidr`) can accommodate at most 1008 node(s). 
This will enable the autorepair feature for nodes. Please see https://cloud.google.com/kubernetes-engine/docs/node-auto-repair for more information on node autorepairs.
ERROR: (gcloud.container.clusters.create) ResponseError: code=403, message=Kubernetes Engine API is not enabled for this project. Please ensure it is enabled in Google Cloud Console and try again: visit https://console.cloud.google.com/apis/api/container.googleapis.com/overview?project=iron-dynamics-242723 to do so.


# 要API有効化とそれに伴い課金設定有効化
# 改めて作成

~$ gcloud container clusters create hands-on-10
WARNING: Currently VPC-native is not the default mode during cluster creation. In the future, this will become the default mode and can be disabled using `--no-enable-ip-alias` flag. Use `--[no-]enable-ip-alias` flag to suppress this warning.
WARNING: Newly created clusters and node-pools will have node auto-upgrade enabled by default. This can be disabled using the `--no-enable-autoupgrade` flag.
WARNING: Starting in 1.12, default node pools in new clusters will have their legacy Compute Engine instance metadata endpoints disabled by default. To create a cluster with legacy instance metadata endpoints disabled in the default node pool, run `clusters create` with the flag `--metadata disable-legacy-endpoints=true`.
WARNING: Your Pod address range (`--cluster-ipv4-cidr`) can accommodate at most 1008 node(s). 
This will enable the autorepair feature for nodes. Please see https://cloud.google.com/kubernetes-engine/docs/node-auto-repair for more information on node autorepairs.
Creating cluster hands-on-10 in asia-northeast1-a... Cluster is being health-checked (master is healthy)...done.                                                                                         
Created [https://container.googleapis.com/v1/projects/iron-dynamics-242723/zones/asia-northeast1-a/clusters/hands-on-10].
To inspect the contents of your cluster, go to: https://console.cloud.google.com/kubernetes/workload_/gcloud/asia-northeast1-a/hands-on-10?project=iron-dynamics-242723
kubeconfig entry generated for hands-on-10.
NAME         LOCATION           MASTER_VERSION  MASTER_IP      MACHINE_TYPE   NODE_VERSION    NUM_NODES  STATUS
hands-on-10  asia-northeast1-a  1.13.11-gke.14  35.243.106.33  n1-standard-1  1.13.11-gke.14  3          RUNNING


```

### 認証情報取得

``` 
~$ gcloud container clusters get-credentials hands-on-10
Fetching cluster endpoint and auth data.
kubeconfig entry generated for hands-on-10.
```

### deployment 作成
``` 
~$ kubectl run hello-server --image gcr.io/google-samples/hello-app:1.0 --port 8080
kubectl run --generator=deployment/apps.v1 is DEPRECATED and will be removed in a future version. Use kubectl run --generator=run-pod/v1 or kubectl create instead.
deployment.apps/hello-server created

```

### hello-server 公開設定

``` 
~$ kubectl expose deployment hello-server --type "LoadBalancer"
service/hello-server exposed

```

### 接続確認

``` 
~$ kubectl get service hello-server
NAME           TYPE           CLUSTER-IP     EXTERNAL-IP     PORT(S)          AGE
hello-server   LoadBalancer   10.59.254.19   104.198.89.47   8080:30842/TCP   87s

~$ curl http://104.198.89.47:8080/
Hello, world!
Version: 1.0.0
Hostname: hello-server-6d89bbd574-gsph7

```

### クリーンアップ

```
~$ kubectl delete service hello-server
service "hello-server" deleted

~$ gcloud container clusters delete hands-on-10
The following clusters will be deleted.
 - [hands-on-10] in [asia-northeast1-a]

Do you want to continue (Y/n)?  Y

Deleting cluster hands-on-10...done.                                                                                                                                                                     
Deleted [https://container.googleapis.com/v1/projects/iron-dynamics-242723/zones/asia-northeast1-a/clusters/hands-on-10].
```
