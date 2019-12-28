
<a href="https://ibb.co/VCJPCPg"><img src="https://i.ibb.co/mybMyM9/20180830161450776.png" alt="20180830161450776" border="0"></a><br /><a target='_blank' href='https://statewideinventory.org/chevrolet-0-60-times'>2014 chevy cruze 1.4 turbo 0 60</a><br />


步骤一：  部署项目.war文件到tomcat的webapps目录下
        
         我们把一个用IDEA工具写好的Java web项目Export-->war文件，然后把它上传到centOs宿主机里，我们需要把war文件放到tomcat的webapps目录下
         但找不到tomcat容器的部署目录webapps，我们首先进入到容器里面，通过命令docker exec -it mytomcat bash进入容器才能
         找到/usr/loca/tomcat/webapps这个目录，把上传到centOs根目录下的tracingfood.war文件，使用命令
         docker cp /tracingfood.war NAMES/CONTAINAER ID /usr/local/tomcat/webapps，进行部署过去，然后通过命令
         docker exe CONTAINER ID ls /usr/local/tomcat/webapps进行查看部署的项目。

         启动tomcat容器
         
         [root]# docker run -it -p 9090:8080 --name mytomcat tomcat
         在本控制终端无法操作，因tomcat在运行，要另开一控制终端
 
         操作：
 
         进入正在运行的tomcat容器，并启动Linux命令行模式
         [root]# docker exec -it mytomcat bash
         [root@38390307305:/usr/local/tomcat]# ls -l
          -------------------webapps目录
          ctrl+P+Q   退出tomcat容器
         [root]# docker cp /tracingfood.war mytomcat: /usr/local/tomcat/webapps
         重新进入tomcat容器，只能用 docker exec -it mytomcat bash 命令，而不能用 docker attach mytomcat 命令，用 attch 命令会
         让tomcat shutdown
 
         [root]# docker exec -it mytomcat bash
 
         [root@38390307305:/usr/local/tomcat]# cd webapps
 
         [root@38390307305:/usr/local/tomcat/webapps]# ls 
         ------------tracingfood.war
 
         webapps目录下了，然后通过 systemctl restart docker 就可自解压了, 创建tracingfood 目录了
 
         http://192.168.28.128:9090/tracingfood/index.jsp 就可以訪问了

