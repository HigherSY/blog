---
title: "ZeroTier: 网络没有阻隔"
date: 2019-06-29T12:56:57+08:00
draft: false
toc: false
images:
tags: 
  - untagged
---

## 背景

随着 **IPv4** 地址的枯竭，一些运营商逐渐停止了分配 **公网 IP** 。对于一般用户来说，也许没有什么区别，但给自由的连接各地的计算机造成了不少麻烦。为了打破这层壁障，一群 ~~年轻人~~ 开发了 **ZeroTier** ，让分居各地，甚至是全球的计算机都能加入到一个网络中。

下面只介绍 Windows 的使用。

## Get

[ZeroTier Download](http://www.zerotier.com/download.shtml)

![Next](https://i.loli.net/2019/01/18/5c41d00360f7e.png)

接下来的步骤我想大家都会吧。提醒一下：虽然安装程序并没有提醒你重启，不过强烈推荐立即重启，以避免无法添加网络的尴尬。

## 使用

在系统托盘中找到 **ZeroTier One**

![Snipaste_2019-01-18_21-12-14.png](https://i.loli.net/2019/01/18/5c41d1e2c5f46.png)

右键后可选择加入网络（Join Network）

![Snipaste_2019-01-18_21-15-37.png](https://i.loli.net/2019/01/18/5c41d1e2e4f7d.png)

默认给出的 ID ``8056c2e21c000001`` ，即为上文提到的全球大内网，加入后，通过查看（Show Networks），可以查看具体 IP。当你和你的好友都成功加入了网络，并得到 IP，就可以互通了。不过请注意，这个网络不支持广播，如果不通请检查防火墙，并开放 ZeroTier 的 UDP 端口。

![Snipaste_2019-01-18_21-14-13.png](https://i.loli.net/2019/01/18/5c41d1e2c5809.png)

![Snipaste_2019-01-18_21-14-57.png](https://i.loli.net/2019/01/18/5c41d1e2c6507.png)

![Snipaste_2019-01-18_21-31-30.png](https://i.loli.net/2019/01/18/5c41d53830d84.png)

当然，如果你从 [My ZeroTier](https://my.zerotier.com/) 上注册账号并建立自己的网络，便可拥有 100 台主机的容量，甚至可以自主路由拓展，接入无限的网络，但这不在本文讨论范围内。

## 一句话

**ZeroTier** ，你值得拥有。 ~~中国移不动多学学人家~~