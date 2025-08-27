### WSL 默认是不开启systemctl命令的,开启方法：
1. 安装daemonize

    sudo apt-get install daemonize

2. 执行以下命令：

    sudo daemonize /usr/bin/unshare --fork --pid --mount-proc /lib/systemd/systemd --system-unit=basic.target

    exec sudo nsenter -t $(pidof systemd) -a su - $LOGNAME