# 最牛B的Linux Shell命令

![rw-book-cover](https://plantegg.github.io/favicon.ico?v=5.1.1)

## Metadata
- Author: [[DNS 服务器]]
- Full Title: 最牛B的Linux Shell命令
- Category: #articles
- URL: https://plantegg.github.io/2017/01/01/top_linux_commands/

## Highlights
- 大家应该都知sudo，不解释。但通常出现的情况是，敲完命令执行后报错才发现忘了sudo。这时候，新手用户就会：按上箭头，按左箭头，盯着光标回到开始处，输入sudo，回车；高手用户就蛋定多了，按Ctrl-p，按Ctrl-a，输入sudo，回车。
  这里介绍这个是天外飞仙级别的，对，就直接sudo !!。 ([View Highlight](https://read.readwise.io/read/01gs7jkgp9zcewxkd3f0nknr4n))
- 两个感叹号其实是bash的一个特性，称为事件引用符（event designators）。!!其实相当于!-1，引用前一条命令，当然也可以!-2，!-50。默认情况下bash会在~/.bash_history文件内记录用户执行的最近500条命令，history命令可以显示这些命令。 ([View Highlight](https://read.readwise.io/read/01gs7jnpcrr3b1akx7ddv2zmkn))
- 命令执行后将在本机8000端口开放HTTP服务，在其他能访问本机的机器的浏览器打开ttp://ip:8000即打开一个目录列表，点击即可下载。
  python3的话
  1
  python3 -m http.server 8080 ([View Highlight](https://read.readwise.io/read/01gs7k9f2pv2t3eg93fyn5m84w))
- 3.在以普通用户打开的vim当中保存一个root用户文件
  1
  :**w** **!sudo** **tee** **%** ([View Highlight](https://read.readwise.io/read/01gs7kwk8fd0g72a58n28k6khq))
- 应该不少人都知道这个，横杆-代表上一个目录的路径。
  实际上cd -就是cd $OLDPWD的简写，bash的固定变量$OLDPWD总保存着之前一个目录的路径。 ([View Highlight](https://read.readwise.io/read/01gs7kz8tgbpv2zmatcn1hakj7))
- **!!**:s**/**foo**/**bar**/** ([View Highlight](https://read.readwise.io/read/01gs7mgfs7gg6bk4b5p5k66ahx))
    - Note: 替换命令行中的文本；!!代表上一条指令。s/同sed替换文本命令
