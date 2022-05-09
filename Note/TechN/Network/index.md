# 网络、云计算、物联网、系统维护相关

## 笔记

[Nginx的配置和使用](Nginx.md)

[CMD命令在网络下的应用](CMDtoNetwork.md)



## 结果

如何用闲置的带宽赚钱？https://www.1nth.com/post/pcdn/

自己建设CDN的方案：https://shimo.im/docs/6CRrv8dcph6rYHJD/read

## 教程

[各种型号的光猫获取后台账户信息](Guangmao.md)

[内网穿透、映射、方案](CitouNetwork.md)

[网络抓包](Zhuabao.md)

[校园网伪造MAC上网](RouteMac.md)

[路由器：Pandavan固件](Pandavan.md)

[TPlink路由器的研究](TP-Link.md)



斐讯K1/K2/K3最新华硕固件老毛子固件3.4.3.9-099  2022.03.30更新

https://www.winos.vip/439.html

## 物联网

mqtt物联网平台

http://www.ranye-iot.net/



## 系统维护

#### 双系统：黑苹果window时间不同步

文章概述:
> 双系统中windows经常出现时间不准确：通过每次开机自动从网络获取时间地址 来解决这个问题。


cmd执行
```Cmd
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```



#### 如何在mac上安装md5校验文件

1、更新brew

```Shell
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

2、安装md5
```Shell
brew install md5sha1sum
```

3、命令行md5校验
```Shell
md5sum 文件名
```





