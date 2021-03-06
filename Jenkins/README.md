# 目录

[精尽 Jenkins 学习指南](http://svip.iocoder.cn/Jenkins/tutorials/)|
---|



* [Jenkins 概述](#Jenkins-概述)


# 知识点

认识Jenkins持续集成

详解持续集成概念

详解Jenkins

Pipeline体系

动手搭建Jenkin是持续集成环境

构建环境配置

配置自动部署

远程仓库推送

自动触发构建

自动项目部署

集成Maven、Git

多环境发布

Jenkins插件体系

常用插件安装与使用

插件开发

# 内容
## Jenkins 概述

当我们使用微服务架构后，随着业务的逐渐发展，系统之间的依赖关系会日益复杂，而且各个模块的构建顺序都有所讲究。对于一个小型系统来说，也许只有几个模块，
那么你每次采用人肉构建的方式也许并不感觉麻烦。但随着系统业务的发展，你的系统之间的依赖关系日益复杂，子系统也逐渐增多，每次构建一下你都要非常小心谨慎，
稍有不慎整个服务都无法正常启动。而且这些构建的工作很low，但却需要消耗大量的精力，这无疑降低了开发的效率。不过没关系，Jenkins就是来帮助你解决这个问
题的。

我们只需在Jenkins中配置好代码仓库、各个模块的构建顺序和构建命令，在以后的构建中，只需要点击“立即构建”按钮，Jenkins就会自动到你的代码仓库中拉取最新
的代码，然后根据你事先配置的构建命令进行构建，最后发布到指定的容器中运行。你也可以让Jenkins定时检查代码仓库版本的变化，一旦发现变动就自动地开始构建
过程，并且让Jenkins在构建成功后给你发一封邮件。这样你连“立即构建”的按钮也不需要按，就能全自动地完成这一切构建过程

# 视频

  * [基于Docker构建企业Jenkins CI平台](https://www.bilibili.com/video/av63925465/?spm_id_from=333.788.videocard.2)
  * [企业如何构建CICD流水线](https://www.bilibili.com/video/av52572586/?spm_id_from=333.788.videocard.2)
  * [Docker+Jenkins集成持续部署](https://www.bilibili.com/video/av62369964/?spm_id_from=333.788.videocard.8)
  * [jenkins集成github实现项目自动部署](https://www.bilibili.com/video/av35343775/?spm_id_from=333.788.videocard.7)
  
  
