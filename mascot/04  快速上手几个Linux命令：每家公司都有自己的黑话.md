# 04 | 快速上手几个Linux命令：每家公司都有自己的黑话

 Linux 的精髓在于命令行，这是和 windows 图形化界面是有很大的区别的，学习 Linux 建议从命令行开始。

## 用户和密码

Linux 的超级管理员用户是 root , 它拥有最高的权限，在安装系统时我们需要设置 root 的密码。

添加用户：

```shell
useradd xxx
```

注意添加用户是没有密码的，密码需要命令 passwd 其实就是 password 的简写

## 文件

Linux 的文件和文件夹是一种树状结构。

cd (change directory) 就是切换目录。cd .  表示切换到当前目录，cd ..  表示切换到上一级目录。

ls (list) 可以列出当前目录下的文件，一般常用的是 ls - l 就是用列表的方式列出。

```shell
# ls -l
drwxr-xr-x 6 root root    4096 Oct 20  2017 apt
-rw-r--r-- 1 root root     211 Oct 20  2017 hosts
```

第一个字段:  表示文件类型，文件类型有很多，d表示目录，-表示普通文件，还有很多，后面再谈

剩下的9位是权限位，每3个一组，分别是用户权限；文件所属组权限；其它用户权限；一组的三个分别表示r读，w写，x执行权限，如果是-表示没有该功能的权限

 第二个字段 :  这个是硬链接的数目，后面再谈

 第三个字段:  所属用户

第四个字段 :  所属组

第五个字段:  文件大小，默认是kb

 第六个字段 :   文件修改日期。

命令 chown 改变所属用户 ， 命令 chgrp 改变所属组。

## 安装软件

CentOS 下软件包格式为 rpm。安装软件的命令为 `rpm -i xxxx.rpm`。`-i` 就是 install 的意思。

`rpm -qa` 用来查看安装的软件列表，其中 -q 就是 query，a 就是 all。

那么，如何删除呢？使用 `rpm -e`，`-e` 就是 erase 的意思。

CentOS 上有个软件管理工具叫作 `yum`。它上面有很多软件可以供我们直接安装使用。

`yum search xxx` 用来搜索软件；`yum install xxx` 用来安装；`yum erase xxx` 用来卸载。

Ubuntu的包管理工具是apt-get， 安装命令 dpkg -i xxxxxxx.deb，其余的和 CentOS 差异不大，就是包管理工具不同

## 压缩格式

Linux 的默认压缩格式是 tar.gz , zip 也可以用但是需要另外安装

```shell
tar -czvf xxxx.tar.gz /home/*
zip -r xxxx.zip /home/*
```

## 运行程序

Linux 执行程序最常用的一种方式，通过 shell 在交互式命令行中执行。

还有就是后台运行，这需要使用 nohup 命令

运行程序还可以以服务的方式运行，类似与 MySQL 这类程序就需要这种运行方式

## 查看和关闭进程

```shell
ps -ef | grep java

kill -9 PID
```



## 关机和重启

```shell
shutdown -h now

reboot
```

## 总结

![](https://camo.githubusercontent.com/04d9f5a15ae7640687c3bb0bfef40718a4d424e2/68747470733a2f2f7374617469633030312e6765656b62616e672e6f72672f7265736f757263652f696d6167652f38382f65352f38383535626236343564386563633335633830616138396364653564313665352e6a7067)

