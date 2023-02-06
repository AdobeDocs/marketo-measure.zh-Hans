---
unique-page-id: 18874706
description: 安全会话限制 — 要的IP允许列表地址 — Marketo Measure — 产品文档
title: 安全会话限制 — 要的IP地允许列表址
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
source-git-commit: b9d9e3110e87be0d6311c17b0ef76dfad8735a00
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 3%

---

# 安全会话限制：要的IP地允许列表址 {#security-session-restrictions-ip-addresses-to-allowlist}

如果存在 [会话安全设置](https://help.salesforce.com/articleView?id=admin_sessions.htm&amp;type=0){target="_blank"} 就地防止特定IP地址向您的 [!DNL Salesforce] 例如，我们需要以下IP范列入允许列表围以允许 [!DNL Marketo Measure] 将数据推送到 [!DNL Salesforce]:

* 52.162.84.192 - 52.162.84.207
* 23.100.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

添加 [!DNL Marketo Measure] 在Salesforce中，将IP转到受信任的IP范围，单击 **[!UICONTROL Setup]** > **[!UICONTROL Administration Setup]** > **[!UICONTROL Security Controls]** > **[!UICONTROL Network Access]** > **[!UICONTROL New]**.

![](assets/1.png)
