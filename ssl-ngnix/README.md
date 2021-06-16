关于给网站申请并配置ssl 证书的教程

### 前提配置：

1. 购买服务器，[linode](https://www.linode.com/)  [vultr](https://www.vultr.com/register/) [阿里云](https://cn.aliyun.com/) [腾讯云](https://cloud.tencent.com/)（注意：如果服务器在国内，则所购买的域名必须备案才能链接，谨慎考虑）
2. 购买域名,可以直接在阿里云或者腾讯云里面购买，也可在域名商 [dynadot](https://www.dynadot.com/) [Namesilo](www.namesilo.com) 上面购买
3. 服务器的配置系统为 Ubuntu 20.04 

一、远程连接你的服务器

设置用户名和密码略过，用 SSH 连接你的远程服务器，Win 系统可以用这个 [SSH](https://docs.microsoft.com/zh-cn/windows-server/administration/openssh/openssh_install_firstuse) 教程，或者想办法下载 [Xshell](https://www.netsarang.com/en/xshell/) 和 Xftp 7 ,具体连接过程略过，[参考教程](https://blog.csdn.net/qq_42744046/article/details/105620368?utm_medium=distribute.pc_relevant.none-task-blog-baidujs_utm_term-1&spm=1001.2101.3001.4242)。



#### 一、安装 Nginx 

连接上服务器后第一件事当然是输入以下命令,对 `linux` 系统进行以下刷新和升级。

```
sudo apt update && sudo apt upgrade
```

接着安装 `nginx` 。

```
sudo apt install nginx
```

如果你只是测试，可以参考以下两个教程

> [nginx 配置实战入门]（https://blog.csdn.net/leon_zeng0/article/details/108820539）
>
> [How To Set Up Nginx Server Blocks (Virtual Hosts) on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-server-blocks-virtual-hosts-on-ubuntu-16-04)

当你用以上教程摸透过程以后，直接给自己的域名配置服务器块了。



#### 二、给自己的域名配置服务器块



首先输入以下命令

```
sudo nano /etc/nginx/sites-available/example.com # 把 example.com 改成你自己的域名
```

在里面配置的内容可以为以下样本

```
server {
        listen 80;
        listen [::]:80;
 
        root /var/www/example.com/html;
        index index.html index.htm index.nginx-debian.html;
 
        server_name example.com www.example.com;
 
        location / {
                try_files $uri $uri/ =404;
        }
}
```



关联 `sites-available` 和 `sites-enable` 两个文件夹，因为 `/etc/nginx/sites-available/ ` 下的配置文件并不会参与配置，必须链接到 `/etc/nginx/sites-enable/` 目录下，操作命令如下

```
sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/
# 同样，将 example.com 改成你自己的域名
```

为了避免可能由于添加其他服务器名称而引起的哈希存储桶内存问题，我们在 `/etc/nginx/nginx.conf` 文件中调整单个值。 打开文件:

```
sudo nano /etc/nginx/nginx.conf
```



在文件里找到server_names_hash_bucket_size项，取消前面的注释。

```
http {
    . . .
    server_names_hash_bucket_size 64;
    . . .
}
```

`ctrl` + `O` 保存，`ctrl` + `x` 退出。使用以下命令测试配置语法是否正确

```
sudo nginx -t # or
sudo nginx -T
```

如果语法报错，可以看看 `/etc/nginx/sites-enbale/`目录下的内容，不是必要的就要删除，也许是他引起的错误。如果没有报错，重启 nginx ，用以下命令

```
sudo systemctl restart nginx
```



#### 三、Certbot 自动配置 SSl 证书

配置自动 `certbot let us encrypt` 请 参考以下教程

>[如何在ubuntu 20 和nginx 上实现加密保护 https](https://blog.csdn.net/leon_zeng0/article/details/113767458)
>
>[How To Secure Nginx with Let's Encrypt on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04)

安装 Certbot 和 nginx 扩展

```
sudo apt install certbot python3-certbot-nginx
```



这里注意 ufw 的配置，查看当前防火墙状态

```
sudo ufw status
```

出现以下说明正常

```
Status: active
 
To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere                  
Nginx HTTP                 ALLOW       Anywhere                  
OpenSSH (v6)               ALLOW       Anywhere (v6)             
Nginx HTTP (v6)            ALLOW       Anywhere (v6)
```

如果没有，则执行以下命令

```
sudo ufw allow 'Nginx Full'
# sudo ufw delete allow 'Nginx HTTP'
# 下面这行是直接关闭 http 服务，可选
```

使用命令让 certbot 自动获取证书

```
sudo certbot --nginx -d example.com # 注意把 example.com 换成你自己的域名
```

后面会让你同意服务条款，输入邮箱等，如果成功，certbot 会向你询问如何配置 HTTP 或者 HTTPS

```
Please choose whether or not to redirect HTTP traffic to HTTPS, removing HTTP access.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
1: No redirect - Make no further changes to the webserver configuration.
2: Redirect - Make all requests redirect to secure HTTPS access. Choose this for
new sites, or if you're confident your site works on HTTPS. You can undo this
change by editing your web server's configuration.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Select the appropriate number [1-2] then [enter] (press 'c' to cancel):
```

这里我们选2，毕竟我们需要证书来保证网站通讯安全。如果配置成功，则会出现以下代码：

```
IMPORTANT NOTES:
 - Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/example.com/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/example.com/privkey.pem
   Your cert will expire on 2020-08-18. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot again
   with the "certonly" option. To non-interactively renew *all* of
   your certificates, run "certbot renew"
 - If you like Certbot, please consider supporting our work by:
 
   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le
```

使用 `systemctl` 来查询证书计时器状态

```
sudo systemctl status certbot.timer
```

使用以下命令让 `certbot` 自动续订证书

```
sudo certbot renew --dry-run
```

如果没有看到任何错误，则说明配置正确，ssl 证书会到期自动续订，如果续订不成功会发邮件告诉你。



#### 四、手动配置 ssl 证书



阿里云可以申请一年版的免费 ssl 证书，[申请教程](https://help.aliyun.com/document_detail/148895.html?spm=5176.14113079.0.dexternal.7d8d1b4cp8MTgd) 。阿里云的配置教程太老了，具体应用过程有数不尽的坑，但可以作为参考，参考教程如下

> [在Nginx（或Tengine）服务器上安装证书](https://help.aliyun.com/document_detail/98728.html?spm=5176.14113079.0.dexternal.343b1b4cNnsSpd)

具体的 ssl 证书下载，传输到服务器可以看参考教程从略。下面主要说新版的区别，新版直接在 `/etc/nginx/` 目录下创建 `cert` 文件夹，并把证书传输到这个文件夹中。



新版也不直接更改 `/etc/nginx/nginx.conf` 文件，这会导致错误。经过前面的设置，我们已经知道，该要改的文件在 `/etc/nginx/sites-available/` 中，用 `nano`  命令打开更改，命令如下：

```
sudo nano /etc/nginx/sites-available/example.com # 把 example.com 改成你自己的域名
```

然后在配置文件中设置成以下内容

```
#以下属性中，以ssl开头的属性表示与证书配置有关。
server {
    listen 443 ssl;
    #配置HTTPS的默认访问端口为443。
    #如果未在此处配置HTTPS的默认访问端口，可能会造成Nginx无法启动。
    #如果您使用Nginx 1.15.0及以上版本，请使用listen 443 ssl代替listen 443和ssl on。
    server_name yourdomain.com; #需要将yourdomain.com替换成证书绑定的域名。
    root html;
    index index.html index.htm;
    ssl_certificate cert/cert-file-name.pem;  #需要将cert-file-name.pem替换成已上传的证书文件的名称。
    ssl_certificate_key cert/cert-file-name.key; #需要将cert-file-name.key替换成已上传的证书密钥文件的名称。
    ssl_session_timeout 5m;
    ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:ECDHE:ECDH:AES:HIGH:!NULL:!aNULL:!MD5:!ADH:!RC4;
    #表示使用的加密套件的类型。
    ssl_protocols TLSv1 TLSv1.1 TLSv1.2; #表示使用的TLS协议的类型。
    ssl_prefer_server_ciphers on;
    location / {
        root html;  #站点目录。
        index index.html index.htm;
    }
}
```

可选：设置HTTP 请求跳转 HTTPS 。如果您希望所有的HTTP访问自动跳转到HTTPS页面，则可以在需要跳转的HTTP站点下添加以下`rewrite`语句。使用示例代码前，请注意将`yourdomain.com`替换成证书绑定的域名。

```
server {
    listen 80;
    server_name yourdomain.com; #需要将yourdomain.com替换成证书绑定的域名。
    rewrite ^(.*)$ https://$host$1; #将所有HTTP请求通过rewrite指令重定向到HTTPS。
    location / {
        index index.html index.htm;
    }
}
```

重新启动你的 Nginx 服务

```
sudo systemctl restart nginx
```

如果没有报错，那么你就可以通过证书绑定的域名访问你的服务器网战了。

```
https://yourdomain.com   #需要将yourdomain.com替换成证书绑定的域名。
```

以下为成功后的效果。

![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7614018061/p108044.png)