# Windows、linux、mac等系统维护

## 通用工具

[CMD命令符如何使用](Note/other/cmd.md)

[Windows计划任务每天定时执行程序](https://zhuanlan.zhihu.com/p/430602325)

### 启动盘制作工具：

[Ventoy](https://ventoy.net/cn/index.html)：简单来说，Ventoy是一个制作可启动U盘的开源工具。有了Ventoy你就无需反复地格式化U盘，你只需要把 ISO/WIM/IMG/VHD(x)/EFI 等类型的文件直接拷贝到U盘里面就可以启动了，无需其他操作。

 [rufus轻松创建启动盘](http://rufus.ie/zh/) ： Rufus此工具也是用于SD或U盘烧写，通常用于制作***\*windows、Ubuntu、Centos\****的U盘系统安装盘，以及制作PE启动的U盘等等，具体情况看你选择刷入的ISO（此软件为github开源软件）。

[Win32DiskImager](https://win32diskimager.org/) ：此实用工具的主要功能是来写img文件到SD和U盘中，只要运行Win32DiskImager工具，填入自己的img，然后选择移动设备写入即可，通常用于烧写嵌入式linux U盘启动的bin或img（软件为绿色版已经被我打包为单文件版本）

## Windows

### 系统激活

[爱纯净Windows激活工具大集合下载](http://www.aichunjing.com/jhgj1/)

[系统激活下载网站](http://www.aichunjing.com/jhgj1/) ：批处理激活脚本 KMS_VL_ALL_AIO v46 中文版、 KMS激活工具 HEU KMS Activator v24.6.1、激活工具合集 KMS Tools Portable 20220201  等等。

### Ghost、系统安装下载

[爱纯净GHOST镜像下载站](http://www.aichunjing.com/)

[Win7之家Ghost下载站](https://www.win7zhijia.cn/xitong/chunjingban/)

 [Windows我告诉你，系统激活镜像站](https://msdn.itellyou.cn/) 



### 系统级别的软件安装

[VC++微软全家桶](http://dreamcast2.ysepan.com/)

[微软常用运行库合集 v2022.04.09 最新版](https://www.downg.com/soft/42101.html#down) 

https://otp.landian.vip/zh-cn/



### WinServer相关

[Windows Server相关](WinServe.md)



## Linux

http://isoredirect.centos.org/centos/7/isos/x86_64/

[mirror.nsc.liu.se镜像源](http://mirror.nsc.liu.se/CentOS/)
[阿里镜像源](http://mirrors.aliyun.com/centos/7.9.2009/isos/x86_64/)

[linux服务器](linux.md)

[Centos的相关操作](Centos.md)



## MacOs



## 通用应用

[运维能力：web服务器（nginx、apache、Caddy2）](Note/TechN/ywshow/webserver.md)

### 关于nginx的配置方式

nginx中，有这么个需求，一个域名二级泛解析到某一个服务器上，想设置某几个网站单独访问一个目录，然后其他的依旧走之前的泛解析，如何操作的呢，就是通过if判断$host 的访问的域名，如果是既定的，就指定规定的路线。

```Shell
# 如果泛解析中域名为指定域名，就被跳转到某一个
if ($host = 'vphp.xxx.com' ) {
        rewrite ^/(.*)$ https://www.jb51.net/$1 permanent;
    }
```

[nginx泛域名解析基础讲解](https://www.liuvv.com/p/d039.html)
[nginx中域名、目录的301重定向配置示例](https://www.jb51.net/article/52570.htm)



阿里云的云教程

https://developer.aliyun.com/adc/?spm=a2c6h.26020838.J_5404914170.24.10d12d294gNI8m

阿里云的日志采集服务，优化智联招聘，服务器的性能

https://developer.aliyun.com/adc/scenario/5e1aca8e9cd14965a6e84ca5cf2fefd0

linux压缩文件夹命令 tar_每天一个Linux系统命令｜tar

https://blog.csdn.net/weixin_39900286/article/details/110813299?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3.pc_relevant_default&utm_relevant_index=6

## Windows与黑苹果双系统？

> 引用语：待编辑

#### 第一步：系统分区
#### 第二步：制作U盘与安装系统
#### 第三步：脱离U盘启动



没有用明白的驱动软件，如果有人会用，请教教我。
![EasyBcd](index.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Y2a57yU,size_20,color_FFFFFF,t_70,g_se,x_16-16517353766902.png)



#### 参考
https://win2mac.top/eeb1bf86.html ：老吴快速安装黑苹果恢复版（收费）

https://www.mfpud.com/topics/2111/ ：黑苹果系统安装通用教程图文版

https://heipg.cn/tutorial/gpu-support-for-hackintosh.html：2022年黑苹果macOS Big Sur/Monterey显卡支持列表，持续更新中。



## Mac系统关于Homebrew的使用
### 如何安装?
[参考这篇](https://zhuanlan.zhihu.com/p/111014448)

### 如何使用？

初步介绍几个brew命令
本地软件库列表：brew ls
查找软件：brew search google（其中google替换为要查找的关键字）
查看brew版本：brew -v  更新brew版本：brew update
安装cask软件：brew install --cask firefox 把firefox换成你要安装的
    
 重启终端 或者 运行 source /Users/jacky/.zprofile   否则可能无法使用



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





