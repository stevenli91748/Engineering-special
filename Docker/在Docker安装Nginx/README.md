
1. 启动docker

       [root]# systemctl start docker
       
2. 查看是否在本地有Nginx的镜像

       [root]# docker images
       
       如果没有
       
       [root]# docker pull nginx
       
 3. 创建和运行nginx容器
 
       [root]#  docker run --name nginx-test -p 8078:80 -d nginx
       
        --name nginx-test：容器名称。
        -p 8080:80： 端口进行映射，将本地 8078 端口映射到容器内部的 80 端口。
        -d nginx： 设置容器在在后台一直运行。
        
 4.  测试是否成功建立Nginx
 
         4.1 在本地虚拟机上用浏览器訪问
         
             [root]# ip addr show  
              ens33 192.168.28.128
         
             http://192.168.28.128:8078
             
             现示Nginx信息
             
          4.2 在物理机上用浏览器訪问
          
              http://192.168.28.128:8078
              
              现示Nginx信息
