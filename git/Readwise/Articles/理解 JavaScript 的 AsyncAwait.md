# 理解 JavaScript 的 Async/Await

![rw-book-cover](https://segmentfault.com/img/bVcV1v3?spec=cover)

## Metadata
- Author: [[segmentfault.com]]
- Full Title: 理解 JavaScript 的 Async/Await
- Category: #articles
- URL: https://segmentfault.com/a/1190000007535316

## Highlights
- 所以，async 函数返回的是一个 Promise 对象 ([View Highlight](https://read.readwise.io/read/01gtjvhecwv1xc9db85drprzpk))
- > `Promise.resolve(x)` 可以看作是 `new Promise(resolve => resolve(x))` 的简写，可以用于快速封装字面量对象或其他对象，将其封装成 Promise 实例。 ([View Highlight](https://read.readwise.io/read/01gtjvhy60rebcybevf1c1frm5))
- 如果一个函数本身就返回 Promise 对象，加 `async` 和不加 `async` 还是有一点点区别：加了 `async` 之后外面得到 Promise 对象并不是 `return` 的那一个 ([View Highlight](https://read.readwise.io/read/01gtjvv8bmnk7v3pys31wr0dym))
# 理解 JavaScript 的 async/await

![rw-book-cover](https://segmentfault.com/img/bVcV1v3?spec=cover)

## Metadata
- Author: [[segmentfault.com]]
- Full Title: 理解 JavaScript 的 async/await
- Category: #articles
- URL: https://segmentfault.com/a/1190000007535316

## Highlights
- 所以，async 函数返回的是一个 Promise 对象 ([View Highlight](https://read.readwise.io/read/01gtjvhecwv1xc9db85drprzpk))
- > `Promise.resolve(x)` 可以看作是 `new Promise(resolve => resolve(x))` 的简写，可以用于快速封装字面量对象或其他对象，将其封装成 Promise 实例。 ([View Highlight](https://read.readwise.io/read/01gtjvhy60rebcybevf1c1frm5))
- 如果一个函数本身就返回 Promise 对象，加 `async` 和不加 `async` 还是有一点点区别：加了 `async` 之后外面得到 Promise 对象并不是 `return` 的那一个 ([View Highlight](https://read.readwise.io/read/01gtjvv8bmnk7v3pys31wr0dym))
