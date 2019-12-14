
第一步  清除旧的dockers

       [root]# sudo yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine

第二步 在dockers安装前配置阿里云镜像倉库地址

      [root]# yum install -y yum-utils device-mapper-persistent-data lvm2

      [root]# yum-config-manager --add-repo https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

第三步 安装docker

      [root]# yum install docker-ce docker-ce-cli containerd.io

第四步 启动docker

     [root]# systemctl start docker


配置镜像加速

    1. mkdir -p /etc/docker
    2. vim /etc/docker/daemon.json
    3. 设置阿里云镜像加速
        {
         "registry-mirrors":["https://72idtxd8.mirror.aliyuncs.com"]
        }
    4. sudo systemctl daemon-reload
    5. sudo systemctl restart docker
    




* [docker office install  document](https://docs.docker.com/install/linux/docker-ce/centos/)
