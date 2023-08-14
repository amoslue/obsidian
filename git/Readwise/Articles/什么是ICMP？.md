# 什么是ICMP？

![rw-book-cover](https://download.huawei.com/mdl/image/download?uuid=1df213b726fc47b7b755c34896c90fbb)

## Metadata
- Author: [[向伏林]]
- Full Title: 什么是ICMP？
- Category: #articles
- URL: https://info.support.huawei.com/info-finder/encyclopedia/zh/ICMP.html

## Highlights
- ICMP就是一个差错报告机制 ([View Highlight](https://read.readwise.io/read/01gw3rj1hcct9n08vjjf0ardg1))
- 在数据传输的过程中，IP提供尽力而为的服务，指为了把数据包发送到目的地址尽最大努力。它并不对目的主机是否收到数据包进行验证，无法进行流量控制和差错控制。因此在数据包传输过程中，产生各种错误在所难免。为了更有效地转发IP数据包和提高数据包交付成功的机会，ICMP应运而生。使用ICMP，当网络中数据包传输出现问题时，主机或设备就会向上层协议报告差错情况和提供有关异常情况的报告，使得上层协议能够通过自己的差错控制程序来判断通信是否正确，以进行流量控制和差错控制，从而保证服务质量。 ([View Highlight](https://read.readwise.io/read/01gsf1s4dazwag7f5gznf1pg6z))
- 因为ICMP报文被封装在IP数据包内部，作为IP数据包的数据部分通过互联网传递。IP数据包中的字段包含源端和最终的目的端，并没有记录报文在网络传递中的全部路径（除非IP数据包中设置了路由记录选项）。因此当设备检测到差错时，它无法通知中间的网络设备，只能向源端发送差错报告。
  源端在收到差错报告后，它虽然不能判断差错是由中间哪个网络设备所引起的，但是却可以根据ICMP报文确定发生错误的类型，并确定如何才能更好地重发传递失败的数据包。
  ICMP报文格式如图所示，每一个ICMP消息都将包含引发这条ICMP消息的数据包的完全IP包头，ICMP报文则作为IP数据包的数据部分封装在IP数据包内部。ICMP包头中包含的三个固定字段就是源端设备确定发生错误的类型的主要依据。
  • Type字段表示ICMP消息的类型；
  • Code字段表示ICMP消息类型细分的子类型；
  • Checksum字段表示ICMP报文的校验和。 ([View Highlight](https://read.readwise.io/read/01gsf1vp5awsr3bn5khp40c0af))
