启动Docker
1. [root]# systemctl start docker
2. [root]# docker pull mysql
3.创建数据库
       
       创建数据库方式一：
       
       [root]# docker run -d --name mysql2 -p 12345:3306 -e MYSQL_ROOT_PASSWORD=gz19731108 mysql
       
       创建数据库方式二：
       
       [root]# docker run -p 12345:3306                             将主机的12345端口射到dockers容器的3306端口  
                         
                         --name dockermysql                        运行服务名字
                         
                         -v /zzyyuse/mysql/conf:/etc/mysql/conf.d  将主机/zzyyuse/mysql目录下的conf/my.cnf挂载到容器的/etc/mysql/conf.d   
                         
                         -v /zzyyuse/mysql/logs:/log               将主机/zzyyuse/mysql目录下的log目录挂载到容器的/logs 
                         
                         -v /zzyyuse/mysql/data:/var/lib/mysql     将主机/zzyyuse/mysql目录下的data目录挂载到容器的/var/lib/mysql 
                         
                         -e MYSQL_ROOT_PASSWORD=654321             初始化root用户的密码
                         
                         -d mysql                                  后台程序运行mysql
       
       
       
4. 和MySQL交互操作
 
       查看mysql的状态
       
       [root]# docker ps
       
       MySQL运行成功后的容器ID ''''
       
       [root]# docker exec -it MySQL运行成功后的容器ID  /bin/bash
       
       启动运行MySQL DATABASE
       
       [root@ MySQL运行成功后的容器ID]# mysql -uroot -p
                       enter password： gz19731108

       
       Mysql>


