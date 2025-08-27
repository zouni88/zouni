### 编译配套 ssl的 uwsgi

#### 安装编译需要的环境
```
yum install openssl
yum install openssl-devel
```
#### 安装 greenlet
```
pip3 install greenlet
```
### 找到 greenlet 位置
```
/root/.virtualenvs/flask/include/site/python3.6
```
### 安装
```
CFLAGS="-I/root/.virtualenvs/flask/include/site/python3.6" UWSGI_PROFILE="asyncio" pip install uwsgi --no-use-wheel
```
or
```
CFLAGS="-I/usr/include/openssl" UWSGI_PROFILE_OVERRIDE=ssl=true pip install uwsgi -I --no-cache-dir
```



CFLAGS="-I$/usr/bin/python3.6" UWSGI_PROFILE="asyncio" pip3 install uwsgi --no-use-wheel

CFLAGS="-I/usr/local/opt/openssl/include" LDFLAGS="-L/usr/local/opt/openssl/lib" UWSGI_PROFILE_OVERRIDE=ssl=true pip install uwsgi -I --no-cache-dir

CFLAGS="-I/usr/include/openssl" UWSGI_PROFILE_OVERRIDE=ssl=true pip install uwsgi -I --no-cache-dir

sudo CFLAGS="-I/usr/local/opt/openssl/include" LDFLAGS="-L/usr/local/opt/openssl/lib" UWSGI_PROFILE_OVERRIDE=ssl=true pip3 install uwsgi -I --no-cache-dir

