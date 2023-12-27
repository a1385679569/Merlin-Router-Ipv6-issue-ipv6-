# Merlin-Router-Ipv6-issue-ipv6-
部分使用梅林固件或华硕路由器的用户在光猫桥接时，路由器PPPOE拨号获取IPV6地址经常出现一些小的问题，常表现在ipv6-stateless模式可以正常获取ipv6地址与网关并正常分配，但在stateful模式获取不了ipv6网关的情况。
基于此做此开机自动获取网关命令。
方法1：管理员权限连接路由器（WEBSHELL，SCP，PUTTY等）。
键入命令
ip -6 route add 0::/0 dev ppp0
ip -6 route add default dev ppp0 metric 1
回车即可。但每次重新启动会失效。

方法2：
下载wan-start文件，移动至/jffs/scripts/，替换原文件。设置脚本命令开机启动，stateful模式可正常获取IPV6地址和网关。
