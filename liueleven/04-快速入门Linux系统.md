# 快速入门Linux系统

### 文件
```
# ls -l
drwxr-xr-x 6 root root    4096 Oct 20  2017 apt
-rw-r--r-- 1 root root     211 Oct 20  2017 hosts
```
##### 第一个字段 drwxr-xr-x
表示文件类型，文件类型有很多，d表示目录，-表示普通文件，还有很多，后面再谈

剩下的9位是权限位，每3个一组，分别是用户权限；文件所属组权限；其它用户权限；一组的三个分别表示r读，w写，x执行权限，如果是-表示没有该功能的权限


##### 第二个字段 6
这个是硬链接的数目，后面再谈


##### 第三个字段 root
所属用户

##### 第四个字段 root
所属组

##### 第五个字段 4096
文件大小，默认是kb

##### 第六个字段 Oct 20
文件修改日期

### 权限
chown 改变所属用户

chgrp 改变所属组

### 包体系
Linux有两大包体系，一个是CentOS，一个是Ubuntu。CentOS用的是rpm，Ubuntu用的是deb

```
CentOS 安装
rpm xxxxxx.rpm

Ubuntu 安装
dpkg -i xxxxxxx.deb
```

使用rpm -qa查看当前系统安装的包，当然会很多,加管道可以过滤下
```
rpm -qa | grep jdk

dpck -l | grep jdk
```

删除
```
rmp -e xxxx.rpm // e 就是erase

dpkg -r xxxx.deb // r 就是remove
```

### 包管理工具
CentOS下的包管理工具是yum，Ubuntu的包管理工具是apt-get

CentOS仓库地址在：` /etc/yum.repos.d/CentOS-Base.repo`

Ubuntu仓库地址在：`/etc/apt/sources.list`
```
// 安装
yum install xxxx
apt-get install xxxx

// 卸载
yum erase xxxx
apt-get purge xxxx
```

### 下载
可以使用wget命令，后面跟下载链接就行
```
wget https://music.qq.com/xxxx.mp3
```

### 压缩格式
默认是tar,也可以使用zip命令，但这个需要额外安装

```
// 解压
tar -xzvf xxxx.tar.gz 
unzip xxxx.zip
// 打包
tar -czvf xxxx.tar.gz /home/*
zip -r xxxx.zip /home/*
```

### 运行程序
如果是可执行的直接执行就可以
```
jar xxx.jar

// 后台运行程序nohup,信息输出到out.file文件中
nohup jar xxx.jar > out.file 2>&1 &
``` 

### 查看进程
管道后面的grep接应用名称
```
ps -ef | grep java
```

### 关闭进程
```
kill -9 PID
```

### 关机
```
shutdown -h now
```

### 重启
```
reboot
```