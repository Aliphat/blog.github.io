## SSH 进阶远程登录服务器免密码

#### 一、SSH 远程登录服务器的方法

1. 用 xshell 工具，这个就不复述了。

2. 用 Win 系统自带的 SSH 远程登录服务器

   用管理员身份打开 `PowerShell` 直接输入 `ssh root@xx.xx.xx.xx` 如果服务器端口打开的话会让你输入密码，然后你就直接连上了。

3. 用 Vscode 来连接，需要下载 `Remote-SSH` 插件

   ![](https://upload-images.jianshu.io/upload_images/11576306-533f352c194a9892.png?imageMogr2/auto-orient/strip|imageView2/2/w/301/format/webp)

打开 Remote-SSH 插件，进行配置（Configure）

![](https://upload-images.jianshu.io/upload_images/11576306-54c8495a88de08f3.png?imageMogr2/auto-orient/strip|imageView2/2/w/353/format/webp)

在 Vscode 顶部的弹窗中选择 config 文件存放的位置，一般是在最上面。

![](https://upload-images.jianshu.io/upload_images/11576306-0d416e2a8e1f2d1f.png?imageMogr2/auto-orient/strip|imageView2/2/w/604/format/webp)

在 config 文件中配置需要连接的服务器，如果需要连接多个服务器，就配置多个

```
Host 服务器1
    HostName xx.xx.xx.xx
    User root
    
Host 服务器2
    HostName xx.xx.xx.xx
    User root
```

保存后就可以看到所设置的需要连接的服务器了。



#### 二、进阶用公钥免登陆

Win 系统中，对于需要重复进行远程登陆，我们需要一个方法使得免去输入密码登陆的烦恼，这时就需要我们进行公钥免登陆。首先用管理员打开`PowerShell` 。输入

```
ssh-keygen -t rsa -C "your_email@example.com" # 其中邮箱要换成自己的
```

连续回车三次直接生成秘钥，当然有需要的可以根据选择自行定制其中的命令。生成的文件一般在 `C/User/用户/.ssh` 文件夹下。

再次用管理员打开`PowerShell`，打开至 `.ssh` 文件夹使用 `scp` 命令将公钥文件上传至服务器 `/root` 文件夹，命令如下

```
scp id_rsa.pub root@xx.xx.xx.xx:/root
```

其中会要求输入密码等。然后用 `PowerShell` 或其它工具连接上服务器，用 以下命令切换至 `root ` 文件夹。

```
cd /root/
```

再输入

```
cat id_rsa.pub >> .ssh/authorized_keys # 添加公钥至服务器端
```

如果服务器端没有 `.ssh` 文件夹，用以下命令测试

```
cd ~/.ssh
```

如果不存在，用以下命令生成公钥

```
ssh-keygen
```

利用以下命令可以复制公钥，方面复制到 `git` 上。

```
cat ~/.ssh/id_rsa.pub
```



