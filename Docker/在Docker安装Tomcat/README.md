
1. 启动docker

   [root]# systemctl start docker

2. 创建tomcat容器 
   
   [root]# docker images 
   
   [root]# docker run -it --name mytomcat -p 9090:8080  tomcat-images-id
   
3. 在虚拟机用浏览器訪问docker 中的 tomcat

     http://localhost:9090
     
    能看到tomcat猫的图像
    
 4. 在物理主机中用浏览器訪问docker 中的 tomcat   
 
    [root]# ip addr show
  
    ens33
     ip 192.168.28.128
 
    在主机中用浏览器訪问
    
    http://192.168.28.128:9090
    
     能看到tomcat猫的图像
     
 # 部署war文件到tomcat的webapps目录    

我们把一个用IDEA工具写好的Java web项目Export-->war文件，然后把它上传到centOs宿主机里，我们需要把war文件放到tomcat的webapps目录下
但找不到tomcat容器的部署目录webapps，我们首先进入到容器里面，通过命令docker exec -it mytomcat bash进入容器才能找到/usr/loca/tomcat/webapps这个目录，把上传到centOs根目录下的tracingfood.war文件，使用命令docker cp /tracingfood.war NAMES/CONTAINAER ID /usr/local/tomcat/webapps，进行部署过去，然后通过命令docker exe CONTAINER ID ls /usr/local/tomcat/webapps进行查看部署的项目。

 在本控制终端无法操作，因tomcat在运行，要另开一控制终端
 
 操作：
 
 进入正在运行的tomcat容器，并启动Linux命令行模式
 
 [root]# docker exec -it mytomcat bash
 
 [root@38390307305:/usr/local/tomcat]# ls -l
 
 -------------------webapps目录
 
 ctrl+P+Q   退出tomcat容器
 
 [root]# docker cp /tracingfood.war mytomcat: /usr/local/tomcat/webapps
 
 重新进入tomcat容器，只能用 docker exec -it mytomcat bash 命令，而不能用 docker attach mytomcat 命令，用 attch 命令会让tomcat shutdown
 
 [root]# docker exec -it mytomcat bash
 
 [root@38390307305:/usr/local/tomcat]# cd webapps
 
 [root@38390307305:/usr/local/tomcat/webapps]# ls 
 
 -------------------tracingfood.war
 
 该文件已部署到tomcat的webapps目录下了，然后通过 docker restart mytomcat 就可自解压了, 创建tracingfood 目录了
 
 然后 在浏览器输入
 
 http://192.168.28.128:9090/tracingfood/index.jsp 就可以訪问了
 
 
 
 
