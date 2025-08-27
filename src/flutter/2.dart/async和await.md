dart异步：
dart是单线程模型，任何耗时操作都会阻塞；通过返回一个Future来接收耗时任务返回结果：future.then();
```dart
import 'dart:io';

void main(List<String> args) {
  print("main方法开始执行");
  Future fu = testAsync("");
  fu.then(
    (value) => print("执行结果：${value}"),
  );
  //sleep(Duration(seconds: 2));
  print('main方法结束');
}

Future testAsync(args) async {
  print("开始执行异步方法");
  return Future(requestHttp);
  // print("异步任务结束");
}

String requestHttp() {
  sleep(Duration(seconds: 2));
  print("请求http结束");
  return "success";
}

```