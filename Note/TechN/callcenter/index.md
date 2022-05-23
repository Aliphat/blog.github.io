# 呼叫中心系统

关于呼叫中心的基本常识

FreeSwitch软电话服务

磐石云以及二开接口。vue大屏

[VOS官方指导文档](https://www.linknat.com/#/support/download)

[FreeSWITCH中文网,电话机器人开发网](http://www.freeswitch.net.cn/index.html)

[如何从零搭建外呼系统](http://www.woshipm.com/pmd/1210429.html)

[WebRTC + JsSIP + freeSWITCH一对一语音聊天](https://www.cnblogs.com/gxp69/articles/12028002.html)

[jssip中文开发文档（完整版） ](https://www.cnblogs.com/benmumu/p/8316670.html)

[三汇语音网关产品介绍说明图](https://www.dsliu.com/products/synway/)

> * [呼叫中心的知识库](knowledge.md)
> * [呼叫中心设备](ipgateway.md)
> * [安装VOS](vos_install.md)
> * [使用VOS](vos_use.md)
> * [磐石云的操作](PSCC.md)

[VOS6最新很详细的安装](vos6install.md)

[Vos安全防护相关的内容](vosSafe.md)

## 电话座机上云方案
### 方案一:运营商为模拟线路
线路要求:运营商根据客户需求通过小交连选等方式实现多条模拟线对应同一个联通接入号，实现多人同时拨打该号码能依次给多条电话线振铃。
设备要求:用户侧提供O口模拟网关与联通模拟线对接，且模拟网关接入任何能访问云主机的互联网网线。

### 方案二:联通提供公网上的SIP线路，比如联通BPO业务
线路要求:
1 联通将用户指定固话号做到联通BPO平台
2 联通BPO平台提供公网注册地址，用户名及密码。
设备要求: 无需其他设备，云主机直接向联通sip注册。

### 方案三:联通提供内网上的SIP线路，类似于移动IMS业务。
设备要求:
1 用户侧提供一台双网卡物理服务器或台式机，操作系统为windows7及以上或centos6.5及以上。
2 物理服务器或台式机一个网卡接能放问云主机的互联网网线。
3 物理服务器或云主机另一个网卡接联通内网(语音专线)网线。
线路要求:
1 联通提供可供号码注册的内网(或语音专线)，提供终端设备(服务器或台式机)使用的ip地址
2 联通提供内网注册地址，用户名及密码。




## 售后服务呼叫中心系统

急用，工单系统 

### 1.[联傲云工单系统](http://www.chainall.com/)  大几十万

大而全，可定制化，微信派单，功能成熟。就是贵。

### 2.12345青岛工单系统

来自psc老哥，目前正在咨询中
据说，预算至少5w

### 3. 钉钉宜搭

搭建很方便，但是呢，不能私有化部署，同时也是免费的。


### 4.JeecgBoot

大体上粗略一看，还没有研究明白

