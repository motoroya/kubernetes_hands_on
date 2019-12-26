

# gcloud container clusters create koujou11


# kubectl run koujou11-mysql --image=mysql:latest --env=MYSQL_ROOT_PASSWORD=1qa3ed5tg7uj9ol --port=3306
# kubectl expose deployment koujou11-mysql  --type NodePort --target-port 3306
# kubectl run ns --restart=Never --image=busybox:1.28 --rm -it --command -- nslookup koujou11-mysql
Server:    10.15.240.10
Address 1: 10.15.240.10 kube-dns.kube-system.svc.cluster.local

Name:      koujou11-mysql
Address 1: 10.15.250.22 koujou11-mysql.default.svc.cluster.local
pod "ns" deleted

# docker build -t 11-rails -f .docker/Dockerfile .
# docker image ls
# docker tag a34eb70a558d gcr.io/iron-dynamics-242723/11-app:latest
# docker push gcr.io/iron-dynamics-242723/11-app:latest
The push refers to repository [gcr.io/iron-dynamics-242723/11-app]
e31b0e5ca3eb: Pushed 
e92e1fc53167: Pushed 
3ebb54b13906: Pushed 
c523513327e1: Pushed 
a5f7e4dd4e48: Pushed 
474d6ea9b785: Pushed 
86a8b2dda85b: Pushed 
6745644b7fd9: Pushed 
a3549f44a2b1: Pushed 
f2f48a68d40e: Pushed 
c15e12dff0e9: Pushed 
31f78d833a92: Layer already exists 
2ea751c0f96c: Layer already exists 
7a435d49206f: Layer already exists 
9674e3075904: Layer already exists 
831b66a484dc: Layer already exists 
latest: digest: sha256:e1ade1eb4fff352a9d0022c68155c8818551c29f3faee62444532e13a494c72f size: 3683

ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)

# kubectl run mgrt --restart=Never --rm -it --image=gcr.io/iron-dynamics-242723/11-app \
       --env=RAILS_ENV=development \
       --env=DB_HOST=koujou11-mysql \
       --env=DB_NAME=app_development \
       --env=DB_PASS=1qa3ed5tg7uj9ol \
       --env=DB_PORT=33060 \
       --env=DB_USER=root \
       --command -- bash
# apt install dnsutils
# root@mgrt:/app# nslookup koujou11-mysql
Server:		10.15.240.10
Address:	10.15.240.10#53

Name:	koujou11-mysql.default.svc.cluster.local
Address: 10.15.250.22
       --command -- bundle exec rake db:create
       --command -- bundle exec rails console
       --command -- bundle exec rake db:migrate

# kubectl run koujou11-migrate --restart=Never --image=11-rails:latest --rm  --env=RAILS_ENV=development --env=DB_HOST=koujou11-mysql  --env=DB_NAME=app_development --env=DB_PASS=1qa3ed5tg7uj9ol --env=DB_PORT=33060  --env=DB_USER=root --command -- bundle exec rails console
 --command -- bundle exec rake db:migrate

# docker-compose build
# docker-compose run --rm rails rails new . --database=mysql

