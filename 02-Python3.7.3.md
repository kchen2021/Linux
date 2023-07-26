# Instal Python3.7.3

####  介绍

在centos7里面默认的python的版本是2.7.5，但是我们需要使用的python版本是3.7+

#### 升级命令如下


```
# 切换到root用户
su - root

# 下载安装包
wget https://www.python.org/ftp/python/3.7.3/Python-3.7.3.tgz

# 解压文件
tar -zxvf Python-3.7.3.tgz

# 安装依赖包
yum install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gcc libffi-devel

# 进入Python目录
cd Python-3.7.3

# 编译
./configure --prefix=/usr/local/python3.7.3

# 安装
make && make install

# 备份默认Python2
mv /usr/bin/python /usr/bin/python.bak

# 创建新的软链接
ln -s /usr/local/python3.7.3/bin/python3.7 /usr/bin/python

# 查看版本
python -V
Python 3.7.3

```

