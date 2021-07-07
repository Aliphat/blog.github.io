### 待处理
1. 我有一个疑问，现在虚拟机都有公网IP地址了，那干嘛还要对接阿里云呢？
明天去测试一下，直接使用虚拟机的端口能不能成功。



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

