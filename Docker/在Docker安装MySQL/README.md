启动Docker
1. [root]# systemctl start docker
2. [root]# docker pull mysql
3. [root]# docker run -p 12345:3306                             将主机的12345端口射到dockers容器的3306端口  
                      --name mydockersql                        运行服务名字
                      -v /zzyyuse/mysql/conf:/etc/mysql/conf.d  将主机/zzyyuse/mysql目录下的conf/my.cnf挂载到容器的/etc/mysql/conf.d   
                      -v /zzyyuse/mysql/logs:/log               将主机/zzyyuse/mysql目录下的log目录挂载到容器的/logs 
                      -v /zzyyuse/mysql/data:/var/lib/mysql     将主机/zzyyuse/mysql目录下的data目录挂载到容器的/var/lib/mysql 
                      -e MYSQL_ROOT_PASSWORD=654321             初始化root用户的密码
                      -d mysql                                  后台程序运行mysql
                                                                                       
