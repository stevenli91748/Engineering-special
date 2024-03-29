# Engineering-special
项目工程化专题

[从零搭建后台技术栈，让你提升一个层次](https://www.jianshu.com/p/41ebad81b5eb)|
---|

# [DevOps 开发](https://github.com/stevenli91748/DevOps-Develope/blob/main/README.md)
# [Jenkins](https://github.com/stevenli91748/JAVA-Architecture/blob/master/Jenkins/README.md)

[GitLab CI/CD 预定义环境变量说明](http://www.dev-share.top/2019/06/14/gitlab-ci-cd-%e9%a2%84%e5%ae%9a%e4%b9%89%e7%8e%af%e5%a2%83%e5%8f%98%e9%87%8f%e8%af%b4%e6%98%8e/)|[Gitlab 备份](http://www.dev-share.top/2019/03/06/gitlab-%e5%a4%87%e4%bb%bd/)|[Centos7 安装 Gitlab Runner](http://www.dev-share.top/2019/02/16/centos7-%e5%ae%89%e8%a3%85-gitlab-runner/)|
---|---|---|

# 前端工程化

[Web前端工程化](https://www.kancloud.cn/chandler/web_technology/344206)|[前端工程化学习笔记](https://www.kancloud.cn/cyyspring/webpack/2287656)|[工程化](https://www.kancloud.cn/xiaobai2/wgt2/2229665)|
---|---|---|

[前端工程化指南](https://www.kancloud.cn/csnikey/fepro-guide)|[前端工程化从入门到进阶 付费](https://www.kancloud.cn/gzamon/feed/2100253)|
---|---|


# [项目工程化面试](https://github.com/stevenli91748/Engineering-special/blob/master/Interview/README.md)


* [套路拆解:大厂是如何保证代码质量的！](https://www.youtube.com/watch?v=k7HgdYoLri8)
* [如何提高工作效率？如何写出高质量的代码？如何成长](https://www.youtube.com/watch?v=H06N-WqldZ0)
* [大,小公司程序员的工作差别到底在哪 ](https://www.youtube.com/watch?v=oINHdLEDmOk)
* [大厂程序员是如何做敏捷开发的?大公司程序员编程开发流程|大公司是如何快速响应用户需求并实现产品的持续交付](https://www.youtube.com/watch?v=Mb6WHtja2fs)
* [项目研发流程规范](https://www.jianshu.com/p/ece3cec561af)


# 前端工程化

---
1.  脚手架
2.  构建
3.  本地开发服务器
       * 动态构建
       * Mock 服务
4.  持续集成流程
      * 4.1.  静态代码检查（linting）
        * 4.1.1.  ESLint：静态代码检查工具
      * 4.2.  测试（testing）
        * [2020 软件测试教程](https://www.kancloud.cn/apachecn/guru99-zh/1953496)
          * [2020 年 15 种最佳测试数据生成工具](https://www.kancloud.cn/apachecn/guru99-zh/1953679) 
            * [mysql数据库的免费测试数据生成器](https://www.coder.work/article/144956)
          * [软件测试全套教程](https://www.bilibili.com/video/av69230181/?spm_id_from=333.788.videocard.0) 
        * 4.2.1.  单元测试（unit testing）
        * 4.2.2.  功能测试（feature testing）
        
                  功能测试必须在真正浏览器做，现在有四种方法。
                  
                  * 4.2.2.1.  使用本机安装的浏览器
                  * 4.2.2.2.  使用 Selenium Driver
                  * 4.2.2.3.  使用 Headless Chrome
                  * 4.2.2.4.  使用 Electron,使用 Electron 模拟真实浏览器环境 提供大量人性化、易用的 API 官网：nightmarejs.org
                  
        * 4.2.3.  集成测试（integration testing）
        * 4.2.4.  端对端测试 (End-to-End testing）
        * 4.2.5.  Mocha 测试框架
        * 4.2.6.  移动平台的自动化测试 目前，最常见的方案是使用 Appium。  
        
                  1. 基于 WebDriver
                  2. 采用 客户端/服务器架构
                  3. 可以在模拟器运行，也可以在真机运行 
                  
      * 4.3.  合并进入主干（merging）
      * 4.4.  自动构建（building） 
      
              代码合并进主干以后，就可以进行自动构建和发布了。网上有很多 PaaS 平台，提供持续集成服务。
              Travis CI 就是其中最著名的一个，它可以根据你提供的脚本，自动完成构建和发布
      
      * 4.5.  自动发布（publishing）
      
5.  部署
    

# 前后端分离，接口API开发(RESTful API)

## API网关概述



### 实现API网关 
可以使用各种不同的技术来实现可扩展的API网关。在JVM上，您可以使用基于NIO的框架之一，例如Netty，Vertx，Spring Reactor或JBoss Undertow。一个
流行的非JVM选项是Node.js，它是一个建立在Chrome的JavaScript引擎上的平台。另一个选择是使用NGINX Plus。 NGINX Plus提供成熟，可扩展，高性能的
Web服务器和反向代理，易于部署，配置和编程。 NGINX Plus可以管理身份验证，访问控制，负载均衡请求，缓存响应，并提供应用感知的健康检查和监控。

使用传统的异步回调方法编写API组合代码很快会将您的回调带入地狱。代码会纠缠不清，难以理解，容易出错。一个更好的方法是使用反应性方法以声明式编写API网关代码。反应抽象的例子包括未来的Scala，Java 8中的CompletableFuture和JavaScript中的Promise。还有Reactive Extensions（也称为Rx或ReactiveX），最初由Microsoft为.NET平台开发。 Netflix为JVM创建了RxJava，专门用于其API网关。还有用于JavaScript的RxJS，它们都在浏览器和Node.js中运行。使用反应式方法将使您能够编写简单而有效的API网关代码。

### API 服务调用 

基于微服务的应用程序是一个分布式的系统，它必须使用进程间通信机制。有两种进程间通信的风格。一种选择是使用基于消息传递的异步机制。一些实现使用诸如JMS或AMQP的消息代理。其他的诸如Zeromq，是无Broker化的服务间的直接通信。进程间通信的另一种风格是HTTP或Thrift之类的同步机制。系统通常将使用异步和同步模式。它甚至可以使用每个样式的多个实现。因此，API网关将需要支持各种通信机制。


### API服务发现 

API网关需要知道与其通信的每个微服务的位置（IP地址和端口）。在传统的应用程序中，您可能会将这些位置硬编码，但在现代的基于云的微服务应用程序中，这是一个非常重要的问题。基础设施服务（例如消息代理）通常将具有静态位置，可以通过OS环境变量来指定。但是，确定应用程序服务的位置并不那么容易。应用服务具有动态分配的位置。此外，由于自动缩放和升级，服务的一组实例会动态地更改。因此，API网关与系统中的任何其他服务客户端一样，需要使用系统的服务发现机制：服务器端发现或客户端发现。稍后的文章将更详细地描述服务发现。现在值得注意的是，如果系统使用客户端发现，则API网关必须能够查询服务注册，服务注册是所有微服务实例及其位置的数据库。

### 处理部分失效 

实现API网关时必须解决的另一个问题是部分故障的问题。每当一个服务调用另一个缓慢响应或不可用的服务时，所有分布式系统都会出现此问题。 API网关不应无限期地等待下游服务。但是，如何处理故障取决于特定方案和哪些服务失败。例如，如果推荐服务在产品详细信息方案中无响应，则API网关应将剩余的产品详细信息返回给客户端，因为它们对用户仍然有用。建议可以是空的，也可以由例如硬编码的前十名列表替代。但是，如果产品信息服务无响应，则API网关应向客户端返回错误。  

如果可用，API网关还可以返回缓存的数据。例如，由于产品价格变化不大，如果定价服务不可用，API网关可能会返回缓存的定价数据。数据可以由API网关本身缓存或存储在外部缓存中，如Redis或Memcached。通过返回默认数据或缓存数据，API网关确保系统故障不会影响用户体验。

Netflix Hystrix是一个令人难以置信的有用的库，用于编写调用远程服务的代码。 Hystrix对超出指定阈值的请求进行超时限制。它实现了断路器模式，这阻止了客户端不必要地等待无响应的服务。如果服务的错误率超过指定的阈值，Hystrix将跳闸断路器，所有请求将在指定的时间内立即失败。 Hystrix允许您在请求失败时定义回退操作，例如从缓存读取或返回默认值。如果您使用的是JVM，那么您一定要考虑使用Hystrix。而且，如果您运行在非JVM环境中，则应使用等效的库。 

总结

对于大多数基于微服务的应用程序，实现一个API网关是有意义的，API网关充当系统的单个入口点。 API网关负责请求路由，组合和协议转换。它为应用程序的每个客户端提供了一个自定义API。 API网关还可以通过返回缓存或默认数据来掩盖后端服务中的故障

 * [REST与RESTFul API最佳实践](https://www.itjc8.com/thread-628-1-1.html)
 * [一个简单可参考的 API 网关架构设计](https://www.infoq.cn/article/api-gateway-architecture-design)
 * [有赞API网关实践](https://tech.youzan.com/api-gateway-in-practice/)
 * [使用API网关构建微服务--实际例子](https://cloud.tencent.com/developer/article/1032069?fromSource=waitui)
 * [八步部署NGINX Plus API网关](https://zhuanlan.zhihu.com/p/38359208?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
 * [Building Microservices: Using an API Gateway](https://www.nginx.com/blog/building-microservices-using-an-api-gateway/)
 * [一个非常适合IT团队的在线API文档、技术文档工具](https://yun.gw.com.cn/doc/#/)
 * [异步 API 的设计](http://www.ruanyifeng.com/blog/2018/12/async-api-design.html)
 * [springboot综合项目练习三定义微服务接口返回规范](https://blog.csdn.net/chenhaotao/article/details/86500548)
 * [微服务RESTful 接口设计规范](https://blog.csdn.net/zl1zl2zl3/article/details/73867113)
 * [前后端分离购物网站—技术选型](https://blog.csdn.net/qq_39206806/article/details/81320826)
 * [JavaWeb项目前后端分离](https://blog.csdn.net/xiaoyangsavvy/article/details/80476703) 
 * [使用RAP2和Mock.JS实现Web API接口的数据模拟和测试](https://www.cnblogs.com/wuhuacong/p/10213540.html)
 * [Web API应用架构设计分析](http://www.uml.org.cn/net/201507222.asp?artid=16667)
 * [从接入层入手，设计高并发的微服务架构？](http://developer.51cto.com/art/201803/567754.htm)
 * [在基于MVC的Web项目中使用Web API和直接连接两种方式混合式接入](https://www.cnblogs.com/wuhuacong/p/5850482.html)
 * [架构设计（4）--API网关](https://blog.csdn.net/hguisu/article/details/79143584)
 * [统一接入层方案](https://blog.csdn.net/JeamKing/article/details/73695200)
 * [一个简单可参考的 API 网关架构设计](https://www.infoq.cn/article/api-gateway-architecture-design)
 * [一切皆API的大环境下，如何打造API Everything](https://dbaplus.cn/news-141-1815-1.html)
 * [基于 Spring Boot 的 Web API 项目的安全设计](https://www.ctolib.com/topics-132196.html)
 * [一个完善的 API 流程标准（草图）](https://segmentfault.com/a/1190000008243832)
 * [设计微服务应用层和 Web API](https://docs.microsoft.com/zh-cn/dotnet/standard/microservices-architecture/microservice-ddd-cqrs-patterns/microservice-application-layer-web-api-design)
 * [使用 Web API 实现微服务应用层](https://docs.microsoft.com/zh-cn/dotnet/standard/microservices-architecture/microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api)
 * [企业级API网关的设计](https://www.jianshu.com/p/84dcce30f7c9)
 * [微服务架构为何需要搭配API网关](https://blog.csdn.net/belalds/article/details/80913504)
 * [微服务与API网关（上）: 为什么需要API网关](http://blog.didispace.com/hzf-ms-apigateway-1)
 * [微服务与API 网关（下）- Kong能为我们做什么？](http://blog.didispace.com/hzf-ms-apigateway-2)
 * [百亿流量 API 网关设计与实践](https://gitbook.cn/books/5bbb3d2a61d11c2d996be26b/index.html)
 * [为什么需要API网关，如何设计API网关](https://www.eefocus.com/communication/423672)
 * [浅谈三种API设计风格RPC、REST、GraphQL](https://zhuanlan.zhihu.com/p/56955812)
 * [spring 指南系列 如何更好的设计RESTful API](https://zhuanlan.zhihu.com/p/24592119)
 * [Google Cloud 的 API 设计](https://zhuanlan.zhihu.com/p/27458970)
 * [web项目前后端开发过程和体会](https://blog.csdn.net/gu_ude_god/article/details/81570544)
 * [构建SpringMVCRestful前后端分离项目实例](https://blog.csdn.net/songxinjianqwe/article/details/54976251)
 * [Docker 对前后端分离项目的部署和运维（详述）](https://blog.csdn.net/qq_35394891/article/details/83027804)
 
 


---


# 后端工程化
---


# [Java 后端团队统一编码规范](http://www.youmeek.com/java-web-coding-specification/)

* [后端项目构建流程](#后端项目构建流程概述)
* [后端项目规范](#后端项目规范)
* [后端项目工具链](#后端项目工具链)
* [后端自动化部署方案---俗称一键部署](#后端自动化部署方案)


# 后端项目构建流程

  整个过程可以分成以下14个步骤：
1.
2. [开发工具](https://weread.qq.com/web/reader/71032d60719ad5af7104ca2k6f4322302126f4922f45dec)
3. 项目立项
4. 产品设计
5. 需求分析
6. 技术方案评审
7. 接口设计
8. 数据库设计
   * [研发库表设计规范](https://www.jianshu.com/p/4b0d82c817fa)
9. 开发
  * Web应用代码开发的步骤---[一个列子让你弄懂SpringBoot实现后台框架的搭建](https://blog.csdn.net/qq_33883389/article/details/81322481)
    * step 1 首先项目搭建---IDEA 
      * 记住Application文件一定要在根目录底下不然程序会运行不起来的 
    * step 2 然后开始新建包
      * constant :常量包，存放一些常量数据，如定义服务器响应状态码。
      * controller: 控制器，存放各种控制器，来提供数据或者返回界面
      * entity：实体类包，存放各种与数据库对应的实体类
      * mapper:存放各种与数据库映射的类
      * modle:封装返回数据json的格式样式
      * service:返回数据给控制调用
    * step 3 Application：程序的入口
      * @SpringBootApplication
      * @MapperScan("com.domain.mapper") 这个用来扫描当前项目的实体类的映射
    * step 4 POM文件的修改
    * step 5 配置application.yml文件
    * step 6 创建实体类层（entity）---创建对应每个表的实体类
    * step 7 封装一个（通用）json数据格式, 在modle目录中创建一个basemodel,在model目录中的其他的json模板继承他就可以了
    * step 8 在modle目录中创建各种model的json数据层
    * step 9 开始写我们的Mapper层（操作数据库层）
    * step 10 再写我们的Service层（调用Mapper层来完成相应操作）
    * step 11 再写Controller层 
  * 7.1 写完代码自行验证
  * 7.2 各种静态检查
    * [java静态代码分析工具](https://weread.qq.com/web/reader/71032d60719ad5af7104ca2kaab325601eaab3238922e53)
      * Checkstyle
      * FindBugs
      * P3C---相对于FindBugs等其他工具，阿里巴巴推出的P3C插件对代码缺陷的描述及改进意见十分详细，是开发人员提升代码质量的必备工具
    * [代码审查](https://weread.qq.com/web/reader/71032d60719ad5af7104ca2k9bf32f301f9bf31c7ff0a60)
      * [Phabricator---Facebook的内部审查工具](https://weread.qq.com/web/reader/71032d60719ad5af7104ca2k9bf32f301f9bf31c7ff0a60)
      * [Gerrit---是Google为Android系统研发量身定制的一套免费的开源代码审查系统 ](https://weread.qq.com/web/reader/71032d60719ad5af7104ca2k9bf32f301f9bf31c7ff0a60)
  * 7.3 代码复杂度
  * 7.4 测试用例
  * 7.5 功能测试
10. 单元测试
11. GIT push 提交代码,触发CI(持续集成)流程，如果不能通过，打回到开发者
12. 人工代码审核，如果不能通过，打回到开发者
13. [集成测试(CI)/发布(CD)](https://github.com/stevenli91748/Engineering-special/blob/master/CI/README.md)
    * Github Actions
    * Travis CI
    * Jenkis
14. 联调
15. 构建
16. 回滚
17. 监控


# 后端项目规范

0. [研发库表设计规范](https://www.jianshu.com/p/4b0d82c817fa)
1. 编码规范
   * [软件研发代码规范](https://www.jianshu.com/p/93e3d991756b)
2. 接口规范
3. 数据规范
4. [GIT分支开发模型规范](https://www.jianshu.com/p/cbd8cf5e232d)
5. 日志规范
6. 安全规范
   * [软件研发安全规范](https://www.jianshu.com/p/a638bb1648b6)
7. 测试用例规范
8. bugfix规范
9. CI/CD系统
   * [Gitlab + Jenkins + k8s 实现企业 CI/CD 落地](https://www.jianshu.com/p/9c1eddec34bc)

# 后端项目工具链

1. 交付平台
2. 工作流平台
3. 构建平台(CI/CD)
4. Mock系统
5. 文档系统
6. 代码管理系统
7. 发布平台
8. 监控平台



# 后端自动化部署方案
  * 比较流行的一种就是Gitlab+Jenkins实现方案---不过这种方案占用内存比较大，没有个8G内存，很难流畅运行，而且部署起来也不快
    * [再见 Jenkins！几行脚本搞定自动化部署，这款神器有点厉害](https://www.jianshu.com/p/304d67c59110) 
    * [Devops自动化部署方案CICD-Jenkins&gitlab实践](https://www.jianshu.com/p/323284cb3ac2)
    * [Jenkins+gitlab 自动化构建部署maven项目](https://www.jianshu.com/p/31537cba1464)
  * Drone+Gogs---轻量级CI/DI工具，结合Gogs使用内存占用不到1G，几行脚本就能实现自动化部署
    * [再见 Jenkins！几行脚本搞定自动化部署，这款神器有点厉害](https://www.jianshu.com/p/304d67c59110) 



----

  1. 确定系统架构
  2. 收集框架相关的jar包
  3. 搭建 SSM 框架
  4. 编写代码
  5. 编译源代码
  6. 运行单元测试和集成测试
  7. 寻找框架依赖的jar包
  8. 剔除冲突jar包
  9. 执行静态代码分析、生成分析报告
  10. 创建发布版本
  11. 部署到目标环境
  12. 部署传递过程
  13. 执行冒烟测试和自动功能测试


# 敏捷开发模式
## 敏捷开发的自动化流程

  *  持续集成
  *  持续交付
  *  持续部署
  
###  敏捷开发自动化工具
   
   *  Maven
   *  分布式版本控制工具--Git
   *  持续集成和持续交付工具---Jenkins
   *  Sonar
   *  基础平台管理工具--SaltStack
   *  Docker 容器化工具
   
 # 视频
 
 [JavaEE进阶1—工程化专题](https://www.bilibili.com/video/av60638359/?spm_id_from=333.788.videocard.14)
   
   
   
 # 测试
 
 ##  [性能测试](https://blog.csdn.net/smooth00/article/category/6793945)
 
 ##  
 
   * [接口测试工具Postman接口测试图文教程](https://blog.csdn.net/niaonao/article/details/80998804)
   * [接口测试总结](https://blog.csdn.net/Lovejulyer/article/details/70544174)
   * [超详细——接口测试总结与分享](https://blog.csdn.net/qq_41370110/article/details/82825224)
  
# 有用的参考
* [程序员一般喜欢浏览哪些网站呢？](https://www.zhihu.com/question/283272958/answer/598956527?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
* [前端工程化](https://github.com/gzpengli/blog)
* [真实软件项目开发流程--从需求到开发的每一步骤](http://www.youmeek.com/java-sofaware-engineer/)
* [前端项目开发流程及技术选型](https://blog.csdn.net/hicoldcat/article/details/53995337)
* [前端构建：3 类 13 种热门工具的选型参考](https://blog.csdn.net/vM199zkg3Y7150u5/article/details/84901166)
* [前端项目开发流程](https://blog.csdn.net/xtaydwxf1988/article/details/75043753)
* [个人开发web应用，从需求设计，界面设计，数据库设计，API设计等，好的开发流程是怎么样的？](https://www.zhihu.com/question/24976128)
