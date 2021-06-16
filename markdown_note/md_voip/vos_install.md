> 本套方案采用ims端做一台服务器，然后映射到一台公网服务器，然后我们可以直接使用公网服务器。

## 思路：
在ims本地端安装一台vos，本地电脑需要开通公网ip地址。
在阿里云服务器安装一台云端服务器
将本地与云端服务器，进行对接。

## 安装流程：
准备好VOS3000 V2.1.6.0的安装包

### 一、优先安装ims端vos：

#### 1.重点硬件：双网卡

配置路由！

配置永久路由：

```Shell
#  在/etc/rc.local里添加
route add -net 218.201.120.0 netmask 255.255.255.0 gw 172.17.145.129
```

```Shell
# 实现这个状态
172.17.145.128/27 dev eth1  proto kernel  scope link  src 172.17.145.132 
192.168.101.0/24 dev eth0  proto kernel  scope link  src 192.168.101.233 
169.254.0.0/16 dev eth0  scope link  metric 1002 
169.254.0.0/16 dev eth1  scope link  metric 1003 
default via 192.168.101.1 dev eth0 
```


> ims内网网卡：联接ims，负责线路。直连移动ims终端

```Shell
DEVICE=eth1
HWADDR=00:0C:29:0F:04:C6
TYPE=Ethernet
UUID=4129e275-24d6-4b50-811c-b7b0d2ed01b0
ONBOOT=yes
NM_CONTROLLED=yes
BOOTPROTO=static
IPADDR=172.17.145.132
NETMASK=255.255.255.224
NETWORK=172.17.145.128
GATWAY=172.17.145.129
```


> 外网网卡：配置互联网，将ims分出sip线路，共享到阿里云。

```Shell
DEVICE=eth0
HWADDR=00:0C:29:0F:04:BC
TYPE=Ethernet
UUID=b8630bca-313c-4159-9482-70e7f3e4bafe
ONBOOT=yes
NM_CONTROLLED=yes
BOOTPROTO=static
IPADDR=192.168.101.233
NETMASK=255.255.255.0
NETWORK=192.168.101.0
GATEWAY=192.168.101.1
DNS1=114.114.114.114
DNS2=1.2.4.8

```

#### 2.虚拟机安装Centos6.5的操作系统

1. 上传一件安装脚本到系统的/home路径下
2. 配置系统的yum源，附件如下：

```Shell
[extras]
gpgcheck=1
gpgkey=http://113.125.102.158:8989/centos6/RPM-GPG-KEY-CentOS-6
enabled=1
baseurl=http://113.125.102.158:8989/centos6/extras/
name=Qcloud centos extras - $basearch
[os]
gpgcheck=1
gpgkey=http://113.125.102.158:8989/centos6/RPM-GPG-KEY-CentOS-6
enabled=1
baseurl=http://113.125.102.158:8989/centos6/os/
name=Qcloud centos os - $basearch
[updates]
gpgcheck=1
gpgkey=http://113.125.102.158:8989/centos6/RPM-GPG-KEY-CentOS-6
enabled=1
baseurl=http://113.125.102.158:8989/centos6/updates/
name=Qcloud centos updates - $basearch
```

#### 3. 系统降核：

#### 4. VOS系统激活
购买正版激活码，然后对其进行激活。
### 二、安装阿里云vos：


关于探索历史：
从github上找vos的源码

待解决的问题？
1. 只能拨打一分钟？
2. 双方没有声音，okcc本地录音可以。
3. 拨打电话经常会出现403的问题，有可能是拨打太频繁导致的。




