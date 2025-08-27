socket.io 配置到外网 服务器后，就会出现如下问题

    Error during WebSocket handshake: Unexpected response code: 400

，根据github的讨论，得到如下答案
```
proxy_http_version 1.1;
proxy_set_header Upgrade $http_upgrade;
proxy_set_header Connection "upgrade";
proxy_set_header Host $host;
```
其中第一行是告诉nginx使用HTTP/1.1通信协议，这是websoket必须要使用的协议。
第二行和第三行告诉nginx，当它想要使用WebSocket时，响应http升级请求。
