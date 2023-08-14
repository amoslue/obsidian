# [译] NAT 穿透是如何工作的：技术原理及企业级实践（Tailscale, 2020）

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article0.00998d930354.png)

## Metadata
- Author: [[arthurchiao.art]]
- Full Title: [译] NAT 穿透是如何工作的：技术原理及企业级实践（Tailscale, 2020）
- Category: #articles
- URL: https://arthurchiao.art/blog/how-nat-traversal-works-zh/

## Highlights
- 来看一下具体建连（穿透）过程：
  1. 如图所示，笔记本出去的第一包，`2.2.2.2:1234 -> 7.7.7.7:5678`，穿过 Windows Defender 防火墙进入到公网。
  ![](https://arthurchiao.art/assets/img/nat-traversal/nat-firewalls-5a.png)
  对方的防火墙会将这个包拦截掉，因为它没有 `7.7.7.7:5678 -> 2.2.2.2:1234` 的流量记录。 但另一方面，Windows Defender 此时已经记录了出向连接，因此会允许 `7.7.7.7:5678 -> 2.2.2.2:1234` 的应答包进来。
  2. 接着，第一个 `7.7.7.7:5678 -> 2.2.2.2:1234` 穿过它自己的防火墙到达公网。
  ![](https://arthurchiao.art/assets/img/nat-traversal/nat-firewalls-5b.png)
  到达客户端侧时，Windows Defender **认为这是刚才出向包的应答包，因此就放行它进入了！** 此外，右侧的防火墙此时也记录了：`2.2.2.2:1234 -> 7.7.7.7:5678` 的包应该放行。
  3. 笔记本收到服务器发来的包之后，发送一个包作为应答。这个包穿过 Windows Defender 防火墙 和服务端防火墙（因为这是对服务端发送的包的应答包），达到服务端。
  ![](https://arthurchiao.art/assets/img/nat-traversal/nat-firewalls-5c.png)
  成功！这样我们就建立了一个**穿透两个相向防火墙**的双向通信连接。 ([View Highlight](https://read.readwise.io/read/01h18yj86c9pmzhvdfpbxtf3qm))
- SNAT 最常见的使用场景是**将很多设备连接到公网，而只使用少数几个公网 IP**。 例如对于消费级路由器，会将所有设备的（私有） IP 地址映射为**单个**连接到公网的 IP 地址。 ([View Highlight](https://read.readwise.io/read/01h18xtvmm8c0ejsp9d1dftnba))
- 包经过路由器时，路由器发现这是一个它没有见过的新会话（session）。 它知道 `192.168.0.20` 是私有 IP，公网无法给这样的地址回包，但它有办法解决：
  1. 在它**自己的公网 IP 上挑一个可用的 UDP 端口**，例如 `2.2.2.2:4242`，
  2. 然后创建一个 *NAT mapping*：`192.168.0.20:1234` `<-->` `2.2.2.2:4242`，
  3. 然后将包发到公网，此时源地址变成了 `2.2.2.2:4242` 而不是原来的 `192.168.0.20:1234`。因此服务端看到的是转换之后地址，
  4. 接下来，每个能匹配到这条映射规则的包，都会被路由器改写 IP 和 端口。 ([View Highlight](https://read.readwise.io/read/01h18y18t049wan7s6hyy8ry88))
    - Note: NAT的过程
- 本质上这就是 **STUN 协议的工作原理**，如下图所示：
  • 笔记本向 STUN 服务器发送一个请求：“从你的角度看，我的地址什么？”
  • STUN 服务器返回一个响应：“我看到你的 UDP 包是从这个地址来的：`ip:port`”。 ([View Highlight](https://read.readwise.io/read/01h18y75ggc9z6hktpy2ztnbv4))
    - Note: STUN：告诉客户端，服务器端看它NAT后的公网ip：port
