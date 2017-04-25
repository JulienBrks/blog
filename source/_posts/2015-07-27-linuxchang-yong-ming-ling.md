* lsb_release -a 查看本机linux的发布版本信息
* df 查看本机磁盘使用情况
* tar zxvf 解压.tar.gz压缩包
* 查看端口连接数 netstat -pnt |grep :80 |wc -l
* 查看端口占用 netstat -anp(linux)
* 查看端口占用 lsof -i :80(mac)
* 关闭防火墙(重启后失效) service iptables stop 
* 查看当前机器的cpu位数 getconf LONG_BIT
* 查看某一个进程号(第二个字段就是进程号) netstat -nap | grep pid
* 防火墙配置关闭,开启(下次启动会生效，当前不会生效，要生效要关闭服务) chkconfig iptables off(on) 
* 防火墙服务关闭,开启 service iptables start(stop)
* 递归删除文件夹下面某一种类型的文件 首先检查要删除的文件: `find . -name "*.bak" -type f`. 可以的话就执行删除 `find . -name "*.bak" -type f -delete`
* 打开mysql mysql.service start
* du -h -d 1 查看当前目录下的一级目录的大小