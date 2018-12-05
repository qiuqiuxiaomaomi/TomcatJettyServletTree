# TomcatJettyServletTree
Tomcat, Jetty, Servlet技术

###Tomcat体系结构

![](https://i.imgur.com/ufJpxx9.png)

###Tomcat一个请求的处理过程

![](https://i.imgur.com/kQXCK9p.png)


Jetty的基本架构

![](https://i.imgur.com/Qeo7JQE.png)


<pre>
Tomcat和Jetty都是一种Servlet引擎，他们都支持标准的Servlet规范和JavaEE的规范。
      不同点：
            1）架构不同
               Jetty的架构是基于Handler来实现的，主要的扩展功能都可以用Handler来实现，
            扩展简单。
               Tomcat的架构师基于容器设计的，进行扩展是需要了解Tomcat的整体设计结构，不
            易扩展。

            2）性能比较
               差异不大。
               Jetty可以同时处理大量连接而且可以长时间保持连接。适合web聊天应用。
               Jetty的架构简单，因为作为服务器，Jetty可以按需加载组件，减少不需要的组件，
            减少了服务器内存的开销，从而提高服务器的性能。
               Jetty默认采用NIO模型处理I/O请求，在处理静态资源时，性能较高。

                Jetty 有一个处理长连接的机制：一个被称为 Continuations 的特性。利用
            Continuation 机制，Jetty 可以使得一个线程能够用来同时处理多个从客户端发送
            过来的异步请求


                Tomcat适合处理少数非常繁忙的连接，也就是说连接生命周期短的话，Tomcat的总
            体性能更高。
                Tomcat默认采用BIO处理I/O请求，处理静态资源时，性能较差。
                当前Tomcat 8以上默认开启NIO, Nio方式，是Java SE 1.4及后续版本提供的一种新的I/O操作方式(即java.nio包及其子包)，是一个基于缓冲区、并能提供非阻塞I/O操作的Java API，它拥有比传统I/O操作(bio)更好的并发运行性能。tomcat 8版本及以上默认nio模式

             3）其他比较
                Jetty的应用更加快速，修改简单，对新的Servlet规范的支持更友好。
                Tomcat目前应用比较广泛，对JavaEE,Servlet的支持更加全面，很多特性会直接
             集成。

        总结：
             可以理解为Jetty是一个嵌入式的WEB服务器，Jetty的运行速度较快，而是轻量级的，
        Jetty的轻量级使其在处理高并发细粒度请求的场景下显得更快更高效。

             Jetty更满足公有云的分布式环境的需求，而Tomcat更符合企业级环境。
</pre>