---
unique-page-id: 18874690
description: 重新授权连接的帐户 —  [!DNL Marketo Measure]
title: 重新授权连接的帐户
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 0%

---

# 重新授权连接的帐户 {#reauthorizing-connected-accounts}

当帐户与您的断开连接时 [!DNL Marketo Measure] 帐户，平台的状态将更改为“需要授权”并显示一个红色钥匙图标。

如果广告平台断开连接， [!DNL Marketo Measure] 将无法下载成本数据，或者，如果已启用自动标记，请附加 [!DNL Marketo Measure] 任何新创建广告的UTM参数。 [!DNL Marketo Measure] 在帐户断开连接时，无法将UTM参数逆向附加到从广告平台创建的任何接触点。

如果您的CRM平台断开连接， [!DNL Marketo Measure] 无法更新 [!DNL Marketo Measure] 数据或将任何新接触点推送到您的组织。 重新建立CRM连接后， [!DNL Marketo Measure] 将推送在帐户断开连接时丢失的任何数据。

![](assets/1-1.png)

## 重新授权断开连接的帐户 {#re-authorizing-disconnected-accounts}

1. 转到 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 并登录。
1. 选择 **[!UICONTROL Settings]** 在 [!UICONTROL My Account] tab键。
1. 在左侧找到集成部分，然后单击 **[!UICONTROL Connections]**.
1. 选择需要重新连接的帐户旁边的红色键符号。
1. 此时会出现一个弹出窗口，提示您提供帐户的登录详细信息。
