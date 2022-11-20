---
title:       "做一个更出色的程序员"
subtitle:    "查漏补缺，三省吾身"
description: "来源某公众号大佬的文章"
date:        2022-11-20
author:      "常振林"
image:       ""
tags:        ["articel"]
categories:  ["Tech", "Archive" ]
---

根据应用系统的数据敏感程度的不同，对于系统内微服务的相互访问可能有不同的安全要求。
<!--more-->

#### SPIFEE标准
[Secure Production Identity Framework For Everyone (SPIFFE)](https://spiffe.io/)是一套服务之间相互进行身份识别的标准，主要包含以下内容：

#### Istio Auth开源实现
Istio服务网格项目的Auth组件实现了SPIFFE标准，可以为网格中服务颁发符合SPIFFE SVID标准的证书，并为服务提供身份认证，细粒度的操作鉴权以及通信加密。Istio的架构如下图所示：
![](/img/2018-05-23-service_2_service_auth/auth.png)

Istio Auth采用了Kubernetes的service account来作为服务标识，其SPIFFE ID的格式为spiffe://&lt;domain&gt;/ns/&lt;namespace&gt;/sa/&lt;serviceaccount&gt;，其中各组成部分如下：
* domain 域名
* namspace kubernetes service account所在的Namespace
* serviceaccout kubernetes中定义的service account名