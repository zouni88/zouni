
### 下载官方nginx 包
> wget http://nginx.org/download/nginx-1.10.1.tar.gz

### 配置nginx
#--prefix 指定安装的目录
#/usr/local/nginx 是安装目录，不能和自己下载的文件目录重了
#./configure --prefix=/usr/local/nginx

#带ssl  stub_status模块 添加strem模块 –with-stream，这样就能传输tcp协议了
#http_stub_status_module  状态监控
#http_ssl_module    配置https
#stream  配置tcp得转发
#http_gzip_static_module 压缩
#http_sub_module  替换请求

./configure --prefix=/usr/local/nginx --with-http_stub_status_module --with-http_ssl_module --with-stream

#带用户得方式
./configure --user=www --group=www --prefix=/usr/local/nginx --with-http_stub_status_module --with-http_ssl_module --with-stream --with-http_gzip_static_module --with-http_sub_module

---------

### 编译 安装
> make && make install
