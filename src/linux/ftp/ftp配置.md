1.查看是否安装ftp服务   

rpm -q vsftpd   

2.安装ftp服务  

yum install vsftpd

3.开机启动

 chkconfig vsftpd on

4.启动服务

 service vsftpd start   

5.重新启动vsftpd    

service vsftpd restart  

来自 <https://www.cnblogs.com/surge/p/3868270.html> 


修改相关配置项在 /etc/vsftpd/vsftpd.conf中
