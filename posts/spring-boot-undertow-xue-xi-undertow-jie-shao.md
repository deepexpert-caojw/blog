---
title: ' 【Spring Boot Undertow学习】Undertow介绍'
date: 2020-01-04 17:53:32
tags: [技术]
published: true
hideInList: false
feature: 
isTop: false
---
  需求缘起：在研究Spring Boot性能优化的时候，碰到了一个高性能Web服务器，本着学习了解的态度，和大家一起学习研究下，有何想法皆可在文章中下面进行评论探讨。
  
<!-- more -->

（1）Undertow介绍；
（2）Undertow几个特点；
（3）相关链接及快速示例；
（4）Spring Boot中使用Undertow；
（5）Undertow之配置信息；


（1）Undertow介绍；
Undertow 是一个采用 Java 开发的灵活的高性能 Web 服务器，提供包括阻塞和基于 NIO 的非堵塞机制。Undertow 是红帽公司的开源产品，是 Wildfly 默认的 Web 服务器。

Undertow 提供一个基础的架构用来构建 Web 服务器，这是一个完全为嵌入式设计的项目，提供易用的构建器 API，完全兼容 Java EE Servlet 3.1 和低级非堵塞的处理器。

 

（2）Undertow几个特点；

（a）轻量化 - Undertow 是一个Web 服务器，但它不像传统的Web 服务器有容器的概念，它由两个核心jar包组成，使用API加载一个Web应用可以使用小于10MB的内存。

（b）HTTP Upgrade 支持 - 设计WildFly时一个重要的考虑因素是在云环境中减少端口数量的需求。在云环境中，一个系统可能运行了几百个甚至几千个WildFly实例。基于HTTP使用HTTP Upgrade可以升级成多种协议，Undertow提供了复用这些协议的能力。

（c）Web Socket 支持 - 对Web Socket的完全支持，用以满足Web应用现在面对巨大数量的客户端，以及对JSR-356规范的支持。

（d）Servlet 3.1 的支持 - Undertow支持Servlet 3.1，提供了一个机会来构建一个超越Servlet规范、对开发人员非常友好的系统。

（e）可嵌套性 - Web 服务器不在需要容器，我们只需要通过API在J2SE代码下快速搭建Web服务。

 

（3）相关链接及快速示例；

Undertow 社区主页（http://undertow.io/）：包括Undertow相关的所有新闻，消息。

Undertow 源代码（https://github.com/undertow-io/）：包括所有Undertow相关的代码

（4）Undertow之配置信息；

Spring boot也为我们提供了Undertow常用的配置信息（在application.properties）:

server.undertow.accesslog.dir= # Undertow access log directory.
server.undertow.accesslog.enabled=false # Enable access log.
server.undertow.accesslog.pattern=common # Format pattern for access logs.
server.undertow.accesslog.prefix=access_log. # Log file name prefix.
server.undertow.accesslog.rotate=true # Enable access log rotation.
server.undertow.accesslog.suffix=log # Log file name suffix.
server.undertow.buffer-size= # Size of each buffer in bytes.
server.undertow.buffers-per-region= # Number of buffer per region.
server.undertow.direct-buffers= # Allocate buffers outside the Java heap.
server.undertow.io-threads= # Number of I/O threads to create for the worker.
server.undertow.max-http-post-size=0 # Maximum size in bytes of the HTTP post content.
server.undertow.worker-threads= # Number of worker threads.