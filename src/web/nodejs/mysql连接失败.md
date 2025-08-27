数据库连接失败
```
Error: ER_NOT_SUPPORTED_AUTH_MODE: Client does not support authentication protocol requested by server; consider upgrading MySQL client
    at Handshake.Sequence._packetToError (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\protocol\sequences\Sequence.js:47:14)
    at Handshake.ErrorPacket (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\protocol\sequences\Handshake.js:123:18)
    at Protocol._parsePacket (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\protocol\Protocol.js:291:23)
    at Parser._parsePacket (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\protocol\Parser.js:433:10)
    at Parser.write (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\protocol\Parser.js:43:10)
    at Protocol.write (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\protocol\Protocol.js:38:16)
    at Socket.<anonymous> (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\Connection.js:88:28)
    at Socket.<anonymous> (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\Connection.js:526:10)
    at Socket.emit (events.js:315:20)
    at addChunk (_stream_readable.js:302:12)
    --------------------
    at Protocol._enqueue (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\protocol\Protocol.js:144:48)
    at Protocol.handshake (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\protocol\Protocol.js:51:23)
    at Connection.connect (D:\WorkProject\DeepLearning\python_basic\node_modules\mysql\lib\Connection.js:116:18)
    at Object.<anonymous> (D:\WorkProject\DeepLearning\python_basic\catch\game\test.js:10:12)
    at Module._compile (internal/modules/cjs/loader.js:1200:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1220:10)
    at Module.load (internal/modules/cjs/loader.js:1049:32)
    at Function.Module._load (internal/modules/cjs/loader.js:937:14)
    at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12)
    at internal/main/run_main_module.js:17:47 {
  code: 'ER_NOT_SUPPORTED_AUTH_MODE',
  errno: 1251,
  sqlMessage: 'Client does not support authentication protocol requested by server; consider upgrading MySQL client',
  sqlState: '08004',
  fatal: true
}
```
解决办法：
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456';

flush privileges;
```
试了之后不好使！
