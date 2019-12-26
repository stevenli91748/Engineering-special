# 修改docker的守护进程docker0的IP地址

  问题：

     docker 的守护进程默认的IP地址范围是

     172.17.0.0---172.17.255.255

     [root]# ip addr show

     ens33 172.17.0.1

     改变docker0 的IP地址 从172.17.0.1 到 192.168.28.166

     [root]# ifconfig docker0 192.168.28.166 netmask 255.255.255.0

     [root]# ip addr show

     ens33 192.168.28.166

     [root]# docker run -it --name mycentos centos

     进入到容器内去查看mycentos的IP地址

     [root@893652890] ip addr show
      eth17   172.17.0.3
 
     容器不能生成跟docker0同一网段的IP地址

     但是如果重启docker, docker0又重新恢复到以前的默任IP 172.17.0.1


解决办法

     [root]#  vi /etc/docker/daemon.json
  
         {
   
           "bip"：“192.168.28.100/24”
  
         }
  
        如果单一项，后面不要有斗号，否则docker 不能启动
  
    [root]# systemctl daemon-reload
    [root]# systemctl restart docker
    [root]# ip addr show
    ens33 192.168.28.100
    
    创建一个centos新容器
    [root]# docker run -it --name mycentos-1 centos
    
    进入到容器内去查看容器mycentos-1的IP地址
    [root@9484574950]# ip addr show
    eth18   192.168.28.3
    
    容器生成跟docker0同一网段的IP地址



# 有用的参考

* [修改docker0默认IP的正确姿势](https://blog.csdn.net/oliverlyn/article/details/96437364)
* [如何修改Docker0的IP地址](https://blog.csdn.net/gaopan20080808/article/details/77431880)
