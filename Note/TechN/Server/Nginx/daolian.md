# 细说Nginx服务器下防盗链的三种方法


Nginx 是一个很牛的高性能Web和反向代理服务器, 它具有有很多非常优越的特性； 在高连接并发的情况下，Nginx是Apache服务器不错的替代品，目前Web服务器调查显示Apache下降Ngnix攀升，Linux下更多的服务商选择了Ngnix放弃了Apache； Nginx在美国是做虚拟主机生意的老板们经常选择的软件平台之一. 能够支持高达 50,000 个并发连接数的响应, 感谢Nginx为我们选择了 epoll and kqueue作为开发模型. 目前中国大陆使用Nginx网站用户有：新浪、网易、 腾讯,另外知名的微网志Plurk也使用Nginx。


首先，Nginx有三种方法可以进行防盗链

 

1、对Nginx下所有项目的指定资源不同文件类型进行防盗链

比如对gif、jpg、png、swf、flv、mp3、mp4等资源进行防盗链

 

2、对指定目录或者指定项目目录进行防盗链

比如Nginx下有3个项目，A、B、C，

可以对A目录下的images进行防盗链，

也可以对B目录下的images进行防盗链，

也就是说，对指定目录进行防盗链。

 

3、nginx 的第三方模块ngx_http_accesskey_module 来实现下载文件的防盗链

（本文不做介绍，上面两种防盗链功能已经足以，新加入的插件可能对性能产生影响）

 

## 1.对Nginx下所有项目的指定资源不同文件类型进行防盗链

 

找到nginx的配置文件nginx.conf：/usr/local/nginx/conf/nginx.conf

```shell
location ~* \.(gif|jpg|png|swf|flv)$ { #需要防盗链资源的文件类型
  		valid_referers none blocked  27wy.cn; #这是可以盗链的域名或IP地址，一般情况可以把google，baidu，sogou，soso，bing，feedsky，zhuaxia，photozero等域名放进来
  		if ($invalid_referer) { 
            #这样设置能够防盗链，不断地302重定向很多次，可能会加重服务器的负担，所以不建议这么做，除非有单独的图片服务器支持
    		#rewrite ^/ https://www.27wy.cn:90/picture/images/details-image-1.jpg; #如果有人非法盗链资源，则返回一张防盗链的图片
    return 403; #或者返回403错误代码
  	} 
}
```

配置完成之后，重启nginx，重启命令：/usr/local/nginx/sbin/nginx -s reload

如何检验？

比如在CSDN上写一篇博文，或者写一个html加载一张图片（url为nginx下的某一张图片），或者在鸟哥的博文下面留言插入图片等等...

 

## 2.对指定目录或者指定项目目录进行防盗链

 

还是在nginx.conf里配置，位置和上面一样

```Shell
location /img/ {  #img是相对目录，是html目录下的img目录
  valid_referers none blocked server_names 27wy.cn ; #允许访问该目录的域名或IP
  if ($invalid_referer) {return 403;} #不允许访问返回403
}


location /picture/images/{ #在html目录下的picture项目下的images目录进行防盗链
    valid_referers none blocked server_names 27wy.cn;#允许访问目录的域名或IP
    if ($invalid_referer){return 403;} #不允许访问返回403
}
```

这里我要强烈吐槽一下，网上搜一下nginx防盗链，教程自原，一大把一大把，特么的几乎完全一样！！！



## 3.nginx 的第三方模块

ngx_http_accesskey_module 来实现下载文件的防盗链,这种方法没有亲测，借鉴就好。

http://www.cnblogs.com/shuaixf/archive/2011/11/14/2249078.html

 http://www.jb51.net/article/68867.htm

