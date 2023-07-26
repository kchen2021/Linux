# Reinstall yum

#### 介绍
升级Python2.7.5 到3.7 导致的 yum 无效

#### 命令
1. 查看已安装的yum

```
rpm -qa|grep yum
```

2. 删除已有的yum

```
rpm -aq|grep yum|xargs rpm -e --nodeps
```
3. 下载以下安装包

```
wget http://tel.mirrors.163.com/centos/7/os/x86_64/Packages/python-2.7.5-89.el7.x86_64.rpm
wget http://tel.mirrors.163.com/centos/7/os/x86_64/Packages/python-iniparse-0.4-9.el7.noarch.rpm
wget http://tel.mirrors.163.com/centos/7/os/x86_64/Packages/yum-3.4.3-168.el7.centos.noarch.rpm
wget http://tel.mirrors.163.com/centos/7/os/x86_64/Packages/yum-metadata-parser-1.1.4-10.el7.x86_64.rpm
wget http://tel.mirrors.163.com/centos/7/os/x86_64/Packages/yum-plugin-fastestmirror-1.1.31-54.el7_8.noarch.rpm

如果找不到以上版本，可以到http://tel.mirrors.163.com/centos/7/os/x86_64/Packages/下载最新版本
```
4. 安装
```
rpm -ivh python-2.7.5-89.el7.x86_64.rpm python-iniparse-0.4-9.el7.noarch.rpm --nodeps --force
rpm -ivh yum-metadata-parser-1.1.4-10.el7.x86_64.rpm --nodeps --force
rpm -ivh yum-3.4.3-168.el7.centos.noarch.rpm yum-plugin-fastestmirror-1.1.31-54.el7_8.noarch.rpm --nodeps --force
```
5. 更改yum源

i.备份、下载配置文件

```
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```

ii.运行以下命令更新缓存

```
yum clean all
yum makecache
```

ref https://www.cnblogs.com/zhuifengshaonianxxyd/p/16550704.html
