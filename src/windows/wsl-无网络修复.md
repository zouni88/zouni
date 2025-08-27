## wsl linux 连不上网
### 解决办法：管理员权限打开命令行工具
```shell
wsl --shutdown
netsh winsock reset
netsh int ip reset all
netsh winhttp reset proxy
ipconfig /flushdns
```

重启电脑，重试