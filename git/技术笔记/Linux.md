+ 查看端口任务： lsof -i :<port>

+ 返回包含匹配模式的文件名，而不输出匹配的具体行：grep -l 匹配模式

+ move文件夹到上级目录
	    - mv  filename ../
+ 删除一个目录
	    - rm -rf 目录名字
    
+ 看本机ip
	    - ifconfig | grep "inet " | grep -v 127.0.0.1
    
+ 本机开server
		- curl phus.lu/fileserver.py | python
		- python -m http.server

+ 查找文件
		- find / -type d -name nginx/config 2>/dev/null
    
+ 看端口任务
		- lsof 
	
+ 杀死进程
	    - kill PID
	    - kill -9 PID
	    - killall pName


ps&stat?
![[Pasted image 20240229161231.png]]

chmod?
l: link
d: directory
-: regular file
![[Pasted image 20240229161338.png]]


TTL is actually used as a hop count limit. 
traceroute used TTL