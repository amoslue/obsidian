# Rust语言圣经

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article2.74d541386bbf.png)

## Metadata
- Author: [[course.rs]]
- Full Title: Rust语言圣经
- Category: #articles
- URL: https://course.rs/advance/smart-pointer/box.html

## Highlights
- 如果一个变量拥有一个数值 `let a = 3`，那变量 `a` 必然是存储在栈上的，那如果我们想要 `a` 的值存储在堆上就需要使用 `Box<T>` ([View Highlight](https://read.readwise.io/read/01gpk3mq1d22wtxjxy0k3kcafc))
- 当栈上数据转移所有权时，实际上是把数据拷贝了一份，最终新旧变量各自拥有不同的数据，因此所有权并未转移。
  而堆上则不然，底层数据并不会被拷贝，转移所有权仅仅是复制一份栈中的指针，再将新的指针赋予新的变量，然后让拥有旧指针的变量失效，最终完成了所有权的转移 ([View Highlight](https://read.readwise.io/read/01gpk41nbps7mj08n2m2a79f32))
