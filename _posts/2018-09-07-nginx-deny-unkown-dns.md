---
title: nginx防止域名被恶意指向
description: 设置nginx只监听指定的域名请求，防止服务器IP被恶意解析。
categories:
- work
- nginx

tags:
- nginx
---

## 概述

> 设置nginx只监听指定的域名请求，防止服务器IP被恶意解析。

nginx的默认配置为允许空主机头，用户可以通过IP来访问服务器资源，或者通过解析管理员未设置的域名来访问主机资源，会对对主机和IP的安全性造成威胁，如果被解析的IP未备案，可能导致管局封掉主机的IP地址，修改nginx默认配置来防止恶意解析。

<!-- more -->

## 配置

编辑conf/nginx.conf文件，修改`server_name`值为`_`，并设置返回的状态码为444

```
server {
listen 80 default;
server_name _;
return 444;
}
```

修改后需要重新载入配置文件才能生效

```sh
$ nginx -s reload
```

也可以设置服务器对恶意解析返回403状态码

```
server {
listen 80 default;
server_name _;
return 403;
}
```