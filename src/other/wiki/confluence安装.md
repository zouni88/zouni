## confluence 学习版安装教程
### 环境要求
docker-compose: 17.09.0+
### 使用 docker-compose 启动
* start confluence & mysql
```shell
git clone https://github.com/haxqer/confluence.git \
&& cd confluence \
&& docker-compose up
```
* 以守护进程的方式启动 confluence & mysql
```shell 
docker-compose up -d
```
* 默认的 数据库(mysql8.0) 配置:
```shell
    driver=mysql
    host=mysql-confluence
    port=3306
    db=confluence
    user=root
    passwd=123456
```

### 使用 docker 启动
* 启动 confluence
```shell
docker volume create confluence_home_data && docker network create confluence-network && docker run -p 8090:8090 -v confluence_home_data:/var/confluence --network confluence-network --name confluence-srv -e TZ='Asia/Shanghai' haxqer/confluence:9.2.1
```
* 然后配置你的数据库:
### 破解 confluence
```shell
docker exec confluence-srv java -jar /var/agent/atlassian-agent.jar \
    -d \
    -p conf \
    -m Hello@world.com \
    -n Hello@world.com \
    -o your-org \
    -s you-server-id-xxxx
```

### 破解 confluence 的插件
* 例如: 你想要破解 BigGantt 插件
1. 从 confluence marketplace 中安装 BigGantt 插件
2. 查看 BigGantt 的 App Key 是 : eu.softwareplant.biggantt
3. 然后执行 :
```shell
docker exec confluence-srv java -jar /var/agent/atlassian-agent.jar \
    -d \
    -p eu.softwareplant.biggantt \
    -m Hello@world.com \
    -n Hello@world.com \
    -o your-org \
    -s you-server-id-xxxx
```
4. 最后粘贴生成的 licence
### How to upgrade
```shell
cd confluence && git pull
docker pull haxqer/confluence:latest && docker-compose stop
docker-compose rm
```
enter y, then start server

    docker-compose up -d
    
参考：https://github.com/haxqer/confluence/blob/master/README_zh.md