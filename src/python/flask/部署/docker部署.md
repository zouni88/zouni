 docker run -itd --name=nginx -p 80:80 -d -v /usr/local/small/nginx/nginx.conf:/etc/nginx/nginx.conf:ro -v /usr/local/small/nginx/conf.d:/etc/nginx/conf.d -v /usr/local/small/web/:/root/web/ -d nginx
