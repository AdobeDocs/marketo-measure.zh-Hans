---
unique-page-id: 18874580
description: 将Marketo测量与Salesforce连接 —  [!DNL Marketo Measure]  — 产品文档
title: 将Marketo Measure连接到Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# 将Marketo Measure连接到Salesforce {#connect-marketo-measure-to-salesforce}

本文概述了如何连接 [!DNL Salesforce] 帐户 [!DNL Marketo Measure] 帐户。

## 连接 [!DNL Marketo Measure] with [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. 使用隐身浏览器登录到 [!DNL Marketo Measure].

1. 在屏幕顶部的菜单栏中，导航到 **[!UICONTROL My Account]** ，然后单击 [!UICONTROL Settings] 选项。

1. 在左侧的设置选项列中，单击 [!UICONTROL Connections] 位于 [!UICONTROL Integrations] 中。

   ![](assets/1.png)

1. 在连接中的CRM部分下，单击 **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/2.png)

1. 将显示一个弹出窗口，要求您选择CRM连接。 单击 [!UICONTROL Connect] 按钮 [!DNL Salesforce] 徽标。

   ![](assets/3.png)

1. 最后将显示一个弹出窗口，要求您 [!DNL Salesforce] 凭据、沙盒或生产。 输入您的信息并单击 **[!UICONTROL Authorize]** 将帐户连接到 [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] 只能连接到一个 [!DNL Salesforce] 实例。
>
>* A [!DNL Marketo Measure] 实例可以连接到SFDC沙盒实例，以在将连接切换到SFDC生产实例之前测试集成。
>* 如果您首先使用SFDC沙盒进行测试，我们强烈建议您使用SFDC生产实例的精确副本来进行测试，该副本包括潜在客户、联系人、帐户、机会、营销活动和案例对象的字段。 如果您在生产中有任何活动的APEX触发器，该触发器在对Lead、Contact、Account、Opportunity、Campaign和Case对象的更新时触发，则应尝试在沙盒中激活它们。
>* 测试完成后，您将更新 [!DNL Marketo Measure] 帐户指向您的生产 [!DNL Salesforce] （而不是沙盒） [!DNL Salesforce])。 由于集成的构建方式， [!DNL Marketo Measure] 帐户已连接到生产 [!DNL Salesforce]，则不能“向后”连接到沙盒 [!DNL Salesforce] org。


