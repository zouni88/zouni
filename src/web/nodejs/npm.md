### 查看版本
> npm -v

### 更新
> npm install -g npm

### 指定版本更新
> npm -g install npm@6.8.0

### 清理
> npm cache clean --force

### 查看当前使用的源
> npm config get registry
### 重置为官方源
> npm config set registry https://registry.npmjs.org/q


### 修改国内源
```
# 阿里源升级
http://npm.taobao.org => http://npmmirror.com
http://registry.npm.taobao.org => http://registry.npmmirror.com
```
#### 1. 临时修改源
> npm --registry http://registry.npmmirror.com install express
#### 2. 永久修改
> npm config set registry http://registry.npmmirror.com


### 使用国内镜像，可以使用 cnpm 命令行,npm的定制版
> npm install -g cnpm --registry=https://registry.npmmirror.com
