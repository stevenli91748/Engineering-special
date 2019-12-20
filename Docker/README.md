# 注意，Docker和VMware workstation 有冲突
# [冲突解决方法--Win10系统下提示VMware与Device/Credential Guard不兼容如何解决](http://www.win7zhijia.cn/win10jc/win10_20680.html)

# 目录

[Docker windows版本安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker%20windows/README.md)|[Docker Linux版本安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/docker%20for%20linux/README.md)|
---|---|

[在Docker安装MySQL](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装MySQL/README.md)|[在Docker安装Redis](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Redis/README.md)|[在Docker安装Tomcat](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Tomcat/README.md)|[在Docker安装Nginx](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Nginx/README.md)|
---|---|---|---|

---

Go|[Swarm-管理docker集群](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Swarm/README.md)|[Compose-管理docker容器的应用部署](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Compose/README.md)|[Machine-安装docker](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Machine/README.md)|
---|---|---|---|

[Mesos-高可用的集群管理](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Mesos/README.md)|[Kubernetes-容器集群管理](https://github.com/stevenli91748/Big-Data/blob/master/Kubernetes/README.md)|CI/CD|Jenkinds|
---|---|---|---|

---

Docker镜像|Docker容器|[Docker网络](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker网络/README.md)|[Docker存储](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/Docker%E5%AD%98%E7%A1%80/README.md)|[容器网络](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/容器网络/README.md)|容器监控|
---|---|---|---|---|---|

[Docker Daemon守护进程](https://docs.docker.com/engine/reference/commandline/dockerd/)|
---|

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

# 有用的文档

* [使用docker部署SpringCloud项目](https://www.javazhiyin.com/39846.html)
* [docker在windows下的安装](https://www.jianshu.com/p/a2184c4a6f5b)
* [indows 10 安装 Docker for Windows](https://www.cnblogs.com/rolandlee/p/10106998.html)
* [6大分类，17大有用的Docker工具](http://dockone.io/article/8887)
* [Oracle Database Server 12 Docker Image ](https://hub.docker.com/u/gzpengli/content/sub-6f6dd5fd-1fb8-414b-858a-cc1e44a6a12c)
