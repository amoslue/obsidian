+ move文件夹到上级目录
	    - mv  filename ../
+ 删除一个目录
	    - rm -rf 目录名字
    
+ 看本机ip
	    - ifconfig | grep "inet " | grep -v 127.0.0.1
    
    
+ 查找文件
		- find / -type d -name nginx/config 2>/dev/null
    
    
+ 杀死进程
	    - kill PID
	    - kill -9 PID
	    - killall pName