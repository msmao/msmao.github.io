---
layout: post
title:  "计划任务、定时任务，作业/任务调度"
date:   2015-08-24 22:25:24
categories: article
---


# 计划任务、定时任务，作业/任务调度

计划任务，也称作业/任务调度，是指在某种条件下执行指定的算法或者命令，根据规定时间执行一段算法或命令叫做定时任务，比如 

1. 每天凌晨2点执行系统关机，凌晨6点执行系统开机命令
2. 2015.08.24 13:58:00 执行一段“数据库备份”的程序
3. 从数据库或者文件中读取执行参数条件，执行一段算法，将返回的结果重新写入数据库或者文件

计划任务可以是执行一次，也可以反复执行，可以结合数据库或者文件等媒介做出复杂的算法程序作为任务，符合“执行条件 执行任务”即可

## Unix/Linux 的 Crontab 命令

### 语法
`-u` 用来设定某个用户的`crontab`服务；`-l` 显示某个用户的`crontab`文件内容；`-r` 删除某个用户的`crontab`文件；`-e` 编辑某个用户的`crontab`文件内容，`-i` 在删除用户的`crontab`文件给出确认提示；`file` 是任务命令文件的名字，表示将`file`作为`crontab`的任务列表载入`crontab`中，如果没有指定`file`，将启动编辑器（标准输入）写入命令，并载入`crontab`

	crontab [-u <user>] [file]
	crontab [-u <user>] [-i] [-elr]

### 格式
`minute`，分钟为从0~59的整数，`hour`，小时为从0~23的整数，`day`，日期为从1~31的整数，`month`，月份为从1~12的整数；`dayofweek`，星期为从0~6的整数，0为周日

	minute hour day month dayofweek command

## Mysql 的 事件调度器 Event Scheduler
晚点再补充吧。

## 参考资料
[Event Scheduler](http://dev.mysql.com/doc/refman/5.5/en/events.html, “Event Scheduler”)
