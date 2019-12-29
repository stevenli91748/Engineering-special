
<details>
<summary> Machine、Swarm、Compose、SocketPlane这些Docker生态圈软件各解决了哪些问题？</summary>

Machine:

(https://docs.docker.com/machine/)：解决的是操作系统异构安装Docker困难的问题，没有Machine的时候，CentOS是一种，Ubuntu又是一种，AWS又是一种。有了Machine，所有的系统都是一样的安装方式。

Swarm:
(https://docs.docker.com/swarm/)：我们有了Machine就意味着有了docker环境，但是那是单机的，而通常我们的应用都是集群的。这正是Swarm要做的事情，给你提供docker集群环境和调度策略等。

Compose:
(https://docs.docker.com/compose/)：有了环境，我们下一步要做什么？部署应用啊。然后我们需要docker run image1、docker run image2...一次一次不厌其烦的重复这些操作，每次都写大量的命令参数。Compose简化了这个流程，只需要把这些内容固话到docker-compose.yml中。

目前Machine、Swarm、Compose已经可以结合使用，创建集群环境，简单的在上面部署应用。但是还不完善，比如对于有link的应用，它们只能跑在Swarm集群的一个机器上，即使你的集群有很多机器。可以参考(http://dockerone.com/question/105)。

SockerPlane:
SocketPlane是Docker最近收购的产品，猜想应该是为了强化Docker的网络功能，比如提供原生跨主机的网络定制、强化Swarm和Compose的结合等。
  
</details>




# 视频

[1. docker_swarm集群安装](https://www.bilibili.com/video/av66625778?from=search&seid=15247674818172733793)|[2. docker_swarm运行service replicas global](https://www.bilibili.com/video/av66637478?from=search&seid=15247674818172733793)|[3. docker如何实现servic伸缩](https://www.bilibili.com/video/av66656647?from=search&seid=15247674818172733793)|[4. 如何访问service](https://www.bilibili.com/video/av66658959?from=search&seid=15247674818172733793)|[5.swarm神奇的routingmesh](https://www.bilibili.com/video/av66658994?from=search&seid=15247674818172733793)|
---|---|---|---|---|

[6. service服务发现](https://www.bilibili.com/video/av66664948?from=search&seid=15247674818172733793)|[7. docker_swarm副本和全局](https://www.bilibili.com/video/av66664981?from=search&seid=15247674818172733793)|[8. 可持续化滚动更新](https://www.bilibili.com/video/av66669308?from=search&seid=15247674818172733793)|[9. lable调度Service容器](https://www.bilibili.com/video/av66669444?from=search&seid=15247674818172733793)|
---|---|---|---|
