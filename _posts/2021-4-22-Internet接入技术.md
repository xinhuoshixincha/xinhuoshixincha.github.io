---
layout: post
title:  "Internet接入技术"
date:   2021-04-22 19:17:34 +0800
tags: 路由器
color: rgb(3,212,0)
---

## Internet接入技术

### 路由器配置PPPOE

####　配置vpdn

vpdn enable 启用虚拟专用拨号网络

vpdn-group groupName 设置一个工作组

accept-dialin 访问拨号网络

protocol pppoe 启用pppoe协议

virtual-template 1 建立虚拟终端1



#### 设置帐号

username chenxuan password 0 123456 设置账号密码



#### 设置虚拟端口

interface virtual-Template 1

ip unnumbered fastEthernet0/0 设置无ip

ipeer default ip address pool mypool 分配ip池中的ip

ppp authentication chap 选择终端认证



####　设置用户端口

interface fa0/0

ip address 公网IP 255.0.0.0 给端口分配公网IP

pppoe enable 启用pppoe



#### 设置线程池

ip local pool mypool 10.1.1.1 10.1.1.10 

