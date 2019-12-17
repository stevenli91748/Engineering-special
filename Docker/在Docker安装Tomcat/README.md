
1. [root]# systemctl start docker
2. 
   [root]# docker images 
   [root]# docker run -it --name mytomcat -p 9090:8080  tomcat-images-id
   
3. 在虚拟机用浏览器訪问docker 中的 tomcat

     http://localhost:9090
     
    能看到tomcat猫的图像
    
 4. 在主机中用浏览器訪问docker 中的 tomcat   
 
    [root]# ip addr show
  
    ens33
     ip 192.168.28.128
 
    在主机中用浏览器訪问
    
    http://192.168.28.128:9090
    
     能看到tomcat猫的图像
