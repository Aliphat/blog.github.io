# NPS内网映射方案

参考文档  https://www.cnblogs.com/qianxiao996/p/13574573.html

官方文档：https://ehang-io.github.io/nps/#/run

https://blog.csdn.net/weixin_42461800/article/details/125566863

## 1.内网穿透工具--NPS

https://www.cnblogs.com/qianxiao996/p/13574573.html

https://blog.csdn.net/qq285744011/article/details/122629797

http://www.manongjc.com/detail/28-aibmsuwxnycmfkv.html

## 开发人员使用方式

1. 服务端开通账号
2. 客户端安装进程。后期可以在虚拟化中心部署。
3. 开发人员服务器软件(Nginx或者Apache、iis)的网站添加，服务端的域名。
   1. PHPenv，在网站里面添加一个服务端的ip地址
   2. IIS，设置默认网站的路径  https://jingyan.baidu.com/article/5225f26ba505fde6fa09080c.html

## TCP映射方案：

直接映射然后，访问就可以了。



## 文件管理sftp映射方案：

###  npc端：

注册客户端并且，linux通过sftp映射22端口

### 访问端：

手机使用Es文件管理器；电脑使用 [Raidrive](https://www.raidrive.com/)进行磁盘映射



