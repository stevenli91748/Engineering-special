0751-8292551  13680097002
在dockers安装前配置阿里云镜像倉库地址

    yum-config-manager --add -repo https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

配置镜像加速

    1. mkdir -p /etc/docker
    2. vim /etc/docker/daemon.json
    3. 设置网易163镜像加速
        {
         "registry-mirrors":["http://hub-mirror.c.163.com"]
        }
    4. sudo systemctl daemon-reload
    5. sudo systemctl restart docker
    
* [docker office install  document](https://docs.docker.com/install/linux/docker-ce/centos/)
