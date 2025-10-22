
### docker-compose
```yaml
version: '3.8'

services:
  verdaccio:
    image: verdaccio/verdaccio:latest  # 使用官方最新镜像
    container_name: verdaccio
    restart: always  # 容器退出时自动重启
    ports:
      - "4873:4873"  # 映射端口（主机端口:容器端口），外部通过 http://localhost:4873 访问
    volumes:
      - ./conf:/verdaccio/conf  # 挂载配置目录（核心配置）
      - ./storage:/verdaccio/storage  # 挂载存储目录（持久化 npm 包）
      - ./plugins:/verdaccio/plugins  # 挂载插件目录（可选）
    environment:
      - VERDACCIO_PORT=4873  # 容器内服务端口（需与容器内端口一致）
      - TZ=Asia/Shanghai  # 时区设置（避免日志时间偏差）
    networks:
      - verdaccio-network

networks:
  verdaccio-network:
    driver: bridge  # 桥接网络，简单易用
```
