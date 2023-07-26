# Basic

1. 安装wget：
```
yum -y install wget
```

2. 安装gcc：
```
yum install gcc
```

3. 无法上网：
```
ls /etc/sysconfig/network-scripts

BOOTPROTO=dhcp
ONBOOT=yes

service network restart
```
4. 端口白名单

```
查看防火墙白名单：
firewall-cmd --list-ports
增加防火墙白名单：
firewall-cmd --permanent --add-port=8080/tcp
关闭端口命令
firewall-cmd --zone=public --add-port=80/tcp --permanent 
重新载入防火墙配置
firewall-cmd --reload

查看所有开启端口，查看防火墙，添加的端口也可以看到
firewall-cmd --list-all 
重启防火墙服务
systemctl restart firewalld.service
查看防火墙状态
systemctl status firewalld 
```



