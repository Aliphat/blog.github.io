

# 内网穿透、映射种种方案

## 钉钉免费内网穿透：实现内网主机上线

## 第一步： clone  git仓库
执行命令：git clone https://github.com/open-dingtalk/pierced.git
## 第二步：开始配置
> 注意：在pierced根目录下执行命令

### Mac:
 (1) cd mac_64
 (2)./ding -config=./ding.cfg -subdomain=abcde 8080

### Windows: 
 (1) cd windows_64
 (2)ding -config=ding.cfg -subdomain=abcde 8080

## 第三步：测试
启动完客户端后，你访问http://abcde.vaiwan.com/xxxxx都会映射到 http://127.0.0.1:8080/xxxxx

## 注意：
1.你需要访问的域名是http://abcde.vaiwan.com/xxxxx 而不是http://abcde.vaiwan.com:8082/xxxxx
2.你启动命令的subdomain参数有可能被别人占用，尽量不要用常用字符，可以用自己公司名的拼音，例如：alibaba、dingding等。
3.可以在本地起个http-server服务，放置一个index.html文件，然后访问http://abcde.vaiwan.com/index.html测试一下。
————————————————
版权声明：本文为CSDN博主「System.o」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/lyh1299259684/article/details/81941268



## 内网映射  zerotier 

通过这个组建大内网环境
[https://my.zerotier.com/](https://my.zerotier.com/) 
突破各种终端限制，直接连接到安装此设备的网卡中。


Centos6/7安装
```Shell
# 1、在线安装zerotier
curl -s https://install.zerotier.com/ | sudo bash

# 2、添加开机自启
chkconfig zerotier-one on
sudo systemctl enable zerotier-one.service

# 3、启动zerotier-one.service
service zerotier-one start
sudo systemctl start zerotier-one.service

# 4、加入网络
sudo zerotier-cli join 8850338390e1c481
```

关于Centos6开机启动的相关命令
```Shell


[root@localhost ~]$ ls /etc/init.d/httpd     # /etc/init.d/目录下必须有启动脚本
[root@localhost ~]$ chkconfig --add httpd    # 添加服务，以便让chkconfig指令管理它
[root@localhost ~]$ chkconfig httpd on       # 设置开机运行该服务，默认是设置2345等级开机运行服务




[root@localhost ~]$ chkconfig --list                 # 列出所有被chkconfig管理的服务
[root@localhost ~]$ chkconfig --add httpd            # 添加指定的服务，让chkconfig指令管理它
[root@localhost ~]$ chkconfig --del httpd            # 删除指定的服务，不再让chkconfig指令管理它
[root@localhost ~]$ chkconfig httpd on               # 设置开机运行服务，需要先执行 --add 才能执行该命令
[root@localhost ~]$ chkconfig httpd off              # 设置开机不运行服务，需要先执行 --add 才能执行该命令
[root@localhost ~]$ chkconfig --level 35 httpd on    # 设置服务在等级3和5时开机运行服务，默认是设置2345等级开机运行服务



[root@localhost ~]$ chkconfig --list                                      # 等级0：关机
atop            0:off   1:off   2:off   3:off   4:off   5:off   6:off     # 等级1：单用户模式/救援模式
auditd          0:off   1:off   2:off   3:off   4:on    5:off   6:off     # 等级2：无网络连接的多用户命令行模式
crond           0:off   1:off   2:on    3:on    4:on    5:on    6:off     # 等级3：有网络连接的多用户命令行模式
ipset           0:off   1:off   2:on    3:on    4:on    5:on    6:off     # 等级4：不可用
iptables        0:off   1:off   2:off   3:off   4:on    5:off   6:off     # 等级5：带图形界面的多用户模式
mysql           0:off   1:off   2:on    3:on    4:on    5:on    6:off     # 等级6：重启
```