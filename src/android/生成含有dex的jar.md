### 1. android studio 生成jar包
```groovy
task makeJar(type: Copy) {
    delete 'build/libs/mylibrary.jar' //删除已经存在的jar包
    from('build/intermediates/compile_library_classes_jar/
    debug/') //从该目录下加载要打包的文件,这里实际上是编译后的classes.jar文件的目录
    into('build/libs/')//jar包的保存目录
    include('classes.jar')//设置过滤，只打包classes文件
    rename('classes.jar', 'dynamic_temp.jar')//重命名，mylibrary.jar 根据自己的需求设置
}
makeJar.dependsOn(build)
```
### 1. 找到android sdk ，以下路径配置到环境变量，目的是为了使用 dx 命令  
`D:\WorkRome\android\Sdk\build-tools\30.0.3`

### 2.  一键生成 jar
- --output 最终输出jar包  
- temp.jar 目标jar  
` dx --dex --output=object.jar temp.jar ` 

