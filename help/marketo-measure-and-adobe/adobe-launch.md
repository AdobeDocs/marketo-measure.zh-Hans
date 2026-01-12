---
description: 与Adobe Launch的[!DNL Marketo Measure]集成 —  [!DNL Marketo Measure]
title: 与Adobe Launch的[!DNL Marketo Measure]集成
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---


# 与Adobe Launch的[!DNL Marketo Measure]集成 {#marketo-measure-integrations}

Adobe Launch扩展专为已在网站上使用Adobe Launch的现有[!DNL Marketo Measure]用户而设计。 扩展用作标签管理解决方案，可用于根据特定事件和条件在页面上配置和动态加载脚本。

在Adobe Launch中安装和配置后，[!DNL Marketo Measure]扩展会在存在Adobe Launch脚本的页面上加载bizible.js脚本。 这允许营销人员通过Adobe Launch配置添加bizible.js，而不是显式修改网页以添加bizible.js脚本标记。

## 配置Adobe Launch扩展 {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>查看以下链接，了解有关Adobe Launch及其扩展的更多信息：
> [[!DNL Marketo Measure] 扩展](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=zh-Hans#catalog){target="_blank"}
> [Adobe Launch概述](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html?lang=zh-Hans){target="_blank"}
> [Adobe Launch扩展概述](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html?lang=zh-Hans){target="_blank"}

1. 按照本文[中的步骤](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=zh-Hans#go-to-the-data-collection-interface){target="_blank"}创建属性。

1. 单击您创建的属性。

   ![Adobe Launch属性选择屏幕显示可用的属性](assets/marketo-measure-integrations-1.png)

1. 单击 **[!UICONTROL Extensions]**。

   Adobe Launch属性设置中的![扩展选项卡](assets/marketo-measure-integrations-2.png)

1. 单击&#x200B;**[!UICONTROL Catalog]**&#x200B;选项卡并搜索“[!UICONTROL Bizible]”。

   ![扩展目录搜索显示Bizible扩展](assets/marketo-measure-integrations-3.png)

1. 在[!UICONTROL Bizible Analytics]图块中，单击&#x200B;**[!UICONTROL Install]**。

   带有“安装”按钮的![Bizible Analytics扩展拼贴](assets/marketo-measure-integrations-4.png)

1. 在Bizible AccountId字段中，键入您网站的URL（例如，`adobe.com`）。

   具有AccountId字段的![Bizible扩展配置](assets/marketo-measure-integrations-5.png)

1. 单击 **[!UICONTROL Save]**。

   Bizible扩展配置的![保存按钮](assets/marketo-measure-integrations-6.png)

1. 单击&#x200B;**[!UICONTROL Rules]**，然后选择&#x200B;**[!UICONTROL Create New Rule]**。

   使用“创建新规则”按钮![的“规则”选项卡](assets/marketo-measure-integrations-7.png)

1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;下的[!UICONTROL Events]按钮。

   ![规则配置的“事件”部分中的“添加”按钮](assets/marketo-measure-integrations-8.png)

1. 在“扩展”下拉列表中，选择&#x200B;**[!UICONTROL Core]**。 然后在“事件类型”下拉列表中，选择&#x200B;**[!UICONTROL Library Loaded (Page Top)]**。 如果不为事件命名，则应用默认名称。 完成后单击&#x200B;**[!UICONTROL Keep Changes]**。

   具有核心扩展和库已加载事件类型的![事件配置对话框](assets/marketo-measure-integrations-9.png)

1. 单击“操作”下的&#x200B;**[!UICONTROL Add]**&#x200B;按钮。

   ![规则配置的“操作”部分中的“添加”按钮](assets/marketo-measure-integrations-10.png)

1. 在“扩展”下拉列表中，选择&#x200B;**[!UICONTROL Bizible Analytics]**。 然后在“操作类型”下拉列表中，选择&#x200B;**[!UICONTROL Initialize]**。 如果没有为您的操作指定名称，则会应用默认名称。 完成后单击&#x200B;**[!UICONTROL Keep Changes]**。

   ![具有Bizible Analytics扩展和初始化操作类型的操作配置对话框](assets/marketo-measure-integrations-11.png)

1. 单击 **[!UICONTROL Save]**。

   规则配置的![保存按钮](assets/marketo-measure-integrations-12.png)

