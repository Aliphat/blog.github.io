

# 内网穿透、映射种种方案

## Zerotier穿透方案

https://www.zerotier.com/



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

# 免费的案例
## 1. Dingding工具

> 来历实锤，确定是钉钉放出的。
> [Ding跳转链接](https://open.dingtalk.com/document/resourcedownload/http-intranet-penetration)

以下页面内容来自
https://www.zhihu.com/question/49629610

自建服务推荐：frp、nps

商业软件推荐：花生壳、蜻蜓映射、神桌互联
网云穿和闪库也不错，最起码稳定，不像有的三天两头断线
小蚂蚁，网云穿都可以，不喜欢的话还有花生壳等等。
stun 为什么没人提这个？
如果不考虑使用域名只是为了内网穿透，实现外网可以访问的话，路由器的虚拟服务器功能了解一下？配置好服务器ip以及内外网端口就好了。外网访问直接路由器wan口ip：外网端口号就行了。



内网穿透，即内网映射，内网端口映射外网，是将本地内网IP映射成自己顶级域名或软件工具自动生成的多级域名，然后通过域名进行访问连接。无公网IP搭建服务器，并提供互联网访问时，一般即采用内网穿透方案。自己有公网IP服务器，也可以自行搭建内网穿透服务来实现对内网跨网的访问。有公网IP服务器，自行搭建内网穿透，一般可以考虑开源的如：ngrok、frp。无公网IP，一般是用现有提供的一些内网穿透服务，类似如：nat123全端口P2P穿透。等。不同的内网穿透软件工具，实现的目的都是一样的，都是实现外网的访问连接。在不同的应用场景上，在实现配置使用过程会有所不同。各人的网络环境和使用习惯上的也有所差异，对于如何定义简单和实用否，还是建议需要自行测试对比，及使用一段时间后更有参考价值。



最近研究了一下，所谓的内网穿透的技术，太难了，搞的头疼了，天天在查资料，网上有很多开源的项目如：frp、ngrok、ns 利用工具实现的，最终测试都不合格，非常不稳定，自己做玩玩还是可以的，不建议给公司使用。也测试了一些商业的软件例如：花生壳、神卓互联，果然付费就是不一样，测试结果都比较好，很稳定。内网穿透领域有很多种办法，可以做到穿透的目的，但是要做到稳定，商业性质的很难的，经过深度的了解：一般商业性的公司基本都是有自己的开发团队，开发出自己核心穿透引擎，例如：花生壳的PHTunnel   神卓互联的Wangooe Tunnel 核心引擎  只有这些核心技术支撑才能保证数据传输的稳定性，   所谓开源的项目，就是给大家学习用的，增长知识。内网穿透，行业内目前做的比较好的有：神卓互联.                                                                神卓互联


链接：https://www.zhihu.com/question/49629610/answer/940088379
链接：https://www.zhihu.com/question/49629610/answer/382512362

Notr内网穿透服务，有几个特性：1、独立研发，所以对内部对项目对掌控很好，有新对需求也可以快速响应。我观察到目前市面上很多内网穿透都是基于FRP和Ngrok进行修改的，出问题的时候很大程度依赖于frp/ngrok的作者进行bug修复。值得注意的是ngrok项目作者已经不维护了，开源的版本一直都有问题，所以基于开源ngrok的内网穿透工具我觉得需要考虑一下的。2、支持http，https，tcp等协议，不用购买域名，备案，购买证书等操作，并且我们HTTP和HTTPS默认直接使用80和443端口，这在微信公众号开发调试等场景是需要的。3、真正的零配置，只需要让用户只要懂自己内部需要穿透的端口，就能够使用4、内部有调度策略，我们一方面会根据服务器的状态来进行调度，另一方面，基于地理位置进行调度，我们碰到过一个海外用户，接入大陆的节点，影响线路质量，于是我们开发了基于地理位置调度的策略。5、支持LICENSE购买，如果您希望使用notr的软件来出售，您不需要非常了解技术，只需要具备一定的销售推广能力，我们有LICENSE购买，购买LICENSE成功之后，就可以将notr部署到您的服务器，您可以对用户等进行操作，我们也衷心的希望Notr能给您带来用户。Notr用户在持续上升，如果您对内网穿透，企业内网访问，企业分支组网等话题感兴趣，可以随时私信我交流。



[Go撸了一个内网穿透工具，可以发布内网http网站及内网所有的TCP端口](https://zhuanlan.zhihu.com/p/60504731)


端口映射（内网穿透）软件工具有不少。
开源的有如：frp、ngrok、nps、等比较适合自己公网服务器搭建独自型使用。
三方的有如：花生壳、nat123、神卓、金万维、等等。
哪些简单实用还要结合看自己场景需求和实际使用效果，不能一概而论之。

一直使用的PP透做内网穿透，很多年了，便宜好用，还不限流量，传输速度很快的。
支持http/https，ws/wss，tcp隧道，每个隧道首月免费，可同时开两，拿走不谢。


[深隧系统-内网穿透](http://mz82.baoyugame.com/deephole/default.php)

https://freefrp.net/

### 使用信息

### 技术方案:



https://www.htm.fun/archives/nas-nps.html


前言
本站有一篇关于nas内网穿透的帖子：

保姆级教程：群晖nas内网穿透之ipv6/ipv4 ddns+frp双管齐下！

前提条件以下所有内容均在博主家庭实际搭建，所有截图均为博主家庭实际操作，请举一反三！本教程面向幼儿园，内容略显简单...

这篇帖子详细的介绍了nas该如何用frp和ipv6进行内网穿透。最近，博主又发现了一个简单快捷的内网穿透方式：nps。
nps内网穿透的前提条件是：拥有一台公网服务器！
NPS安装
NPS官方文档：https://ehang-io.github.io/nps/#/
请准备一台服务器，并配置安全组，开放所有端口！
基础配置
由于NPS是基于GO语言开发的，所以，先安装GO语言！

# Debian/Ubuntu系统
使用nps：https://ehang-io.github.io/nps/#/use