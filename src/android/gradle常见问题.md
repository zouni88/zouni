# 新版本 build.gralde
```groovy
plugins {
    id "org.springframework.boot" version "2.2.2.RELEASE"
}
```
旧版本
```groovy
//Using legacy plugin application
buildscript {
  repositories {
    maven {
      url "https://plugins.gradle.org/m2/"
    }
  }
  dependencies {
    classpath "org.springframework.boot:spring-boot-gradle-plugin:2.2.2.RELEASE"
  }
}

apply plugin: "org.springframework.boot"
```

# android studio 运行 main 方法 报错
```
SourceSet with name ‘main‘ not found
```
解决：./idea/gradle.xml -> <GradleProjectSettings> 节点下 加入下面这句

```
<option name="delegatedBuild" value="false" />
```
    