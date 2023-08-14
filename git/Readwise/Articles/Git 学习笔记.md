# Git 学习笔记

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article1.be68295a7e40.png)

## Metadata
- Author: [[知乎专栏]]
- Full Title: Git 学习笔记
- Category: #articles
- URL: https://zhuanlan.zhihu.com/p/453613712

## Highlights
- • 已修改（Modified）：该状态表示文件已经被修改，但尚未被记录为下一次要提交的版本。
  • 已暂存（Staged）：该状态表示文件已被记录为下一次要提交的版本，但尚未提交到本地仓库中，
  • 已提交（Committed）：该状态表示文件已经被记录为一个版本，并提交到了本地仓库中。
  这三种文件记录状态会致使每个由 Git 维护的项目在文件结构上被分成了以下三个组成部分：
  • 工作区域：该部分主要用于存放项目中处于已修改状态的文件。
  • 暂存区域：这部分主要用于存放项目中处于已暂存状态的文件。
  • 本地仓库：该部分主要用于存放项目中处于已提交状态的文件。 ([View Highlight](https://read.readwise.io/read/01grby42ervbywsx0qzrnzzsqb))
- 如果想撤销在执行了`git add`命令之后对`README.md`文件的修改，可以在`demo_repo`项目的根目录下执行`git restore README.md`命令。 ([View Highlight](https://read.readwise.io/read/01grbya6nmw2r83ctqc4t02e59))
    - Note: 撤销未暂存
- 如果想将这次修改也更新到暂存区域，可以在`demo_repo`项目的根目录下再次执行`git add README.md`命令。 ([View Highlight](https://read.readwise.io/read/01grbyb435cd6e9pdn7xpewws2))
- 如果想撤销上一次执行`git add`命令将文件添加到暂存区域的操作，可以在`demo_repo`项目的根目录下执行`git rm –cached README.md`命令。 ([View Highlight](https://read.readwise.io/read/01grbybxd35v73bwfh1e3xynw9))
    - Note: 取消暂存
- 直接使用`git commit`命令的`-a`参数跳过重新添加文件的步骤，将其合并到提交动作中去 ([View Highlight](https://read.readwise.io/read/01grbz33g41yk8b9jxxvbt3jna))
- 如果我们想将`demo_repo`项目恢复到标注信息为“third commit.”的版本，就只需要在该项目的根目录下执行`git reset cb003`命令 ([View Highlight](https://read.readwise.io/read/01grbz683b5p50zjeyf28y9086))
- `git tag <版本标识>`这个命令为这个版本打上一个标识，以便在日后的项目维护中快速定位到它 ([View Highlight](https://read.readwise.io/read/01grc09d2ak97jekr69ay5f8tb))
- 使用`git show <标签>`命令查看指定标签所在版本的具体信息 ([View Highlight](https://read.readwise.io/read/01grc08r0a3qh60fpwmjv35h12))
- it push <远程仓库标识> <本地分支>:<远程分支> ([View Highlight](https://read.readwise.io/read/01grc0m9y903wy8xdqysntse96))
