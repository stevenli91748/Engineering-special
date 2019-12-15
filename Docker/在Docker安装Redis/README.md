
1  启动dockers

     [root]# systemctl start docker
     
2. 下载images

     [root]# docker pull redis
     
3. 创建容器

     [root]# docker run -p 6379:6379 -d redis redis-server
     
     Redis容器创建成功的ID

4.   在创建成功容器中调用redis 的客户端软件

     [root]# docker exec -it Redis容器创建成功的ID redis-cli

     127.0.0.1:6379> set foo bar
     OK
     
     127.0.0.1:6379> get foo
     
     "bar"
