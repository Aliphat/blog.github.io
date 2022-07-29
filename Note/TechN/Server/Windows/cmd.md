# 教你如何使用cmd，俗称命令提示符?

## 导出文件夹中的所有文件的名字

```bash
dir /b>1.txt
```
然后就会生成一个  1.txt的文件





## 将txt文本中的ip，改为ip段

> 从本地文件夹中找到a.txt，然后批量替换后，输出名为out.txt的文本

[教程来源：bat读取文本内容用法](https://wenku.baidu.com/view/aa3d6ae84593daef5ef7ba0d4a7302768e996fe3.html)

```bash
@echo off
set file=a.txt
(for /f "tokens=1-3 delims=." %%a in (%file%) do echo %%a.%%b.%%c.0 %%a.%%b.%%c.255)>$
move $ out.txt>nul 2>nul
exit
```





# cmd 修改静态ip地址

输入命令 netsh 网络的shell管理界面
输入 interface 进入网卡设置的cli界面
这里有提示会取消这些命令,暂时不管.

输入ip 准备设置网卡
set address "Ethernet0" static 10.24.101.1 255.255.0.0 10.24.255.254
static 设置 固定ip地址 第一个地址为 ip 第二个地址是掩码 第三个地址是网关

设置完ip地址 设置 DNS

set dns "Ethernet0" static 10.100.1.12


要想恢复的话 
set address  "Ethernet0" dhcp
set dns  "Ethernet0" dhcp


https://blog.csdn.net/weixin_30419799/article/details/95177821
