确保 php环境 变量要在 7 以上
否则安装 laravel有的版本会报错

1.windows 安装composer
环境采用的phpstudy8

打开phpstudy->环境->找到composer点击安装->(进入phpstudy安装目录/Extensions->composer1.8.5)->进入composer安装目录复制此路径->添加到环境变量
最新 cmd 窗口检查是否安装成功-> composer -V /composer -v

2.composer切换 阿里镜像 原文地址 https://developer.aliyun.com/composer
全局配置 ：composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/
composer config -gl 查看全局配置
[repositories.packagist.org.url] https://mirrors.aliyun.com/composer/ --成功
3.安装laravel5.6
环境 windows phpstudy8 php7.3.4
以composer来安装laravel 5.6 前提已安装composer
打开cmd-> composer create-project --prefer-dist laravel/laravel=5.6.* blog

4.启动laravel 项目
域名方式指向 入口文件 即 /public
然后浏览器域名访问

了解什么是特征以及如何使用它们的最好方法是观察它们的本质