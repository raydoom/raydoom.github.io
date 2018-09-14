---
title: mysql事务隔离级别
description: mysql事务隔离级别设置.

categories:
- work
- mysql

tags:
- mysql
---

## 概述
> mysql事务隔离级别设置.

<!-- more -->

## 查看和设置mysql事务隔离级别

#### 查看当前设置

查看当前会话隔离级别

```sh
mysql> select @@tx_isolation;
+-----------------+
| @@tx_isolation  |
+-----------------+
| REPEATABLE-READ |
+-----------------+
1 row in set, 1 warning (0.00 sec)
```

查看系统当前隔离级别

```sh
mysql> select @@global.tx_isolation;
+-----------------------+
| @@global.tx_isolation |
+-----------------------+
| REPEATABLE-READ       |
+-----------------------+
1 row in set, 1 warning (0.00 sec)
```

#### 设置隔离级别

设置当前会话隔离级别

```sh
mysql> set session transaction isolatin level repeatable read;
```

设置系统当前隔离级别

```sh
mysql> set global transaction isolation level repeatable read;
```

命令行操作，开始事务时

```sh
mysql> set autocommit=off 
#或
mysql> start transaction
```

#### 配置文件写法在

my.cnf中加入一行

```sh
transaction-isolation = READ-COMMITTED
```

## mysql事务隔离级别解析

* read uncommitted
> 可以看到未提交的数据（脏读）

* read committed
> 读取提交的数据。但是，可能多次读取的数据结果不一致（不可重复读，幻读）

* repeatable read(MySQL默认隔离级别)
> 可以重复读取，但有幻读。读写观点：读取的数据行不可写，但是可以往表中新增数据。在MySQL中，其他事务新增的数据，看不到，不会产生幻读。采用多版本并发控制（MVCC）机制解决幻读问题

* serializable
>可读，不可写。写数据必须等待另一个事务结束



