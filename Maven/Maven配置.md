1. 下载

2. 解压完毕后就是配置环境变量了，在桌面我的电脑上右键点击“属性”，“高级系统设置”，“环境变量”，新建系统变量名为“M2_HOME”，地址为你刚刚解压的maven目录。

3. 然后找到“path”添加“%M2_HOME%\bin”

4. 以上步骤做完后，启动命令行窗口来验证一下安装是否正确。输入“mvn -version”

5. maven安装好了，我们需要来设置一下代理服务器

6. 在你的maven目录下找conf文件夹，下面有个settings文件，打开它，找到<mirror>标签，添加下列代码
  
        <mirror>
          <id>nexus-aliyun</id>
          <mirrorOf>central</mirrorOf>
          <name>Nexus aliyun</name>
           <url>http://maven.aliyun.com/nexus/content/groups/public</url>   //国内的下载中心
           <url>http://repo.maven.apache.org/maven2
	</mirror>

7. maven默认的本地的仓储位置是在c盘你的用户名下的“.m2”文件夹中，如果不想让它把从网上下载下来的jar包存在c盘，可以修改其默认仓储位置，依旧是找到刚才的settings文件，找到这行修改为：

       <localRepository>f:\MavenlocalRepository</localRepository>
  
  这样我们就把默认的jar存储位置改在了f盘的repository目录下

很容易你就发现了springframework，里面存放了spring框架所使用的基本上所有的jar包，

8. 设置JDK 的版本号

   在你的maven目录下找conf文件夹，下面有个settings文件，打开它，找到<Profiles>标签，添加下列代码
   
  <profile>
       <id>jdk-1.8</id>
       <activation>
         <activeByDefault>true</activeByDefault>
         <jdk>1.8</jdk>
       </activation>
       <properties>
	   <maven.compiler.source>1.8</maven.compiler.source>
	   <maven.compiler.target>1.8</maven.compiler.target>
	   <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>
       </properties>
  </profile>
   
