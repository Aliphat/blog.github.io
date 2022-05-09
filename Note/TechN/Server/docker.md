# Docker在不同操作系统下的安装

## Centos7的Docker安装

### 1.卸载旧版本

较旧的Docker版本称为docker或docker-engine。
```Shell
sudo yum remove docker\
docker-client\
docker-client-latest\
docker-common\
docker-latest\
docker-latest-logrotate\
docker-logrotate\
docker-engine 
```

### 2.安装依赖

docker前需要安装的依赖包
```Shell
sudo yum install -y yum-utils
```

### 3.配置阿里docker源
```Shell
yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

### 3.更新缓存
```shell
yum makecache fast
```
### 4.安装docker
```shell
yum install -y docker-ce docker-ce-cli containerd.io
systemctl enable  docker
sudo systemctl daemon-reload
sudo systemctl restart docker
```

### 5.配置阿里云镜像加速器
```shell
# vim /etc/docker/daemon.json
# 将文件内容修改为以下信息，不可有空格
{"registry-mirrors": ["https://kfwkfulq.mirror.aliyuncs.com","https://2lqq34jg.mirror.aliyuncs.com","https://pee6w651.mirror.aliyuncs.com","https://registry.docker-cn.com","http://hub-mirror.c.163.com"],"dns": ["8.8.8.8","8.8.4.4"]}

# 如果上面信息不行，粘贴下面的信息
{ "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn"]}

# Docker中国官方，其他官方.
https://registry.docker-cn.com 网易http://hub-mirror.c.163.com 中科大https://docker.mirrors.ustc.edu.cn
```

### 6.重启生效

```shell
sudo systemctl daemon-reload
sudo systemctl restart docker
```

### 7.docker-compose安装 

```Shell
# 下载docker-compose
sudo curl -L https://get.daocloud.io/docker/compose/releases/download/1.25.1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
# 进行授权
sudo chmod +x /usr/local/bin/docker-compose

# 查看版本号:验证是否安装成功
docker-compose --version
```

## Ubuntu20.08的Docker安装

### 1. 安装依赖

```shell
1）sudo apt-get update

2）允许apt通过https使用repository安装软件包 
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
    
3）添加Docker官方GPG key
国内阿里云版 sudo curl -fsSL https://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | apt-key add -
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

4）验证key的指纹
sudo apt-key fingerprint 0EBFCD88

正常输出为：
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]

5）添加稳定版repository
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
或者国内阿里云版repository：
sudo add-apt-repository \
   "deb [arch=amd64] https://mirrors.aliyun.com/docker-ce/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

5）sudo apt-get update
```



6）安装最新版本的docker ce和containerd

sudo apt-get install docker-ce docker-ce-cli containerd.io
（如果您启用了多个Docker存储库，则在apt-get install或apt-get update命令中未指定版本的情况下安装或更新将始终安装尽可能高的版本）

7）安装指定版本的版本
查看可获取的版本 

apt-cache madison docker-ce
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io

 8）验证：

docker --version
sudo docker run hello-world

 9）将非root用户加入docker组，以允许免sudo执行docker

sudo gpasswd -a 用户名 docker    重启服务并刷新docker组成员

sudo service docker restart
newgrp - docker

10)设置开机自启动并启动 Docker-ce（安装成功后默认已设置并启动，可忽略）sudo systemctl enable docker
sudo systemctl start docker



11）升级版本

a) sudo apt-get update

b) 按照以上步骤安装新版本

12）安装docker-compose

```shell
https://www.runoob.com/docker/docker-compose.html

sudo curl -L https://github.com/docker/compose/releases/download/1.25.4/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

docker-compose --version

```

