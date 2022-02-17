### 注意，Docker和VMware workstation 有冲突
### [冲突解决方法--Win10系统下提示VMware与Device/Credential Guard不兼容如何解决](http://www.win7zhijia.cn/win10jc/win10_20680.html)
### Docker服务端默认配置文件,docker1.12版本之前是修改vim /etc/default/docker的DOCKER_OPTS参数的，但是1.12之后docker建议在/etc/docker/daemon.json文件中修改docker启动参数，修改完后，通过   [root]# dockerd     命令启动守护进程
### Docker服务启动文件 ： /usr/lib/systemd/system/docker.service




## 如果你只想在tomcat 8上运行Java Web应用程序，可以只使用：

      docker run tomcat:8 -v HelloWorld.war:/usr/local/tomcat/webapps/Helloworld.war


---

<details>
<summary>docker启动参数</summary>
 {
    "authorization-plugins": [],
   
   "data-root": "",
   
   "dns": [],
   
   "dns-opts": [],
   
   "dns-search": [],
   
   "exec-opts": [],
   
   "exec-root": "",
   
   "experimental": false,
   
   "storage-driver": "",
   
   "storage-opts": [],
   
   "labels": [],
   
   "live-restore": true,
   
   "log-driver": "",
   
   "log-opts": {},
   
   "mtu": 0,
   
   "pidfile": "",
   
   "cluster-store": "",
   
   "cluster-store-opts": {},
   
   "cluster-advertise": "",
   
   "max-concurrent-downloads": 3,
   
   "max-concurrent-uploads": 5,
   
   "default-shm-size": "64M",
   
   "shutdown-timeout": 15,
   
   "debug": true,
   
   "hosts": [],
   
   "log-level": "",
   
   "tls": true,
   
   "tlsverify": true,
   
   "tlscacert": "",
   
   "tlscert": "",
   
   "tlskey": "",
   
   "swarm-default-advertise-addr": "",
   
   "api-cors-header": "",
   
   "selinux-enabled": false,
   
   "userns-remap": "",
   
   "group": "",
   
   "cgroup-parent": "",
   
   "default-ulimits": {},
   
   "init": false,
   
   "init-path": "/usr/libexec/docker-init",
   
   "ipv6": false,
   
   "iptables": false,
   
   "ip-forward": false,
   
   "ip-masq": false,
   
   "userland-proxy": false,
   
   "userland-proxy-path": "/usr/libexec/docker-proxy",
   
   "ip": "0.0.0.0",
   
   "bridge": "",
   
   "bip": "",
   
   "fixed-cidr": "",
   
   "fixed-cidr-v6": "",
   
   "default-gateway": "",
   
   "default-gateway-v6": "",
   
   "icc": false,
   
   "raw-logs": false,
   
   "allow-nondistributable-artifacts": [],
   
   "registry-mirrors": [],
   
   "seccomp-profile": "",
   
   "insecure-registries": [],
   
   "no-new-privileges": false,
   
   "default-runtime": "runc",
   
   "oom-score-adjust": -500,
   
   "node-generic-resources": ["NVIDIA-GPU=UUID1", "NVIDIA-GPU=UUID2"],
   
   "runtimes": {
   
        "cc-runtime": {
   
           "path": "/usr/bin/cc-runtime"
        },
        
        "custom": {
        
             "path": "/usr/local/bin/my-runc-replacement",
             
             "runtimeArgs": [
             
                 "--debug"
            ]
        }
    }
}
 
</details>


# 在线书籍

* [Docker: 容器与容器云（第2版）](https://weread.qq.com/web/reader/33f32b50718ff5d533f22e7)
* [Docker技术入门与实战（第3版）](https://weread.qq.com/web/reader/57f327107162732157facd6kc81322c012c81e728d9d180)
* [深入浅出Docker---2019  非常好](https://weread.qq.com/web/reader/a6332ce0718b75f2a63b772)
* [容器云运微实战： Docker与kubernetes集群](https://weread.qq.com/web/reader/31e3261071822fbe31ebcadkc81322c012c81e728d9d180)


# 目录
---

* [Docker配置实验例子](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/%E5%AE%9E%E9%AA%8C/README.md)
* Docker原理
  * [Docker引擎与架构](https://weread.qq.com/web/reader/69532da0717d3026695636ek19c3222022419ca14e7eef7)
  * [Docker底层技术](https://weread.qq.com/web/reader/69532da0717d3026695636eka5b325d0225a5bfc9e0772d)
* DockerFil
  * [DockerFil的使用命令](https://docs.docker.com/engine/reference/builder/)
  * [编写 Dockerfile 最佳实践](https://mp.weixin.qq.com/s/Vq64iXB3fPD9J9ju4XirxA) 
* [微服务与Docker的整合](https://weread.qq.com/web/reader/69532da0717d3026695636ek72b327f023972b32a1f7e2d)
* [使用Docker Compose部署SpringBoot应用](https://mp.weixin.qq.com/s?__biz=MzU1Nzg4NjgyMw==&mid=2247483800&idx=1&sn=b9e0b6c006bad05e4055a3c0bb61c815&scene=21#wechat_redirect)



## 博客

[精尽 Docker 学习指南](http://svip.iocoder.cn/Docker/tutorials/)|[周志明 如何部署 Docker CE 容器环境](https://icyfenix.cn/appendix/deployment-env-setup/setup-docker.html)|
---|---|

[史上讲解最好的 Docker 教程，学Docker看这篇就够了！](https://mp.weixin.qq.com/s/qzKu95JVazQu1h0zu9GizA)|[看云 Docker —— 从入门到实践](https://www.kancloud.cn/docker_practice/docker_practice)|[还在百度Docker命令？推荐一套我用起来特顺手的命令！](http://www.macrozheng.com/#/reference/docker_command)|
---|---|---|


[两款Docker可视化工具](https://zhuanlan.zhihu.com/p/149693508)|[Spring Boot with Docker](https://spring.io/guides/gs/spring-boot-docker/)|
---|---|

[新版docker启动配置文件不生效问题](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker守护进程/新版docker启动配置文件不生效问题.md)|[Docker 不能启动](https://blog.csdn.net/w1316022737/article/details/83692701)|[深入浅出大型互联网，企业开发运维利器-docker](https://www.bilibili.com/video/BV1MW411N7dV)|
---|---|---|


[在容器中部署静态网站](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在容器中部署静态网站/README.md)|[Docker的远程訪问](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker的远程訪问/README.md)|
---|---|

[基于docker+nginx+tomcat容器+mysql容器部署Java web项目实现负载均衡实战](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/实验/基于docker%2Bnginx%2Btomcat容器%2Bmysql容器部署Java%20web项目实现负载均衡实战.md)|[不用网络，创建一个点到点连接](https://yeasy.gitbooks.io/docker_practice/advanced_network/ptp.html)|
---|---|

[实战在Docker中使用CI/CD](https://yeasy.gitbooks.io/docker_practice/cases/ci/)|[如何调试 Docker](https://yeasy.gitbooks.io/docker_practice/appendix/debug.html)|[IDEA中使用Docker插件](https://mrbird.cc/IDEA-Docker-Plugin.html)|
---|---|---|

[如何查看Docker容器环境变量，如何向容器传递环境变量](https://juejin.im/post/6857283423380504584)|[使用docker五步搭建ELK日志收集分析系统](http://www.zimug.com/container/docker/%e4%bd%bf%e7%94%a8docker%e4%ba%94%e6%ad%a5%e6%90%ad%e5%bb%baelk%e6%97%a5%e5%bf%97%e6%94%b6%e9%9b%86%e5%88%86%e6%9e%90%e7%b3%bb%e7%bb%9f/.html)|[docker-compose安装和配置jenkins](https://www.jianshu.com/p/52f04b59596e)|
---|---|---|

[吊炸天的 Docker 图形化工具 Portainer，必须推荐给你](https://www.jianshu.com/p/e76054edabe1?utm_campaign=hugo&utm_medium=reader_share&utm_content=note&utm_source=weixin-friends)|
---|

[收藏手册：Docker安装RabbitMQ，只需3步](https://www.toutiao.com/a6872582086776226307/?log_from=15a2866372c8d_1630132988859)|[Linux Docker 搭建 MongoDB 集群](https://www.jianshu.com/p/43fd9e24270e)|
---|---|


# Docker 内存

* [一次 Docker 容器内大量僵尸进程排查分析](https://juejin.im/post/5e0002adf265da33dc7a3a1f)


# Docker布署
* [使用 Docker 部署 Spring Boot 项目，带劲！！](https://mp.weixin.qq.com/s/1uAZ56XFoZ2l6bGNvBgKNA)
* [手动部署springboot工程到Docker](https://www.jianshu.com/p/e635eb540c97)
* [Docker+Jenkins持续集成搭建](https://www.jianshu.com/p/64a0b1be55b2)
* [Docker安装Tomcat镜像并部署web项目](https://www.jianshu.com/p/ac7bceb6f457)
* [基于Docker的Jenkins安装部署与流水线脚本](https://www.jianshu.com/p/ff2be84f2fa4)



---

## 参考实验

[Docker容器化部署尝试——多容器通信(node+mongoDB+nginx)](https://www.jb51.net/article/153042.htm)|
---|

[docker的简单搭建(java/tomcat 环境)](https://www.cnblogs.com/lemon-flm/p/7039880.html)|
---|


[docker的各种配置](https://blog.csdn.net/qq_36688928/article/details/93164651)|[Docker容器链接-WEB容器连接MYSQL容器](https://my.oschina.net/ht896632/blog/909276)|
---|---|




Go|[Swarm-管理docker集群](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Swarm/README.md)|[Compose-管理docker容器的应用部署](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Compose/README.md)|[Machine-安装docker](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Machine/README.md)|
---|---|---|---|

[Mesos-高可用的集群管理](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Mesos/README.md)|[Kubernetes-容器集群管理](https://github.com/stevenli91748/Big-Data/blob/master/Kubernetes/README.md)|CI/CD|Jenkinds|
---|---|---|---|

Rancher|Flannel|Calico|
---|---|---|


---

Docker镜像|Docker容器|[Docker网络](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker网络/README.md)|[Docker存储](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker%E5%AD%98%E7%A1%80/README.md)|[Docker容器网络](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/容器网络/README.md)|容器监控|
---|---|---|---|---|---|

[Docker Daemon守护进程](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker守护进程/README.md)|[Open vSwitch虚拟交换机](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Open%20vSwitch虚拟交换机/README.md)|[weave 虚拟网络](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/weave%20虚拟网络/README.md)|
---|---|---|

多主机管理|日志管理|Dockerfile|[Docker API](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker%20API/README.md)|
---|---|---|---|


[Docker集群网络](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker集群/README.md)|
---|






### 知识点
快速搭建Docker环境
Docker日常维护命令
Docker镜像、仓库、容器详解
Docker网络配置
Dockerfile、DockerCompose详解
Docker应用部署
Docker构建私有仓库

# 内容
## Docker概述

Docker 不是万能的，只是为了解决资源重用和动态分配而设计的，

当我们使用了微服务架构后，我们将一个原本完整的系统，按照业务逻辑拆分成一个个可独立运行的子系统。为了降低系统间的耦合度，我们希望这些子系统能够运行在
独立的环境中，这些环境之间能够相互隔离。

在Docker出现之前，若使用虚拟机来实现运行环境的相互隔离的话成本较高，虚拟机会消耗较多的计算机硬件/软件资源。Docker不仅能够实现运行环境的隔离，而且能
极大程度的节约计算机资源，它成为一种轻量级的“虚拟机”。





# 视频

## 阿良教育----是一家专门面向DevOps中高端技术人才的集训营
* [Docker 快速入门实战](https://ke.qq.com/course/456282?taid=3834834565133914)

---

  * [千锋达摩院】微服务架构 2.0（上）Linux + Docker + Kubernetes +SpringBoot+SpringCloud ](https://www.bilibili.com/video/av62628434/?p=2)
  * [千锋达摩院】微服务架构 2.0（下）Linux + Docker + Kubernetes +SpringBoot+SpringCloud](https://www.bilibili.com/video/av74438452/?spm_id_from=333.788.videocard.1)
  * [容器化+分布式+实战](https://www.bilibili.com/video/BV1Dz411q7Xi/?spm_id_from=333.788.videocard.2)

  * [高级Pass卡—领略Docker负载均衡及批量编排之美](https://www.bilibili.com/video/av54371967?from=search&seid=5320849185764424951)
  * [高级Pass卡—撑起双十一的几十万docker容器](https://www.bilibili.com/video/av51825449?from=search&seid=5320849185764424951)
  * [Docker 容器化实战项目（完）](https://www.bilibili.com/video/av58185419/?spm_id_from=333.788.videocard.0)
  * [尚硅谷Docker从入门到精通](https://www.bilibili.com/video/av67964765?from=search&seid=16448355563394202110)
  * [马哥Docker容器技术](https://www.bilibili.com/video/av57934753)
  * [Docker入坑教程【33集】](https://www.bilibili.com/video/av17854410/?p=2)
  * [项目实战&跟着我1小时学会Docker部署微服务](https://www.bilibili.com/video/av65306049/?spm_id_from=333.788.videocard.11)
  * [一小时学会Docker部署微服务](https://www.bilibili.com/video/av60467718/?spm_id_from=333.788.videocard.6)
  * [Docker实战docker镜像和容器的存储结构视频讲解](https://www.bilibili.com/video/av62373859/?spm_id_from=333.788.videocard.6)
  * [Docker+K8S+Jenkins项目实战视频教程（经典）](https://www.bilibili.com/video/av62049929/?spm_id_from=333.788.videocard.2)
  * [【尚硅谷】Java视频教程_Docker核心技术](https://www.bilibili.com/video/av30010765?from=search&seid=3633366878054862549)
  * [Docker零基础到CaaS集群部署（完](https://www.bilibili.com/video/av49671303?from=search&seid=15247674818172733793)
  * [2018黑马docker容器技术+k8s集群技术](https://www.bilibili.com/video/av35847195?from=search&seid=15247674818172733793)
  * [基于Docker架构Mysql集群实战](https://www.bilibili.com/video/av73770025?from=search&seid=4231697486262267816)
  * [基于Docker构建企业Jenkins CI平台](https://www.bilibili.com/video/av63925465/?spm_id_from=333.788.videocard.2)
  * [通过Amazon ECS轻松部署Docker容器](https://www.bilibili.com/video/av50493050?from=search&seid=10551429260496554172)
  * [IDEA部署springboot程序到docker上](https://www.bilibili.com/video/av40407605/?spm_id_from=333.788.videocard.14)
 * [Docker部署SpringBoot快速入门[千锋南京]【idea集成docker实现镜像](https://www.bilibili.com/video/av80606083?from=search&seid=6827222005976129424)
 * [使用 Docker 搭建第一个 Node 项目到服务器](http://dockone.io/article/9606)


# 有用的文档
* [还在百度Docker命令？推荐一套我用起来特顺手的命令！](http://www.macrozheng.com/#/reference/docker_command)
* [docker部署vue项目](https://www.jianshu.com/p/03dde86ebd4e)
* [Docker部署SpringBoot+Vue前后端分离项目](https://www.jianshu.com/p/85b4665530cf)
* [docker搭建Kafka集群及监控、可视化部署实战](https://www.jianshu.com/p/7ccf0a316676)
* [万字长文：Docker容器安全性分析](https://mp.weixin.qq.com/s/1qVUlUNR7qVyby_c4vfrFg)
* [Kubernetes vs Docker：2021年容器有哪些变化？](https://posts.careerengine.us/p/614df9961153ea348fcebd8a?from=latestPostSidePanel)
* [IDEA的Docker插件]
  * [IDEA中使用Docker插件](https://mrbird.cc/IDEA-Docker-Plugin.html)
  * [IDEA的Docker插件实战(Dockerfile篇)](https://blog.csdn.net/boling_cavalry/article/details/100051325)
  * [IDEA的Docker插件实战(Docker Image篇)](https://xinchen.blog.csdn.net/article/details/100062008)
  * [IDEA的Docker插件实战(Docker-compose篇)](https://xinchen.blog.csdn.net/article/details/100064934)
* [Docker 和 Kubernetes：给程序员的快速指南](https://zhuanlan.zhihu.com/p/39937913)
* [既然有了Docker， 为什么还要Kubernetes](https://zhuanlan.zhihu.com/p/77308665)
* [Docker---从入门到实战](https://yeasy.gitbooks.io/docker_practice/network/port_mapping.html)
* [使用 Docker 搭建 Java Web 运行环境](https://my.oschina.net/huangyong/blog/372491)
* [docker中文社区](http://www.docker.org.cn)
* [使用docker部署SpringCloud项目](https://www.javazhiyin.com/39846.html)
* [docker在windows下的安装](https://www.jianshu.com/p/a2184c4a6f5b)
* [indows 10 安装 Docker for Windows](https://www.cnblogs.com/rolandlee/p/10106998.html)
* [6大分类，17大有用的Docker工具](http://dockone.io/article/8887)
* [Oracle Database Server 12 Docker Image ](https://hub.docker.com/u/gzpengli/content/sub-6f6dd5fd-1fb8-414b-858a-cc1e44a6a12c)
* [Docker构建ELK Docker集群日志收集系统](https://www.jb51.net/article/96913.htm)
* [解决centos7 docker1.9 没有配置文件](https://blog.csdn.net/qq_34173549/article/details/79820251)
* [新版docker启动配置文件不生效问题](https://blog.csdn.net/zz_15127160921/article/details/80408644)
* [CentOS 7 配置Docker 远程API访问](https://blog.csdn.net/hjh00/article/details/77816661)
* [docker配置文件以及各种问题汇总---随笔](https://blog.csdn.net/xxb249/article/details/79149783)
* [Docker环境搭建集成tomcat](https://cloud.tencent.com/developer/article/1408917?from=article.detail.1751679)
* [Docker Compose搭建mycat读写分离](https://blog.csdn.net/wang_jingj/article/details/54023892)
* [远程连接docker daemon，Docker Remote API](https://deepzz.com/post/dockerd-and-docker-remote-api.html)
* [详解docker使用阿里云Docker镜像库加速(修订版)](https://www.jb51.net/article/113041.htm)
* [docker-compose 安装FastDFS](http://www.dev-share.top/2019/11/13/docker-compose-%e5%ae%89%e8%a3%85fastdfs/)
* [docker、kubernetes安装部署fastdfs文件集群系统](http://www.dev-share.top/2019/12/04/docker%e3%80%81kubernetes%e5%ae%89%e8%a3%85%e9%83%a8%e7%bd%b2fastdfs%e6%96%87%e4%bb%b6%e9%9b%86%e7%be%a4%e7%b3%bb%e7%bb%9f/)
* [FastDFS数据迁移及常用命令](http://www.dev-share.top/2019/12/04/fastdfs%e6%95%b0%e6%8d%ae%e8%bf%81%e7%a7%bb%e5%8f%8a%e5%b8%b8%e7%94%a8%e5%91%bd%e4%bb%a4/)
* [使用Spring Boot创建docker image](https://cloud.tencent.com/developer/article/1739237?from=article.detail.1751679)
* [Docker容器可视化监控中心搭建](https://mp.weixin.qq.com/s?__biz=MzU4ODI1MjA3NQ==&mid=2247483763&idx=1&sn=6ceb9e73540b5016dadfb212636b3855&chksm=fdded7b7caa95ea1165b507397c39267d3bf7522c83cc8ed10eae4ee4a13db831eb58a3dc167&scene=21#wechat_redirect)
