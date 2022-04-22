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