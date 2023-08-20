---
doc_type: weread-highlights-reviews
bookId: "22655637"
author: 肖睿 肖静 董宁
cover: https://wfqqreader-1252317822.image.myqcloud.com/cover/637/22655637/t7_22655637.jpg
reviewCount: 0
noteCount: 12
isbn: 9787115480354
category: 计算机-编程设计
lastReadDate: 2021-04-13
---
# 元数据
> [!abstract] SSM轻量级框架应用实战
> - ![ SSM轻量级框架应用实战|200](https://wfqqreader-1252317822.image.myqcloud.com/cover/637/22655637/t7_22655637.jpg)
> - 书名： SSM轻量级框架应用实战
> - 作者： 肖睿 肖静 董宁
> - 简介： 在互联网迅猛发展的今天，SSM框架被越来越多地应用于企业级开发之中，其发展势头已经超过大部分JavaWeb框架，稳居榜首。本书以实用性为原则，重点讲解SSM框架在企业开发中常用的核心技术。内容逐层深入，而非一次铺开，先逐一讲解MyBatis、Spring和SpringMVC三大框架的精髓内容，再利用经典案例说明和实践，提炼含金量十足的开发经验。为保证学习效果，本书使用SSM框架技术改造经典项目，通过项目的实现加深读者对SSM框架技术的理解和掌握程度。本书提供配套完善的学习资源和支持服务，包括视频教程、案例素材、学习交流社区、讨论组等，为开发者带来全方位的学习体验。
> - 出版时间 2018-04-01 00:00:00
> - ISBN： 9787115480354
> - 分类： 计算机-编程设计
> - 出版社： 人民邮电出版社

# 高亮划线

## 任务3 掌握MyBatis的核心对象


- 📌 build(Reader reader, String environment, Properties properties)。➢ build(InputStream inputStream, String environment, Properties properties)。➢ build(Configuration config 
    - ⏱ 2021-04-13 07:39:31 

- 📌 SqlSessionFactoryBuilder的最大特点是用过即丢。 
    - ⏱ 2021-04-13 07:40:19 

- 📌 SqlSessionFactory对象，这个类就不需要存在了，因此SqlSessionFactoryBuilder的最佳使用范围就是存在于方法体内，也就是局部变量 
    - ⏱ 2021-04-13 07:40:39 

- 📌 openSession()方法的参数为boolean值时，若传入true表示关闭事务控制，自动提交；若传入false表示开启事务控制。若不传入参数，默认为true。openSession(boolean autoCommit)openSession()//若不传入参数，默认为true，自动提交 
    - ⏱ 2021-04-13 07:41:50 

- 📌 ，即随着应用的生命周期一同存在 
    - ⏱ 2021-04-13 07:42:28 

- 📌 单例模式（ 
    - ⏱ 2021-04-13 07:42:38 

- 📌 创建SqlSession的方式只有一个，那就是使用SqlSessionFactory对象的openSession()方法。 
    - ⏱ 2021-04-13 07:49:49 

- 📌 每个线程都有自己的SqlSession实例，SqlSession实例不能被共享，也不是线程安全的。因此最佳的作用域范围是request作用域或者方法体作用域。 
    - ⏱ 2021-04-13 07:50:03 

- 📌 下面的标准方式来关闭 
    - ⏱ 2021-04-13 07:50:21 
## 任务4 掌握MyBatis的核心配置文件


- 📌 property子节点设置的user和password的值会先被读取，由于database.properties中也设置了这两个属性，所以resource中的同名属性将会覆盖property子节点的值。结论：resource属性值的优先级高于property子节点配置的值。 
    - ⏱ 2021-04-13 20:53:51 

- 📌 通过default属性来指定当前的运行环境ID为development，对于环境ID的命名要确保唯一 
    - ⏱ 2021-04-13 21:00:47 

- 📌 mappers映射器用来定义SQL的映射语句，我们只需要告诉MyBatis去哪里找到这些SQL语句，即去哪里找相应的SQL映射文件，可以使用类资源路径或者URL等，关键代码如下。 
    - ⏱ 2021-04-13 21:02:02 
# 读书笔记

# 本书评论
