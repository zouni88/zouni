### supervisor是进程守护服务
安装supervisor有以下操作

supervisor必须用python2
```Shell
pip2 install supervisor
```
创建supervisor.conf 配置文件

```Shell
# supervisor的程序名字
[program:项目名字]
# supervisor执行的命令
command=uwsgi --ini uwsgi.ini
# 项目的目录
directory = /项目路径
# 开始的时候等待多少秒
startsecs=0
# 停止的时候等待多少秒
stopwaitsecs=0  
# 自动开始
autostart=true
# 程序挂了后自动重启
autorestart=true
# 输出的log文件
stdout_logfile=/var/log/supervisord.log
# 输出的错误文件
stderr_logfile=/var/log/supervisord.err

[supervisord]
# log的级别
loglevel=debug

[inet_http_server]
# supervisor的服务器
port = :9001
# 用户名和密码
username = admin
password = 123

# 使用supervisorctl的配置
[supervisorctl]
# 使用supervisorctl登录的地址和端口号
serverurl = http://127.0.0.1:9001

# 登录supervisorctl的用户名和密码
username = admin
password = 123

[rpcinterface:supervisor]
supervisor.rpcinterface_factory = supervisor.rpcinterface:make_main_rpcinterface

```

#### supervisor命令操作

启动supervisor
```Shell
supervisord -c filename
```
重启supervisor
```Shell
supervisorctl -u admin -p 123 reload
or
ps -aux | grep supervisor
找到进程
kill -9 [supervisor pid]
```

进入supervisor控制台
```Shell
supervisorctl -c filename
```

查看当前运行状态

```Shell
status    
```
关闭在运行的程序  

``` Shell
stop
```
重启应用
```Shell
reload
```
