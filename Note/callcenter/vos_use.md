### 待处理
1. 我有一个疑问，现在虚拟机都有公网IP地址了，那干嘛还要对接阿里云呢？
明天去测试一下，直接使用虚拟机的端口能不能成功。

添加IMS线路
对接阿里云


阿里云在线对接ims端虚拟机

MicroSip电话的配置
拨打电话
配置天天外呼，外呼系统。





### 1.VOS虚拟机系统使用


- 配置ims线路账户
- 将ims线路进行落地操作。
- 配置阿里云ims线路，不需要进行落地
- 配置话机用于测试。


### 2.VOS阿里云系统使用

- 阿里云在线对接ims端虚拟机
- 配置话机线路，用以对接天天外呼


### 3.天天外呼对接VOS系统
- 配置天天外呼，外呼系统。
- MicroSip电话的配置
- 或者 eyeBeam 软电话的配置



#### 1.新添加号码

导入Excel账户，应用，修改落地通话限制，修改菜单里的，转发从自动改为确定。



#### 2.新添加SIP账户

出现问题，就直接添加新企业账户。


### 4.vos数据操作
```Shell
# 虚拟机本地主机
GRANT ALL PRIVILEGES ON *.* TO 'root'@'192.168.101.%' IDENTIFIED BY '' WITH GRANT OPTION;
flush privileges;

REVOKE ALL PRIVILEGES ON *.*  'root'@'192.168.101.%';
flush privileges;


# 远程本地远程
GRANT ALL PRIVILEGES ON *.* TO 'root'@'112.240.14.183' IDENTIFIED BY '' WITH GRANT OPTION;
flush privileges;

REVOKE ALL ON *.*  'root'@'112.240.14.183';
flush privileges;

```





## 问题解决方案？

如果出现 服务器未注册的情况？


解决电话封号问题，

1. 现有外显本机号码，
   2.专业回呼系统+直呼系统
   3.接所有的行业
   4.解决封卡封号问题，
   5.线路稳定，欢迎咨询
   6.不限数量
   电话13849641417微信同步
   欢迎咨询

