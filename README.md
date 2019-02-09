# Engineering-special
项目工程化专题

# [项目工程化面试](https://github.com/stevenli91748/Engineering-special/blob/master/Interview.md)

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

 * [异步 API 的设计](http://www.ruanyifeng.com/blog/2018/12/async-api-design.html)
 * [springboot综合项目练习三定义微服务接口返回规范](https://blog.csdn.net/chenhaotao/article/details/86500548)
 * [微服务RESTful 接口设计规范](https://blog.csdn.net/zl1zl2zl3/article/details/73867113)


---


# 后端工程化
---
# [Java 后端团队统一编码规范](http://www.youmeek.com/java-web-coding-specification/)

# 项目构建流程概述

  整个过程可以分成以下几个步骤：

  1. 编译源代码
  2. 运行单元测试和集成测试
  3. 执行静态代码分析、生成分析报告
  4. 创建发布版本
  5. 部署到目标环境
  6. 部署传递过程
  7. 执行冒烟测试和自动功能测试


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
  
# 有用的参考
* [前端工程化](https://github.com/gzpengli/blog)
* [真实软件项目开发流程--从需求到开发的每一步骤](http://www.youmeek.com/java-sofaware-engineer/)
