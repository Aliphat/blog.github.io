#### 利用免费 CDN 加速你的网页

如果你的个人静态博客架设在海外服务器或者 `Github Pages` 上，由于众所周知的原因，通常可能会导致网页显示缓慢。如果你想对网页进行加速的话，购买那些流量加速服务并不是最好的选择，运行一个个人静态博客的话用不到那么大的流量，等你打好基础运作大项目的时候再购买不迟。

还好神奇的开源世界为我们提供了许多小而美的选择。

> * [jsDelivr](https://www.jsdelivr.com/)
> * [BootCDN](https://www.bootcdn.cn/)
>
>注意这些免费加速适用于所加速文件小于 50m

以下教程以 `jsDelivr` 为主，并且假设你已经有了如何搭建个人博客和使用 Github 的基础，如果你不会的话，我写了一个免费搭建个人静态的 [教程](https://lilongbin.com/#/new-blog/README)。

首先打开你的 `Github` 主页，并创建一个个人的公开仓库，如下图所示。

![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/speedup-web/images/new-re.png)

因为我已经创建好了，具体创建过程就不演示了。我创建了一个仓库叫 `cdn` ,然后把仓库 `clone` 到本地，把你要加速的图片和文件加入仓库并 `push`到仓库中,然后创建一个 `Releases` 如下面几图所示。

![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/speedup-web/images/rel-1.png)

![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/speedup-web/images/rel-2.png)

![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/speedup-web/images/rel-3.png)

下面就简单了，利用 `jsDelivr` 进行图片加速不用下载客户端，也不用再把图片再次上传到别的地方，它本身就是利用刚才创建的 `Releases` 进行加速，只需要加入下面的语句就能进行加速了。

```
# 使用方法：在 markdown 图片引用的括号里面加入如下语句
https://cdn.jsdelivr.net/gh/你的用户名/你的仓库名@发布的版本号/文件路径

# 例如我的一个引用，我没有加版本号就是直接引用最新的一个版本
![](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/new-blog/sign-git.png)
```

`jsDelivr` 不仅可以用来加速图片，还可以用来加速图片，还可以用来加速 `css` `js` 等，例如 `docsify` 就用 `jsDelivr` 加速了自家的内容和版本。

```
# 官方的加速代码如下所示，只要替换 index.html 中的内容相应内容
# 就可以不用本地文件，直觉引用网上的加速版本 docsify
<!-- 引入 css -->
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/vue.css">

<!-- 引入 script -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.js"></script>
```
利用 Github 下载文件通常很慢，利用加速可以提高文件的下载速度，下面的文件来自李笑来的 [定投改变命运](https://ri.firesbox.com/#/)，仅供测试使用。

> * [定投大佬的自我修养 PDF 版本下载（原始版）](https://raw.githubusercontent.com/unscientific/unscientific.github.io/master/speedup-web/images/%E5%AE%9A%E6%8A%95-%E5%A4%A7%E4%BD%AC%E7%9A%84%E8%87%AA%E6%88%91%E4%BF%AE%E5%85%BB.pdf)
> 
> * [定投大佬的自我修养 PDF 版本下载（加速版）](https://cdn.jsdelivr.net/gh/unscientific/cdn/images/speedup-web/images/定投-大佬的自我修养.pdf)