---
layout: post
title: Fedora 20 安装qq2013
category: Fedora
tagline: "Supporting tagline"
tags: [Fedora, QQ]
---
{% include JB/setup %}
# Fedora 20 安装qq2013
---

在当今中国，qq已经成为必不可少的交流工具了，但是官网linux版本的QQ功能和windows的相比真的是大相庭径，于是龙井开发出了wineqq共广大linux用户使用，ubuntu等debian系统直接安装deb包就可以了，但是fedora安装比较麻烦。所以在这里把自己安装的心得和步骤和大家分享一下。

首先需要的就是安装`wine`：

```
sudo yum install wine
```

<!--break-->

然后是下载最新版本的`wine qq2013`：
```
http://www.longene.org/download/
```

我下载的是最新版的`qq2013SP6`，文件名为`WineQQ2013SP6-20140102-Longene.deb`，将他直接解压，会有一个名为`data.tar.gz`的压缩包，在`data.tar.gz`所在文件夹使用命令：

```
tar -zxvf data.tar.gz -C /
```

在`/opt`目录中会生成一个名为`longene`的文件夹，然后运行`qq`文件夹中的`qq.sh`，`qq`就可以启动了，如果遇见缺少某些组件的问题的话，直接安装就可以，我安装时是缺少`libgdk-x11-2.0.so.0`这个包，直接使用命令：

```
sudo yum install libgdk-x11-2.0.so.0
```

安装完成后`qq`即可正常启动。

<p style="color:red">注意wine qq的密码只可以用软键盘输入。</p>

启动效果图：

![qq2013](/image/qq2013.jpg)
