# WebTree
Web技术研究(研究web前端与后端的交互技术)

![](https://i.imgur.com/B71YZ6U.png)

![](https://i.imgur.com/k9vKge8.png)

<pre>
npm, webpack, gulp, bower, package.json
</pre>

<pre>
npm(node package manager)node.js的包管理工具
npm提供了一个包管理工具，可以重用其它开发者的代码
</pre>

<pre>
webpack
WebPack可以看做是模块打包机：它做的事情是，分析你的项目结构，找到JavaScript模块以及其它的一些浏览器不能直接运行的拓展语言（Scss，TypeScript等），并将其转换和打包为合适的格式供浏览器使用。
</pre>

<pre>
gulp
Gulp 是基于node.js的一个前端自动化构建工具，开发这可以使用它构建自动化工作流程
</pre>

<pre>
bower
表现层的包管理工具
</pre>

<pre>
package.json
定义项目所需要的各种模块，以及项目的配置信息。npm install则是根据这个配置文件，自动下载所需要的模块，也就是配置项目所需的运行和开发环境,文件require依赖时也会从该文件查询
</pre> 

<pre>
js, ajax, jquery
javaScript是用于Web客户端开发的脚本语言，Ajax是基于JS语言，主要组合JS、CSS、XML三种技术的新技术，是用于创建交互式网页应用的网页开发技术。jQuery是JS的框架，基于JS语言，集合Ajax技术开发出来的JS库，封装JS和Ajax的功能，提供函数接口，大大简化了Ajax，JS的操作。 
</pre>

Angularjs

![](https://i.imgur.com/G1dQZ9b.png)

Ajax/Jsonp
<pre>
  Ajax
</pre>

<pre>
  Jsonp
</pre>

cookie/session

![](https://i.imgur.com/o0rF3He.png)

CDN

![](https://i.imgur.com/BjJ0qjU.jpg)

浏览器缓存机制：
    Ctrl+F5 组合键刷新一个页面时，在HTTP的请求头中会增加一些请求头Pragma:no-cache 和 Cache-Controle:no-cache

CDN架构

![](https://i.imgur.com/FuyHoKZ.jpg)

DNS域名解析

![](https://i.imgur.com/6Jl2wfv.jpg)
DNS域名解析：
     当用户在浏览器中输入域名并按下回车键后
     第一步：浏览器会检查缓存中有没有这个域名对应的 解析过的IP地址，如果缓存中有，这个解析过程就将结束。域名缓存的时间是有限制的
     第二步：如果用户的浏览器中没有，浏览器会查找 操作系统缓存中是否有这个域名对应的DNS解析结果（本地DNS解析）

![](https://i.imgur.com/dzfWvUJ.jpg)
	
Socket通信示例

![](https://i.imgur.com/5kNeJ7I.jpg)

<pre>
网络IO的优化
    1）减少网络交互的次数
	2）减少网络传输数据量的大小
	3）编码是需要耗时的，尽量减少编码
</pre>

<pre>
深入理解Session与Cookie
    Session与Cookie的作用都是为了保持访问用户与后端服务器的交互状态。他们有各自的优点，也有各自的缺点，然而具有讽刺意味的是他们的优点
	和它们使用的场景又是矛盾的。例如，使用Cookie传递信息时，随着Cookie个数的增多和访问量的增加，它占用的网络带宽是非常巨大的，
	所以大访问量时希望使用Session，但是Session的致命弱点就是不容在多台服务器间共享，这也限制了Session的使用。

    Session:
         同一个客户端每次与服务端交互时，不需要每次都传回所有的cookie值，而是只要传回一个ID，这个ID是客户端第一次访问服务器时生成的，而且每个客户端是唯一的。这个ID通常是一个名为JSESSIONID的一个cookie，由tomcat分配
    Cookie数据由服务器生成发送给客户端，数据保存在客户端，每次请求由客户端发送给服务器，很   多浏览器插件可解析cookie，不安全
    Session:Session数据保存在服务器端，只是通过Cookie传递一个SessionID而已，所以Session更适合存储用户隐私和重要的数据。
</pre>

分布式session框架

![](https://i.imgur.com/yCOQn4x.jpg)

<pre>
Cookie
       Cookie是存储在用户本地终端上的数据，同时它是与具体的web页面或者站点相关的
    额，cookie数据会自动为web浏览器和服务器之间传输，也就是说HTTP请求发送时，会把保存在该
    请求域名下的所有cookie值发送给web服务器，因此服务器端脚本是可以读，写，存储客户端的
    cookie的操作。

    cookie的有效期：默认情况下有效期是很短暂的，一旦用户关闭浏览器，cookie保存的数据就会
                   丢失。如果想要延长cookie的有效期，可以通过设置HTTP头信息中的
                  cache-control属性中的max-age值，或者修改HTTP头信息中的expires
                  属性的值来延长有效期。
    cookie的作用域：它是通过文档源和文档路径来确定的。该作用域通过cookie的path和domain
                  属性也是可以设置的，默认情况下，cookie和创建它的web页面有关，并对该
                  页面以及该页面同目录或者子目录的其他页面可见。
    cookie的数目和大小的限制：每个web服务器（域名）保存的cookie数不能超过50个，每
                  个cookie保存的数据不能超过4KB，如果超过了4KB,服务器会处理不了。
    cookie的优点：能用于和服务端通信，当cookie快要过期时，可以重新设置而不是删除
    cookie的缺点：它会随着http头信息一起发送，增加了网络流量；它只能储存少量的数据；
                 它只能储存字符串；有潜在的安全问题。
                 另外，自从有了Web Storage(Local and Session Storage)，cookie就不
                 被推荐使用存储数据了。
</pre>

<pre>
LocalStorage
      在HTML5中，新加入了LocalStorage特性，这个特性主要用来做本地存储使用的，解决
   了cookie存储空间不足的问题（cookie每条大小一般为4k），LocalStorage中支持的大小为
   5M大小，这个在不同的浏览器中LocalStorage会有所不同。

   LocalStorage的优点：
       1）LocalStorage拓展了cookie的4K限制
       2）LocalStorage会可以将第一次请求的数据直接存储在本地，这个相当于一个5M大小的针对
          前端页面的数据库，相比于cookie可以节约带宽，但是这个却是只有在高版本的浏览器中才支持
       3）LocalStorage方法存储的数据没有时间限制，
   LocalStorage的缺点
       1）浏览器的大小不统一，并且在IE8以上的IE版本中才支持LocalStorage这个属性
       2）目前所有的浏览器都会把LocalStorage的值类型限定为String类型，这个在对我们日常
          比较常见的JSON对象类型需要一些转换；
       3）LocalStorage在浏览器的隐私模式下是不可读取的
       5）LocalStorage本质上是对字符串的读取，如果存储内容多的话会消耗内存空间，会导致
          页面变卡。
</pre>

<pre>
Session Storage
    sessionStorage与localStorage的唯一区别就是localStorage属于永久性存储，
    而sessionStorage属于当前会话，会话一旦结束键值对就会被清空
</pre>

<pre>
浏览器跨域访问
</pre>