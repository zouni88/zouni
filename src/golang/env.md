### golang 配置环境

不通架构运行可能出现  不能运行的问题
```
-ash: ./alidns: cannot execute binary file: Exec format error
```
这种情况要根据当前运行环境决定修改 go env参数

`GOARCH`& `GOOS`
```shell
go env -w GOOS= linux 
# 这里GOARCH 分为  amd64  arm64  根据个人环境决定
go env -w GOARCH=amd64
go env -w GOARCh=arm64
```

