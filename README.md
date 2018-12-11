# Engineering-special
项目工程化专题


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

---


# 后端工程化
---

# 敏捷开发模式

## 敏捷开发的自动化流程

  *  持续集成
  *  持续交付
  *  持续部署
  
###  敏捷开发自动化工具

   *  分布式版本控制工具--Git
   *  持续集成和持续交付工具---Jenkins
   *  基础平台管理工具--SaltStack
   *  Docker 容器化工具
  

