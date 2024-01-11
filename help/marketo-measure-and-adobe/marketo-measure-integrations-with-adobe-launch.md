---
description: ’[!DNL Marketo Measure] 与AdobeLaunch的集成 —  [!DNL Marketo Measure]  — 产品文档'
title: ’[!DNL Marketo Measure] 与AdobeLaunch的集成
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 1b583dac72aadff5d7c2352a064e2ff842b91891
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# [!DNL Marketo Measure] 与AdobeLaunch的集成 {#marketo-measure-integrations-with-adobe-launch}

Adobe Launch扩展专为现有的 [!DNL Marketo Measure] 已在其网站上使用AdobeLaunch的用户。 扩展用作标签管理解决方案，可用于根据特定事件和条件在页面上配置和动态加载脚本。

在AdobeLaunch中安装和配置后， [!DNL Marketo Measure] 扩展将在存在AdobeLaunch脚本的页面上加载bizible.js脚本。 这允许营销人员通过AdobeLaunch配置添加bizible.js，而不是显式修改网页以添加bizible.js脚本标记。

## 配置AdobeLaunch扩展 {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>查看以下链接，了解有关AdobeLaunch及其扩展的更多信息：
>
>* [[!DNL Marketo Measure] 扩展名](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=en#catalog){target="_blank"}
>* [Adobe启动项概述](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/index.html?lang=en#prerequisites){target="_blank"}
>* [AdobeLaunch扩展概述](https://experienceleague.adobe.com/docs/launch/using/extension-dev/overview.html?lang=en#extension-configuration){target="_blank"}

1. 按照以下步骤创建资产 [本文内容](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=en#go-to-the-data-collection-interface){target="_blank"}.

1. 单击刚刚创建的资产。

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. 单击 **[!UICONTROL Extensions]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. 单击 **[!UICONTROL Catalog]** 选项卡并搜索&#39;&#39;[!UICONTROL Bizible]“

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. 在 [!UICONTROL Bizible Analytics] 图块，单击 **[!UICONTROL Install]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. 在Bizible AccountId字段中，键入您网站的URL(例如， `adobe.com`)。

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >此字段不是Business_Prod.Business表中的“帐户ID”。 来自给定URL的所有Web活动(例如， `adobe.com`)将被映射到 [!DNL Marketo Measure] 租户。

1. 单击 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. 单击 **[!UICONTROL Rules]**，然后选择 **[!UICONTROL Create New Rule]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. 单击 **[!UICONTROL Add]** 按钮位于 [!UICONTROL Events].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. 在扩展下拉列表中，选择 **[!UICONTROL Core]**. 然后在事件类型下拉列表中，选择 **[!UICONTROL Library Loaded (Page Top)]**. 如果不为事件命名，则将应用默认名称。 单击 **[!UICONTROL Keep Changes]** 完成时。

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. 单击 **[!UICONTROL Add]** 按钮。

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. 在扩展下拉列表中，选择 **[!UICONTROL Bizible Analytics]**. 然后在操作类型下拉列表中，选择 **[!UICONTROL Initialize]**. 如果不为操作命名，则将应用默认名称。 单击 **[!UICONTROL Keep Changes]** 完成时。

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. 单击 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
