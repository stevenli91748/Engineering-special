
<a href="https://ibb.co/VCJPCPg"><img src="https://i.ibb.co/mybMyM9/20180830161450776.png" alt="20180830161450776" border="0"></a><br /><a target='_blank' href='https://statewideinventory.org/chevrolet-0-60-times'>2014 chevy cruze 1.4 turbo 0 60</a><br />

负载均衡原理：

      基于centOs-7的环境，安装nginx，运行docker里的两个以上的tomcat服务器，一般情况访问Java web项目的jsp页面，通过直接tomcat来访问的，但是我
      们现在不通过对tomcat进行访问页面，而是通过直接访问nginx进行访问，即你发出请求到nginx,nginx再request到tomcat,tomcat然后reponse
      到nginx,nginx 把接收到的服务转化为视图响应到客户端，这个过程，ngixn实行了拦截，或者说是代理，随机访问其中任何一个tomcat提供的服务，如果
      其中的一个tomcat无法提供服务，nginx就访问另一个tomcat.


环境：

     基于centos-7环境，安装docker和nginx,在docker里搭建两个或两个以上tomcat集群（多个tomcat容器)和两个mysql容器，并成功地把web应用程序部署
     到docker里的tomcat集群里，tomcat不能被直接訪问，所有的訪问都通过Nginx来分发。

步骤一：安装 nginx tomcat mysql 

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
 
         http://192.168.159.130:8081/tracingfood/login.jsp 就可以訪问了
         http://192.168.159.130:8082/tracingfood/login.jsp 就可以訪问了
         
 步骤三：更改nginx的配置文件实现负载均衡     
 
        [root@localhost ~]# vi /usr/local/nginx/conf/nginx.conf
        
        http {
              include       mime.types;
              
              default_type  application/octet-stream;

             sendfile        on;
             
             #tcp_nopush     on;

             #keepalive_timeout  0;
             
             #keepalive_timeout  65;

             #gzip  on;

             upstream myweb{//名称要一致，我部署两台容器，两个tomcat服务器集群来服务，任何客户端向nginx发出的请求，这两台tomcat会随机
                              响应，weight值越大，让它去访问的机率就大。
             
             server 192.168.159.130:8082 weight=2;
             
             server 192.168.159.130:8081 weight=1;
           
           }
        
        server {
               
               listen       80;
        
               server_name  localhost;

               #charset koi8-r;

               #access_log  logs/host.access.log  main;

              location / {
                         
                         proxy_pass http://myweb;        //实现nginx代理,随机访问tomcat1和tomcat2
                         
                         proxy_redirect default;         //设置默认的nginx代理，而不是访问下面的默认的nginx的index.html页面
                         
                         #root   /usr/local/nginx/html;
                         
                         #index  index.html index.htm;
                         }
              }
 
 
 
 
 步骤四： 防火墙的设置
 
      启动nginx的代理服务，每配置一次，就要重启一次，重启之后，需要编辑编辑防火墙的设置，这里一定要注意，你要配置80的端口，你只能问nginx了，
      nginx代理去随机访问任意docker里的tomcat容器，你再通过http://192.168.159.130:8082/tracingfood/userlogin.jsp或
      者http://192.168.159.130:8081/tracingfood/userlogin.jsp 就不能访问到tomcat响应的页面了，你要先去访问nginx，nginx再去访问tomcat,
      然后把相应的页面响应给客户端
 
    
     启动Nginx 服务
     
        [root]# cd /usr/local/nginx/sbin ./nginx            //启动nginx的服务
        
     重启动防火墙
     
       [root]# systemctl restart iptables.service 
       [root]# vi /etc/sysconfig/iptables
       
       :INPUT ACCEPT [0:0]
       :FORWARD ACCEPT [0:0]
       :OUTPUT ACCEPT [0:0]
       -A INPUT -m state --state RATED,ESTABLISHED -j ACCEPT
       -A INPUT -p icmp -j ACCEPT
       -A INPUT -i lo -j ACCEPT
       -A INPUT -p tcp -m state --state NEW -m tcp --dport 22 -j ACCEPT
       -A INPUT -m state --state NEW -m tcp -p tcp --dport 80 -j ACCEPT
       -A INPUT -m state --state NEW -m tcp -p tcp --dport 3306 -j ACCEPT
       -A INPUT -j REJECT --reject-with icmp-host-prohibited
       -A FORWARD -j REJECT --reject-with icmp-host-prohibited
       COMMIT
       
       看到没，防火墙里有nginx的80端口，mysql的3306端口，你都可以通过ip地址对其进行远程访问，如果你还想直接访问tomcat提供的服务，好办，
       在3306下面添加一个8080的端口就ok了
       
       -A INPUT -m state --state NEW -m tcp -p tcp --dport 8080 -j ACCEPT
 
       如果设置了8080端口，就可以在浏览器直接訪问tomcat，不需要通过Nginx服务
       
       http://192.168.159.130:8081/tracingfood/login.jsp 就可以訪问了
       
  步骤五：      
  
       下面是客户端向nignx发出请求，nginx向tomcat1或tomcat2发出请求，weight值越大，分配到哪个服务器的概率就大，下面的页面可能是tomcat1也可
       能是tomcat2相应的的，而不是直接对tomcat服务器进行访问，负载均衡说的就是，假设有多台tomcat服务器，如果其中的有一台坏掉了，这台无法提供服
       务，其他的服务器依然可以提供服务，这个时候nginx负载均衡的作用就体现
