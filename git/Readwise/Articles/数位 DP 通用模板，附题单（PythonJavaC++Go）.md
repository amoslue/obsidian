# 数位 DP 通用模板，附题单（Python/Java/C++/Go）

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article3.5c705a01b476.png)

## Metadata
- Author: [[力扣 LeetCode]]
- Full Title: 数位 DP 通用模板，附题单（Python/Java/C++/Go）
- Category: #articles
- URL: https://leetcode.cn/problems/numbers-with-repeated-digits/solution/by-endlesscheng-c5vg/

## Highlights
- 前置知识：位运算与集合论
  集合可以用二进制表示，二进制从低到高第 iii 位为 111 表示 iii 在集合中，为 000 表示 iii 不在集合中。例如集合 {0,2,3}\{0,2,3\}{0,2,3} 对应的二进制数为 1101(2)1101_{(2)}1101(2)​。
  设集合对应的二进制数为 xxx。本题需要用到两个位运算操作：
  1. 判断元素 ddd 是否在集合中：`x >> d & 1` 可以取出 xxx 的第 ddd 个比特位，如果是 111 就说明 ddd 在集合中。
  2. 把元素 ddd 添加到集合中：将 `x` 更新为 `x | (1 << d)`。 ([View Highlight](https://read.readwise.io/read/01gvyb19asz85f99dbnteszkas))
