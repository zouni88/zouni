查看ftp默认用户主目录在哪里
Yum install finger

 finger ftp
 [root@OX39Ø6c finger ftp
 Login: ftp
 Directory: / var/ftp
 Never logged in.
 No mail.
 No Plan.
 Name:
 FTP User
 Shell:
 /sbin/nologin /

 修改默认目录
vim /etc/passwd


[root@OX39Ø6c vim /etc/passwd
ftp:x:14:50: FTP


修改/var/ftp 为想要修改的目录路径
然后重启vsftpd服务 service vsftpd restart

如果修改之后仍不能用，需要关闭  SELinux
1. 修改/etc/selinux/config文件中的SELINUX="" 为 disabled ，然后重启。
2. 如果不想重启系统，使用命令setenforce 0
