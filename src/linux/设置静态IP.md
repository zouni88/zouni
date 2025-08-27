### linux 设置静态IP
1. 查看网卡
```shell
root@zouni:~# ifconfig
    eno1: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
            inet 192.168.1.6  netmask 255.255.255.0  broadcast 192.168.1.255
            inet6 fe80::2247:47ff:fe98:9e30  prefixlen 64  scopeid 0x20<link>
            inet6 240e:305:7880:36d2:2247:47ff:fe98:9e30  prefixlen 64  scopeid 0x0<global>
            ether 20:47:47:98:9e:30  txqueuelen 1000  (Ethernet)
            RX packets 15733  bytes 3827041 (3.8 MB)
            RX errors 0  dropped 8440  overruns 0  frame 0
            TX packets 3586  bytes 376173 (376.1 KB)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
            device interrupt 16

    enp3s0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
            ether 00:e0:51:46:0b:01  txqueuelen 1000  (Ethernet)
            RX packets 0  bytes 0 (0.0 B)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 0  bytes 0 (0.0 B)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

    lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
            inet 127.0.0.1  netmask 255.0.0.0
            inet6 ::1  prefixlen 128  scopeid 0x10<host>
            loop  txqueuelen 1000  (Local Loopback)
            RX packets 14175  bytes 21113848 (21.1 MB)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 14175  bytes 21113848 (21.1 MB)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
2. 设置网卡配置
```shell
root@zouni:/etc/network# cd /etc/netplan
root@zouni:/etc/netplan# ls
00-installer-config.yaml
root@zouni:/etc/netplan# vi 00-installer-config.yaml

# This is the network config written by 'subiquity'
network:
  ethernets:
    eno1:
      dhcp4: no
      dhcp6: no
      addresses: [192.168.1.6/24]
      optional: true
      gateway4: 192.168.1.1
      nameservers:
        addresses: [192.168.1.1,114.114.114.114]


    enp3s0:
      dhcp4: true
  version: 2
```

3. 重启网卡
```
root@zouni:/etc/netplan# netplan apply
```