---             
title:  04 | 快速上手几个Linux命令：每家公司都有自己的黑话
date:   2019-04-21 12:00:00
---

修改密码：`passwd`  

登录用户：`su`，输入密码。

添加用户：`useradd xxx`  调用`passws xxx` 来设置密码，再进行登录。    

删除用户：`userdel xxx`





### 安装软件
一个是 CentOS 体系，一个是 Ubuntu体系，前者使用 rpm，后者使用 deb。

CentOS 下面使用 `rpm -i xxxx.xxx`，Ubuntu 下面使用 `dpkg -i xxx.xxx`

凭借 rpm -qa 和 dpkg -l 就可以查看安装的软件列表。-q 就是 query，a 就是 all，-l 的意思就是 list。


CentOS 下面是 yum，Ubuntu 下面是 apt-get。

使用 yum erase  xxx ，和apt-get purge 进行卸载。







