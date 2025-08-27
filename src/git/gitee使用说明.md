# 第一次使用git，没有环境？

### 1. 先安装git

### 2. 生成公钥，用来添加到远程仓库

  1. 生成公钥
```shell
# 生成公钥，然后一路回车
ssh-keygen -t rsa -C "cao_cgq@163.com"
```

  2. 查看公钥
![查看公钥](/res/git/git_6.png)

### 3. 复制公钥，打开码云-> 个人头像点设置->找到安全设置->SSH公钥

![查看公钥](/res/git/git_7.png)

添加完公钥之后，就可以接下来的步骤了

### 怎么样将代码提交到远程仓库

### 1. 在码云新建仓库，beego_first

![新建仓库](/res/git/git_3.png)

### 2. 本地项目路径下初始化仓库

``` shell
git init
```

![初始化](/res/git/git_2.png)

### 3. 本地项目添加远程仓库

```shell
# git remote add origin 仓库地址
git remote add origin git@gitee.com:SmallMrCao/beego_first.git
```

![初始化](/res/git/git_4.png)

### 4. 添加完之后先pull，然后再add

```shell
git pull
git add *
```

出现这个问题，说明在add之前没有pull，需要执行以下命令，把无关的内容pull下来

![没有关联](/res/git/git_5.png)

```shell
git pull origin master --allow-unrelated-histories
```

### 5. 最后执行提交就完成了

```shell
git push
```
