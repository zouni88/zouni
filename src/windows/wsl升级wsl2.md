### 检查当前运行的wsl版本
```
wsl -l -v
```

[下载windows wsl2 linux内核](https://docs.microsoft.com/zh-cn/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)


`wsl --set-version <distro name> 2`，将 `<distro name>` 替换为要更新的 Linux 发行版的名称。   
例如，`wsl --set-version Ubuntu-20.04 2` 会将` Ubuntu 20.04` 发行版设置为使用 WSL 2