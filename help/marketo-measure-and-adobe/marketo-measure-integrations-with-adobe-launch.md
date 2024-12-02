---
description: 与Adobe启动项[!DNL Marketo Measure]集成 —  [!DNL Marketo Measure]
title: '[!DNL Marketo Measure]与Adobe启动项的集成'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 6aaf6fd26f19e9382cc559e54558e1c5d84cfd6d
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---

# [!DNL Marketo Measure]与Adobe启动项的集成 {#marketo-measure-integrations-with-adobe-launch}

Adobe启动项扩展专为已在网站上使用Adobe启动项的现有[!DNL Marketo Measure]用户而设计。 扩展用作标签管理解决方案，可用于根据特定事件和条件在页面上配置和动态加载脚本。

在AdobeLaunch中安装和配置后，[!DNL Marketo Measure]扩展将在存在AdobeLaunch脚本的页面上加载bizible.js脚本。 这允许营销人员通过AdobeLaunch配置添加bizible.js，而不是显式修改网页以添加bizible.js脚本标记。

## 配置AdobeLaunch扩展 {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>查看以下链接，了解有关AdobeLaunch及其扩展的更多信息：
>
>* [[!DNL Marketo Measure] 扩展](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Adobe启动项概述](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Adobe启动扩展概述](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. 按照本文](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}中的步骤[创建属性。

1. 单击您创建的属性。

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. 单击 **[!UICONTROL Extensions]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. 单击&#x200B;**[!UICONTROL Catalog]**&#x200B;选项卡并搜索“[!UICONTROL Bizible]”。

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. 在[!UICONTROL Bizible Analytics]图块中，单击&#x200B;**[!UICONTROL Install]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. 在Bizible AccountId字段中，键入您网站的URL（例如，`adobe.com`）。

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

1. 单击 **[!UICONTROL Save]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. 单击&#x200B;**[!UICONTROL Rules]**，然后选择&#x200B;**[!UICONTROL Create New Rule]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. 单击[!UICONTROL Events]下的&#x200B;**[!UICONTROL Add]**&#x200B;按钮。

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. 在“扩展”下拉列表中，选择&#x200B;**[!UICONTROL Core]**。 然后在“事件类型”下拉列表中，选择&#x200B;**[!UICONTROL Library Loaded (Page Top)]**。 如果不为事件命名，则应用默认名称。 完成后单击&#x200B;**[!UICONTROL Keep Changes]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. 单击“操作”下的&#x200B;**[!UICONTROL Add]**&#x200B;按钮。

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. 在“扩展”下拉列表中，选择&#x200B;**[!UICONTROL Bizible Analytics]**。 然后在“操作类型”下拉列表中，选择&#x200B;**[!UICONTROL Initialize]**。 如果没有为您的操作指定名称，则会应用默认名称。 完成后单击&#x200B;**[!UICONTROL Keep Changes]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. 单击 **[!UICONTROL Save]**。

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)

