# 虚拟机克隆之后网卡不能用的解决方法

> 环境：centos6.5

## 第0️⃣种方法：待整理

虚拟机克隆之后网卡不能用的解决方法
https://blog.csdn.net/ljf10010/article/details/80331372
使用方法3，直接删掉mac地址，和一个文件，然后重启电脑，就可以
 [https://blog.csdn.net/ljf10010/article/details/80331372](https://blog.csdn.net/ljf10010/article/details/80331372) 


{dotted startColor="#ff6c6c" endColor="#1989fa"/}

linux路由配置问题
https://blog.csdn.net/qq_34595352/article/details/82218515 [https://blog.csdn.net/qq_34595352/article/details/82218515](https://blog.csdn.net/qq_34595352/article/details/82218515) 



## 第一种方法
```Shell
在克隆后的虚拟机中编辑
#vim /etc/udev/rules.d/70-persistent-net.rules
会有两行记录，分别问eth0和eth1的属性
把第一行注释掉，然后把第二行的eth1改为eth0，记住attr中的值，即分配给这台虚拟机的mac地址    
#vim /etc/syscofig/network-scripts/ifcf-eth0
修改mac地址为上文中记住的新mac地址，把onboot改为yes，保存退出后重启网络服务
#service network restart
```

## 第二种方法

```Shell
我的centos按照上文的方法修改后仍然报错，可以使用另一种方法，其实原理是一样的
#cp /etc/syscofig/network-scripts/ifcf-eth0 /etc/syscofig/network-scripts/ifcf-eth1
复制出一个新网卡eth1，并编辑
#vim /etc/syscofig/network-scripts/ifcf-eth1
把第一行名称修改为eth1，把onboot改为yes
mac地址改为上文中70-persistent-net.rules文件里eth1的mac地址，重启网络服务即可
#service network restart

```

## 第三种方法
```Shell

刚刚又看到第三种方法，网卡启动失败的原因无非是mac地址冲突，可以编辑
/etc/syscofig/network-script/ifcf-eth0 直接删除mac地址的那一行，把onboot改为yes，然后删除70-persistent-net.rules文件，这个文件会在系统重启后自动生成。
 
#vim /etc/syscofig/network-scripts/ifcf-eth0
删除HWADDR=00:0C:29:BE:B0:45这一行，保存退出，把ONBOOT=no改为ONBOOT=yes
 
#rm -rf /etc/udev/rules.d/70-persistent-net.rules
#reboot               //重启
启动后service network restart即可
```