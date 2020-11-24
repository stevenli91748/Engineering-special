### 注意，Docker和VMware workstation 有冲突
### [冲突解决方法--Win10系统下提示VMware与Device/Credential Guard不兼容如何解决](http://www.win7zhijia.cn/win10jc/win10_20680.html)
### Docker服务端默认配置文件,docker1.12版本之前是修改vim /etc/default/docker的DOCKER_OPTS参数的，但是1.12之后docker建议在/etc/docker/daemon.json文件中修改docker启动参数，修改完后，通过   [root]# dockerd     命令启动守护进程
### Docker服务启动文件 ： /usr/lib/systemd/system/docker.service


[精尽 Docker 学习指南](http://svip.iocoder.cn/Docker/tutorials/)|
---|

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


# 目录
## 实验

[两款Docker可视化工具](https://zhuanlan.zhihu.com/p/149693508)|
---|

[Docker windows版本安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker%20windows/README.md)|[Docker Linux版本安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/docker%20for%20linux/README.md)|[Docker Compose安装]()|
---|---|---|

[在Docker安装MySQL](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装MySQL/README.md)|[在Docker安装Redis](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Redis/README.md)|[在Docker安装Tomcat](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Tomcat/README.md)|[在Docker安装Nginx](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Nginx/README.md)|
---|---|---|---|



[新版docker启动配置文件不生效问题](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker守护进程/新版docker启动配置文件不生效问题.md)|[Docker 不能启动](https://blog.csdn.net/w1316022737/article/details/83692701)|[Docker容器可视化监控中心搭建](https://mp.weixin.qq.com/s?__biz=MzU4ODI1MjA3NQ==&mid=2247483763&idx=1&sn=6ceb9e73540b5016dadfb212636b3855&chksm=fdded7b7caa95ea1165b507397c39267d3bf7522c83cc8ed10eae4ee4a13db831eb58a3dc167&scene=21#wechat_redirect)|[深入浅出大型互联网，企业开发运维利器-docker](https://www.bilibili.com/video/BV1MW411N7dV)|
---|---|---|---|


[在容器中部署静态网站](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在容器中部署静态网站/README.md)|[Docker的远程訪问](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker的远程訪问/README.md)|
---|---|

[基于docker+nginx+tomcat容器+mysql容器部署Java web项目实现负载均衡实战](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/实验/基于docker%2Bnginx%2Btomcat容器%2Bmysql容器部署Java%20web项目实现负载均衡实战.md)|[不用网络，创建一个点到点连接](https://yeasy.gitbooks.io/docker_practice/advanced_network/ptp.html)|
---|---|

[实战在Docker中使用CI/CD](https://yeasy.gitbooks.io/docker_practice/cases/ci/)|[如何调试 Docker](https://yeasy.gitbooks.io/docker_practice/appendix/debug.html)|[IDEA中使用Docker插件](https://mrbird.cc/IDEA-Docker-Plugin.html)|
---|---|---|

[如何查看Docker容器环境变量，如何向容器传递环境变量](https://juejin.im/post/6857283423380504584)|[使用docker五步搭建ELK日志收集分析系统](http://www.zimug.com/container/docker/%e4%bd%bf%e7%94%a8docker%e4%ba%94%e6%ad%a5%e6%90%ad%e5%bb%baelk%e6%97%a5%e5%bf%97%e6%94%b6%e9%9b%86%e5%88%86%e6%9e%90%e7%b3%bb%e7%bb%9f/.html)|
---|---|


# Docker 内存

* [一次 Docker 容器内大量僵尸进程排查分析](https://juejin.im/post/5e0002adf265da33dc7a3a1f)

---

## 参考实验

[Docker容器化部署尝试——多容器通信(node+mongoDB+nginx)](https://www.jb51.net/article/153042.htm)|[Docker容器使用jenkins部署web项目(总结)](https://www.jb51.net/article/146319.htm)|[docker部署rabbitmq集群的实现方法](https://www.jb51.net/article/144748.htm)|
---|---|---|

[docker的简单搭建(java/tomcat 环境)](https://www.cnblogs.com/lemon-flm/p/7039880.html)|[Docker 搭建 Tomcat + Mysql](https://www.cnblogs.com/primadonna/p/10411857.html)|[基于docker+nginx+tomcat容器+mysql容器部署Java web项目实现负载均衡实战](https://blog.csdn.net/liqz666/article/details/82222511)|
---|---|---|

[使用Docker部署tomcat、mysql、nginx静态服务器](https://blog.csdn.net/a745233700/article/details/80452862)|[如何在docker里搭建自己的云数据库](https://blog.csdn.net/liqz666/article/details/103277559)|
---|---|

[docker的各种配置](https://blog.csdn.net/qq_36688928/article/details/93164651)|[在Docker环境构建、打包和运行Spring Boot应用](http://dockone.io/article/9530)|[使用 docker 高效部署前端应用](https://github.com/shfshanyue/op-note/blob/master/deploy-fe-with-docker.md)|
---|---|---|

[Node 项目从构建到使用 Jenkins 与 Docker 实现自动化部署](http://dockone.io/article/9507)|[Docker部署Java项目持续集成？](http://dockone.io/question/283)|
---|---|

[Spring Boot项目部署在Docker中](https://itweknow.cn/blog-site/posts/e2232a75.html)|
---|

---

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


# Docker视频

[Docker跨主机通讯-overlay原理](https://www.bilibili.com/video/av66558776)|[跨主机通讯-overlay环境](https://www.bilibili.com/video/av66557496/?spm_id_from=333.788.videocard.0)|[创建overlay网络](https://www.bilibili.com/video/av66557604/?spm_id_from=333.788.videocard.1)|
---|---|---|

[跨主机通信-macvlan创建](https://www.bilibili.com/video/av66558990)|[跨主机通信-macvlan结构分析](https://www.bilibili.com/video/av66559633)|
---|---|

[docker监控走势图cAdvisor](https://www.bilibili.com/video/av66629451)|[Docker日志处理ELK](https://www.bilibili.com/video/av66570108)|[docker监控sysdig](https://www.bilibili.com/video/av66578934)|
---|---|---|

[docker-框架结构](https://www.bilibili.com/video/av68291802)|[docker-镜像分层结构](https://www.bilibili.com/video/av68292120)|[docker-镜像-缓存-排错](https://www.bilibili.com/video/av68292314)|[docker-最小镜像和base镜像](https://www.bilibili.com/video/av68292010)|
---|---|---|---|

[docker-registry本地仓库](https://www.bilibili.com/video/av68376632)|[docker-Dockerfile常用指令](https://www.bilibili.com/video/av68379090)|[docker-none&host网络类型](https://www.bilibili.com/video/av68773859)|
---|---|---|

[docker-搞懂状态与操作](https://www.bilibili.com/video/av68778961)|[docker-必须要懂的bridge网络](https://www.bilibili.com/video/av68782002)|[docker-内外网访问](https://www.bilibili.com/video/av68789710)|
---|---|---|

[docker-两类存储资源bindmount](https://www.bilibili.com/video/av68863431)|[docker-两类存储managevolume](https://www.bilibili.com/video/av68863536)|[docker_共享数据volumecontainer](https://www.bilibili.com/video/av68863619)|
---|---|---|

[docker_共享数据DatapackedVolumeContainer](https://www.bilibili.com/video/av68863724)|[docker_machine集中安装与管理](https://www.bilibili.com/video/av68953512)|[Docker_容器内启动systemd程序](https://www.bilibili.com/video/av70483806)|
---|---|---|

[容器的端口映射](https://www.bilibili.com/video/av17854410?p=12)|[Docker+Jenkins+Git集成持续部署](https://www.bilibili.com/video/av62369964/?spm_id_from=333.788.videocard.1)|
---|---|


# 视频

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
* [Docker Compose搭建mycat读写分离](https://blog.csdn.net/wang_jingj/article/details/54023892)
* [远程连接docker daemon，Docker Remote API](https://deepzz.com/post/dockerd-and-docker-remote-api.html)
* [详解docker使用阿里云Docker镜像库加速(修订版)](https://www.jb51.net/article/113041.htm)
