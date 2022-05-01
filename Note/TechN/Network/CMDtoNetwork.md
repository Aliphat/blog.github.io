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