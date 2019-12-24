


# docker0虚拟网桥的用法

      docker0设备是网桥，处在数据链路层

     docker的守护进程就是通过docker0设备为docker容器提供网络联接的,docker0实际上就是 Linux的虚拟网桥
     docker的守护进程在容器启动时，实际上要创建网络链接的两端，一端是在容器中的网络设备，而另一端是在运行docker守护进程的主机上
     名为veth*。用以实现docker0这个网桥与容器的通信。
     
     查看docker0 设备的信息
      
      [root]# ip addr show
     
     docker0  172.135.25.65------信息
     
     查看网桥的信息
     
     安装网桥工具
      [root]# yum install bridge-utils
      [root]# brctl show
      
      docker0  172.135.25.65------信息
      
      假如要把docker0 的IP地址172.135.25.65修改为我们惯用的IP地址网段192.168.200.1
      
      [root]# ifconfig docker0 192.168.200.1 netmask 255.255.255.0
      [root]# ip addr show
      
      docker0  192.168.200.1------信息
      
      [root]# systemctl restart docker
      
      
   #   自定义虚拟网桥
   
          添加自定义的虚拟网桥
          
          [root]# brctl addbr br0
          [root]# ifconfig br0 192.168.100.1 netmask 255.255.255.0
          
          更改docker守护进程的启动配置
          /etc/default/docker中添加DOCKER_OPTS= “  -b=br0 ”
          
          [root]# systemctl start docker
          [root]# pd -ef|grep docker
          -----------------/usr/bin/docker -d -b=br0
