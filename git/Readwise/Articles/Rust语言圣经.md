# Rust语言圣经

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article2.74d541386bbf.png)

## Metadata
- Author: [[course.rs]]
- Full Title: Rust语言圣经
- Category: #articles
- URL: https://course.rs/basic/crate-module/module.html

## Highlights
- **父模块完全无法访问子模块中的私有项，但是子模块却可以访问父模块、父父..模块的私有项**。 ([View Highlight](https://read.readwise.io/read/01gpj0vmnpp62ncz9mknhbt5m0))
- 模块可见性不代表模块内部项的可见性，模块的可见性仅仅是允许其它模块去引用它，但是想要引用它内部的项，还得继续将对应的项标记为 `pub`。 ([View Highlight](https://read.readwise.io/read/01gpj0z8zbqg1cg4ceap7j1vkf))
- • 将结构体设置为 `pub`，但它的所有字段依然是私有的
  • 将枚举设置为 `pub`，它的所有字段也将对外可见 ([View Highlight](https://read.readwise.io/read/01gpj6cfy1hcm37ag47nqx5fd5))
- `mod front_of_house;` 告诉 Rust 从另一个和模块 `front_of_house` 同名的文件中加载该模块的内容 ([View Highlight](https://read.readwise.io/read/01gpj6sb52zhpypzp4mw0j1thk))
