
# 使用Docker Compose的步骤

        使用Dockerfile定义应用程序环境，一般需要修改初始镜像行为时才需要使用；

        使用docker-compose.yml定义需要部署的应用程序服务，以便执行脚本一次性部署；

        使用docker-compose up命令将所有应用服务一次性部署起来。

# Docker Compose将所管理的容器分为三层，工程、服务及容器。docker-compose.yml中定义所有服务组成了一个工程，services节点下即为服务，服务之下为容器。容器与容器直之间可以以服务名称为域名进行访问，比如在mall-tiny-docker-compose服务中可以通过jdbc:mysql://db:3306这个地址来访问db这个mysql服务。



# 目录

* [1. 安装Docker Compose](#1-安装Docker-Compose)
* [2. 卸载Docker Compose](#2-卸载Docker-Compose)
* [3. Docker Compose 命令](#3-Docker-Compose-命令)
* [4. docker compose 案例](#4-docker-compose-案例)
* [使用Docker Compose部署SpringBoot应用](https://mp.weixin.qq.com/s?__biz=MzU1Nzg4NjgyMw==&mid=2247483800&idx=1&sn=b9e0b6c006bad05e4055a3c0bb61c815&scene=21#wechat_redirect)

# 1 安装Docker Compose

首先安装Docker 在extend 虚拟机上，安装Docker见上一讲

[root]#>  curl -L "https://github.com/docker/compose/releases/download/1.25.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

对下载的文件添加可执行权限：

[root]> chmod +x /usr/local/bin/docker-compose

测试一下是否安装成功

[root]#> docker-compose --version

Docker-compose  version 1.25.0 , builded 458962



好了，如果想指定 docker-compose 的版本，先卸载：

[root]#> pip uninstall docker-compose

再安装指定版本：

[root]#> pip install docker-compose==1.5.2
至此，docker-compose 指定版本成功！

# 卸载Docker Compose

通过curl方式安装以下方式卸载
    
    sudo rm /usr/local/bin/docker-compose

pip方式安装以下方式卸载

    pip uninstall docker-compose


# 3 Docker Compose 命令

docker-compose 常用操作

通过docker-compose -h可以得到docker-compose的命令列表

            Define and run multi-container applications with Docker.

            Usage:
              docker-compose [-f <arg>...] [options] [COMMAND] [ARGS...]
              docker-compose -h|--help

            Options:
              -f, --file FILE             Specify an alternate compose file
                                          (default: docker-compose.yml)
              -p, --project-name NAME     Specify an alternate project name
                                          (default: directory name)
              --verbose                   Show more output
              --log-level LEVEL           Set log level (DEBUG, INFO, WARNING, ERROR, CRITICAL)
              --no-ansi                   Do not print ANSI control characters
              -v, --version               Print version and exit
              -H, --host HOST             Daemon socket to connect to

              --tls                       Use TLS; implied by --tlsverify
              --tlscacert CA_PATH         Trust certs signed only by this CA
              --tlscert CLIENT_CERT_PATH  Path to TLS certificate file
              --tlskey TLS_KEY_PATH       Path to TLS key file
              --tlsverify                 Use TLS and verify the remote
              --skip-hostname-check       Don't check the daemon's hostname against the
                                          name specified in the client certificate
              --project-directory PATH    Specify an alternate working directory
                                          (default: the path of the Compose file)
              --compatibility             If set, Compose will attempt to convert keys
                                          in v3 files to their non-Swarm equivalent
              --env-file PATH             Specify an alternate environment file

            Commands:
              build              Build or rebuild services
              config             Validate and view the Compose file
              create             Create services
              down               Stop and remove containers, networks, images, and volumes
              events             Receive real time events from containers
              exec               Execute a command in a running container
              help               Get help on a command
              images             List images
              kill               Kill containers
              logs               View output from containers
              pause              Pause services
              port               Print the public port for a port binding
              ps                 List containers
              pull               Pull service images
              push               Push service images
              restart            Restart services
              rm                 Remove stopped containers
              run                Run a one-off command
              scale              Set number of containers for a service
              start              Start services
              stop               Stop services
              top                Display the running processes
              unpause            Unpause services
              up                 Create and start containers
              version            Show the Docker-Compose version information


(1)查看版本
   
        docker-compose version

(2)根据yml创建service

        根据当前docker-compose.yml 创建​docker-compose up .
        ​指定yaml：docker-compose up -f xxx.yaml
        后台运行：docker-compose up -d

(3)查看启动成功的service

        docker-compose psdocker ps

(4)查看images

        docker-compose images

(5)停止/启动service

        docker-compose stop/start

(6)删除service[同时会删除掉network和volume]

        docker-compose down

(7)进入到某个service

        docker-compose exec redis sh


# 4 docker compose 案例

* [官网案例：通过redis记录点击数 ](https://docs.docker.com/compose/gettingstarted/)
* [docker compose 案例](https://www.kancloud.cn/pm1028/kubenetes/1767448)
