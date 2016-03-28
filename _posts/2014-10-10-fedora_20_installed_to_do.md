---
layout: post
title: Fedora 20 安装后的一些操作
category: Fedora
tagline: "Supporting tagline"
tags: [Fedora]
---
{% include JB/setup %}
# Fedora 20 安装后的一些操作
---
###1. 安装fedora20后的初始化配置

**1.1. 防火墙**

如果你的电脑处于局域网内，默认开启的防火墙会导致局域网内的其他电脑无法与你的电脑进行连接，所以，停止它！

```
sudo systemctl stop firewalld.service
sudo systemctl disable firewalld.service
```
<!--break-->

**1.2. SELinux**

停止[SELinux](http://baike.baidu.com/view/487687.htm?fr=aladdin"百度百科")，如果你不需要它。

```
sudo vi /etc/sysconfig/selinux
```

```
# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#enforcing - SELinux security policy is enforced.
#permissive - SELinux prints warnings instead of enforcing.
#disabled - SELinux is fully disabled.
SELINUX= disabled	# change
# SELINUXTYPE= type of policy in use. Possible values are:
#targeted - Only targeted network daemons are protected.
#strict - Full SELinux protection.
SELINUXTYPE=targeted
```


**2. 安装rpmfusion源**

Fedora20的源：

```
sudo yum localinstall --nogpgcheck http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-20.noarch.rpm http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-20.noarch.rpm
```


**3. 安装一下有用的一些软件包**

```
sudo yum -y install yum-fastestmirror vim gnome-tweak-tool cmake gcc p7zip
```

**4. 升级一下系统：**

```
sudo yum -y update
```

**5. 安装 flash plugin**

32位系统：

```
wget http://linuxdownload.adobe.com/adobe-release/adobe-release-i386-1.0-1.noarch.rpm
sudo rpm -ivh adobe-release-i386-1.0-1.noarch.rpm
sudo yum -y install flash-plugin
```

64位系统：

```
wget http://linuxdownload.adobe.com/adobe-release/adobe-release-x86_64-1.0-1.noarch.rpm
sudo rpm -ivh adobe-release-x86_64-1.0-1.noarch.rpm
sudo yum -y install flash-plugin
```