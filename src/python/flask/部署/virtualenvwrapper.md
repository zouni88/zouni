### 安装虚拟环境  

安装虚拟环境
```Shell
pip2 install virtualenvwrapper
# **查找安装路径**   
which virtualenvwrapper.sh
```
![virtual](/res/python/bushu_1.png)

编辑`.bashrc`
```Shell
vim ~/.bashrc
# 增加以下环境变量
export WORKON_HOME=$HOME/.virtualenvs  
source /usr/local/bin/virtualenvwrapper.sh

```

立即生效

```Shell
source .bashrc
```
查找python3路径
```Shell
which python3
```
![python3](/res/python/bushu_2.png)

创建虚拟环境
```Shell
mkvirtualenv --python=/usr/bin/python3 name-env

workon name-env
```

切换/激活 虚拟环境
```Shell
workon name-evn

cd ~/.virtualenvs/name-env/bin/
```
退出虚拟环境
```Shell
deactivate name-env
```

删除虚拟环境
```shell
rmvirtualenv env-name
```
