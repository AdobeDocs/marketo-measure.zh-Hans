---
unique-page-id: 18874590
description: '"[!DNL Marketo Measure] Cookie - [!DNL Marketo Measure]  — 产品文档”'
title: "[!DNL Marketo Measure] Cookie"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Marketo Measure Cookies {#marketo-measure-cookies}

了解各种 [!DNL Marketo Measure] 在您应用时加载到您网站上的Cookie [!DNL Marketo Measure] 将JavaScript添加到登陆页面。 这些信息在实施过程中可能会对Web开发团队非常有用。

| **Cookie名称** | **Cookie类型** | **用途** |
|---|---|---|
| _BUID | 第三方，保存在.bizible.com域上 | 跨多个客户端域标识同一用户的通用用户ID。 |
| _biz_uid | 第一方 | 当前域中的用户ID。 |
| _biz_sid | 第一方 | 用户的会话ID。 |
| _biz_flagsA | 第一方 | 单个Cookie存储多种信息，例如用户是否已提交表单、执行跨域迁移、发送显示到达像素、选择退出跟踪等。 |
| _biz_nA | 第一方 | 序列号 [!DNL Marketo Measure] 包括所有请求，用于内部诊断 |
| _biz_dfsA | 第一方 | 临时存储以前发生的表单提交数据 [!DNL bizible.js] 接收配置JS以确定是否已启用HTTPS上的跟踪表单。 |
| _biz_pendingA | 第一方 | 临时存储尚未成功发送到的分析数据 [!DNL Marketo Measure] 服务器尚未启用。 |

如果在JavaScript设置期间触发了Web应用程序防火墙(WAF)警告，则用户可以禁用该WAF规则或将Cookie列入允许列表，如下例所示：

![](assets/marketo-measure-cookies-1.png)
