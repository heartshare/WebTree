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

       在页面中使用js访问其他网站的数据时，就会出现跨域问题，比如在网站中使用ajax请求其它
    网站的数据。

    为什么会出现跨域问题
        因为浏览器受到同源策略的限制，当前域名的js只能读取同域下的窗口属性。
        同源策略：不同的域名，不同的端口，不同的协议不允许共享资源，保障浏览器安全
        同源策略是针对浏览器设置的门槛，如果绕过浏览器就能实现跨域，所以说早期的跨域都是
            打着安全路数的擦边球，都可以认为是hack处理。

解决跨域的集中方法：
    1）jsonp跨域方法
       我们提供了一个script标签，请求页面中的数据，同时传入一个回调函数的名字，服务器端得到名字后，并且函数执行格式的字符串，发送回浏览器，script在下载代码后并执行，执行的就是这个函数调用形式的字符串，因此将本地函数调用了，同时拿到了服务端得到的数据。

    2）window.name
       通过修改document的domain属性，我们可以在域和子域火种不同的子域之间通信。同域策略
       认为域，子域隶属于不同的域，这时，我们无法在www.a.com下的页面中调用sub.a.com中
       定义的javascript方法，但是当我们把它们document的domain属性修改为a.com，浏览器
       就会认为它们处于同一个域下，那么我们就可以互相调用对方的method来通信了。

    3）window.postMessage
       window.postMessage是H5定义的一个很新的方法这个方法可以很方便的跨window通信，由于
       它是一个很新的方法，所以在很旧和比较旧的浏览器中无法使用。

借助于服务器代码来跨域（正向代理，反向代理）
</pre>

![](https://i.imgur.com/fNuUpXc.png)

<pre>
正向代理，反向代理
   1）正向代理
      正向代理 是一个位于客户端和原始服务器(origin server)之间的服务器，为了从原始服务器取得内容，客户端向代理发送一个请求并指定目标(原始服务器)，然后代理向原始服务器转交请求并将获得的内容返回给客户端。客户端必须要进行一些特别的设置才能使用正向代理。

      正向代理的用途：
          1）访问原来无法访问的资源
          2）可以做缓存，加速访问资源
          3）对客户端访问授权，上网进行认证
          5）代理可以记录用户访问记录（上网行为管理），对外隐藏信息
      
   2）反向代理
      反向代理（Reverse Proxy）实际运行方式是指以代理服务器来接受internet上的连接请求，然后将请求转发给内部网络上的服务器，并将从服务器上得到的结果返回给internet上请求连接的客户端，此时代理服务器对外就表现为一个服务器

      反向代理用途：
          1）保证内网的安全，可以使用发现代理提供WAF(防火墙功能),组织web攻击
             大型网站，通常将反向代理作为公网访问地址，Web服务器时内网
          2) 负载均衡
             通过反向代理服务器来优化网站的负载     
</pre>

<pre>
Ajax技术
    Ajax技术是一种创建交互式网页应用的网页开发技术，它使用：
        1）使用XHTML + CSS标准化呈现
        2）使用XML与XSL进行数据交换及相关操作
        3）使用XMLHttpRequest对象与WEB服务器进行异步数据通信
        5）使用Javascript操作Document Object Model进行动态显示及交互
        6）使用Javascript绑定和处理所有数据

Ajax工作原理：
    Ajax的工作原理相当于在用户和服务端之间增加了一个中间层（AJAX引擎）,使得用户操作与
    服务响应异步化，并不是所有的用户请求都提交给服务器，像一些数据验证和数据处理等都交给Ajax引擎自己来做，只是确定需要从服务器读取新数据时再由Ajax引擎代为向服务器提交请求。

    Ajax：实现了客户端与服务器端进行数据交流过程，使用技术的好处是:不用页面刷新，并且在
          等待页面传输数据的同时可以进行其他操作。

    举个例子：比如你去图书馆借某种书，可惜图书馆此书已经被借完，这是可以采用两种做法。
        第一种方法：在图书馆一直等待，直到有人还书，然后再去吃饭睡觉
        第二种方法: 直接跟图书馆管理员约定，若是有人还书，直接通知你，你则该忙什么就忙什么，到时候再通知你。
      
        第一种方式就是同步的表现，必须等待别人还书（等待服务器返回信息）才进行其他事情
        第二种方式就是异步的表现。
</pre>