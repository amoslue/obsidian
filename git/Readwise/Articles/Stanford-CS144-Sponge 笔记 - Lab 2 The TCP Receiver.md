# Stanford-CS144-Sponge 笔记 - Lab 2: The TCP Receiver

![rw-book-cover](https://files.epis2048.net/uploads/2022/%E5%9B%BE%E5%83%8F7.png)

## Metadata
- Author: [[吃着土豆坐地铁]]
- Full Title: Stanford-CS144-Sponge 笔记 - Lab 2: The TCP Receiver
- Category: #articles
- URL: https://www.epis2048.net/2022/cs144-lab2/

## Highlights
- 所以流的序列号不是从0开始的。流中的第一个序列号是一个随机的32位数字，称为初始序列号(Initial sequence number, ISN)。这是表示SYN(流的开始)的序列号。 ([View Highlight](https://read.readwise.io/read/01gqhxpmdcex2e6cpkv2xpwdq0))
- **每个逻辑开始和结束占用一个序列号**：除了确保接收到所有字节的数据外，TCP还确保可靠地接收流的开始和结束。因此，在TCP中SYN (start -ofstream)和FIN (end- stream)控制标志被分配了序列号。每一个都占用一个序列号。(SYN标志占用的序列号是ISN。)流中的每个数据字节也占用一个序列号。 ([View Highlight](https://read.readwise.io/read/01gqhxrgx7g4srwr2ynhg2r8mw))
