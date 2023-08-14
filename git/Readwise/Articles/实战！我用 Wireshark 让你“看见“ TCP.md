# 实战！我用 Wireshark 让你“看见“ TCP

![rw-book-cover](https://pica.zhimg.com/v2-e42bad387cb9f0783b5c35def8b9aa77_720w.jpg?source=172ae18b)

## Metadata
- Author: [[知乎专栏]]
- Full Title: 实战！我用 Wireshark 让你“看见“ TCP
- Category: #articles
- URL: https://zhuanlan.zhihu.com/p/142665708

## Highlights
- 客户端 SYN 包超时重传的最大次数，是由 tcp_syn_retries 决定的，默认值是 5 次；服务端 SYN、ACK 包时重传的最大次数，是由 tcp_synack_retries 决定的，默认值是 5 次。 ([View Highlight](https://read.readwise.io/read/01gsf512s0fyt1q05h1jegb63k))
- • 服务端在重传 SYN、ACK 包时，超过了最大重传次数 `tcp_synack_retries`，于是服务端的 TCP 连接主动断开了。
  • 客户端向服务端发送数据包时，由于服务端的 TCP 连接已经退出了，所以数据包一直在超时重传，共重传了 15 次， telnet 就断开了连接。 ([View Highlight](https://read.readwise.io/read/01gsf5q3kn1b3xnvypqe5prbfj))
- TCP 建立连接后的数据包传输，最大超时重传次数是由 `tcp_retries2` 指定，默认值是 15 次 ([View Highlight](https://read.readwise.io/read/01gsf5qf5q6cwy7hwhcr4sxae8))
- 定义一个时间段，在这个时间段内，如果没有任何连接相关的活动，TCP 保活机制会开始作用，每隔一个时间间隔，发送一个「探测报文」，该探测报文包含的数据非常少，如果连续几个探测报文都没有得到响应，则认为当前的 TCP 连接已经死亡，系统内核将错误信息通知给上层应用程序。
  在 Linux 内核可以有对应的参数可以设置保活时间、保活探测的次数、保活探测的时间间隔，以下都为默认值：
  net.ipv4.tcp_keepalive_time=7200
  net.ipv4.tcp_keepalive_intvl=75 
  net.ipv4.tcp_keepalive_probes=9
  • tcp_keepalive_time=7200：表示保活时间是 7200 秒（2小时），也就 2 小时内如果没有任何连接相关的活动，则会启动保活机制
  • tcp_keepalive_intvl=75：表示每次检测间隔 75 秒；
  • tcp_keepalive_probes=9：表示检测 9 次无响应，认为对方是不可达的，从而中断本次的连接。 ([View Highlight](https://read.readwise.io/read/01gsf5xftn486nxrwjg7k7216j))
- • 如果客户端没发送数据包，一直处于 `ESTABLISHED` 状态，然后经过 2 小时 11 分 15 秒才可以发现一个「死亡」连接，于是客户端连接就会断开连接。
  • 如果客户端发送了数据包，一直没有收到服务端对该数据包的确认报文，则会一直重传该数据包，直到重传次数超过 `tcp_retries2` 值（默认值 15 次）后，客户端就会断开 TCP 连接。 ([View Highlight](https://read.readwise.io/read/01gsf60f2mk1k2mk1hkyyb5429))
- 当发送方收到 3 个重复 ACK 时，就会触发快速重传，立刻重发丢失数据包。 ([View Highlight](https://read.readwise.io/read/01gsf66jw8r22fq0p00qf9jvtd))
- 接收窗口的大小，是在 TCP 三次握手中协商好的，后续数据传输时，接收方发送确认应答 ACK 报文时，会携带当前的接收窗口的大小，以此来告知发送方。 ([View Highlight](https://read.readwise.io/read/01gshaq43qjvt3e2rx82y7tkgj))
