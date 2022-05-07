# Git 安装与维护

git国内下载[跳转链接](https://registry.npmmirror.com/binary.html?path=git-for-windows/)

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
https://blog.csdn.net/Forcezs/article/details/84136902

## Centos以及Win配置git的方式，以及自动化部署 webhook

https://blog.csdn.net/weixin_43957211/article/details/117309935

git使用
https://blog.csdn.net/xwj1992930/article/details/96428998?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-1.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-1.pc_relevant_default&utm_relevant_index=2


使用宝塔面板配置webhook
https://blog.csdn.net/qq_40995752/article/details/89467931

使用coding + webhook实现自动部署
https://www.cnblogs.com/aigeileshei/p/13324212.html


## 3.Github代理加速器
https://ghproxy.com/

# Git分布式版本控制工具使用教程

## 01、Git分布式版本控制工具(5)

### 01、企业开发的现状



### 02、Git概述

### 03、Git与SVN对比

### 04、Git工作流程

### 05、Git下载与安装

## 02、Git代码托管服务(2)

## 03、Git常用命令(13)

## 04、.gitignore文件忽略

## 05、Git远程仓库操作(5)

## 06、Git分支-Branch(7)

## 07、Git标签(5)

## 08、TortoiseGit管理文件版本(1)

## 09、在IDEA中使用Git(3)

## 10、使用SSH协议传输数据

## 11、远程协作开放-pull request

## 12、GitLab的搭建