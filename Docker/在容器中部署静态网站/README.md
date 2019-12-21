
1. 创建映射80端口的交互式容器

       [root]# docker run -p 80 --name web-centos -it centos /bin/bash
        
      
2. 在容器中新安装的centos系统中安装Nginx

       [root@7836353839]# yum install nginx 
       
3. 在容器中新安装的centos系统中vim

       [root@7836353839]# yum install vim
       
 4. 创建静态页面
      [root@7836353839]# mkdir /var/www/html
 
      [root@7836353839]# cd /var/www/html
 
      [root@7836353839 /var/www/html]# touch index.html
      
      [root@7836353839 /var/www/html]# vi index.html
      
       <html>
         <head>
            <title> our web</title>
         </head>
         <body>
             this is my world
         </body>
      </html>
  
 5. 修改Nginx配置文件
       
        [root@7836353839 nginx]# whereis nginx
        [root@7836353839 nginx]# cd /etc/nginx
        [root@7836353839 nginx]# vi nginx.conf.default
       
        server {
                listen   80;
                
                location / { 
                           # 设置 root 路径为刚才建立的路径
                           root /var/www/html
 
 6. 运行Nginx
 
         [root@7836353839]# nginx
         [root@7836353839]# ps -ef
         
         ctrl+p+q 退出 新建容器
         
         [root]# docker ps
         
         nginx 容器-------------
         
         # 用docker命令 查看端口
         [root]# docker port web-centos  
         
         web-centos: 容器ID
         
         80/tcp->0.0.0.0:49167
 
       # 用docker命令查看容器进程的状态
        [root]# docker top web-centos
 
 7. 验证网站訪问
       
        7.1 在本虚拟机上用浏览器訪问
        
          
          http://127.0.0.1:49167
          
          显示Nginx信息，但不是自定义信息，还有问题
          
          [root]# ip addr show
          ens33   192.168.28.128
          
          http://192.168.28.128:49167
          
          不能訪问
  

        7.2 在物理主机上用浏览器訪问
        
          
          http://192.168.28.128:49167
          
          不能訪问
          
