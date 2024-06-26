---
doc_type: weread-highlights-reviews
bookId: "31418034"
author: 张亚
cover: https://wfqqreader-1252317822.image.myqcloud.com/cover/34/31418034/t7_31418034.jpg
reviewCount: 0
noteCount: 11
isbn: 9787111653721
category: 计算机-编程设计
lastReadDate: 2021-02-21
---
# 元数据
> [!abstract] 深入理解JVM字节码
> - ![ 深入理解JVM字节码|200](https://wfqqreader-1252317822.image.myqcloud.com/cover/34/31418034/t7_31418034.jpg)
> - 书名： 深入理解JVM字节码
> - 作者： 张亚
> - 简介： 本书一共12章，从逻辑上主要分为字节码原理篇和应用篇两大部分。第1章详细剖析了class文件的内部结构，帮助读者理解本书后面介绍的字节码原理。第2章首先介绍了什么是字节码，接下来介绍了Java虚拟机栈和栈帧的相关内容，然后通过for循环、switch-case、try-catch-finally等语法讲解了字节码指令的用法。第3章介绍了字节码的进阶知识，主要目的是让读者掌握方法调用指令、泛型擦除、synchronized关键字、反射的底层实现原理。第4章介绍了javac编译器的原理。编译原理是计算机科学皇冠上的明珠，只有弄懂了javac才能更好地理解字节码的生成原理。本章一开始介绍了javac源码的调试方法，随后详细介绍了javac编译的七大阶段和各阶段的作用。第5章从字节码角度看Kotlin语言，介绍了常见语法糖和协程等的原理，希望读者在学习其他JVM系语言时可以举一反三，使用类似的思路。第6章介绍了ASM和Javassist两个字节码操作工具。这两个工具非常重要，被广泛用于中间件框架中，后面关于APM、软件破解的章节都涉及这两个工具的使用。第7章介绍了Java Instrumentation的原理，分两种方式讲解了如何使用Instrumentation，最后介绍了Attach API的底层UNIX域套接字的通信原理。第8章介绍了JSR 269插件化注解处理的原理，希望读者可以通过本章掌握编译期间生成、修改代码的方法，理解Lombok、ButterKnife工具的实现原理。第9章主要介绍了字节码在cglib、Fastjson、Dubbo、JaCoCo、Mock这些框架上的应用，可以让读者接触到更多字节码的使用场景。第10章主要介绍了反编译、破解、防破解和逆向工程的相关内容。了解常见的破解和逆向方法能更好地保护自己的软件产品。第11章介绍了APM的概况、分布式跟踪的基本原理、OpenTracing的基本概念和无埋点字节码插桩的代码实现。如果对APM有兴趣，可以将本章作为入门指导，实现自己的APM产品。第12章详细介绍了Android dex文件的组成结构，以及Android字节码指令与Java字节码指令的区别，最后介绍了Gradle字节码改写实现无侵入插桩的方法。
> - 出版时间 2020-05-01 00:00:00
> - ISBN： 9787111653721
> - 分类： 计算机-编程设计
> - 出版社： 机械工业出版社

# 高亮划线

## 1.1 初探class文件


- 📌 通过这些虚拟机加载和执行同一种平台无关的字节码，我们的源代码就不用根据不同平台编译成不同的二进制可执行文件， 
    - ⏱ 2021-02-21 19:55:09 

- 📌 JDK中自带的javac命令可以将源文件编译成．class文件， 
    - ⏱ 2021-02-21 19:56:19 
## 1.2 class文件结构剖析


- 📌 魔数0 xCAFEBABE是JVM识别．class文件的标志，虚拟机在加载类文件之前会先检查这4个字节，如果不是0 xCAFEBABE，则会抛出java.lang.ClassFormatError异常。 
    - ⏱ 2021-02-21 20:01:24 

- 📌 如果操作数是很常用的数字，比如0，这些操作数是内嵌到字节码中的。如果是字符串常量和较大的整数等，class文件则会把这些操作数存储在常量池（Constant Pool）中，当使用这些操作数时，会根据常量池的索引位置来查找。 
    - ⏱ 2021-02-21 20:11:07 

- 📌 常量池大小 
    - ⏱ 2021-02-21 20:11:37 

- 📌 常量池项 
    - ⏱ 2021-02-21 20:12:10 

- 📌 第一个字节表示常量项的类型（tag），接下来的几个字节表示常量项的具体内容。 
    - ⏱ 2021-02-21 20:12:47 

- 📌 int和float类型的常量，两者的结构很类似，都用4个字节来 
    - ⏱ 2021-02-21 20:30:17 

- 📌 Java语言规范还定义了boolean、byte、short和char类型的变量，在常量池中都会被当作int来处理 
    - ⏱ 2021-02-21 20:25:21 

- 📌 第一个字节是tag，值为固定值1; tag之后的两个字节length并不是表示字符串有多少个字符，而是表示第三部分byte数组的长度；第三部分是采用MUTF-8编码的长度为length的字节数组。 
    - ⏱ 2021-02-21 20:32:22 

- 📌 CONSTANT_String_info用来表示java.lang.String类型的常量对象。它与CONSTANT_Utf8_info的区别是CONSTANT_Utf8_info存储了字符串真正的内容，而CONSTANT_String_info并不包含字符串的内容，仅仅包含一个指向常量池中CONSTANT_Utf8_info常量类型的索引 
    - ⏱ 2021-02-21 20:33:50 
# 读书笔记

# 本书评论
