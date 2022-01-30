

启动Docker

1. [root]# systemctl start docker

//tag is version number

2. [root]#  docker pull mysql/mysql-server:tag

3. 创建数据库
       
       创建数据库方式一：
       
       [root]# docker run --name=mysql-master01 
                          
                          -p 33306:3306 
    
                          -v /zzyyuse/mysql/conf:/etc/mysql/conf.d  将主机/zzyyuse/mysql目录下的conf/my.cnf挂载到容器的/etc/mysql/conf.d   
                         
                          -v /zzyyuse/mysql/logs:/log               将主机/zzyyuse/mysql目录下的log目录挂载到容器的/logs 
                         
                          -v /zzyyuse/mysql/data:/var/lib/mysql     将主机/zzyyuse/mysql目录下的data目录挂载到容器的/var/lib/mysql 
                          
                          -d mysql/mysql-server:tag
       
       
       //The container initialization might take some time. When the server is ready for use, the STATUS of the container in the output of the docker ps command changes 
         from (health: starting) to (healthy).
       
       [root]# docker ps
       CONTAINER ID   IMAGE                COMMAND                  CREATED             STATUS                              PORTS                NAMES
       a24888f0d6f4   mysql/mysql-server   "/entrypoint.sh my..."   14 seconds ago      Up 13 seconds (health: starting)    3306/tcp, 33060/tcp  mysql1
       
       
       // Once initialization is finished, the command's output is going to contain the random password generated for the root user
       
       [root]# docker logs mysql-master01
       
       [root]#  docker logs mysql-master01 2>&1 | grep GENERATED
       GENERATED ROOT PASSWORD: Axegh3kAJyDLaRuBemecis&EShOs
       
       // 进入到MYSQL容器中
       [root]#  docker exec -it mysql-master01 mysql -uroot -p
       the password: 输入以上的原始密码
       
       //在mysql数据库中更改root用户的密码
       mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'gz@19731108';            //不要忘记分号 “ ；”
       mysql> FLUSH PRIVILEGES;
       
       //  Mysql8开放远程访问
       mysql> create user 'root'@'%' identified by 'Gz@19731108'; //1、先创建权限记录
       mysql> grant all privileges on *.* to 'root'@'%' with grant option; //2、授权
       mysql> exit
       
       
4. 和MySQL交互操作
 
       查看mysql的状态
       
       [root]# docker ps
       
       MySQL运行成功后的容器ID ''''
       
       [root]# docker exec -it MySQL运行成功后的容器ID  /bin/bash
       
       启动运行MySQL DATABASE
       
       [root@ MySQL运行成功后的容器ID]# mysql -uroot -p
                       enter password： gz@19731108

       
       Mysql>


