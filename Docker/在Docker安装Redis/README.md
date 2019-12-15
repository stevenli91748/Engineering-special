
1  启动dockers

     [root]# systemctl start docker
     
2. 下载images

     [root]# docker pull redis
     
3. 创建容器

     [root]# docker run -p 6379:6379 -d redis redis-server
     Redis容器创建成功的ID

4.   [root]# docker exec -it Redis容器创建成功的ID redis-cli
