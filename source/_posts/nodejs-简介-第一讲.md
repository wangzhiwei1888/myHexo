---
title: nodejs 简介(第一讲)
date: 2016-04-12 11:52:31
tags: ['node']
---

1.1 Node的诞生
1.2 Node 的命名
1.3 Node 给 javascript 带来的意义
1.4 node的特点
 1、异步I/O
 2、事件与回调函数
 3、单线程
 4、跨平台
 
1.5 node的应用场景
 1、I/O密集型
 2、是否不擅长 CPU密集型业务
 3、与遗留系统和平共处
 4、分布式应用
 5、开源硬件

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
atom

工具类
grunt
gulp
webpack
browserify
之前 
maven，ant

**1.4 node的特点**
1.4.1、异步I/O
https://www.zhihu.com/question/19732473
https://cnodejs.org/topic/4f16442ccae1f4aa2700113b

1.4.2、事件与回调函数

![此处输入图片的描述][5]

事件
http://blog.csdn.net/kandyer/article/details/8187613
回调函数
http://www.jb51.net/article/55598.htm

1.4.3、单线程

优点：不用像多线程那样处处在意状态的同步问题，这里没有死锁的存在，也没有上下文交互所带来的性能的开销。

缺点：
1、无法利用多核CPU
2、错误会引起整个应该退出，应用的健壮性值得考虑。
3、大量计算占用CPU导致无法继续调用异步I/O.

一些解决方案。
process.nextTick
nodejs的单线程让群中有些朋友很不满，他们认为如果我们需要进行一些密集计算（比如while(true)这样的），岂不是把整个线程等卡死了？我在一些资料上看到，的确是有这个担心，所以nodejs不适合用来开发cpu密集运算的程序，而适合做那些IO操作比较多，但本身不需要计算太多的程序。因为IO操作通过都是通过异步由nodejs在其它线程中完成，所以不会影响到主线程。
http://www.360doc.com/content/12/0926/15/9579107_238274731.shtml

node 采用了 与 H5 里面的 web workers 相同的思路来解决单线程中大量计算的问题：child_process
https://developer.mozilla.org/zh-CN/docs/Web/API/Web_Workers_API/Using_web_workers

1.4.4、跨平台

![此处输入图片的描述][4]
https://github.com/joyent/libuv
http://www.ghostchina.com/writing-cross-platform-node-js/

**1.5 node的应用场景**
1.5.1、I/O密集型
http://www.zhihu.com/question/29927678?sort=created
1.5.2、是否不擅长 CPU密集型业务
v8很快，如何合理调度cpu
1.5.3、与遗留系统和平共处
linkedin taobao 雪球财经 都是在之前的系统上面 用node 做一块业务。取长补短。
1.5.4、分布式应用
http://baike.baidu.com/link?url=okc9v_tZoSaJcqazY1HJANHg4KjvSSRfdHMiWckKN2gafnKZVctdpU_EAHbVVnts9McgIbjSeVwAr91QUFSxLq
http://developer.51cto.com/art/201507/485041.htm
https://github.com/ty4z2008/Qix
https://github.com/NetEase/pomelo
https://github.com/NetEase/pomelo/wiki/Home-in-Chinese
https://github.com/rvagg/node-worker-farm
https://github.com/lloyd/node-compute-cluster
Reliable 是分布式架构的持续集成系统，由 Macaca 团队的成员开发。适用于集成构建、集成构建等场景。她是典型的主从结构，分为 reliable-master 与 reliable-slave 两部分。
http://www.oschina.net/p/reliable
Write End-to-End tests in Node.js and run against a Webdriver server.
https://github.com/alibaba/macaca
http://macacajs.github.io/macaca/
https://github.com/reliablejs/reliable-master

1.5.5 开源硬件 
https://cnodejs.org/topic/54032efa9769c2e93797cd06

**1.6 node 使用者**
![此处输入图片的描述][3]


**1.7 参考资源**

总结：Node.js采用事件驱动、异步编程，为网络服务而设计
http://www.oschina.net/project/tag/334/nodejs-extends?lang=0&os=156&sort=time
Node.js 扩展开源软件
http://www.dewen.net.cn/q/647
https://github.com/chimurai/http-proxy-middleware

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
https://cnodejs.org/topic/53eb7c1df4b616a82f2338f6
本章参考
http://www.admin10000.com/document/4196.html
https://nodejs.org/dist/latest-v4.x/docs/api/
https://www.baidu.com/s?wd=%E6%B7%B1%E5%85%A5%E6%B5%85%E5%87%BANode.js+site%3Ainfoq.com&rsv_spt=1&rsv_iqid=0xa0e93a3500016f78&issp=1&f=8&rsv_bp=0&rsv_idx=2&ie=utf-8&tn=baiduhome_pg&rsv_enter=1&inputT=13006
http://www.infoq.com/cn/articles/what-is-nodejs
https://github.com/bolshchikov/js-must-watch
http://www.w3school.com.cn/html5/html_5_webworkers.asp
http://blog.jobbole.com/30592/
https://developer.mozilla.org/zh-CN/docs/Web/API/Web_Workers_API/Using_web_workers
http://groups.google.com/group/nodejs/browse_thread/thread/85f6a3829bc64cb6
http://groups.google.com/groups/profile?enc_user=dPo6jggAAACthftLMWCfUq8U6obMz179
http://search.npmjs.org/
http://code.google.com/p/v8/
http://cnodejs.org/topic/4f16442ccae1f4aa27001137
http://weibo.com/1744667943/eBszJXcEsX1
http://stackoverflow.com/questions/5621812/why-is-node-js-named-node-js
http://www.theregister.co.uk/2011/03/01/the_rise_and_rise_of_node_dot_js/page4.html
http://ued.taobao.com/blog/2011/09/02/what-is-nod/
http://www.infoq.com/cn/news/2012/04/interview-xueqiu-using-nodejs
http://teddziuba.com/2011/10/node-js-is-cancer.html
http://www.cnblogs.com/fengmk2/archive/2011/12/14/2288147.html



  [1]: https://nodejs.org/static/images/logos/nodejs-new-white-pantone.png
  [2]: /img/node01.jpg
  [3]: /img/node02.png
  [4]: /img/node03.png
  [5]: /img/node04.png


