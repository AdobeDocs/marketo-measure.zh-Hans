---
description: '[!DNL Marketo Measure] 与Launch集成 — Adobe [!DNL Marketo Measure]  — 产品文档'
title: '''[!DNL Marketo Measure] 与Launch的集成Adobe'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
source-git-commit: 19f670505358b04fb26620574b71c2af8d0d9847
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# [!DNL Marketo Measure] 与Launch集成Adobe {#marketo-measure-integrations-with-adobe-launch}

AdobeLaunch扩展专为现有 [!DNL Marketo Measure] 已在其网站上利用AdobeLaunch的用户。 该扩展用作标签管理解决方案，您可以使用该解决方案根据某些事件和条件在您的页面上配置和动态加载脚本。

在Launch中安装和配置后， [!DNL Marketo Measure] 扩展将在存在AdobeLaunch脚本的页面上加载bizible.js脚本。 这允许营销人员通过AdobeLaunch配置添加bizible.js，而不是显式修改网页以添加bizible.js脚本标记。

## 配置AdobeLaunch扩展 {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>请访问以下链接，了解有关Launch及其扩展的更多Adobe:
>
>* [[!DNL Marketo Measure] 扩展](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=en#catalog){target=&quot;_blank&quot;}
>* [Adobe启动概述](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/index.html?lang=en#prerequisites){target=&quot;_blank&quot;}
>* [AdobeLaunch扩展概述](https://experienceleague.adobe.com/docs/launch/using/extension-dev/overview.html?lang=en#extension-configuration){target=&quot;_blank&quot;}


1. 按照步骤创建属性 [在本文中](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=en#go-to-the-data-collection-interface){target=&quot;_blank&quot;}。

1. 单击之前创建的资产。

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. 单击 **[!UICONTROL Extensions]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. 单击 **[!UICONTROL Catalog]** 选项卡，搜索“[!UICONTROL Bizible].&quot;

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. 在 [!UICONTROL Bizible Analytics] 拼贴，单击 **[!UICONTROL Install]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. 在Bizible AccountId字段中，键入您网站的URL。

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >此字段不是Business_Prod.Business表中的“帐户ID”。 来自给定URL的所有Web活动都将映射到 [!DNL Marketo Measure] 租户。

1. 单击 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. 单击 **[!UICONTROL Rules]**，然后选择 **[!UICONTROL Create New Rule]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. 单击 **[!UICONTROL Add]** 按钮 [!UICONTROL Events].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. 在扩展下拉菜单中，选择 **[!UICONTROL Core]**. 然后，在事件类型下拉菜单中，选择 **[!UICONTROL Library Loaded (Page Top)]**. 如果不为事件指定名称，则会应用默认名称。 单击 **[!UICONTROL Keep Changes]** 完成时。

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. 单击 **[!UICONTROL Add]** 按钮。

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. 在扩展下拉菜单中，选择 **[!UICONTROL Bizible Analytics]**. 然后，在操作类型下拉菜单中，选择 **[!UICONTROL Initialize]**. 如果您没有为操作指定名称，则会应用默认名称。 单击 **[!UICONTROL Keep Changes]** 完成时。

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. 单击 **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
