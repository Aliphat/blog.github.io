# 校园网MAC地址白名单破冰

第一步：关闭网络  ifconfig ens33 down
第二步：修改TTL。
修改/etc/sysctl.conf配置文件，添加如下一行    net.ipv4.ip_default_ttl = 128
第三步：修改为 添加过白名单的MAC地址。
一般用本地机器即可。Linux与Windows同时使用同一个MAC地址不冲突。
 ifconfig eth0（网卡名称） hw ether 94:C6:91:02:8D:0E（529机房53号机子Mac地址）
第四步：开启网络  ifconfig ens33 up