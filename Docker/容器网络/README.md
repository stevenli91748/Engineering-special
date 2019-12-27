
* [第一部分  DOCKER容器的网络基础](#DOCKER容器的网络基础)
* [第二部分  DOCKER容器的互联](#DOCKER容器的互联)
* [第三部分  DOCKER容器与外部网络的连接](#DOCKER容器与外部网络的连接)
* [第四部分  不同宿主机上容器跨网络的互连](#不同宿主机上容器跨网络的互连)


# DOCKER容器的网络基础
  
  [docker0网桥设备](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/容器网络/docker0设备.md)|
  ---|
  
  
# DOCKER容器的互联

* [1. 同一宿主机上不同容器的互连](#同一宿主机上不同容器的互连)
* [2. 不同宿主机上容器跨网络的互连](#不同宿主机上容器跨网络的互连)


# 同一宿主机上不同容器的互连
 
 [默认允许所有容器互联](#默认允许所有容器互联)|[拒绝容器间互联](#拒绝容器间互联)|[允许特定容器间的连接](#允许特定容器间的连接)|
 ---|---|---|


 容器的互联有三种方式
 
  # 默认允许所有容器互联
    
         在同一宿主机下，容器联接是通过网桥连接的，docker 提供了一个设置选项来打开允许所有容器互联
     
         docker 守护进程的启动选项
         --icc=true   默认
         
         [root]# vi /etc/default/docker
         添加 --icc=true 到 DOCKER_OPTS 设置为允许所有容器互联
         DOCKER_OPTS-"--icc=true"
         
         实操举例
          
         1.1  启动同一宿主机下的两容器
         
              [root]# docker run -it -p 80 --name firstcentos centos
              [root]# docker run -it -p 80 --name secondcentos centos
              
              在两台容器上都安装Nginx
              
              然后在第一个容器中启动Nginx服务
              
              [root@firstcentos]# nginx
              
              取的在第一个容器的IP地址
              [root@firstcentos]# ip addr show
              eth12  172.17.0.2
              
              在第二个容器中启动Nginx服务
              [root@secondcentos]# nginx
              [root@secondcentos]# ip addr show
              eth14 172.17.0.3
              
              ping 第一个容器的IP地址
              [root@secondcentos]# ping 172.17.0.2
              succeful
              
              訪问第一个容器的Nginx服务
              [root@secondcentos]# curl http://172.17.0.2
              nginx 信息
              
              两容器是联通的
    
  # 拒绝容器间互联
  
          docker 守护进程的启动选项
          --icc=false

          [root]# vi /etc/default/docker
          添加 --icc=false 到 DOCKER_OPTS 设置为拒绝所有容器互联
          DOCKER_OPTS-"--icc=false"
 
           [root]# systemctl restart docker
  
  # 允许特定容器间的连接
      
          需要三个配置
      
          --icc=false
      
          --iptables=true
      
          --link
      
          修改docker默认配置文件
       
            [root]# vi /etc/default/docker
            
            添加 --icc --iptables 到DOCKER_OPTS中
            
            DOCKER_OPTS=" --icc=false --iptables=true"
       
            [root]# systmectl restart docker
       
            现在，容器间是不能互相訪问的
       
            我们利用 --link 创建第三个容器，允许它能訪问第一容器，但不能訪问第二个容器
       
            [root]# docker run -it --name threecentos --link=firstcentos:firsttest centos
            
            [root]# curl firsttest
            
            如果不能成功，检查防火墙
       
            [root]# iptables -L -n
            
            把iptables 清空
       
            [root]# iptables -F
       
            重新启动docker服务
       
            [root]# systemctl start docker
            
            启动容器
            
            [root]# docker restart firstcentos secondcentos threecentos
       
            启动firstcentos 的Nginx
            
            [root]# docker attache firstcentos
            
            [root@firstcentos]# nginx
       
            启动threecentos容器
            
            [root]# docker attach threecentos
       
            从第三容器訪问第一容器
       
            [root@threecentos]# curl firsttest
       
            显示NGINX 信息，訪问成功

# DOCKER容器与外部网络的连接

   ip_forward 和 iptables决定了容器与外部网络的连接
     
   [ip_forward](#ip_forward)|[iptables](#iptables)|[端口映射訪问](#端口映射訪问)|[限制IP訪问容器](#限制IP訪问容器)|
   ---|---|---|---|
   
   
   # ip_forward
   
      在Linux系统中如果要开启数据转发功能，可用以下的Linux命令来查看数据转发功能是否开发
      
      [root]# sysctl net.ipv4.conf.all.forwarding
      net.ipv4.conf.all.forwarding=0      // 0 就是关闭   1 就是开启
      
      如果在docker系统中启动Linux数据转发功能，就必须要配置/etc/default/docker默认配置文件
      
      [root]# vi /etc/default/docker
      
      添加 --ip-forward=true 到 DOCKER_OPTS
      
      DOCKER_OPTS=" --ip-forward=true"

      当设置 --ip-forward=true时，Linux的net.ipv4.conf.all.forwarding 就为 1
      
   
   # iptables
      
      查看forward output 等表
      [root]# iptables -L -n
      
      
   
   # 端口映射訪问
   
     在第一台的虚拟机上
     [root]# docker run -it -p 32768:80 --name firstcentos centos
     [root@89087654]# nginx
     ctrl+P+Q 退出容器
     
     [root]# ip addr show
     ens33 192.168.28.128

     查看容器的端口映射
     [root]# docker port firstcentos
     80/tcp -> 0.0.0.0:32768
     
     从本虚拟机訪问容器firstcentos中的Nginx
     [root]# curl 127.0.0.1:32768
     
     显示nginx信息 

     启动第二台虚拟机
     
     从第二台虚拟机上远程訪问第一台虚拟机容器firstcentos上的Nginx服务
     [root]# curl 192.168.28.128：32768
     
     显示nginx信息 
     
   
   # 限制IP訪问容器
   
    例子
     在另一虚拟机上新建一个容器 fourcentos
     
     [root]# docker run -it -p 80 --name fourcentos centos
     [root@984746443]# nginx
     ctrl+P+Q 退出容器
     
     [root]# ip addr show
     ens33  10.200.55.3  
     
     现在设置： 不允许192.168.28.128的那一台机訪问本机
     
     在本机的iptables中添加一条新规则
     [root]# iptables -I docker -s 10.200.55.3 -d 192.168.28.128 -p TCP --dport 80 -j DROP
     
     
     -I docker           新加一条docker规则
     -s 10.200.55.3      源地址
     -d 192.168.28.128   目的地址
     -P TCP              使用的协仪
     --dport 80          目的端口
     -J DROP             所需要的操作
     
# 不同宿主机上容器跨网络的互连     
     
 * [1. 使用网桥实现跨主机容器连接](#使用网桥实现跨主机容器连接)
 * [2. 使用Open vSwitch实现跨主机容器连接](#使用Open-vSwitch实现跨主机容器连接)
 * [3. 使用weave实现跨主机容器连接](#使用weave实现跨主机容器连接)
 
# 使用网桥实现跨主机容器连接
 
  * [利用虚拟网桥实现Docker容器的跨主机访问](https://www.cnblogs.com/ruiqingzhang/p/4463971.html)
   
   
<a href="https://imgbb.com/"><img src="https://i.ibb.co/98L41dp/281956582865851.jpg" alt="281956582865851" border="0"></a>

     由于Docker容器通过docker0 网桥实现同一主机间中，容器的ip地址分配和访问，也就是说容器中的IP 是由docker0网桥分配的，所以，如果希望Docker
     跨主机访问，最简单的方式就是将不同主机的 docker0 网桥设置为同一网段。那么怎么实现跨主机呢？将本机网卡host eth0 端口也通过网桥来连接，
     但是通过这种桥接，所有网卡端口都要在一个网段下，所以要对每个Docker守护进程对ip的分配做出限制
     
   环境配置
     
        创建两台虚拟机
        host1 ip: 192.168.28.5   端口 eth0
        host2 ip: 192.168.28.8   端口 eth1
        
        网关 ： 192.168.28.2
        
        对容器ip的划分：

        Host1: 192.168.28.64/26

　　        地址范围： 192.168.28.65～192.168.28.126

        Host2: 192.168.28.128/26

　　        地址范围： 192.168.28.129～192.168.28.190
     
   需要的操作：

       以下，以Host1 为例，Host2 上操作相似，只是网卡名字不一样
    
   方式一  使用默认的docker0 网桥
   
          
          
          
   
   方式二  使用新建虚拟网桥
   
       
       1、删除旧网桥

          [root]# systemctl stop docker
          [root]# ip link set dev docker0 down
          [root]# brctl delbr docker0
          
        2、手动创建一个新的网桥名称为 bridge0  
        
           [root]# brctl addbr bridge0
           
           为网桥分配一个同网段ip
           [root]# ifconfig bridge0 192.168.28.5 netmask 255.255.255.0
           [root]# ip link set dev bridge0 up
        
         3. 桥接本地网卡：
         
           [root]# brctl addif bridge0 ens33 
            ens33  //本地网卡
   
         4. 查看是否已经创建bridge0
        
           [root]# ifconfig bridge0
      
        这里，我们就准备好了网桥设置
    
        下面我们来修改Docker的配置
        5、创建dameon.json
        
           vim /etc/docker/dameon.json
             { 
               "bridge": "beidge0",                    //指定容器连接的网桥名字
               “fixed-cidr”：“192.168.28.65/26”        // 用来限定为容器分配的IP地址范围
             }
             
        6. 重启docker服务
        
          [root]# systemctl restart docker
          
        7. 分别在两个host上启动一个容器
        
            [root]# docker run -it --name host1-centtos centos
            
            然后在容器中互相运行ping命令查看连接情况
   
   





# 使用Open vSwitch实现跨主机容器连接

# 使用weave实现跨主机容器连接

   
   
# 有用的参考

* [Docker 给运行中的容器设置端口映射的方法](https://www.jb51.net/article/127630.htm)
   
   
