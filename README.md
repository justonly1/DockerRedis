# DockerRedis

本环境是redis未授权访问漏洞环境，可以使用该环境练习重置/etc/passwd文件从而重置root密码
在docker下搭建


也可直接使用docker search ju5ton1y来搜索我已经做好的镜像

镜像开放两个端口，分别为6379和22

容器搭建好之后需要进入容器重启ssh服务
/etc/init.d/ssh restart
