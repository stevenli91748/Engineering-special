1. 设置环境

      1.1 要配置两台虚拟机，第一台为客户端，第二台要配置docker服务器
      
      1.2  修改docker守护进程启动选项，添加label选项，区别服务器
      
      1.3  保证clinet API 和 Server API版本一致

2. 设置两台服务器的server label，docker_server_1 和docker_server_2以示区别 

       分别在两台服务器上操作
       2.1.  [root]# vi /etc/default/docker
             添加
             DOCKER_OPTS="--label name=docker_server_1"   
     
       2.2. 打开docker.service文件， 
            [root]# vim /lib/systemd/system/docker.service    
            在[Service]添加一行
            EnvironmentFile=-/etc/default/docker   (-表示忽略错误)
            然后在
            ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock 的后面加上 $DOCKER_OPTS
            [root]# systemctl daemon-reload
            [root]# systemctl restart docker

 3.  修改docker守护进程启动选项   
       
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
              
              
              
              
              
