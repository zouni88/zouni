## 开发环境修改wsl 默认登录用户为root

### 1. 现在用的是`ubuntu`，找到安装目录
```shell
C:\Users\用户名\AppData\Local\Microsoft\WindowsApps\ubuntu版本.exe config --default-user root
```

![](/res/windows/wsl_path.png)

### 2. 执行命令
```
ubuntu2004.exe config --default-user root
```
### 3. 重新进入wsl,就是root用户了

