---
title: Install Redmine with Docker
date: 2018-04-25 20:56:15
tags:
---

# 安装
sudo docker pull mysql:5.7
sudo docker pull redmine:3.2
sudo docker run -d -p 3307:3306 --name mymysql --restart=always -e MYSQL_ROOT_PASSWORD="pass"  -e MYSQL_DATABASE=redmine mysql:5.7 --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci
sudo docker run -d -p 8081:3000 --name myredmine --restart=always -e MYSQL_ROOT_PASSWORD="pass" --link mymysql:mysql -v /var/redmine:/usr/src/redmine redmine:3.2 

这里一定要注意，默认mysql image 如果不指定字符集，倒时候数据库不支持中文的，后期改起来很麻烦

# 访问
sudo docker start myredmine
http://localhost:8081
admin/admin

# 后续维护

#Backup

docker exec mymysql /usr/bin/mysqldump -u root --password=root DATABASE > backup.sql

#Restore
docker exec -i mymysql /usr/bin/mysql -u root --password=root DATABASE < backup.sql

#执行Shell
docker exec -it mymysql /bin/bash
#文件拷贝
docker cp mymysql:/var/lib/mysql/redmine ./ 
#其他
docker stop mymysql
docker rm   mymysql
docker rmi  (id)

Redmine 和 Mysql都是Docker服务
如果 Redmine 连接宿主机器的 mysql