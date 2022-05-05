# Git

## Git删除本地任意提交记录的方法

https://blog.csdn.net/weixin_46267445/article/details/122328025



[Git命令——提交、查看、后退、前进](https://www.cnblogs.com/jiqianqian/p/7027572.html)

https://www.cnblogs.com/jiqianqian/p/7027572.html



## git 记住密码

### 通过ssh-keygen
```Shell
$ ssh-keygen -t rsa -C "xxx@163.com"
```

### 通过记住密码

输入命令 git config --global credential.helper store

之后再操作git输入一次用户名、密码，后续不需要再次输入了

push你的代码 (git push), 这时会让你输入用户名和密码, 这一步输入的用户名密码会被记住,
下次再push代码时就不用输入用户名密码 ! 这一步会在用户目录下生成文件.git-credential记录用户名密码的信息。
————————————————
版权声明：本文为CSDN博主「「已注销」」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/Forcezs/article/details/84136902





## Centos以及Win配置git的方式，以及自动化部署 webhook

https://blog.csdn.net/weixin_43957211/article/details/117309935

git使用
https://blog.csdn.net/xwj1992930/article/details/96428998?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-1.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-1.pc_relevant_default&utm_relevant_index=2


使用宝塔面板配置webhook
https://blog.csdn.net/qq_40995752/article/details/89467931

使用coding + webhook实现自动部署
https://www.cnblogs.com/aigeileshei/p/13324212.html





> 本文章适用于，下载各种国外的系统慢的人，使用各种软件国外源，加载慢的人。

# 一：国外软件下载
## 各个版本的Linux系统
### Centos
[mirror.nsc.liu.se镜像源](http://mirror.nsc.liu.se/CentOS/)
[阿里镜像源](http://mirrors.aliyun.com/centos/7.9.2009/isos/x86_64/)

## 其他
### git国内下载[跳转链接](https://registry.npmmirror.com/binary.html?path=git-for-windows/)
# 二：国内源提速（Windows版本）
## 1.NPM包管理器提速
### 通过命令配置
#### 1.直接配置

```bash
npm config set registry https://registry.npm.taobao.org
```

#### 2.验证是否配置成功
```bash
npm config get registry
```

### 通过使用cnpm安装
#### 1.安装cnpm

```bash
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

#### 2.使用cnpm
```bash
cnpm install xxx
```
## 2.Python国内源
[目前参考这篇文章](https://www.cnblogs.com/sunnydou/p/5801760.html)

## 3.Github代理加速器
https://ghproxy.com/