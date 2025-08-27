 
 ### consul 实例1
    docker run -itd --name=consule1 -p 8500:8500 --restart=always -e consul_bind_interface='eth0' --privileged=true --name=consul1 consul agent -server -bootstrap-expect=2  -ui -node=consul1 -client='0.0.0.0' -data-dir /consul/data -config-dir /consul/config -datacenter=consul_dc


参数说明：  
```
docker run -itd --name=consul -p 8500:8500 consul agent -server -bootstrap -ui  -client 0.0.0.0
```
`-server` : 以服务端方式启动
`-bootstrap` : 指定自己为leader ,而不需要选举
`-ui` : 启动一个内置管理web界面
`-client` : 指定客户端可以访问的IP. 设置为0.0.0.0 则任意访问，否则默认本机可以访问


实例1 ip : 172.17.0.2
### consul 实例2
    docker run -itd --name=consule1 -p 8200:8500 --restart=always -e consul_bind_interface='eth0' --privileged=true --name=consul2 consul agent -server -bootstrap-expect=2  -ui -node=consul2 -client='0.0.0.0' -data-dir /consul/data -config-dir /consul/config -datacenter=consul_dc -join=172.17.0.2