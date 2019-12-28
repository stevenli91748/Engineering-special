
<a href="https://ibb.co/VCJPCPg"><img src="https://i.ibb.co/mybMyM9/20180830161450776.png" alt="20180830161450776" border="0"></a><br /><a target='_blank' href='https://statewideinventory.org/chevrolet-0-60-times'>2014 chevy cruze 1.4 turbo 0 60</a><br />

负载均衡原理：

      基于centOs-7的环境，安装nginx，运行docker里的两个以上的tomcat服务器，一般情况访问Java web项目的jsp页面，通过直接tomcat来访问的，但是我
      们现在不通过对tomcat进行访问页面，而是通过直接访问nginx进行访问，即你发出请求到nginx,nginx再request到tomcat,tomcat然后reponse
      到nginx,nginx 把接收到的服务转化为视图响应到客户端，这个过程，ngixn实行了拦截，或者说是代理，随机访问其中任何一个tomcat提供的服务，如果
      其中的一个tomcat无法提供服务，nginx就访问另一个tomcat.


环境：

     基于centos-7环境，安装docker和nginx,在docker里搭建两个或两个以上tomcat集群（多个tomcat容器)和两个mysql容器，并成功地把web应用程序部署
     到docker里的tomcat集群里，tomcat不能被直接訪问，所有的訪问都通过Nginx来分发。

步骤一： 

       启动docker
       
        [root]# systemctl start docker
       
       
       安装Nginx服务器在虚拟机上：
       
       
       
       创建两个tomcat容器 在docker上：
    
        [root]# docker run -it -p 8081:8080 --name tomcat-1 tomcat
        [root]# docker run -it -p 8082:8080 --name tomcat-2 tomcat
        
        创建两个MySQL容器在docker上：
        
        [root]# docker run -p 4306:3306 --name mysql-1 -e MYSQL_ROOT_PASSWORD=123456 -d mysql
        [root]# docker run -p 4307:3306 --name mysql-2 -e MYSQL_ROOT_PASSWORD=123456 -d mysql

步骤二：  部署项目.war文件到tomcat的webapps目录下
        
         我们把一个用IDEA工具写好的Java web项目Export-->war文件，然后把它上传到centOs宿主机里，我们需要把war文件分别放到tomcat1和tomcat2
         的webapps目录下，但找不到tomcat容器的部署目录webapps，我们首先进入到容器里面，通过命令docker exec -it mytomcat bash进入容器才能
         找到/usr/loca/tomcat/webapps这个目录，把上传到centOs根目录下的tracingfood.war文件，使用命令
         docker cp /tracingfood.war NAMES/CONTAINAER ID /usr/local/tomcat/webapps，进行部署过去，然后通过命令
         docker exe CONTAINER ID ls /usr/local/tomcat/webapps进行查看部署的项目。

         在本控制终端无法操作，因tomcat在运行，要另开一控制终端
 
         操作：
 
         进入正在运行的tomcat-1容器，并启动Linux命令行模式
         [root]# docker exec -it tomcat-1 bash
         [root@38390307305:/usr/local/tomcat]# ls -l
          -------------------webapps目录
          ctrl+P+Q   退出tomcat容器
          
         [root]# docker cp /tracingfood.war tomcat-1: /usr/local/tomcat/webapps
         [root]# docker cp /tracingfood.war tomcat-2: /usr/local/tomcat/webapps
         
         重新进入tomcat容器，只能用 docker exec -it mytomcat bash 命令，而不能用 docker attach mytomcat 命令，用 attch 命令会
         让tomcat shutdown
 
         [root]# docker exec -it mytomcat-1 bash
 
         [root@38390307305:/usr/local/tomcat]# cd webapps
 
         [root@38390307305:/usr/local/tomcat/webapps]# ls 
         ------------tracingfood.war
 
         webapps目录下了，然后通过 systemctl restart docker 就可自解压了, 创建tracingfood 目录了
 
         http://192.168.159.130:8081/tracingfood/index.jsp 就可以訪问了

