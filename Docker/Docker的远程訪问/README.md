1. 设置环境

      1.1 要配置两台虚拟机，第一台为客户端，第二台要配置docker服务器
      
      1.2  修改docker守护进程启动选项，添加label选项，区别服务器
      
      1.3  保证clinet API 和 Server API版本一致

2. 设置两台服务器的server label，docker_server_1 和docker_server_2以示区别 

       分别在两台服务器上操作
       
       2.1.  [root]# vi /etc/default/docker
             添加
             DOCKER_OPTS="--label name=docker_server_1"   
             or 
             DOCKER_OPTS="--label name=docker_server_2"   
             
       2.2. 打开docker.service文件， 
            [root]# vim /lib/systemd/system/docker.service    
            在[Service]添加一行
            EnvironmentFile=-/etc/default/docker   (-表示忽略错误)
            然后在
            ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock 的后面加上 $DOCKER_OPTS
            [root]# systemctl daemon-reload
            [root]# systemctl restart docker

 3.  修改服务端docker守护进程启动选项   
       
       3.1 docker守护进程Socket的修改
       
              socket的三种协议
          
              -H   tcp://host:port
                   unix:///path/to/socket
                   fd://socketfd
                   
              docker守护进程socket的默认配置
                  -H unix:///var/run/docker.sock

              设置docker_server_1的sock 协议
              [root]# vi /etc/default/docker
              
              添加
              DOCKER_OPTS="--label name=docker_server_1 -H tcp://0.0.0.0:2375"     
              
              0.0.0.0 的地址表示用自身的IP 来绑定
              
              重新启动docker
              
              [root]# systemctl restart docker
              
              然后用ps 查看
              
              [root]# ps -ef|grep docker
              
              得到服务端 docker_server_1 的IP地址
              [root]# ip addr show
              ens33  192.168.28.128
                      
   4.  用另一台虚拟机docker_server_2来訪问服务器端docker_server_1      
   
        在docker_server_2机上
         
        方式一
        
           [root]# docker -H tcp://192.168.28.128:2375 info
           
           显示docker_server_1的信息
           
           or
        
       方式二
       
          [root]#  curl http://192.168.28.128:2375/info
            
           显示docker_server_1的信息

       方式三    
         
        也可设置环境变量来设置，就不用每次手动在命令行输入 
        
        [root]# docker -H tcp://192.168.28.128:2375 info    //查看docker_server_1 的信息
        
        [root]# docker -H tcp://192.168.28.128:2375 images  //查看docker_server_1 境像
        
        使用环境变量DOCKER_HOST后，就好象在docker_server_1上使用docker命令一样
        
        [root]# export DOCKER_HOST="tcp://192.168.28.128:2375"
        
        [root]# docker info        //查看docker_server_1 的信息
        
        [root]# docker images      //查看docker_server_1 境像

        
         显示docker_server_1的信息      
              
         当使用完远程服务器时，把 DOCKER_HOST="" 置空，那就重设为本地机器
         
         [root]# export DOCKER_HOST=""
        
         [root]# docker info
         
         显示docker_server_2 的信息 ,也就是本机信息
         
5.  回到docker_server_1 机上

    [root]# docker info
    
         err: cannot connect to the docker daemon  is "docker -d" runing on the this host?
         当我们在docker_server_1的客户端输入命令时出错，表示当前的守护进程不支持当前客户端和服务端的链接方式，已将当前的链接改为
         tcp://ip:port
         
         解决方法
         
          [root]# vi /etc/default/docker
       
         
          在DOCKER_OPTS选项上添加  -H unix:///var/run/docker.sock
         
          -H 是能添加多个选项的
         
          DOCKER_OPTS="--label name=docker_server_1 -H tcp://0.0.0.0:2375"   -H unix:///var/run/docker.sock
         
          [root]# systemctl restart docker
          
          [root]# docker info
          
          显示本地 docker_server_1 的信息 
