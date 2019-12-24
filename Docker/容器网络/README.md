
* [第一部分  DOCKER容器的网络基础](#DOCKER容器的网络基础)
* [第二部分  DOCKER容器的互联](#DOCKER容器的互联)
* [第三部分  DOCKER容器与外部网络的连接](#DOCKER容器与外部网络的连接)



# DOCKER容器的网络基础
  
  [docker0网桥设备](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/容器网络/docker0设备.md)|
  ---|
  
  
# DOCKER容器的互联

 容器的互联有三种方式
 
  1. 默认允许所有容器互联
    
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
    
  2. 拒绝容器间互联
  
          docker 守护进程的启动选项
          --icc=false

          [root]# vi /etc/default/docker
          添加 --icc=false 到 DOCKER_OPTS 设置为拒绝所有容器互联
          DOCKER_OPTS-"--icc=false"
 
           [root]# systemctl restart docker
  
  3. 允许特定容器间的连接
      
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
