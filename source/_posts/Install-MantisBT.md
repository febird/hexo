---
title: Install MantisBT
date: 2018-04-19 21:00:06
tags:
---

    安装软件包
    sudo apt-get install mysql-server(安装过程需要输入用户名/密码：root/rootpwd)
    sudo apt-get install php7.0 php7.0-mysql php7.0-xml php-mbstring apache2  libapache2-mod-php7.0
    安装Mantis
    到官网下载最新版本mantisbt,解压到/var/www/html/mantisbt
    chmod 777 mantisbt -R
    然后如下网页来测试下环境：
    http://localhost/mantisbt/admin/check/index.php
    最后通过如下网页安装：
    http://localhost/mantisbt/admin/install.php
    安装完成就可以访问了：
    http://localhost/mantisbt/login_page.php
    系统默认用户名/密码：
    administrator/root
