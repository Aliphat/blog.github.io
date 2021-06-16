### 搭建免费 Docsify + Pages 个人静态博客

首先千万不要产生畏惧心理，以为搭建一个网站是只有程序员才能干的事情，我也是边学边做就摸索清楚了怎么搭建一个静态个人博客。不要害怕提问，因为搜索引擎老师不会不耐烦，也不会羞辱你，[必应](https://cn.bing.com/?mkt=zh-CN) [谷歌](http://google.com/) 我就是这么一步步搜出来的。

创立一个个人静态网页博客有多种方式，你不用预先学习好 `HTML` 等类似的知识才能做一个网页，就像你拼乐高的时候不用学习怎么制作乐高零件，因为厂家已经制作好了，你买过来成品照着步骤拼就好了。如果你比较着急想要先上线一个网页再说的话，其实已经有很多做好的网页实例，拿过来改改就可以正式上线了。

当然你也可以学习照着步骤拼积木，即看通用工具的文档，通常可以用来进行个人静态网页博客工具有：

> * [Docsify](https://docsify.js.org/#/zh-cn/) 容易上手
> * [Hexo](https://hexo.io/zh-cn/docs/) 需要一定耐心和基础
> * [Jekyll](https://jekyllcn.com/docs/home/) 需要一定耐心和基础

在这里我们使用的是 `Docsify` 结合 `Github Pages` ，因为简单便捷，只需要对照着步骤稍微改变几个参数就可以马上上传形成个人的静态博客。

### 准备

1. 耐心
   
2. 本教程以 `Win` 系统为主，请更新至 `Win 10` , 因为 `Win 7` 微软已经停止支持了。`MacOs` 系统举一反三也能够进行类似操作，因为只用到各平台通用的编辑器 VScode 和浏览器就好，用 `Linux` 系统的兄 dei 就不要来淘气了。
 


### 几种快速搭建的方式


### 超极速 Github Pages 版

1. 注册 `Github` 账号
   点击打开 [Github](https://github.com/) 网页，进行注册，需要验证邮箱，推荐使用微软的 [Outlook](http://outlook.com/) 邮箱，国内邮箱可能会接受不到邮件。
  
   ![注册 Github](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/sign-git.png)

2. 创建新的仓库
   
   步骤1： 点击网页右上角的加号创建新的仓库。

   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/create-new-1.png)

   步骤2： 如果要创建静态网页博客，仓库名称必须以 `xxx.github.io` 作为格式才能被识别。

   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/create-new-2.png)

   步骤3： 点击右上角的 `settings` 按钮进行设置

   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/create-new-3.png)

   步骤4： 页面往下拉到 `GitHub Pages`,点击选择一个主题。
  
   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/chose-theme.png)
   
   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/theme-1.png)
  

   步骤5：切换到这个页面后等待一会，等到 `Commit changes` 变绿后点击。

   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/update-theme-1.png)
  
   步骤6： 返回到 `Settings` 里面，找到 `GitHub Pages` 这一栏查看博客的网页地址，并可以强制博客地址 `https` 加密。
    
   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/back-settings.png)
  
   步骤7： 编辑你的博客页面，需要你学习一点 [Mrakdown](https://www.w3cschool.cn/markdownyfsm/markdownyfsm-odm6256r.html) 语法知识，下面简单看一下效果。
    
   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-readme-1.png)
  
   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-readme-2.png)
  
   ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-readme-3.png)
  
   步骤8： 最终效果。
    
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/pages-blog.png)
  

### 进阶 Docsify 版

  当然你肯定不会满足于这个初级版本，你估计也想要一个类似于李笑来老师的 [个人博客](http://lixiaolai.com/) 版本。笑来老师说拿他的仓库去改改就可以用了，但这个改改就可以用可不是那么简单的。有了前面的热身后面的步骤就要稍微那么好办一点。

#### 前期准备工作

##### Anaconda3

  下载 [Anaconda3](https://www.anaconda.com/products/individual) 并安装,进入前面网页后一直下拉到下载页面如下。在下图中可以看到苹果的 `MacOs` 和 `Linux` 下载方式，安装方式就不复述了。
    
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/download-anaconda3.png)
  
  `Win 10` 系统必须要进行如下面几图所示的步骤把 `Anaconda3` 加入系统环境变量，`MacOs` 与 `Linux` 系统可以忽略以下步骤。
    
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-path-1.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-path-2.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-path-3.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-path-4.png)
  
  下载安装 `Win10` 的新版终端编辑器，如下图所示
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/install-ter-1.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/install-ter-2.png)
  
  运用管理员权限打开新的终端处理器，并输入以下命令 `set-executionpolicy remotesigned`，如下图所示。
  
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/open-ter-1.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/open-ter-2.png)
  
##### VScode

   下载并安装 [VSCode](https://code.visualstudio.com/Download) 编辑器，如下图所示，安装过程不再复述。

  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/download-vscode.png)
  
  安装完vscode后可进行的必要设置如下系列图所示。
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/vscode-ex-1.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/vscode-ex-2.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/vscode-ex-3.png)
  
   
  然后你就可以像我一样一边编辑一边预览 Markdown 文件了

  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-markdown.gif)

##### GIT
  
  下载并安装 [Git](https://git-scm.com/)，安装过程就不复述了，git默然是自动添加路径的，就不用像前面的 `Anaconda3` 那样添加系统环境变量了。
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/download-git.png)
  
  配置 `Git` ，后面管理个人仓库会用到。首先打开 C 盘自己的用户文件夹并创建 `.ssh` 文件夹如下图所示。
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/create-ssh.png)
  
  用 `VScode` 编辑器打开刚刚创建的 `.ssh` 文件夹并运行终端，然后在终端中输入以下命令（`#` 和后面的话为注释），如下图所示。

  ```
  $ git config –global user.name “Yourname”  # 注册 Github 时的用户名
  $ git config –global user.email “Youremail@xxx.com”  # 注册 Github 时的邮箱
  $ ssh-keygen -t rsa -C “you email@xxx.com"  # 后面默认键入连续三个空格
  ```
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-ssh.png)
  
  然后需要打开你的网页 `Github` 地址，并执行以下操作。
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/add-ssh-1.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/add-ssh-2.png)
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/add-ssh-3.png)
  
  最后在你的 `VScode` 控制台输入命令`ssh -T git@github.com`,如下图所示。

  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/add-ssh-4.png)
  
  最后出现 `You've successfully authenticated, but GitHub does not provide shell access.` 代表配置 `Git` 成功。
      
  进行一些必要的升级和安装，首先打开 `VScode` 自带的终端，依次输入以下命令进行一些升级。以下命令行内 `#` 后面的内容为注释，输入命令时不要带上 `#` 及其后面的内容。
   
  ```
  conda update conda  
  conda update anaconda  # 前两个命令是升级刚刚安装的anaconda
  conda install -c conda-forge nodejs  # 这个命令跟后面的命令是安装一个测试工具，也可以不安装，但就别想实时预览了
  npm i docsify-cli -g # 用来编辑并预览网页的主要程序 docsify 
  ```

  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/coda-update-1.png)
   
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/coda-update-2.png)
   


#### 开始制作一个个人静态博客吧

如果你到这里都没有被上面的环境设置所劝退的话，恭喜你我们的热身活动结束了，我们要进入正题了，正式开始制作你的个人博客。

步骤1： 打开你的前面创建的 `Github text` 项目仓库，并复制克隆地址。

  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/clone-re.png)

步骤2: 打开你的 `VScode` 并找一个固定的文件夹打开。例如我在 D 盘创建了一个 `text` 文件夹并用 `VScode` 打开，并输入 `git clone + 刚复制的仓库地址` ，如下图所示。
  
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/clone-text-re-1.png)
   
  ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/clone-text-re-2.png)
   
步骤3： 到我的个人博客 [仓库地址](https://github.com/unscientific/unscientific.github.io)，下载我的个人博客仓库的 `.zip` 文件，并解压 `text` 文件夹中，然后删除 `text-github.io` 中的所有文件，用 `unscientific.github.io-master` 文件夹中的文件复制替换，如下图所示。

 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/down-mbf.png)
   
 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/copy-mbf.gif)
   

步骤4： 用 `VScod` 打开文件夹到 `x:\text\text.github.io`  这个位置。如下图所示，然后输入 `docsify serve` ，就可以看到网页在本地的运行状态了。

 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/doc-s-1.png)
   
 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/doc-s-2.png)
   
 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/doc-s-3.png)
   
步骤5： 了解 [Mrakdown](https://www.w3cschool.cn/markdownyfsm/markdownyfsm-odm6256r.html) 语法知识，编辑 `README.MD` 这个文件就可以改变网页最终的显示效果了。

 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-read.png)
   
步骤6： 调节 `index.html` 文件，改变其中一些参数为自己的,具体可以参考 [Docsify](https://docsify.js.org/#/zh-cn/) 的官方文档。
  
 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/edite-html.png)
   
步骤7： 用 `VScode` 的终端把自己改变后的仓库上传，完成后自己的个人静态博客就上线了，先依次执行如下命令。
```
git status  #查看仓库的状态
git add .   #标记所有更改文件
git commit -m "修改博客"   # 这个命令是标记更改说明
git push   # 上传仓库
```

 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/git-push.png)
   
 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/up-end.png)
   
再点击 `text` 仓库的网页地址就可以看到自己网页上线的样子了，到这里就算是完成了一大步了，后面自己博客的内容就靠自己创造了，记得参考 [Docsify](https://docsify.js.org/#/zh-cn/) 的官方文档。
   

#### 购买域名关联

购买域名的网址有

> * [Namesilo](https://www.namesilo.com/)
> * [Dynadot](https://www.dynadot.com/zh/)

这里以 [Dynadot](https://www.dynadot.com/zh/) 为例，注册过程就省略了。购买一个域名，如下图所示。
![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/dy-1.png)
   
我已经购买好域名了，以我自己购买的域名为例，进行如下设置。

步骤1： 更改 `text.github.io` 文件夹里面的 `CNAME` 文件，在里面添加自己的域名并保存，执行一次 `git status commit push`，如下图所示。

 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/change-cn.png)
   
步骤2： 变更自己域名的 DNS 地址，如下几图所示。其中输入 `185.199.110.153` 是定位到 `Github` 。
 
 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/dns-3.png)
   
步骤3： 过个一两分钟，域名就应该定位到自己的仓库地址了，可以到自己仓库的 `settings` 中的 `github pages` 中去确认，我的如下所示。再输入自己的域名就可以看到自己的静态博客了。

 ![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/final.png)
   

#### 写在最后

如果你执行到了这里并最终让自己的个人静态博客上线了的话，我相信你已经产生了很大的兴趣，现在就是反向探究的过程了，打开 [docsify](https://docsify.js.org/#/zh-cn/) 官方文档好好探究下接下来的进程吧。

#### 联系我

欢迎连接我，添加请给我个来意说明或者自我介绍，防止误删.

![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/callme.png)

**这篇文章的 PRESS.one 签名：**
https://press.one/file/v?s=f1dc4c595914bebd81a5db0e302968b7b5c59c4c85ddafdb1c555a20f807fb7b25a1d7031152b02f0b91f6864d0995444afcce70854fdab463084fa590215e4900&h=bd8e2f4ed8ac7e6bb6196480dd2e39ee73ffd697fbfea8eab416e42e702b2b7f&a=0246351c0a880aab694a1e1e7654a06ca384316e&hash_alg=sha256&f=P1&v=3