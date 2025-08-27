### pip 安装软件  
`-U` : 升级到最新版本  
`-i` : 指定下载库源  
```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -U funcat
```

### pip 更新失败
```
pip install --upgrade pip
```
更新失败
![pip更新](/res/python/pip_update.png)

解决办法：
重新下载安装
```
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py

```

强制安装：
```
python get-pip.py --force-reinstall
```
