## 安装
### 1. 配置好环境变量：GOPATH GOROOT
GOROOT: GO安装目录  
GOPATH: 项目目录 src pkg bin目录
### 2. 安装go 开发工具集
`ctrl` + `shift` + `P` 打开命令面板，选择 `GO:Install/Update Tools`

## 调试
### go run test 不打印 详情
> go test -v # 正常命令应该是这样的，vscode 默认运行 不带-v
修改工作空间设置
```json
{
    "go.inferGopath": false,
    "go.testFlags": ["-v"],  //增加这一行
}
```
再运行就正常了。

