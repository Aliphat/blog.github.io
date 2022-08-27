#### 一 Git（重点）

##### 1  git是什么？

```
git是目前世界上最先进的分布式版本控制工具（没有之一）。
git由什么特点?

什么是版本控制工具?
说白了就是帮助我们管理不同版本的文件的一个应用程序。
```

##### 2 git诞生

```
2002年之前，linus自己手动维护linux的版本代码
2002之后到2005年，使用的免费的bitkeeper
2005年之后，linus开发git
```

##### 3 集中型版本控制工具和分布式版本控制工具

###### 3.1  集中型的版本控制工具

```
svn,cvs,vss
特点：
1. 实现大部分开发中对版本管理的需求
2. 结构很简单，上手容易
缺点：
1. 对中央仓库依赖严重，一旦损坏了，历史数据怎么恢复？
2. 程序员上传的都是完整版，如何追溯查询？
3. 系统正在上线运行，需要修改bug或增加几个不同的功能，持续几个月的时间。如何同时管理几个版本
4. 如果管理一个分布在世界上各地且互不相识的大型开发团队
```

![](012.png)

###### 3.2 分布式版本控制工具

![](013.png)



##### 4 git的作用

```
1. 协同开发
2. 版本记录
3. 冲突解决
4. 历史追查
5. 代码备份
6. 版本还原
7. 权限管理
8. 分支管理
9. 代码审查
...
```

##### 5 git安装

```
	最早的git是在linux上开发的，很长一段时间中，git只能在linux和unix上运行。不过，后来有人把他一直到windows平台。现在git可以在linux、unix、mac os和windows几个主流平台运行。
	要使用git，第一步当然是安装。在windows安装
```

###### 5.1 在windows中安装git

```
1. 命令行工具：git for windows(重点)
https://git-for-windows.github.io/1
tip:
点击安装包，然后傻瓜式的安装就可以成功

2. 可视化工具：TortoiseGit
https://tortoisegit.org

3. idea插件(掌握)

4. github网站(掌握)
http://www.github.com
```

##### 6 配置git签名

###### 6.1 第一步

```
选中你要作为git工程存放的目录，然后单击鼠标右键选择git bash即可。

tip:
git是分布式版本控制工具，所以我们需要填写用户名和邮箱作为一个标志。
C:\Users\lixi19861125路径下.gitconfig文件，这个我文件里面可以看到--global属性，所有的git项目都会公用这个属性

git config --global user.name "lixi"
git config --global user.email "lixi@1000phone.com"
```

##### 7 创建版本库

###### 7.1 第一步 选中一个的git工程的目录

###### 7.2 第二步 输入命令初始化版本库

```
git init
```

##### 8 git命令行操作

###### 8.1 查看文件状态

```
git status
```

###### 8.2 将文件/目录添加到临时暂存区

```
git add 文件名/目录名
e.g.
git add src/HelloWorld.java

tip:
以上通过git add命令的文件会提交到暂存区中，但是这里的文件其实没有真正的提交。使用下一个命令才是把他提交到一个统一的版本文件
```

###### 8.3 提交文件

```
git commit

e.g.
git commit -m "提交提示信息"

tip:
每当有文件被修改/添加/删除的时候，都需要重新git add，然后再git commit
```

###### 8.4 查看日志

```
git log : 查看历史记录

e.g.
$ git log


commit 29df21765ff605e8f204417f9251c410f88563b0
Author: lixi <lixi@1000phone.com>
Date:   Mon Mar 9 15:10:55 2020 +0800

    update 002

commit 76551c4baf66d295d26a2798fe5ff8ca3e827f4a
Author: lixi <lixi@1000phone.com>
Date:   Mon Mar 9 15:04:25 2020 +0800

    create 001

e.g.
$ git log --pretty=oneline
29df21765ff605e8f204417f9251c410f88563b0 update 002
76551c4baf66d295d26a2798fe5ff8ca3e827f4a create 001

```

###### 8.5 回退历史

8.5.1 创建一个文件 : a.txt

```
aaaaaaaaaaaaa
bbbbbbbbbbbbb
ccccccccccccc
ddddddddddddd

tip:
添加到暂存区然后提交
```

8.5.2 修改这个文件：a.txt

```
aaaaaaaaaaaaa
ccccccccccccc
eeeeeeeeeeeee

tip:
添加到暂存区然后提交
```

8.5.3 回退到上一次提交

```
git reset --hard HEAD^1

tip:
HEAD是一个指针，永远指向最新版本，^1表示让HEAD指针指向上一个版本

--hard 硬:这种回顾不但将版本回顾，还会将指定的数据抹除。不会保留任何你修改的记录
--soft 软:回退版本，也会保留改动的记录。会自动帮你git add。
--mix 折中:回退版本，并会保留所有改动记录。但是不会自动帮你git add

git reset : 修改HEAD的位置

这种方式可以恢复到之前某个提交的版本，但是恢复之后，当前版本之后的版本将不复存在。
```

![](014.png)



8.5.4 回退到多个版本

```
git reset --hard HEAD~2 #回退到2个版本之前的版本
```

8.5.5 版本穿越

```
git reflog # 查看历史记录的版本号

e.g.
$ git reflog
29df217 HEAD@{0}: reset: moving to HEAD~2
8938885 HEAD@{1}: reset: moving to HEAD^1
7c77ab0 HEAD@{2}: commit: update 004
8938885 HEAD@{3}: commit: update 003
c07b56d HEAD@{4}: commit: update 003
29df217 HEAD@{5}: commit: update 002
76551c4 HEAD@{6}: commit (initial): create 001

e.g.
git reset --hard 7c77ab0
```

###### 8.6 还原文件

```
git checkout 文件名

e.g.
vi src/b.txt
111111111
222222222
333333333
444444444

git add src/b.txt
git commit -m "update 005"

修改 b.txt
111111111
222222222
333333333
444444444
555555555
666666666

git checkout src/b.txt
```

###### 8.7 删除文件

```
1. 先删除文件
2. git add
3. git commit
```

##### 9 工作区、暂存区、本地库

###### 9.1 概念

```
工作区(Working Directory) : 电脑的本地磁盘目录
本地库(Repostory) : 工作区中有一个因此目录.git，它就是git的本地版本库
暂存区(stage) : 一般存储再git目录下的index文件，所以我们把暂存区有时候也叫做索引。
```

###### 9.2 关系图





![](015.png)

##### 10 分支

###### 10.1 分支概念

```
项目已经上线了，但是产品精力又提出了新的需求，评估实现这个新功能需要2个月的时就按。但是项目还是需要同时上线运行，时不时修改bug，如何管理这几个版本。
```

![](016.png)

###### 10.2 查看分支

```
git branch -v

e.g.
$ git branch -v
* master b94d274 update 006
```

###### 10.3 创建分支

```
git branch 分支名称
e.g.
$ git branch common
$ git branch -v
  common b94d274 update 006
* master b94d274 update 006

```

###### 10.4 切换分支

```
git checkout 分支名

e.g.
git checkout common
```

###### 10.5 合并分支（将其他分支合并到主分支：master）

```
1. 切换到主分支
git checkout master

2. 合并
git merge 分支名
e.g.

git merge common
```

##### 11 冲突

###### 11.1 什么是冲突

```
冲突一般是指同一个文件同一位置的代码，再两种版本的仓库合并时，版本的管理软件无法判断到底应该保留哪一个版本，因此会提示该文件发生冲突，冲突一般都需要程序员手动解决。
```

###### 11.2  在分支合并的时候解决冲突

```
1. 先在master分支上创建一个luosenhan.txt
2. 再在common分支上创建一个luosenhan.txt
3. 分别提交
4. 最后合并

e.g.
$ git merge common
Auto-merging src/luosenhan.txt
CONFLICT (add/add): Merge conflict in src/luosenhan.txt
Automatic merge failed; fix conflicts and then commit the result.

5. 查看冲突
git diff

$ git diff
diff --cc src/luosenhan.txt
index 7d8fefb,9f9848c..0000000
--- a/src/luosenhan.txt
+++ b/src/luosenhan.txt
@@@ -1,3 -1,2 +1,8 @@@
++<<<<<<< HEAD
 +11111111111111111
 +22222222222222222
- 33333333333333333
++33333333333333333
++=======
+ 222222222222222
 -333333333333333
++333333333333333
++>>>>>>> common
6. 解决冲突：切换到哪个目录，然后查看文件
7. 再重新add和commit即可
```

#### 二 GitHub(重点)

##### 1 什么是github？

```
github是一个git项目托管网站，主要提供基于git的版本托管服务。
网址：https://github.com

注册账号的注意事项
- 不要使用163邮箱，有可能收不到校验邮件。
- 较长时间不适用，有可能被github冻结账号。
- 如果冻结账号，请登录https://github.com/contact恢复申请
```

![](017.png)

##### 2 GitHub操作

###### 2.1 建立本地仓库

```
1. 创建guojing和huangrong子目录
2. 搭建代码库
git init
git config user.name "huangrong"
git config user.email "lixi19861125@qq.com"

3. 提交代码
git add
git commit
```

###### 2.2 注册github账号并登录

![](018.png)

###### 2.3 创建github的项目库

![](019.png)

![](020.png)

###### 2.4 推送代码到git

- 增加远程地址

```
git remote add <远端代号> <远端地址>
<远端代号> ：指远程链接的代号，一般直接用origin做代号，也可以自定义 
<远端地址> ：指远程链接的url

e.g.
git remote add origin https://github.com/rocklee86/kongfu.git
```

- 推送到远程库

```
git push <远端代号> <分支名>

e.g.
git push origin master
```

###### 2.5 下载GitHub上的库

- 从GitHub上克隆（guojing）

```
git clone <远端地址> <项目的目录名>
<项目的目录名> ： 指为克隆的项目在本地新建的一个目录名，可以不填，默认就是使用github仓库名

e.g.
git clone https://github.com/rocklee86/kongfu.git kongfu
```

- 修改文件

```
git push origin master

1. 问题1：
fatal: 'origin' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

解决方案如下图：
```

![](021.png)

![](022.png)

```
当黄蓉邀请了郭靖之后，郭靖用户的邮箱会接受到一份邀请的邮件，点击查看邀请会来到如下图:
```

![](023.png)

```
再次提交代码：
git push origin master
```

###### 2.6 huangrong用户同步更新代码

- 从github更新项目

```
git pull <远程代码> <远程分支>

e.g.
git pull origin master
```

##### 3 合作冲突

###### 3.1 什么是协作冲突

```
	在上传或者同步代码时，由于你和他人都修改了同一文件的同一位置的代码，版本管理工具无法判断究竟以谁为准，这就会报告冲突，需要程序员手动解决。
```

###### 3.2 解决方式

```
1. 修改合并
2. git add
3. git commit
```

![](024.png)

```
1. 在huangrong用户修改打狗棒法.txt并提交
2. 在guojing用户修改打狗棒法.txt并提交
```

![](025.png)

![](026.png)

![](027.png)

![](028.png)

##### 4 第三方团队参与场景

###### 4.1 画图分析

![](029.png)



###### 4.2 操作测试

```
1. 使用所谓的穆念慈用户（lixi86）fork出黄蓉对应的库
2. 使用穆念慈用户修改fork出来的某个文件
3. 然后查看如图
4. 操作完成之后，项目管理者（黄蓉）就会收到一封同步请求的邮件
```

![](030.png)

![](031.png)

![](032.png)

![](033.png)

![](034.png)

#### 三 GitLab

###### 5.1 什么是gitlab

```
"自架私服版"的github
官网:https://about.gitlab.com
下载网址:https://about.gitlab.com/install
```

###### 5.2 安装

```
1. 下载依赖
yum install -y curl policycoreutils-python openssh-server cronie lokkit http ssh 

2. 安装
rpm -ivh /opt/software/gitlab-ce-11.9.0-ce.0.el6.x86_64.rpm

3. 预配gitlab的组件
gitlab-ctl reconfigure

4. 修改gitlab的配置url
vi /etc/gitlab/gitlab.rb

external_url 'http://gitlab.1000phone.com'

vi /opt/gitlab/embedded/service/gitlab-rails/config/gitlab.yml

host: gitlab.1000phone.com
port: 80
https: false

5. 修改windows的hosts
192.168.49.103 slave3 gitlab.1000phone.com
```

###### 5.3 启动gitlab

```
gitlab-ctl start/stop/restart
```

#### 四  idea整合git

###### 6.1 在github上创建一个库

###### 6.2 打开idea，选择setting

```
settings ---> Version Control ---> Git
```

###### 6.3 再选择github

```
1. 需要现在github上生成授权令牌（token）
https://github.com/settings/tokens/new

2. 然后再将生成的令牌填入到idea的githup处即可
2.1 file ---> New ---> Project from Version Control ---> Git

3. 如何想要上传的文件
右键 ---> Git ---> add/commit

4. repostory ---> clone/push/pull

5. 如果有冲突会自动提示，选择merge
```

