# The Rust Programming Language

![rw-book-cover](https://rdl.ink/render/https%3A%2F%2Fdoc.rust-lang.org%2Fstable%2Fbook%2Fch10-03-lifetime-syntax.html)

## Metadata
- Author: [[rust-lang.org]]
- Full Title: The Rust Programming Language
- Category: #articles
- URL: https://doc.rust-lang.org/stable/book/ch10-03-lifetime-syntax.html

## Highlights
- Lifetime annotations don’t change how long any of the references live. Rather, they describe the relationships of the lifetimes of multiple references to each other without affecting the lifetimes ([View Highlight](https://read.readwise.io/read/01gqpdk1wdt5fdhw2b99t9wdzp))
- One special lifetime we need to discuss is `'static`, which denotes that the affected reference *can* live for the entire duration of the program. ([View Highlight](https://read.readwise.io/read/01gqpervm3gpxrr16pxar9by6w))
- Because lifetimes are a type of generic, the declarations of the lifetime parameter `'a` and the generic type parameter `T` go in the same list inside the angle brackets after the function name. ([View Highlight](https://read.readwise.io/read/01gqpexg379k7kqsstw4vcjbzw))
