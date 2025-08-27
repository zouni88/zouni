### 下载
```shell
go install github.com/shadowsocks/go-shadowsocks2
```
### 运行

```shell
go-shadowsocks2 -s 'ss://AEAD_CHACHA20_POLY1305:qaz521..@:8488' -verbose
```


### 客户端

```shell
go-shadowsocks2 -c 'ss://AEAD_CHACHA20_POLY1305:qaz521..@[zouni.vip]:8488' -verbose -socks :1080 -u -udptun :8053=8.8.8.8:53,:8054=8.8.4.4:53 -tcptun :8053=8.8.8.8:53,:8054=8.8.4.4:53
```

go-shadowsocks2 -c 'ss://AEAD_CHACHA20_POLY1305:qaz521..@[zouni.vip]:8488' -redir :1082 -redir6 :1083