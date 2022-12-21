---
unique-page-id: 18874590
description: '"[!DNL Marketo Measure] Cookie - [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Measure] Cookie”'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
source-git-commit: 3a13ab3e497652d1975e69280a3d224ac95504aa
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Marketo测量Cookie {#marketo-measure-cookies}

了解 [!DNL Marketo Measure] 应用 [!DNL Marketo Measure] JavaScript到登陆页面。 此信息可能对Web开发团队在实施过程中有用。

| **Cookie名称** | **Cookie类型** | **用途** |
|---|---|---|
| _BUID | 第三方，保存在.bizible.com域上 | 通用用户ID，用于在多个客户端域中标识同一用户。 |
| _biz_uid | 第一方 | 当前域上的用户ID。 |
| _biz_sid | 第一方 | 用户的会话ID。 |
| _biz_flagsA | 第一方 | 一个Cookie，用于存储多个信息，例如用户是否提交了表单、执行跨域迁移、发送显示到达像素、选择退出跟踪等。 |
| _biz_nA | 第一方 | 序列号 [!DNL Marketo Measure] 包括用于所有请求的内部诊断的 |
| _biz_dfsA | 第一方 | 临时存储之前发生的表单提交数据 [!DNL bizible.js] 接收配置JS以确定是否启用HTTPS上的跟踪表单。 |
| _biz_pendingA | 第一方 | 临时存储未成功发送到的分析数据 [!DNL Marketo Measure] 服务器。 |

如果在JavaScript设置期间触发了Web应用程序防火墙(WAF)警告，则用户可以禁用该WAF规则或允许列出Cookie，如以下示例所示：

![](assets/marketo-measure-cookies-1.png)
