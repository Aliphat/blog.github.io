# Python

Python快速开发web

## 2.Python国内源

[目前参考这篇文章](https://www.cnblogs.com/sunnydou/p/5801760.html)

[这边文章主要是找国内源失效的url](https://blog.csdn.net/weixin_41633902/article/details/115754289)



### 1. 基于python+openCV+flask的实时移动检测ALL

最近手痒，就造了个轮子。名字随意一点，就叫**rtm2**吧, real-time motion moitior.
 算是一个实时移动侦测程序，主要使用python+flask+[socketIO](https://links.jianshu.com/go?to=https%3A%2F%2Fsocket.io%2F)+openCV开发。

与类似程序的不同在于，rtm2只在检测到运动🏃的时候才推送视频帧给客户端。
 服务端为树莓派、笔记本等带有摄像头的设备，在上面运行openCV和flask。
 openCV负责抓取视频帧和比较视频帧之间的区别。发现区别后通过websocket把结果实时发送给浏览器，这样可以避免不必要的数据传输。
 如果没有发现运动，就发送心跳包，告知浏览器等客户端通信正常。
 检测到移动或通信异常时通过弹框、声音、震动（如手机等移动设备）等方式提醒用户。
 移动侦测到的结果会存储在服务器上（可选），在网页上可以查看移动帧的历史情况。

作者：def_fun
链接：https://www.jianshu.com/p/585f0ac00a19







# 免费的分布式的自动化测试工具

http://www.selenium.org.cn/





# 什么是 Python？
Python 很好用
适合初学者
而且在各个领域都很强大![在这里插入图片描述](index.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Y2a57yU,size_20,color_FFFFFF,t_70,g_se,x_16-16517224504666.png)

python3 早已有之
最终逆风翻盘
当然 java 也是非常伟大的对手
![在这里插入图片描述](index.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Y2a57yU,size_20,color_FFFFFF,t_70,g_se,x_16-16517224383141-16517224559717.png)

三次问鼎 tiobe 霸主之位
LinuxJournal
最喜欢的编程语言 2009-2011
最喜欢的脚本语言 2006-2008、2010、2011
LinuxQuestion.org
会员选择大奖 2007-2010
![在这里插入图片描述](index.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Y2a57yU,size_20,color_FFFFFF,t_70,g_se,x_16-16517224383142-16517224578048.png)
打开终端 terminal
运行 python3
更新 apt 源，安装 python3
打开 xfce(这个词的发音为X-f-c-e即四个字母一个一个的读)
进入终端

```bash
#首先是更新源
sudo apt update
#然后是安装Python
sudo apt install python3
#最后升级Python
sudo apt upgrade python3
```

退出
1. quit()
2. ctrl+d