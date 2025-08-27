群晖nas配置 ssh连接，root用户登录

群晖默认不支持root权限登录，需要修改权限

1. 普通管理员用户登录之后，找到 `/etc/ssh/sshd_config`文件
2. 修改sshd_config 权限  
    ```
    chmod 755 sshd_config 
    ```
2. 编辑`sshd_config`文件，找到

    ```
    #PermitRootLogin prohibit-password  
    # 修改成 yes
    PermitRootLogin yes
    ```
    退出编辑
4. 修改root密码
    ```
    synouser --setpw root 这里是新密码
    ```
5. 退出重新用root登录 . OK!

