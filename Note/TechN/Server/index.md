# Server服务器

## 关于nginx的配置方式

nginx中，有这么个需求，一个域名二级泛解析到某一个服务器上，想设置某几个网站单独访问一个目录，然后其他的依旧走之前的泛解析，如何操作的呢，就是通过if判断$host 的访问的域名，如果是既定的，就指定规定的路线。

```Shell
# 如果泛解析中域名为指定域名，就被跳转到某一个
if ($host = 'vphp.xxx.com' ) {
        rewrite ^/(.*)$ https://www.jb51.net/$1 permanent;
    }
```


### 参考文献
[nginx泛域名解析基础讲解](https://www.liuvv.com/p/d039.html)
[nginx中域名、目录的301重定向配置示例](https://www.jb51.net/article/52570.htm)





阿里云的云教程

https://developer.aliyun.com/adc/?spm=a2c6h.26020838.J_5404914170.24.10d12d294gNI8m



阿里云的日志采集服务，优化智联招聘，服务器的性能

https://developer.aliyun.com/adc/scenario/5e1aca8e9cd14965a6e84ca5cf2fefd0

linux压缩文件夹命令 tar_每天一个Linux系统命令｜tar

https://blog.csdn.net/weixin_39900286/article/details/110813299?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-3.pc_relevant_default&utm_relevant_index=6









## Linux

[linux服务器](linux.md)

## WindowsServer

[Windows Server相关](WinServe.md)











## Windows与黑苹果双系统？

> 引用语：待编辑

#### 第一步：系统分区
#### 第二步：制作U盘与安装系统
#### 第三步：脱离U盘启动



没有用明白的驱动软件，如果有人会用，请教教我。
![EasyBcd](index.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Y2a57yU,size_20,color_FFFFFF,t_70,g_se,x_16-16517353766902.png)



#### 参考
https://win2mac.top/eeb1bf86.html







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