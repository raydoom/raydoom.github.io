---
title: NFS实现多服务器间的目录共享及文件同步
description: NFS（Network File System）即网络文件系统。
categories:
- work
- nfs

tags:
- nfs
---

## 概述

> NFS（Network File System）即网络文件系统。

<!-- more -->

## 安装部署
#### 基础组件
服务器端和客户端均安装组件
```sh
yum -y install nfs-utils rpcbind
```
#### 服务端
创建共享目录
```sh
mkdir /data/nfs
```
NFS配置文件
```sh
$ cat vim /etc/exports
/data/nfs/ 10.10.10.0/24(rw,no_root_squash,no_all_squash,sync)
/data/nfs/ 10.10.10.0/24(rw,no_root_squash,no_all_squash,async)
```
参数说明
>* sync：数据同步写入磁盘
>* async：数据可暂存于内存，可提高性能

配置文件生效
```sh
exportfs  -r
```
启动服务
```sh
service rpcbind start
```
查看状态
```sh
showmount -e 
```
** 需要在hosts中做好本机的主机名与IP地址**
