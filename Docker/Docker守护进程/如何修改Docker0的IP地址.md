# 修改docker的守护进程docker0的IP地址

[root]# ifconfig docker0 192.168.28.166 netmask 255.255.255.0

[root]# ip addr show

ens33 192.168.28.166

但是如果重启docker, docker0又重新恢复到以前的默任IP 172.17.0.1


# 有用的参考

* [修改docker0默认IP的正确姿势](https://blog.csdn.net/oliverlyn/article/details/96437364)
* [如何修改Docker0的IP地址](https://blog.csdn.net/gaopan20080808/article/details/77431880)
