---
doc_type: weread-highlights-reviews
bookId: "37445673"
author: 尼恩编著
cover: https://cdn.weread.qq.com/weread/cover/93/YueWen_37445673/t7_YueWen_37445673.jpg
reviewCount: 2
noteCount: 23
isbn: 9787111677581
category: 计算机-编程设计
lastReadDate: 2022-03-15
---
# 元数据
> [!abstract] Java高并发核心编程（卷1）：NIO、Netty、Redis、ZooKeeper
> - ![ Java高并发核心编程（卷1）：NIO、Netty、Redis、ZooKeeper|200](https://cdn.weread.qq.com/weread/cover/93/YueWen_37445673/t7_YueWen_37445673.jpg)
> - 书名： Java高并发核心编程（卷1）：NIO、Netty、Redis、ZooKeeper
> - 作者： 尼恩编著
> - 简介： 本书从操作系统底层的IO原理入手讲解Java高并发核心编程知识，同时提供高性能开发的实战案例，是一本Java高并发编程的基础原理和实战图书。本书共分为15章。第1～4章为高并发基础，浅显易懂地剖析高并发IO的底层原理，图文并茂地介绍Java异步回调模式，细致地讲解Reactor高性能模式。这些原理方面的基础知识非常重要，会为读者打下坚实的基础，也是日常开发Java后台应用时解决实际问题的金钥匙。第5～8章为Netty原理和实战，是本书的重中之重，主要介绍高性能通信框架Netty、Netty的重要组件、单体IM的实战设计和模块实现。第9～12章从TCP、HTTP入手，介绍客户端与服务端、服务端与服务端之间的高性能HTTP通信和WebSocket通信。第13～15章对ZooKeeper、Curator API、Redis、Jedis API的使用进行详尽的说明，以提升读者设计和开发高并发、可扩展系统的能力。本书兼具基础知识和实战案例，既可作为对Java NIO、高性能IO、高并发编程感兴趣的大专院校学生以及初/中级Java工程师的自学图书，也可作为在生产项目中需要用到Netty、Redis、ZooKeeper三大框架的架构师或项目人员的参考书。
> - 出版时间 2021-03-01 00:00:00
> - ISBN： 9787111677581
> - 分类： 计算机-编程设计
> - 出版社： 机械工业出版社

# 高亮划线

## 4.1 Reactor模式的重要性


- 📌 Reactor模式由Reactor线程、Handlers处理器两大角色组成，两大角色的职责分别如下：（1）Reactor线程的职责：负责响应IO事件，并且分发到Handlers处理器。（2）Handlers处理器的职责：非阻塞的执行业务处理逻辑。 
    - ⏱ 2022-03-11 11:36:07 
## 4.2 单线程Reactor模式


- 📌 1）Reactor：负责查询IO事件，当检测到一个IO事件时将其发送给相应的Handler处理器去处理。这里的IO事件就是NIO中选择器查询出来的通道IO事件。（2）Handler：与IO事件（或者选择键）绑定，负责IO事件的处理，完成真正的连接建立、通道的读取、处理业务逻辑、负责将结果写到通道等。 
    - ⏱ 2022-03-11 11:50:43 

- 📌 在Reactor模式实现中，通过attachment()方法所取出的是之前通过attach(Object o)方法绑定的Handler实例，然后通过该Handler实例完成相应的传输处理。 
    - ⏱ 2022-03-11 11:54:03 
## 5.2 解密Netty中的Reactor模式


- 📌 （1）反应器（或者SubReactor子反应器）和通道之间是一对多的关系：一个反应器可以查询很多个通道的IO事件。（2）通道和Handler处理器实例之间是多对多的关系：一个通道的IO事件可以被多个Handler实例处理；一个Handler处理器实例也能绑定到很多通道，处理多个通道的IO事件。 
    - ⏱ 2022-03-14 12:11:57 

- 📌 Netty设计了一个特殊的组件，叫作ChannelPipeline（通道流水线）。它像一条管道，将绑定到一个通道的多个Handler处理器实例串联在一起，形成一条流水线。ChannelPipeline的默认实现实际上被设计成一个双向链表。所有的Handler处理器实例被包装成双向链表的节点，被加入到ChannelPipeline中。 
    - ⏱ 2022-03-14 12:12:41 

- 📌 Netty是这样规定的：入站处理器的执行次序是从前到后，出站处理器的执行次序是从后到前。 
    - ⏱ 2022-03-14 12:15:15 

- 📌 入站的IO操作只能从Inbound入站处理器类型的Handler流过；出站的IO操作只能从Outbound出站处理器类型的Handler流过。 
    - ⏱ 2022-03-14 12:16:00 
## 5.3 详解Bootstrap


- 📌 负责服务器连接监听和接收的监听通道（如NioServerSocketChannel）也叫父通道（ParentChannel），对应于每一个接收到的传输类通道（如NioSocketChannel）也叫子通道（Child Channel）。 
    - ⏱ 2022-03-14 13:02:56 

- 📌 EventLoopGroup就是一个多线程版本的反应器，其中的单个EventLoop线程对应于一个子反应器（SubReactor）。 
    - ⏱ 2022-03-14 13:03:44 

- 📌 默认的EventLoopGroup内部线程数量为最大可用的CPU处理器数量的2倍 
    - ⏱ 2022-03-14 13:04:31 

- 📌 从前文可知，为了及时接收新连接，在服务端，一般有两个独立的反应器，一个负责新连接的监听和接收，另一个负责IO事件轮询和分发，并且两个反应器相互隔离。对应到Netty服务器程序中，则需要设置两个EventLoopGrou 
    - ⏱ 2022-03-14 13:04:58 

- 📌 （1）负责新连接的监听和接收的EventLoopGroup中的反应器完成查询通道的新连接IO事件查询。这些反应器有点像负责招工的包工头，因此，该轮询组可以形象地称为“包工头”（Boss）轮询组。（2）负责IO事件轮询和分发的反应器完成查询所有子通道的IO事件，并且执行对应的Handler处理器完成IO处理——例如数据的输入和输出（有点儿像搬砖），这个轮询组可以形象地称为“工人”（Worker）轮询组。 
    - ⏱ 2022-03-14 15:37:17 

- 📌 可以仅配置一个EventLoopGroup反应器轮询组。具体的配置方法是调用b.group(workerGroup)。在这种模式下，新连接监听IO事件和数据传输IO事件可能被挤在了同一个线程中处理。这样会带来一个风险：新连接的接收被更加耗时的数据传输或者业务处理所阻塞。所以，在服务端，建议设置成两个轮询组的工作模式。 
    - ⏱ 2022-03-14 21:33:53 
## 5.7 详解ByteBuf


- 📌 Direct Memory不属于Java堆内存，所分配的内存其实是调用操作系统malloc()函数来获得的，由Netty的本地Native堆进行管理。 
    - ⏱ 2022-03-15 13:41:10 

- 📌 Direct Buffer的读写比Heap Buffer快，但是它的创建和销毁比普通Heap Buffer慢。 
    - ⏱ 2022-03-15 13:41:38 
## 5.8 Netty的零拷贝


- 📌 ompositeByteBuf里面有一个Component数组，聚合的ByteBuf都放在Component数组里面，最小容量为16 
    - ⏱ 2022-03-15 13:57:10 

- 📌 调用CompositeByteBuf的addComponents()方法向自身增加了ByteBuf对象实例。对于所添加的ByteBuf，Heap ByteBuf、Direct ByteBuf均可。 
    - ⏱ 2022-03-15 14:00:15 
 

- 📌 Unpooled提供的wrap操作既复用了空间，又节省了时间。 
    - ⏱ 2022-03-15 14:20:47 
## 7.3 使用Protobuf协议通信


- 📌 （1）语言无关，平台无关 
    - ⏱ 2022-03-15 14:43:13 

- 📌 （2）高效 
    - ⏱ 2022-03-15 14:43:16 

- 📌 （3）扩展性、兼容性好 
    - ⏱ 2022-03-15 14:43:21 

- 📌 因为Protobuf是二进制数据格式，所以数据序列化之后体积相比JSON和XML要小，更加适合网络传输。 
    - ⏱ 2022-03-15 14:44:05 
# 读书笔记

## 5.2 解密Netty中的Reactor模式

### 划线评论
- 📌 以入站处理为例，每一个来自通道的IO事件都会进入一次ChannelPipeline。在进入第一个Handler处理器后，这个IO事件将按照既定的从前往后次序，在流水线上不断地向后流动，流向下一个Handler处理器。 
    - 💭 责任链模式

    - ⏱ 2022-03-14 12:14:36
   
## 5.8 Netty的零拷贝

### 划线评论
- 📌 Unpooled类提供了很多重载的wrappedBuffer()方法，将多个ByteBuf包装为CompositeByteBuf实例，从而实现零拷贝。 
    - 💭 实现零拷贝：将ByteBuf包装成CompositeByteBuf
    - ⏱ 2022-03-15 14:19:25
   
# 本书评论
