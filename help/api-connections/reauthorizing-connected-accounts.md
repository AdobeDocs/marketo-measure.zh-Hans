---
description: 为Marketo Measure用户重新授权“连接帐户”指南
title: 重新授权连接的帐户
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
feature: APIs, Integration
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# 重新授权连接的帐户 {#reauthorizing-connected-accounts}

当帐户与您的[!DNL Marketo Measure]帐户断开连接时，平台的状态将更改为“需要授权”并显示一个红色钥匙图标。

如果您的广告平台断开连接，[!DNL Marketo Measure]将无法下载成本数据，或者，如果您启用了自动标记，请将[!DNL Marketo Measure] UTM参数附加到任何新创建的广告。 在帐户断开连接时，[!DNL Marketo Measure]将无法以追溯方式将UTM参数附加到从广告平台创建的任何接触点。

如果您的CRM平台断开连接，[!DNL Marketo Measure]将无法更新[!DNL Marketo Measure]数据或将任何新的接触点推送到您的组织。 重新建立CRM连接后，[!DNL Marketo Measure]将推送在帐户断开连接时丢失的任何数据。

![如果您的CRM平台断开连接，Marketo Measure将不会断开连接](assets/utilizing-connections-7.png)

## 重新授权断开连接的帐户 {#re-authorizing-disconnected-accounts}

1. 转到[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}并登录。
1. 选择左上角&#x200B;**[!UICONTROL Settings]**&#x200B;选项卡下的[!UICONTROL My Account]。
1. 在左侧找到集成部分，然后单击&#x200B;**[!UICONTROL Connections]**。
1. 选择需要重新连接的帐户旁边的红色键符号。
1. 此时会出现一个弹出窗口，提示您提供帐户的登录详细信息。
