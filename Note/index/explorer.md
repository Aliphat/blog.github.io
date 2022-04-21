

# 存放一些系统软件资源

## VC++微软全家桶
http://dreamcast2.ysepan.com/





# 待处理

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
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

# 待处理

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
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。



## 2.量子计算架构  https://www.dwavesys.com/



## VC++微软全家桶

http://dreamcast2.ysepan.com/
