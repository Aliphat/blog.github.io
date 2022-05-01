# Nginx的配置和使用



### Windows 下手动配置 Nginx 及 PHP-CGI 多进程开机自启方法

https://blog.csdn.net/maxsky/article/details/78820967


OK，先入手这些玩意儿的压缩包

Nginx：http://nginx.org/en/download.html
PHP4Windows：http://windows.php.net/download/【请下载 NTS（Non Thread Safe 非线程安全）版】

下面这货是用来创建 Windows 自启服务的：
WinSW：https://github.com/kohsuke/winsw/releases【下载 .exe 文件即可，根据系统选择，Win 10 选择 .NET4 版本，以下选择 .NET2 版本】

xxfpm 用来开启 PHP-CGI 多进程
xxfpm：https://github.com/78/xxfpm
（也可以使用我编译的版本，支持带空格的路径：https://github.com/maxsky/xxfpm）

规规矩矩的办事是基本
先在 D 盘或任意位置建立一个文件夹（一定不能有空格），例如 D:\WebDevEnvironment

依次创建 nginx、php56、xxfpm（PHP 视版本命名，例如 PHP 7.1 则为 php71。）

将已下载的 Nginx 和 PHP 都扔到对应文件夹内，nginx 内包含 nginx.exe 和 conf 文件夹；php56 内包含 php-cgi.exe 和 ext 文件夹

将 WinSW.NET4.exe 分别扔进 nginx 文件夹和 php71。xxfpm 压缩包内 bin 文件夹里除了 xxfpm，将 xxfpm.exe 和 pthreadGC2.dll 扔进 xxfpm 文件夹

nginx 内的 WinSW.NET4.exe 重命名为 nginx-server.exe，然后新建一个同名的 XML 文件 nginx-server.xml

编辑 nginx-server.xml 文件，内容如下：
————————————————
版权声明：本文为CSDN博主「至天」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/maxsky/article/details/78820967