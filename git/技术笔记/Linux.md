+ 查看端口任务： lsof -i :<port>

+ 返回包含匹配模式的文件名，而不输出匹配的具体行：grep -l 匹配模式

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