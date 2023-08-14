# 超详细的网络抓包神器 tcpdump 使用指南

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article4.6bc1851654a0.png)

## Metadata
- Author: [[juejin.cn]]
- Full Title: 超详细的网络抓包神器 tcpdump 使用指南
- Category: #articles
- URL: https://juejin.cn/post/6844904084168769549

## Highlights
- `tcpdump` 的常用参数如下：
  $ tcpdump -i eth0 -nn -s0 -v port 80复制代码
  • **-i** : 选择要捕获的接口，通常是以太网卡或无线网卡，也可以是 `vlan` 或其他特殊接口。如果该系统上只有一个网络接口，则无需指定。
  • **-nn** : 单个 n 表示不解析域名，直接显示 IP；两个 n 表示不解析域名和端口。这样不仅方便查看 IP 和端口号，而且在抓取大量数据时非常高效，因为域名解析会降低抓取速度。
  • **-s0** : tcpdump 默认只会截取前 `96` 字节的内容，要想截取所有的报文内容，可以使用 `-s number`， `number` 就是你要截取的报文字节数，如果是 0 的话，表示截取报文全部内容。
  • **-v** : 使用 `-v`，`-vv` 和 `-vvv` 来显示更多的详细信息，通常会显示更多与特定协议相关的信息。
  • `port 80` : 这是一个常见的端口过滤器，表示仅抓取 `80` 端口上的流量，通常是 HTTP。 ([View Highlight](https://read.readwise.io/read/01gsckcgc85jqz6aypzqf3gf8p))
- 一般计算机网卡都工作在非混杂模式下，此时网卡只接受来自网络端口的目的地址指向自己的数据。当网卡工作在混杂模式下时，网卡将来自接口的所有数据都捕获并交给相应的驱动程序 ([View Highlight](https://read.readwise.io/read/01gsckee8zndyckkzwxm9895a4))
- 如果想实时将抓取到的数据通过管道传递给其他工具来处理，需要使用 `-l` 选项来开启行缓冲模式（或使用 `-c` 选项来开启数据包缓冲模式）。使用 `-l` 选项可以将输出通过立即发送给其他命令，其他命令会立即响应。
  $ tcpdump -i eth0 -s0 -l port 80 | grep 'Server:' ([View Highlight](https://read.readwise.io/read/01gshvt55f9s0q7jwcr99jhh3j))
