# Linux Grep 命令

![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article1.be68295a7e40.png)

## Metadata
- Author: [[runoob.com]]
- Full Title: Linux Grep 命令
- Category: #articles
- URL: https://www.runoob.com/linux/linux-comm-grep.html

## Highlights
- 以递归的方式查找符合条件的文件。例如，查找指定目录/etc/acpi 及其子目录（如果存在子目录的话）下所有文件中包含字符串"update"的文件，并打印出该字符串所在行的内容，使用的命令为：
  grep -r update /etc/acpi ([View Highlight](https://read.readwise.io/read/01grtt9jz7vg8t34hm8em46bxe))
- 反向查找。前面各个例子是查找并打印出符合条件的行，通过"-v"参数可以打印出不符合条件行的内容。
  查找文件名中包含 test 的文件中不包含test 的行，此时，使用的命令为：
  grep -v test *test* ([View Highlight](https://read.readwise.io/read/01grtta98f8d2d54zefhwg1dfz))
- 从根目录开始查找所有扩展名为 .log 的文本文件，并找出包含 "ERROR" 的行：
  $ find / -type f -name "*.log" | xargs grep "ERROR" ([View Highlight](https://read.readwise.io/read/01grtz6x5ng5h059aacvhx1gyp))
