
首先安装Docker 在extend 虚拟机上，安装Docker见上一讲

[root]>  curl -L "https://github.com/docker/compose/releases/download/1.25.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

对下载的文件添加可执行权限：

[root]> chmod +x /usr/local/bin/docker-compose

测试一下是否安装成功

[root]> docker-compose --version

Docker-compose  version 1.25.0 , builded 458962



好了，如果想指定 docker-compose 的版本，先卸载：

# pip uninstall docker-compose

再安装指定版本：

# pip install docker-compose==1.5.2
至此，docker-compose 指定版本成功！


