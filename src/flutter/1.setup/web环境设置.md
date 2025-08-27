 flutter 2.0 已经正式支持了web，不需要用下面方式单独启用web开发支持
 --------------
### flutter web 开发
1. 开启`web`支持 (正式版默认启用)

    > flutter config --enable-web

2. 再次 执行环境检查
    > flutter doctor

3. 一切正常之后,正常创建项目，会多出一个`web`文件夹  

    以前旧的项目可以执行以下命令：
    > flutter create .

4. 运行在浏览器看下效果：
    >flutter run -d edge

    我这里用的 microsoft edge 浏览器
5. 打包
    > flutter build web

    > flutter build web --release  //生产环境打包
    
    可以看到 `build` 目录下多出一个**web** 文件夹 

flutter web 常见问题 
======================  
**Finished with error: Failed to bind web development server:SocketException: Failed to create server socket (OS Error: Failed to start accept), address = localhost, port = 53041**

浏览器运行失败

解决方法：配置启动参数或者关闭ipv6网络属性
```shell
flutter run -d chrome --web-port=8080 --web-hostname=127.0.0.1
```
或者在android studio运行环境中配置:    
```shell
--web-port=8080 --web-hostname=127.0.0.1
```
vscode 配置启动参数：
```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "flutter_app",
            "request": "launch",
            "type": "dart",
            "args": [
                "--web-port=8080",
                "--web-hostname=127.0.0.1"
            ]
        }
    ]
}
```

