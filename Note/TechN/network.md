# 网络、云计算、物联网、系统维护相关

## 笔记

[Nginx的配置和使用](Network/Nginx.md)

[CMD命令在网络下的应用](Network/CMDtoNetwork.md)





## 教程

[各种型号的光猫获取后台账户信息](Network/Guangmao.md)

[内网穿透、映射、方案](Network/CitouNetwork.md)

[网络抓包](Network/Zhuabao.md)

[校园网伪造MAC上网](Network/RouteMac.md)

[路由器：Pandavan固件](Network/Pandavan.md)

[校园网伪造MAC上网](Network/RouteMac.md)

[校园网伪造MAC上网](Network/RouteMac.md)



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





## 运维工程师

阿里云的云教程

https://developer.aliyun.com/adc/?spm=a2c6h.26020838.J_5404914170.24.10d12d294gNI8m



阿里云的日志采集服务，优化智联招聘，服务器的性能

https://developer.aliyun.com/adc/scenario/5e1aca8e9cd14965a6e84ca5cf2fefd0

linux压缩文件夹命令 tar_每天一个Linux系统命令｜tar

https://blog.csdn.net/weixin_39900286/article/details/110813299?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3.pc_relevant_default&utm_relevant_index=6







# Docker及K8s

https://www.docker.com/play-with-docker/

这可能是最为详细的Docker入门总结  http://www.dockone.io/article/8350

[Docker新手入门学习笔记(含视频演示)](https://baiyue.one/archives/368.html)







# 【5分钟玩转Lighthouse】Theia IDE 腾讯云在线编译环境

https://zhuanlan.zhihu.com/p/265646097



- 日志服务：日志服务SLS是云原生观测与分析平台，为Log、Metric、Trace等数据提供大规模、低成本、实时的平台化服务。日志服务一站式提供数据采集、加工、查询与分析、可视化、告警、消费与投递等功能，全面提升您在研发、运维、运营、安全等场景的数字化能力。
- 云服务器ECS：云服务器（Elastic Compute Service，简称ECS）是阿里云提供的性能卓越、稳定可靠、弹性扩展的IaaS（Infrastructure as a Service）级别云计算服务。云服务器ECS免去了您采购IT硬件的前期准备，让您像使用水、电、天然气等公共资源一样便捷、高效地使用服务器，实现计算资源的即开即用和弹性伸缩。阿里云ECS持续提供创新型服务器，解决多种业务需求，助力您的业务发展



