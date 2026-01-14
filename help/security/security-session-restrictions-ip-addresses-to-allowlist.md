---
description: 列出要Salesforce的列入允许列表 IP范围，以便在实施会话限制时Marketo Measure可以连接
title: 安全会话限制 — 要允许列表的IP地址
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# 安全会话限制：要允许列表的IP地址 {#security-session-restrictions-ip-addresses-to-allowlist}

如果[会话安全设置](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"}已到位，阻止特定IP地址将数据推送/提取到您的[!DNL Salesforce]实例，我们需要列入允许列表以下IP范围以允许[!DNL Marketo Measure]将数据推送到[!DNL Salesforce]：

* 52.162.84.192 — 52.162.84.207
* 23.100.229.112 — 23.100.229.127
* 20.186.163.0 — 20.186.163.15

要将[!DNL Marketo Measure] IP添加到Salesforce中的受信任IP范围，请单击&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Administration Setup]** > **[!UICONTROL Security Controls]** > **[!UICONTROL Network Access]** > **[!UICONTROL New]**。

![](assets/compliance-resources-1.png)
