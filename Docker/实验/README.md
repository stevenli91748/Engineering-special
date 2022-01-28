# 目录
---
* [1. docker环境配置](#1-docker环境配置)
  * [Docker安装](#1-Docker安装)
  * [Docker开启远程安全访问](https://www.cnblogs.com/niceyoo/p/13270224.html)
  * [Docker 仓库搭建](#Docker-仓库搭建)
  * [在docker上安装MySQL](#在docker上安装MySQL)
  * [Docker 搭建 MongoDB 集群](#Docker-搭建MongoDB集群)
  * [在docker上安装Redis](#在docker上安装Redis)
  * [在docker上安装Tomcat](#在docker上安装Tomcat)
  * [在docker上安装Nginx](#在docker上安装Nginx)
  * [在docker上安装消息队列](#在docker上安装消息队列)
  * [Docker Swarm 搭建 kafka 集群](#Docker-Swarm搭建kafka集群)
  * [在docker上安装监控](#在docker上安装监控)
  * [在docker上安装DNS](#在docker上安装DNS)
  * [在docker上安装SVN](#在docker上安装SVN)
  * [Docker Swarm 搭建 solr 集群](#Docker-Swarm搭建solr集群)
  * [Docker Swarm 搭建 zookeeper 集群](#Docker-Swarm搭建zookeeper集群)
  * [在docker上安装部署ceph集群](#在docker上安装部署ceph集群)
  * [Docker Swarm 搭建 ELK 日志系统](#Docker-Swarm搭建ELK日志系统)
  * [Docker Swarm 搭建 Hadoop](#Docker-Swarm搭建Hadoop)
  * [在docker上安装部署filebeat](#在docker上安装部署filebeat)
  * [docker gitlib CI/CD](#Docker-gitlib-CICD)
  * [Docker中搭建FastDFS文件系统](#Docker中搭建FastDFS文件系统)
  * [SpringBoot打包成Docker镜像](#SpringBoot打包成Docker镜像)
  * [Docker+Jenkins+Git+GitLab实现DevOps](#Docker+Jenkins+Git+GitLab实现DevOps)
  * [使用Docker方式发布微服务](https://weread.qq.com/web/reader/ca932ea071d7c798ca9a714k5fd32dd02725fd0b37cd75e) 
  * [使用Docker部署日志分析平台(ELK)](https://weread.qq.com/web/reader/ca932ea071d7c798ca9a714kc45328f0274c45147dee704)
  * [基于Docker的高级部署工具](https://weread.qq.com/web/reader/ca932ea071d7c798ca9a714keb132680275eb160de1d35c)
  * [Spring Cloud组件的Docker化](https://weread.qq.com/web/reader/71d32370716443e271df020k01332b9028a013d407161b5)
    * [建造基础镜像](https://weread.qq.com/web/reader/71d32370716443e271df020k398323202893988c7f885f0)---基础镜像dockerfile的模板基本一致，这里都放到每个工程的根目录下面，跟pom.xml文件一个目录
    * [Spring Cloud Config-Server的Docker化](https://weread.qq.com/web/reader/71d32370716443e271df020k01332b9028a013d407161b5)
    * Spring Cloud Eureka-server的Docker化
    * Spring Cloud Gateway的Docker化
    * turbine的Docker化
    * Spring Admin的Docker化
    * 业务微服务的Docker化

* [2. 在docker集成持续部署](#2-在docker集成持续部署)
  * [在docker上安装jenkins](#在docker上安装jenkins)
  * [在docker上部署spring boot 项目](#在docker上部署Java项目)


---

# 1 docker环境配置

## Docker安装
   * [Docker windows版本安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker%20windows/README.md)
   * [Docker Linux版本安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/docker%20for%20linux/README.md)

## Docker 仓库搭建
   * [Docker 仓库搭建](https://www.jianshu.com/p/d27ec8b8ab5e)

## Docker中搭建FastDFS文件系统
   * [Docker中搭建FastDFS文件系统](https://www.cnblogs.com/niceyoo/p/13511082.html)

## Docker+Jenkins+Git+GitLab实现DevOps

   * [Docker+Jenkins+Git+GitLab实现DevOps](https://www.cnblogs.com/niceyoo/p/13096218.html)


## SpringBoot打包成Docker镜像
   * [SpringBoot打包成Docker镜像](https://www.cnblogs.com/niceyoo/p/13796792.html)

## Docker-gitlib-CICD

   * [docker gitlib CI/CD](https://www.jianshu.com/p/49555945bc2d)

##  在Docker 运行 Oracle 数据库
   * [使用 Docker 运行 Oracle 数据库](https://rovo98.github.io/posts/c5182a98/)

## Docker Swarm搭建Hadoop
   * [Docker Swarm 搭建 Hadoop](https://www.jianshu.com/p/4c4ccc60f4dd)

## Docker Swarm搭建ELK日志系统
 
   * [Docker Swarm 搭建 ELK 日志系统](https://www.jianshu.com/p/da81ce484eb9)
 
## Docker Swarm搭建solr集群
   * [Docker Swarm 搭建 solr 集群](https://www.jianshu.com/p/f3fbbea3ff66)

## Docker 搭建MongoDB集群 
   * [ Docker 搭建 MongoDB 集群](https://www.jianshu.com/p/43fd9e24270e)
 
## Docker Swarm搭建kafka集群
   * [Docker Swarm 搭建 kafka 集群](https://www.jianshu.com/p/54811ae630a7)

## 在docker上安装MySQL
   * [在Docker安装MySQL](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装MySQL/README.md)
   * [搭建 Pxc + Haproxy 对MySQL数据库做心跳检测](https://www.jianshu.com/p/28396151526c)

## Docker Swarm搭建zookeeper集群

   * [Docker Swarm 搭建 zookeeper 集群](https://www.jianshu.com/p/82f94f67c701)

## 在docker上安装Redis
   * [在Docker安装Redis](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Redis/README.md)
   * [基于Docker搭建Redis集群（主从集群）](https://www.cnblogs.com/niceyoo/p/14118146.html)
   * [redis集群官方不支持docker的swarm 集群网络方式，需指定容器的network使用host方式连接](https://www.cnblogs.com/ybch/p/14445612.html)
## 在docker上安装Tomcat
   * [在Docker安装Tomcat](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Tomcat/README.md)
   * [使用Docker部署tomcat、mysql、nginx静态服务器](https://blog.csdn.net/a745233700/article/details/80452862)
   * [Docker 搭建 Tomcat + Mysql](https://www.cnblogs.com/primadonna/p/10411857.html)
   
## 在docker上安装Nginx  
   * [在Docker安装Nginx](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Nginx/README.md)
   * [Docker Nginx 下载 启动 配置](https://www.jianshu.com/p/4d9570b3fcf0)
## 在docker上安装监控
   * [Docker容器可视化监控中心搭建](https://mp.weixin.qq.com/s?__biz=MzU4ODI1MjA3NQ==&mid=2247483763&idx=1&sn=6ceb9e73540b5016dadfb212636b3855&chksm=fdded7b7caa95ea1165b507397c39267d3bf7522c83cc8ed10eae4ee4a13db831eb58a3dc167&scene=21#wechat_redirect)
   * [使用 docker-compose 安装 Prometheus+Alertmanager+Grafana](http://www.dev-share.top/2019/06/25/%e4%bd%bf%e7%94%a8-docker-compose-%e5%ae%89%e8%a3%85-prometheusalertmanagergrafana/)

## 在docker上安装消息队列
   * [docker部署rabbitmq集群的实现方法](https://www.jb51.net/article/144748.htm)
   * [Docker中安装RabbitMQ ](https://www.cnblogs.com/niceyoo/p/14094715.html)
## 在docker上安装DNS
* [docker-compose 搭建 DNS 私服](http://www.dev-share.top/2020/06/04/%e6%90%ad%e5%bb%ba-dns-%e7%a7%81%e6%9c%8d/)


## 在docker上安装SVN
* [Docker-Dompose 安装 SVN](http://www.dev-share.top/2020/08/28/docker-dompose-%e5%ae%89%e8%a3%85-svn/)

## 在docker上安装部署ceph集群
* [docker-compose 部署ceph集群](http://www.dev-share.top/2019/12/24/docker-compose-%e9%83%a8%e7%bd%b2ceph%e9%9b%86%e7%be%a4/)

## 在docker上安装部署filebeat
* [使用 docker-compose 安装 filebeat+redis](http://www.dev-share.top/2019/06/27/%e4%bd%bf%e7%94%a8-docker-compose-%e5%ae%89%e8%a3%85-filebeatredis/)



# 2 在docker集成持续部署

## 在docker上安装jenkins
* [Docker容器使用jenkins部署web项目(总结)](https://www.jb51.net/article/146319.htm)
* [Docker+Jenkins+Git集成持续部署](https://www.bilibili.com/video/av62369964/?spm_id_from=333.788.videocard.1)
* [Node 项目从构建到使用 Jenkins 与 Docker 实现自动化部署](http://dockone.io/article/9507)
* [Docker-Compose 安装 Jenkins](http://www.dev-share.top/2020/08/23/docker-compose-%e5%ae%89%e8%a3%85-jenkins/)

## 在docker上部署Java项目
* [Docker部署Java项目持续集成？](http://dockone.io/question/283)
* [Spring Boot项目部署在Docker中](https://itweknow.cn/blog-site/posts/e2232a75.html)
* [使用 docker 高效部署前端应用](https://github.com/shfshanyue/op-note/blob/master/deploy-fe-with-docker.md)
* [在Docker环境构建、打包和运行Spring Boot应用](http://dockone.io/article/9530)
* [基于docker+nginx+tomcat容器+mysql容器部署Java web项目实现负载均衡实战](https://blog.csdn.net/liqz666/article/details/82222511)
* [docker-compose 构建项目](http://www.dev-share.top/2019/07/16/docker-compose-%e6%9e%84%e5%bb%ba%e9%a1%b9%e7%9b%ae/)


# 参考
* [各种集成例子1](https://www.jianshu.com/u/cf31b9838b17)
* [各种集成例子2](https://www.cnblogs.com/niceyoo/category/1544920.html)
