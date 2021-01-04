
# MAVEN 安装


    1.下载

	2.解压1所下载文件，本人解压到：c:\apache-maven-3.5.0

	3.配置Maven环境变量

	解压完毕后就是配置环境变量了，在桌面我的电脑上右键点击“属性”，“高级系统设置”，“环境变量”，新建系统变量名为“MAVEN_HOME”，地址为你刚刚解压的maven目录。

			a. MAVEN_HOME : C:\apache-maven-3.5.0

			b.PATH : %MAVEN_HOME%\bin;

			c. MAVEN_OPTS : -Xms128m -Xmx512m -Duser.language=zh -Dfile.encoding=UTF-8 （如果没有在本机这设置该变量，可在IDEA中设置）

	4.在CMD中输入mvn -v,如出现下列信息，表示配置成功。

	其中会显示Java 配置环境以及Maven配置环境

# 设置Maven本地仓库路径

  本地仓库的地址默认为${user.home}/.m2/repository，这个 user.home 在 Windows 下一般就是 C 盘 Users 文件夹中以自己登录的那个用户名命名的文件夹。
  但是可在在你刚刚解压的maven目录( C:\apache-maven-3.5.0 )下找conf目录，下面有个settings.xml文件，打开它
  
      <localRepository> f:\MavenlocalRepository </localRepository>
  
  我把maven的本地仓库路径设为 f:\MavenlocalRepository，本地仓库是装载了在 pom 文件中添加的依赖包的物理文件所在位置，如果在 pom 文件中添加了依赖，可是并没有什么反应，IDEA 反而会把它标红。
  这是因为对应的包在本地仓内找不到， 需要采取以下步骤：
  
  1. 先到 project setting 中设置， 我选已经安装在机上的JDK版本1.8.0
  
  <a href="https://ibb.co/Z2fj6c6"><img src="https://i.ibb.co/3RT3ySy/maven1.png" alt="maven1" border="0"></a>
  
  2. 我们需要调整 IDEA 的设置，依次点击“File”—>“Settings”->"Build, execuition,deployment"，
  
<a href="https://ibb.co/N6WWLgC"><img src="https://i.ibb.co/XZFFzfL/maven3.png" alt="maven3" border="0"></a>

（检查maven仓库配置是否正确）检查Maven directory，local repository的配置和settings.xml中配置的仓库地址是否一致，如果不是选用IDEA默认的Maven版本,而是选用自己安装的Maven版本的话就必需要
 勾选“Override”
    
 
    
  
  3. “File”—>“Settings”->"Build, execuition,deployment"->“Maven”->"Importing"之后在 Maven 选项卡中找到“Importing”一项，勾选“Import Maven projects automatically” 和 选择 
      对的版本 在“ JDK FOR Importer:”

<a href="https://ibb.co/ZgNTGF4"><img src="https://i.ibb.co/M19NZtw/maven5.jpg" alt="maven5" border="0"></a>

  4. 在IDEA 中 打开编译器右边的maven管理工具(重新导包），点击reimport all maven projects。所有在POM文件中报红的依赖项目(表示该依赖包没有下载到本地仓库)会从setting.xml文件中的mirror指定
     的境像地址下载需要的包
     
     setting.xml文件：
     
		  <mirrors>
		    <mirror>
		      <id>usacentral</id>
		      <mirrorOf>central</mirrorOf> 
		      <name>Central Repository</name> 
		      <url>https://repo1.maven.org/maven2</url>
		    </mirror>  
		  </mirrors>
  
  <a href="https://ibb.co/qg952HY"><img src="https://i.ibb.co/Ks7w8tx/maven4.png" alt="maven4" border="0"></a>


maven安装好了，我们需要来设置一下代理服务器

 在你刚刚解压的maven目录下找conf文件夹，下面有个settings文件，打开它，找到<mirror>标签，添加下列代码
  
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
   
