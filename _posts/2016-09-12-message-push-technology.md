---
layout: post
title:  "消息推送技术"
date:   2016-09-12 14:30:00
categories: article
---

# 消息推送技术

## 关键词
WebSocket、简易轮询、长轮询（COMET）、Html5 服务器推送事件（Server-sent Event）

## 简易轮询
浏览器定时向服务器发出请求，来查询是否有数据更新，技术实现简单，但是需要考虑轮询的时间间隔。间隔时间过长导致用户不能及时收到更新的数据，时间过短，导致查询的请求过多，增加服务器负担。

## 长轮询（COMET）
在每次请求时，服务端会保持该连接在一段时间内处于打开状态，服务端将更新的数据及时的返回给客户端浏览器。当上一个长连接关闭之后，浏览器会重新打开一个新的长链接来继续请求。COMET技术的实现需要在服务端和客户端有第三方Javascript库的支持。

## WebSocket
使用套接字连接，基于TCP协议。在服务端与客户端浏览器之间建立一个套接字连接，进行双向的数据传输。功能强大，使用灵活，实时性高，但是技术复杂。

## Html5 服务器推送事件（Server-sent Event）
Html5的 Server-sent Event 规范有两部分。
1. 第一部分是定义了服务器端与浏览器端通讯的协议，基于纯文本的简单协议，响应的内容类型是`text/event-stream`，可以看成一个由不同的事件组成的事件流，每个事件由类型和数据组成，同时每个事件可有一个可选的标示符。类型为空白表示注释；类型为`data`表示数据；类型为`event`表示事件类型；浏览器收到数据时，会产生对应类型的事件；类型为`id`表示声明事件的标示符；类型为`retry`表示浏览器在连接断开之后进行再次连接之前的等待时间。
2. 第二部分是定义了在浏览器中可供Javascript使用的EventSource对象。EventSource对象提供了标准事件，当成功与服务器建立连接时产生的`onopen()`，当收到服务器发送的事件时产生的`onmessage()`，当出现错误时产生的`onerror()`。

需要注意的是，EventSource对象不支持IE浏览器，在IE上用长轮询（COMET）或者使用第三方Javascript库支持原生的对象，比如：polyfill。
另外，默认每隔3秒发送一个请求，除非将链接关闭（用onclose()），时间间隔可以调整的。


## 相关链接
http://www.ibm.com/developerworks/cn/web/1307_chengfu_serversentevent/
https://w3c.github.io/eventsource/
http://school.youth.cn/px/lamp/2012/1130/38537.shtml
http://www.oschina.net/question/82993_63312?sort=default&p=1#answers