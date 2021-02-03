
# 目录

* [1. 安装Docker Compose](#1-安装Docker-Compose)
* [2. 卸载Docker Compose](#2-卸载Docker-Compose)
* [3. Docker Compose 命令](#3-Docker-Compose-命令)

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
