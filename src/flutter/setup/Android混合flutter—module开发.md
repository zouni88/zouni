# 新建flutter module

## 1. module 的 `settings.gradle` ：
```
// Generated file. Do not edit.
include ':app'
//复制下面内容到主项目的 settings.gradle 中
rootProject.name = 'android_generated'
setBinding(new Binding([gradle: this]))
//这里模块名称修改成自己的，参考下图
evaluate(new File(settingsDir, 'include_flutter.groovy'))
```
效果：
![settings](/res/flutter/flutter_2.png)

## 2. 引入依赖 在工程app/build.gradle 中：
```
dependencies {
  implementation project(':flutter')
}
```
## 3. 编译运行：失败
### Caused by: org.gradle.api.internal.plugins.PluginApplicationException: Failed to apply plugin class 'FlutterPlugin'.  
这是一个非常不明所以的问题：android 集成flutter module时，按照官网说明完毕必会出现  

病根：参照下面`settings.gradle`文件
```groovy
pluginManagement {
    repositories {
        gradlePluginPortal()
        google()
        mavenCentral()
    }
}
dependencyResolutionManagement {
    // 1. 这里改动 替换成了下面一行
//    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositoriesMode.set(RepositoriesMode.PREFER_PROJECT)
    repositories {
        google()
        mavenCentral()
//        jcenter() // Warning: this repository is going to shut down soon
    // 2. 增加下面4行
        maven { url 'https://maven.aliyun.com/repository/public' }
        maven { url 'https://maven.aliyun.com/repository/public' }
        maven { url 'https://maven.aliyun.com/repository/google' }
        maven { url 'https://maven.aliyun.com/repository/gradle-plugin' }
    }
}
rootProject.name = "Flutter_Android"
include ':app'


setBinding(new Binding([gradle: this]))
evaluate(new File(settingsDir.parentFile, 'flutter_module2/.android/include_flutter.groovy'))

```
## 4. 重新编译运行，成功



