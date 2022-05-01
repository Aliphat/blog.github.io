# 钉钉免费内网穿透：实现内网主机上线

## 第一步： clone  git仓库
执行命令：git clone https://github.com/open-dingtalk/pierced.git
## 第二步：开始配置
> 注意：在pierced根目录下执行命令

### Mac:
 (1) cd mac_64
 (2)./ding -config=./ding.cfg -subdomain=abcde 8080

### Windows: 
 (1) cd windows_64
 (2)ding -config=ding.cfg -subdomain=abcde 8080

## 第三步：测试
启动完客户端后，你访问http://abcde.vaiwan.com/xxxxx都会映射到 http://127.0.0.1:8080/xxxxx

## 注意：
1.你需要访问的域名是http://abcde.vaiwan.com/xxxxx 而不是http://abcde.vaiwan.com:8082/xxxxx
2.你启动命令的subdomain参数有可能被别人占用，尽量不要用常用字符，可以用自己公司名的拼音，例如：alibaba、dingding等。
3.可以在本地起个http-server服务，放置一个index.html文件，然后访问http://abcde.vaiwan.com/index.html测试一下。
————————————————
版权声明：本文为CSDN博主「System.o」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/lyh1299259684/article/details/81941268