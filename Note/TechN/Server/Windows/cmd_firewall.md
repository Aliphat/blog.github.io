# Cmd 操作域防火墙

> 命令需要使用管理员运行，调用bash脚本去操作防火墙。

```Bash
// 开放所有的端口通过防火墙
netsh advfirewall firewall add rule name=ai dir=in action=allow 
netsh advfirewall firewall add rule name=ao dir=out action=allow 

//禁止某个端口通过防火墙
netsh advfirewall firewall add rule name=deny445t dir=in action=block protocol=tcp localport=445
netsh advfirewall firewall add rule name=deny445u dir=in action=block protocol=udp localport=445


// 开启防火墙
netsh advfirewall set allprofile state on

//关闭防火墙
netsh advfirewall set allprofile state off
```

