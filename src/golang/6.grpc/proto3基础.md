### 1. 定义proto文件  

```
//声明protobuf版本
syntax = "proto3";
```
**自动生成pb的时候，会提示要有go_package**
```
option go_package='.;grpc';
```
* `.`:     表示生成pb文件在哪个位置  
* `;grpc`: 表示生成的pb文件所属包名

```
package grpc;

service Greeter{
  rpc SayHello (HelloRequest) returns(HelloReply){}
}

message HelloRequest{
  string name = 1;
}

message HelloReply{
  string message = 1;
}

```
### 2. 生成pb文件
```
//go:generate protoc -I . --go_out=plugins=grpc:./ ./helloworld.proto

```
