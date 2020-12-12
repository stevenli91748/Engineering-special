* [方式一：重头到尾，一步一步安装配置docker](#重头到尾-一步一步安装配置docker)
* [方式二：安装docker后 重新配置阿里云镜像加速](#在命令行重新配置阿里云镜像加速)


# 重头到尾 一步一步安装配置docker

第一步  清除旧的dockers

       [root]#  yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-engine

第二步 在dockers安装前配置阿里云镜像倉库地址

      [root]# yum install -y yum-utils device-mapper-persistent-data lvm2

      [root]# yum-config-manager --add-repo https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
      
      or
      
      [root]# yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
      
      查看yum仓库中是否安装了docker-ce仓库
      
      [root]# cd /etc/yum.repos.d/
      [root@localhost /etc/yum.repos.d/]# ll
      
        ........
        docker-ce.repo
      
       查看选择docker-ce各版本
       [root@localhost /etc/yum.repos.d/]# yum list docker-ce --showduplicates|sort –r
       
      docker-ce.x86...................3.19.03 .................
       
      
      
      
      
      
      
      

第三步 安装docker

      [root]# yum install docker-ce-18.09.0 docker-ce-cli-18.09.0 containerd.io

第四步 启动docker
     
     [root]# systemctl enable docker
     
     [root]# systemctl start docker

第五步 验证下是否安装成功

     [root]# docker -v
     Docker version 19.0.3, builded 546978


当在docker中下载images非常慢时，可配置阿里云镜像加速

    1. mkdir -p /etc/docker
    2. vim /etc/docker/daemon.json
    3. 设置阿里云镜像加速
        {
         "registry-mirrors":["https://72idtxd8.mirror.aliyuncs.com"]
        }
    4. sudo systemctl daemon-reload
    5. sudo systemctl restart docker
    
# 在命令行重新配置阿里云镜像加速

    
   [root]# cp -n /lib/systemd/system/docker.service /etc/systemd/system/docker.service
   
   [root]# sed -i "s|ExecStart=/usr/bin/docker daemon|ExecStart=/usr/bin/docker daemon --registry-mirror=https://pee6w651.mirror.aliyuncs.com|g" /etc/systemd/system/docker.service
   
   [root]# systemctl daemon-reload
   
   [root]# service docker restart



* [docker office install  document](https://docs.docker.com/install/linux/docker-ce/centos/)
