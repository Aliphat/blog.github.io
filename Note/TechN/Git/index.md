# Git

## Git删除本地任意提交记录的方法

https://blog.csdn.net/weixin_46267445/article/details/122328025



[Git命令——提交、查看、后退、前进](https://www.cnblogs.com/jiqianqian/p/7027572.html)

https://www.cnblogs.com/jiqianqian/p/7027572.html



## git 记住密码

### 通过ssh-keygen
```Shell
$ ssh-keygen -t rsa -C "xxx@163.com"
```

### 通过记住密码

输入命令 git config --global credential.helper store

之后再操作git输入一次用户名、密码，后续不需要再次输入了

push你的代码 (git push), 这时会让你输入用户名和密码, 这一步输入的用户名密码会被记住,
下次再push代码时就不用输入用户名密码 ! 这一步会在用户目录下生成文件.git-credential记录用户名密码的信息。
————————————————
版权声明：本文为CSDN博主「「已注销」」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/Forcezs/article/details/84136902