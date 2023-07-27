# Linux

- **move文件夹到上级目录**
    - mv 要移动的文件名 ../
- **删除一个目录**
    - rm -rf 目录名字
    
    查找文件名，清理no permission
    
    ![Untitled](Linux/Untitled.png)
    
    看本机ip：
    
    ifconfig | grep "inet " | grep -v 127.0.0.1
    
    ifconfig查出来的是你本机的IP地址，也就是内网私有地址，此类地址仅在局域网使用，不能联通外网。
    
    find / -type d -name nginx/config 2>/dev/null
    
    ![Untitled](Linux/Untitled%201.png)
    
    ![Untitled](Linux/Untitled%202.png)
    
    ![Untitled](Linux/Untitled%203.png)
    
    协助调试
    
    **管道pipe：**
    
    ![Untitled](Linux/Untitled%204.png)
    
    杀死进程：
    
    kill PID
    
    kill -9 PID
    
    killall pName