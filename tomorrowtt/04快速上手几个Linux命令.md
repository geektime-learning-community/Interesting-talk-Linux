# 04 | 快速上手几个Linux命令

## 用户与密码

当我们打开一个新的系统，首先要登陆系统。Windows系统默认有一个`Administrator`，也就是超级管理员，权限最大，可以做任何事。Linux上也有一个类似的用户，叫`root`，拥有最高权限。

1. Linux下修改密码

```
passwd 
```
修改指定用户密码

```
passwd tomorrow
```

2. 添加新用户
```
useradd  tomorrow
```

* 帮助文档  -h
```
 useradd -h
```
新建用户会默认创建一个用户组，新建的用户都会放在这个组里，我们也可以根据需求，将用户创建到指定用户组里。其他功能可以用-h命令查看

## 浏览文件

Linux的文件系统和Windows是一样的，都是用文件夹吧文件组织起来，形成一个树形结构

1. 切换目录   
```
cd  文件夹名   ：进入制定文件夹
cd .          : 切换到当前目录
cd ..         : 切换到上级目录
```

2. 列出当前目录下的文件
```
ls
ls -l   用列表的方式列出文件
```

> ls -l 命令列出的文件，第一个字符表示文件类型。如下示例
```
# ls -l
drwxr-xr-x 6 root root 4096 Oct 20 2017 apt
-rw-r--r-- 1 root root 211 Oct 20 2017 hosts
```
* 如果是‘-’，表示普通文件
* 如果是‘d’，表示目录

## 安装软件 

Windows最方便的方式是现在exe文件双击直接安装。</br>
对Linux来说，你可以下载`rpm`或者`deb`。因为Linux有两大体系，一个是CentOS体系，一个是Ubuntu体系。前者使用`rpm`，后者使用`deb`。

* Linux上没有双击安装，需要安装命令。

> CentOS 下面使用rpm -i jdk-XXX_linux-x64_bin.rpm进行安装</br>
> Ubuntu 下面使用dpkg -i jdk-XXX_linlinux-x64_bin.deb

-i 就是install的意思

在 Linux 下面，凭借`rpm -qa和dpkg -l`就可以查看安装软件列表，`-q`就是`query`，`a`就是`all`，`-l`就是`list`

### grep 很好用的搜索工具 

### Linux下的软件管家 
* CentOS 下面是 `yum`</br>
* Ubuntu 下面是 `apt-get`

```
下载安装
yum install java-11-openjdk.x86_64
apt-get install openjdk-9-jdk
```
```
卸载
yum erase java-11-openjdk.x86_64
apt-get purge openjdk-9-jdk
```
**** 
其实无论是先下载再安装，还是通过软件管家安装，都是下载一些文件，然后将这些文件放在耨个路径下，然后在相应的配置文件中配置一下。Windows会放在`C:Program Files`下面的文件夹以及注册表里面的一些配置。对应的Linux里面会放的更散，主执行文件会放在`/usr/bin`或者`/hsr/sbin`下面，其他的库文件会放在`/var`下面，配置文件会放在`/etc`下面。

> `vim` 就像 Windows 里面的 `notepad` 一样，是我们第一个要学会的工具

## 运行程序
* 运行程序
```
./程序
```
*  进程
```
ps -ef |grep 关键字
//杀死进程
kill -9 进程编号
```
* 关机重启
>`shutdown -h now` 立即就关机当然 `shutdown` 还有很多参数，可以用来定时关机、延时关机等等。</br>
> `reboot`就是重启


## 总结
![](https://static001.geekbang.org/resource/image/88/e5/8855bb645d8ecc35c80aa89cde5d16e5.jpg)