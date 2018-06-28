---
title: Install Jenkins with Docker
date: 2018-04-25 14:33:59
tags:
---

docker确实是一个伟大的发明，有了她，一切变得简单！

sudo docker pull jenkins
sudo docker run -d --name myjenkins -p 8080:8080 -v /var/jenkins:/var/jenkins_home jenkins  --restart=always

两条命令之后，访问:
http://localhost:8080
继续配置后就可以享用Jenkins了。

docker的默认路径在：
/var/lib/docker，所有东西在这里找。
比如
jenkins的workspase，在/var/lib/docker/volumes/XXXXXXXXXX/_data
Jenkins -v 挂载的/var/jenkins_home是对于容器的路径，在host里是看不到的

通过
sudo docker inspect myjenkins
可以一看究竟。
如果要修改已经运行的容器，可以先暂停docker服务，然后找到容器的配置文件修改之
/var/lib/docker/containers/XXXXXXX/hostconfig.json

