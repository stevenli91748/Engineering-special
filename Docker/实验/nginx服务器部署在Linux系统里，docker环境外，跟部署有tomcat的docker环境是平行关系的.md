
<a href="https://ibb.co/VCJPCPg"><img src="https://i.ibb.co/mybMyM9/20180830161450776.png" alt="20180830161450776" border="0"></a><br /><a target='_blank' href='https://statewideinventory.org/chevrolet-0-60-times'>2014 chevy cruze 1.4 turbo 0 60</a><br />


步骤一：  在IDEA等开发工具把打包后的Java web项目Export-->war文件部署到tomcat容器内部的webapps里面
         你可以把war文件部署到tomcat的webapps目录下，tomcat容器的webapps目录只有通过进入到tomcat容器里才能找到webapps目录，把war.文件部署进去，
         重启一下docker的服务（不用重启貌似也可以），就可以自动解压war文件
         
         [root]# docker cp /宿主机目录/xxx.war container-id:/usr/local/tomcat/webapps
         
         这样你就成功的把项目部署到容器里面了，然后使用docker restart命令自动把war文件解压。然后在浏览器里输入http://ip:8080或8081就可以访问到了。
          

