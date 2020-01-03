
# 数据在容器内的存储原则

    不要在容器中保存业务数据，要把这业务数据保存在宿主机里，使用的技术就是目录映射，可一把宿主机的目录映射到容器内，在运行容器的时，把业务数据
    保存到这映射目录内，存储到宿主机上，如果容器出现故障，只要重启容器就行了，然后再把该目录重新映射到新容器上，新容器就自带了这些数据，
    但是在MySQL集群中采用PXC架构是无法采用目录映射技术的，如果在PXC集群中采用目录映射技术，PXC容器会闪退，那就要采用另一种目录映射技术：
    docker 卷技术，采用docker 卷技术，把该目录映射到PXC容器上就可用来存储数据了

 # 容器中的PXC节点映射数据目录的解决方法
 
    创建数据卷
    [root]# docker volume create  --name v1
    
    查看数据卷,可看到创建到宿主机上的数据卷目录路径
    [root]# docker inspect v1
    
    {
    
      mountpoint : /var/lib/docker/volumes/v1/data
    }
    
    [root]# docker pull  docker.io/percona/percona-xtradb-cluster
    
    境像名太长，修改境像名
   
    [root]# docker tag  docker.io/percona/percona-xtradb-cluster pxc
    
    
    创建网段给MySQL PXC网段的集群使用
    [root]# docker network create --subnet 172.18.0.0/26 net1
    
    创建一个PXC架构的mysql数据库容器带有docker数据卷，不能直接目录映射的
    [root]# docker run -d -p 3306:3306
                       -v v1:/var/lib/mysql
                       -e MYSQL_ROOT_PASSWORD=abc123456
                       -e CLUSTER_NAME=PXC
                       -e XTRABACKUP_PASSWORD=abc123456        // 数据库节点之间同步所用的密码
                       --privileged --name=mysql_node1 --net=net1 --ip 172.18.0.2 pxc
    
    
    
    删除数据卷
    
    [root]# docker volume rm v1
    
    



* [Bind Mount--filesystem](#Bind)
* [Volume--filesystem](#Volume)
* [Tmpfs mount---memory](#Tmpfs)
* [named pipes](#named-pipes)

# Bind

   may be stored anywhere on the host system. They may even be important system files or directories. Non-Docker processes on the Docker 
   host or a Docker container can modify them at any time
   
   The docker provides DNS resolution to container by mounting /etc/resolv.conf from the host machine into each container

# Volume

   Volumes are stored in a part of the host filesystem which is managed by Docker (/var/lib/docker/volumes/<volume-name> on Linux)

# Tmpfs

   mounts are stored in the host system’s memory only, and are never written to the host system’s filesystem.
   
# named pipes
