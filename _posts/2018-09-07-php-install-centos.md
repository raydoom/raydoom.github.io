---
title: centos安装php环境
description: 使用yum方式在线安装php环境。
categories:
- work
- php

tags:
- php
---

## 概述

> 使用yum方式在线安装php环境。

<!-- more -->

## 安装

#### 添加Webtatic yum源

Webtatic EL7 for CentOS/RHEL 7

```sh
$ rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
$ rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
```

Webtatic EL6 for CentOS/RHEL 6

```sh
$ rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm
$ rpm -Uvh https://mirror.webtatic.com/yum/el6/latest.rpm
```

#### 安装php环境及相关组件

```sh
$ yum install php55w php55w-bcmath php55w-cli php55w-common php55w-devel php55w-fpm php55w-gd php55w-imap php55w-ldap php55w-mbstring php55w-odbc php55w-pdo php55w-pear php55w-pecl-igbinary php55w-xml php55w-xmlrpc php55w-opcache php55w-intl php55w-pecl-memcache php55w-pecl-redis php55w-mysql
```

如需安装其他版本，只需替换版本号，例如，需要安装5.6版，则将55改为56即可

#### 查看php版本

```sh
$ php -v
PHP 5.5.9 (cli) (built: Feb 11 2014 08:25:33)
Copyright (c) 1997-2014 The PHP Group
Zend Engine v2.5.0, Copyright (c) 1998-2014 Zend Technologies
```

在apache目录/var/www/html/下面新建文件phpinfo.php

```sh
$ cat phpinfo.php
<?php      
phpinfo();
?>
```

启动apache

```sh
$ service httpd start
```

访问http://IP/phpinfo.php




