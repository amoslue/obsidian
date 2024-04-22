# Rust语言圣经(Rust Course)

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article0.00998d930354.png)

## Metadata
- Author: [[course.rs]]
- Full Title: Rust语言圣经(Rust Course)
- Category: #articles
- Summary: The text discusses memory management in programming languages, focusing on Rust's ownership system. Rust ensures memory safety by tracking ownership of values and preventing issues like dangling pointers and double freeing memory. The ownership system in Rust helps avoid common memory-related errors and ensures efficient memory management during program execution.
- URL: https://course.rs/basic/ownership/ownership.html

## Highlights
- • Rust 中每一个值都被一个变量所拥有，该变量被称为值的所有者
  • 一个值同时只能被一个变量所拥有，或者说一个值只能拥有一个所有者
  • 当所有者(变量)离开作用域范围时，这个值将被丢弃(drop) ([View Highlight](https://read.readwise.io/read/01hvxppg8b4ej13ctswr4pf26y))
- Rust 为我们提供动态字符串类型: `String`, 该类型被分配到堆上，因此可以动态伸缩，也就能存储在编译时大小未知的文本。 ([View Highlight](https://read.readwise.io/read/01hvxpx4jadgst474erm0ef3y6))
- `String` 类型是一个复杂类型，由存储在栈中的**堆指针**、**字符串长度**、**字符串容量**共同组成，其中**堆指针**是最重要的，它指向了真实存储字符串内容的堆内存，至于长度和容量 ([View Highlight](https://read.readwise.io/read/01hvxpz8pfgmt47q0vm6y53ga5))
- Rust 这样解决问题：**当 `s1` 被赋予 `s2` 后，Rust 认为 `s1` 不再有效，因此也无需在 `s1` 离开作用域后 `drop` 任何东西，这就是把所有权从 `s1` 转移给了 `s2`，`s1` 在被赋予 `s2` 后就马上失效了**。 ([View Highlight](https://read.readwise.io/read/01hvxq0sysq3gezxf276t2dj2j))
