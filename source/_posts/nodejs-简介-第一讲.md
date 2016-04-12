---
title: nodejs 简介(第一讲)
date: 2016-04-12 11:52:31
tags: node
---

1.1 Node的诞生
1.2 Node 的命名
1.3 Node 给 javascript 带来的意义
1.4 node的特点
 1、异步I/O
 2、时间与回调函数
 3、单线程
 4、跨平台
 
1.5 node的应用场景
 1、I/O密集型
 2、是否不擅长 CPU密集型业务
 3、与遗留系统和平共处
 4、分布式应用

1.6 node 使用者
1.7 参考资源


---

**1.1 Node的诞生**
2009年3月，Ryan Dahl在其博客上宣布准备基于V8创建一个轻量级的Web服务器并提供一套库。
http://book.51cto.com/art/201311/417106.htm

**1.2 Node 的命名**
![此处输入图片的描述][1]
https://nodejs.org/en/
Node.js®

**1.3 Node 给 javascript 带来的意义**

![此处输入图片的描述][2]
在node 中，js 可以随心所欲的访问本地文件，可以搭建websocket服务器端，可以连接数据库，可以如 web workers 一样玩转多进程。
node打破了过去 js只能在浏览器中运行的局面。前后端编程环境统一，可以大大降低前后端转换所需要的上下文交换代价。

node-webkit 的出现
工具类
grunt
gulp
webpack
browserify



**1.7 参考资源**
http://www.dewen.net.cn/q/647

除了Node.js，我所知道的，另外还有好几种程序跟技术也是一个支持JavaScript运行于服务器端，我补充一下：

服务端JavaScript框架 RingoJS
RingoJS 是一个用 Java 编写的 JavaScript 允许环境，基于 Mozilla 的 Rhino 的 JavaScript 引擎，可用来开发Web应用程序。

PhantomJS
Phantom JS是一个服务器端的 JavaScript API 的 WebKit。其支持各种Web标准： DOM 处理, CSS 选择器, JSON, Canvas, 和 SVG

JavaScript的Web服务器 Firecat
Firecat是一个服务端JavaScript Web服务器。通过firecat你就能够使用JavaScript来构建一个完整的Web应用程序包括客户端(AJAX)与服务端(NSP)。它类似于ASP和JSP,但用VBScript与Java来代替,它使用JavaScript来作为主要的脚本语言。

JavaScript 语法解析器 PEG.js
Chloropropanoic JS是一个JavaScript 语法解析器，它可以使您轻松建立复杂的数据或计算机程序语言的解析器。 在线版本：http://pegjs.majda.cz/online

SpiderNode
Mozilla对Node.js项目产生了兴趣，正将Node.js移植到Firefox使用的SpiderMonkey引擎中，它的项目被称为SpiderNode，其中所用的技术被称为V8Monkey。由于Node.js与V8是深度整合，因此Mozilla采用的方法是在SpiderMonkey中建立V8接口。Mozilla的目标是创建一个与Node.js不同的版本。
 


  [1]: https://nodejs.org/static/images/logos/nodejs-new-white-pantone.png
  [2]: /img/node01.jpg


