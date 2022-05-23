# vos3000 VOS3000端口介绍及安全防护

如何把 web端口改为8080之外的端口 

vos3000 ，如何修改web端口

vi /home/kunshiweb/base/apache-tomcat-7.0.23/conf/server.xml

![安装文件](vossafe.assets/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Y2a57yU,size_20,color_FFFFFF,t_70,g_se,x_16-16517360463961.png)
找到这里的8080，把它改为1024以上端口 （web端口由kunshiweb用户启动，故无法使用1024以下端口，若确需修改，可联系技术人员）

/etc/init.d/vos3000webct restart （V2.1.4.0执行该命令）
/etc/init.d/webserverd restart （V2.1.6.00执行该命令）



tcp 端口：
vos登录: 1202
web： 8080 52088 61888 88
ssh:22
数据库：3306 3389
H323： 443 1719 1720 3719 3720
H245： 10000-49999
UDP端口:
数据库：3306 3389
ssh:22
SIP： 5060 5070 2028 2038(RC4)

RTP: 10000-49999