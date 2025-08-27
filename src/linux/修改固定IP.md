### 给系统设置固定IP
定位到目录：
```shell
cd /etc/sysconfig/network-scripts

ifcfg-em1      ifdown-eth   ifdown-ppp       ifup          ifup-ipv6   ifup-routes    init.ipv6-global
ifcfg-em1.bak  ifdown-ib    ifdown-routes    ifup-aliases  ifup-isdn   ifup-sit       network-functions
ifcfg-em2      ifdown-ippp  ifdown-sit       ifup-bnep     ifup-plip   ifup-Team      network-functions-ipv6
ifcfg-lo       ifdown-ipv6  ifdown-Team      ifup-eth      ifup-plusb  ifup-TeamPort
ifdown         ifdown-isdn  ifdown-TeamPort  ifup-ib       ifup-post   ifup-tunnel
ifdown-bnep    ifdown-post  ifdown-tunnel    ifup-ippp     ifup-ppp    ifup-wireless
```

`vi` 编辑 `ifcfg-em1`文件， 这个文件是对应网卡的脚本内容，直接修改：增加如下几项，包括IP地址，网关等等
```shell
IPADDR="192.168.2.6"
NETMASK="255.255.255.0"
GATEWAY="192.168.1.1"
NETWORK="192.168.1.0"
DNS1="192.168.1.1"
```
### 修改完成后，重启network
```shell
service network restart
```

ending...