### pip3 安装 uwsgi遇到异常：  

> **Exception: you need a C compiler to build uWSGI**


**解决办法**：  
```
yum install gcc
```

### 安装完c解释器后没有 又提示没找到python文件

> plugins/python/uwsgi_python.h:2:10: fatal error: Python.h: No such file or directory

**解决办法**：

> 安装`python3-dev`,正常这么安装 提示找不到,先搜索

```shell
yum search python3 dev
```

![uwsgi1](/res/python/uwsgi_1.png)

> 因为当前版本是`python3.6`, 所以最终找到`python36-devel` 并安装

```Shell
yum install python36-devel
```
![uwsgi2](/res/python/uwsgi_2.png)
