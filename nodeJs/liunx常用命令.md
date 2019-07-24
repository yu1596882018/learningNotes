+ df -hl
+ ps -ef | grep node
+ ps -ef | grep ngi
+ vim ads.aataotao.com.conf
+ pwd
+ top
+ tail -f
+ nginx -t
+ cat 
+ ping 
+ curl 
+ sudo
+ iotop
+ iftop
+ history
+ vmstat

+ 查看物理CPU个数
    + cat /proc/cpuinfo| grep "physical id" | sort| uniq | wc -l

+ 查看每个物理CPU中core的个数(即核数)
    + cat /proc/cpuinfo| grep "cpu cores"| uniq

+ 查看逻辑CPU的个数
    + cat /proc/cpuinfo| grep "processor"| wc -l

+ 判断nginx配置文件是否正确：
    + nginx -t -c /etc/nginx/nginx.conf

+ 更改配置重启nginx：
    + kill -HUP 主进程号或进程号文件路径
    + nginx -s reload
