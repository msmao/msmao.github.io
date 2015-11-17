---
layout: post
title:  "Mysql 开启远程连接"
date:   2015-11-17 18:25:00
categories: article
---

# Mysql 开启远程连接

## 授予用户权限

grant 权限1、权限2... 权限n on 数据库名称.表名称 to 用户名@用户地址 identified by ‘连接口令’

	grant all privileges on *.* to root@'%' identified by ‘password’

权限1、权限2...权限n 代表`select`、`insert`、`update`、`delete`、`create`、`drop`、`index`、
`alter`、`grant`、`references`、`reload`、`shutdown`、`process`和`file`等14个权限

当权限1、权限2...权限n被`all privileges`或者`all`代替，表示赋予用户全部权限

当数据库名称.表名称被*.*代替，表示赋予用户操作服务器上所有数据库所有表的权限

用户地址可以是`localhost`，也可以是ip地址、机器名字、域名。也可以用`%`表示从任何地址连接

连接口令不能为空，否则创建失败

## 重新刷权限表到内存

	flush privileges

## 退出

	exit