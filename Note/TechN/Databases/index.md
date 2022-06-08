# 数据库能力



[Redis开源客户端](https://github.com/qishibo/AnotherRedisDesktopManager)



python 操作数据库

https://www.cnblogs.com/xiaomitu/p/15186003.html

# 

## MySQL删除表数据 MySQL清空表命令 3种方法

https://blog.csdn.net/qq_49912622/article/details/122882008





## MySQL允许root远程登录

[MYSQL设置允许所有访问](https://www.cnblogs.com/mmykdbc/p/14737779.html)



 [https://blog.csdn.net/zhazhagu/article/details/81064406](https://blog.csdn.net/zhazhagu/article/details/81064406) 

{dotted startColor="#ff6c6c" endColor="#1989fa"/}


 [https://www.markdream.com/technologies/server/mysql-allow-root-remote.shtml](https://www.markdream.com/technologies/server/mysql-allow-root-remote.shtml) 

## 授权
如果你想允许用户myuser从ip为192.168.1.64的主机连接到mysql服务器，并使用root作为密码 
GRANT ALL PRIVILEGES ON vos3000.* TO 'webdata'@'39.75.241.125' IDENTIFIED BY 'webdata' WITH GRANT OPTION; 

 FLUSH PRIVILEGES;

# MySQL查看所有用户及拥有权限


查看MYSQL数据库中所有用户
mysql> SELECT DISTINCT CONCAT('User: ''',user,'''@''',host,''';') AS query FROM mysql.user;

查看数据库中具体某个用户的权限
mysql> show grants for 'cactiuser'@'%';   

mysql> select * from mysql.user where user='cactiuser' \G   

查看user表结构　需要具体的项可结合表结构来查询
mysql> desc mysql.user;