# “一把梭：REST API 全用 POST”

![rw-book-cover](https://coolshell.cn/wp-content/uploads/2022/02/http_method.png)

## Metadata
- Author: [[陈皓]]
- Full Title: “一把梭：REST API 全用 POST”
- Category: #articles
- URL: https://coolshell.cn/articles/22173.html

## Highlights
- 很多同学以为 `GET` 的请求数据在URL中，而 `POST` 的则不是，所以以为 `POST` 更安全。不是这样的，整个请求的HTTP URL PATH会全部封装在HTTP的协议头中。只要是HTTPS，就是安全的。当然，有些网关如nginx会把URL打到日志中，或是会放在浏览器的历史记录中，所以有人会说 `GET` 请求不安全，但是，`POST` 也没有好到哪里去，在 [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) 这个最常见的安全问题上，则完全就是针对 `POST` 的。  安全是一件很复杂的事，无论你用哪方法或动词都会不能代表你会更安全。 ([View Highlight](https://read.readwise.io/read/01h0fnewqznktwmsrr5nepbj1s))
