### 修改源的两种方式
1. 临时修改 `-i` 指定源 安装指定的 model  
`-U` : 升级到最新版本  
`-i` : 指定下载库源  
```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -U funcat
```

2. 永久修改

```
pip install pip -U
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/

```

### 源


name | source |
-|-|
清华|https://pypi.tuna.tsinghua.edu.cn/simple
阿里| https://mirrors.aliyun.com/pypi/simple/
