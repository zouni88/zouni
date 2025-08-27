### 生成配置文件
```Shell
jupyter notebook --generate-config
```
### 生成密钥
```Shell
jupyter notebook password
# 设置密码：123456

```

### 如下地址
```Shell
/root/.jupyter/jupyter_notebook_config.json
# 生成密钥如下：
sha1:23524a335a85:461a1f37e8e32af1ab8899329b3e41c41ea6e546
```

![jupyter](/res/conda/jupyter_1.png)

### 修改配置文件
```
vi /root/.jupyter/jupyter_notebook_config.py
```

修改如下内容：

```Shell
# 允许 作为root访问
c.NotebookApp.allow_root = True
# 允许访问的主机ip  * 随意访问
c.NotebookApp.ip='*'   
# 密钥：/root/.jupyter/jupyter_notebook_config.json 文件的内容
c.NotebookApp.password = u'sha1:03...  '
# 修改工作目录
c.NotebookApp.notebook_dir='filepath'
```

修改完之后，重新启动`jupyter notebook`，浏览器打开`127.0.0.1:8888`输入刚开始设置的密码就正常登录了
