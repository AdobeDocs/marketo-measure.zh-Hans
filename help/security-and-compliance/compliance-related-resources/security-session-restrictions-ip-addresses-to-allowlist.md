---
unique-page-id: 18874706
description: 安全会话限制 — 要允许列表的IP地址 — Marketo Measure — 产品文档
title: 安全会话限制 — 要允许列表的IP地址
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
TQID: https://experienceleague.adobe.com/Ka7ff5qarBVEm4JdSGCbaUM3Mrug0r3ZOPSKPrnc3Zo
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 76
ht-degree: 0%

---

# 安全会话限制：要允许列表的IP地址 {#security-session-restrictions-ip-addresses-to-allowlist}

如果[会话安全设置](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"}已到位，阻止特定IP地址将数据推送/提取到您的[!DNL Salesforce]实例，我们需要列入允许列表以下IP范围以允许[!DNL Marketo Measure]将数据推送到[!DNL Salesforce]：

* 52.162.84.192 — 52.162.84.207
* 23.100.229.112 — 23.100.229.127
* 20.186.163.0 — 20.186.163.15

要将[!DNL Marketo Measure] IP添加到Salesforce中的受信任IP范围，请单击&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Administration Setup]** > **[!UICONTROL Security Controls]** > **[!UICONTROL Network Access]** > **[!UICONTROL New]**。

![](assets/1.png)
