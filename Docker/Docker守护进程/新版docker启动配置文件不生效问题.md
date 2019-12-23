问题

新版的docker，没有默认配置文件/etc/default/docker或有但直接在/etc/default/docker中修改启动项，然后输入 
   
   [root]# vi /etc/default/docker
   
   添加
   
   DOCKER_OPTS="--label name=docker_server_1"
   
   [root]# systemctl daemon-reload
   
   [root]# systemctl restart docker
   
   [root]# docker info
   
   label 为空
   
   在默认的配置文件中修改的项不生效
  
 解决的方法 
 
 1.  [root]# vi /etc/default/docker
   
     添加
   
     DOCKER_OPTS="--label name=docker_server_1"   
     
 2. 打开docker.service文件， 
 
    * [root]# vim /lib/systemd/system/docker.service    
    
      在[Service]添加一行
     
     EnvironmentFile=-/etc/default/docker   (-表示忽略错误)
      
      然后在
     
     ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock 的后面加上 $DOCKER_OPTS
      
      [root]# systemctl daemon-reload
     
      [root]# systemctl restart docker
      
  3   检验是否有效
  
      [root]# docker info
      
      label 
        name=docker_server_1
      
      在/etc/default/docker 文件上设置的项有效了
      
      
    
