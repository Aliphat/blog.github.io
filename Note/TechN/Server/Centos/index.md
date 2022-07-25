# Centos的操作



## 关于硬盘挂载的操作

[详情页](harddisk.md)





## centos6更换yum源脚本

```
wget -O /etc/yum.repos.d/CentOS-Base.repo http://files.tttidc.com/centos6/Centos-6.repo
wget -O /etc/yum.repos.d/epel.repo http://files.tttidc.com/centos6/epel-6.repo
yum makecache
```



## Centos6的下载以及各版本的区分

Centos 6系列全版本下载
下面是下载网址进入后选择版本号，选择系统目录文件夹isos，在选择X86_64（就是64位）或者i386（就是32位），进入后就看到了，复制到迅雷下载即可。

主站：http://vault.centos.org/
http://linuxsoft.cern.ch/
http://archive.kernel.org/centos-vault/
rsync://archive.kernel.org::centos-vault/
http://linuxsoft.cern.ch/centos-vault/
rsync://linuxsoft.cern.ch/centos-vault/
http://mirror.nsc.liu.se/centos-store/
rsync://mirror.nsc.liu.se::centos-store/


CentOS 和红帽系统的最大不同在于
    CentOS完全免费，不存在红帽系统中需要系列号的问题；
    CentOS支持在线升级，不需要像红帽系统那样购买支持服务； 

总之一句话，CentOS源自RHEL，在其基础上进行适当的优化，并提供免费服务。

CentOS 系统版本介绍
    安装CentOS系统时，无论哪个版本，官方都会提供多种映像文件，大体分为以下几类：

liveDVD版：DVD镜像，无需安装系统，插入光盘就可以体验 CentOS 的各种功能。
liveCD版： CD光盘映像，和liveDVD一样，唯一的区别就是该版本中包含的软件包会少一点，安装系统时使用 U 盘或者CD光盘进行安装。
bin：完整版，由于整个系统安装文件过大，所以一般会分为多个小文件，在下载时需全部下载。
bin-DVD版：该版本就是一个普通的安装版本，本身文件就比较大，包含了大量的常用软件。
minimal版：该版本同bin-DVD相似，不同之处在于该版本只包含有系统必须的几个基本软件包。
netinstall版：该版本也同 bin-DVD相似，不同在于netinstall的软件包全部需要通过网络下载进行安装。
CentOS 更多的是用于服务器上，也有桌面版本，安装系统时，可根据自己的需要，选择合适的映像。安装映像版本解析DVD版,假若你不清楚用哪个映像，就选择DVD版本映像，此版本可以让你选择需要安装的组件，并包含所有在图像安装界面内可选择的组件。
Everything版   everything 映像内收录了 CentOS-7 提供的所有组件，包括那些不能通过安装程序直接安装的组件。
LiveGNOME版   该版本允许你通过以DVD或USB开机的方式来测试CentOS系统。你可以将live映像上的系统安装到映像，但是此版本会安装live映像内包含的所有的组件。
LiveKDE版    KDE桌面版，此版本同GnomeLive版本类似。
Minimal版
NetInstall版        网络安装镜像。

