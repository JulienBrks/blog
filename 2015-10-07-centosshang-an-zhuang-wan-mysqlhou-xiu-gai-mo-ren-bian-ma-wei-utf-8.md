1. 查看当前编码`mysql> SHOW VARIABLES LIKE 'character%';`

2. `vim /etc/my.cnf`在尾部加上下面代码：

		```
		[client]
		default-character-set=utf8
		[mysql]
		default-character-set=utf8
		[mysqld]
		default-character-set=utf8
		```
3. 然后重启(或者启动)mysqld `service mysqld start`

4. 检查`mysql> SHOW VARIABLES LIKE 'character%';`是否都已经设置成utf-8，下图为正确的结果:
![](/content/images/2015/10/EE38975A-BDDF-450C-868A-8FEF968A7969.png)