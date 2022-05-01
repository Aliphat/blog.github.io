# 网络及云计算相关

## 笔记

[Nginx的配置和使用](Network/Nginx.md)


OK，先入手这些玩意儿的压缩包

Nginx：http://nginx.org/en/download.html
PHP4Windows：http://windows.php.net/download/【请下载 NTS（Non Thread Safe 非线程安全）版】

下面这货是用来创建 Windows 自启服务的：
WinSW：https://github.com/kohsuke/winsw/releases【下载 .exe 文件即可，根据系统选择，Win 10 选择 .NET4 版本，以下选择 .NET2 版本】

xxfpm 用来开启 PHP-CGI 多进程
xxfpm：https://github.com/78/xxfpm
（也可以使用我编译的版本，支持带空格的路径：https://github.com/maxsky/xxfpm）

规规矩矩的办事是基本
先在 D 盘或任意位置建立一个文件夹（一定不能有空格），例如 D:\WebDevEnvironment

依次创建 nginx、php56、xxfpm（PHP 视版本命名，例如 PHP 7.1 则为 php71。）

将已下载的 Nginx 和 PHP 都扔到对应文件夹内，nginx 内包含 nginx.exe 和 conf 文件夹；php56 内包含 php-cgi.exe 和 ext 文件夹

将 WinSW.NET4.exe 分别扔进 nginx 文件夹和 php71。xxfpm 压缩包内 bin 文件夹里除了 xxfpm，将 xxfpm.exe 和 pthreadGC2.dll 扔进 xxfpm 文件夹

nginx 内的 WinSW.NET4.exe 重命名为 nginx-server.exe，然后新建一个同名的 XML 文件 nginx-server.xml

编辑 nginx-server.xml 文件，内容如下：
————————————————
版权声明：本文为CSDN博主「至天」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/maxsky/article/details/78820967)



## 教程



用FTP获取联通光猫PT952G的管理员密码

https://blog.csdn.net/weixin_45378201/article/details/106461825



联通HG8321R光猫开路由破解详细步骤

https://jingyan.baidu.com/article/a681b0de09fe0d3b19434644.html



**华为HG8321R超级密码怎么获得，版本号：V3R016C10S135**

http://www.chinadsl.net/thread-131171-1-1.html



斐讯K1/K2/K3最新华硕固件老毛子固件3.4.3.9-099  2022.03.30更新

https://www.winos.vip/439.html

# 物联网

mqtt物联网平台

http://www.ranye-iot.net/



# 运维工程师

阿里云的云教程

https://developer.aliyun.com/adc/?spm=a2c6h.26020838.J_5404914170.24.10d12d294gNI8m



阿里云的日志采集服务，优化智联招聘，服务器的性能

https://developer.aliyun.com/adc/scenario/5e1aca8e9cd14965a6e84ca5cf2fefd0

# linux压缩文件夹命令 tar_每天一个Linux系统命令｜tar

https://blog.csdn.net/weixin_39900286/article/details/110813299?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3.pc_relevant_default&utm_relevant_index=6







# Docker及K8s

https://www.docker.com/play-with-docker/

这可能是最为详细的Docker入门总结  http://www.dockone.io/article/8350

[Docker新手入门学习笔记(含视频演示)](https://baiyue.one/archives/368.html)







# 【5分钟玩转Lighthouse】Theia IDE 腾讯云在线编译环境

https://zhuanlan.zhihu.com/p/265646097



- 日志服务：日志服务SLS是云原生观测与分析平台，为Log、Metric、Trace等数据提供大规模、低成本、实时的平台化服务。日志服务一站式提供数据采集、加工、查询与分析、可视化、告警、消费与投递等功能，全面提升您在研发、运维、运营、安全等场景的数字化能力。
- 云服务器ECS：云服务器（Elastic Compute Service，简称ECS）是阿里云提供的性能卓越、稳定可靠、弹性扩展的IaaS（Infrastructure as a Service）级别云计算服务。云服务器ECS免去了您采购IT硬件的前期准备，让您像使用水、电、天然气等公共资源一样便捷、高效地使用服务器，实现计算资源的即开即用和弹性伸缩。阿里云ECS持续提供创新型服务器，解决多种业务需求，助力您的业务发展



## Git

Git删除本地任意提交记录的方法

https://blog.csdn.net/weixin_46267445/article/details/122328025



## [Git命令——提交、查看、后退、前进](https://www.cnblogs.com/jiqianqian/p/7027572.html)

https://www.cnblogs.com/jiqianqian/p/7027572.html