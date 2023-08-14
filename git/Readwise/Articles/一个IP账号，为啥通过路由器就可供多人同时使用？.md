# 一个IP账号，为啥通过路由器就可供多人同时使用？

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article1.be68295a7e40.png)

## Metadata
- Author: [[51cto.com]]
- Full Title: 一个IP账号，为啥通过路由器就可供多人同时使用？
- Category: #articles
- URL: https://blog.51cto.com/u_15281548/4754171

## Highlights
- 当一个电脑（192.168.1.2）上网时，先通过DNS协议解析出某个域名对应的IP，然后
  • 发送数据时,在经过路由器时转换为公网IP以及路由器自己分配的临时端口：192.168.1.2:6789 -->192.168.1.1 路由器116.226.52.212:6539 -->猫-->万维网
  • 接收数据时，在经过路由器时转换为路由器之前记录的IP以及port：万维网-->猫 -->116.226.52.212:6539 路由器 192.168.1.1 -->192.168.1.2:6789 ([View Highlight](https://read.readwise.io/read/01gshm7yvxa5dk9g71dfxdm3q0))
