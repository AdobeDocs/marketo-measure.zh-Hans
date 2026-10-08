---
description: 正在将[!DNL Marketo Measure]脚本添加到Marketo Measure用户的Sitecore Pages指南
title: 正在将[!DNL Marketo Measure]脚本添加到Sitecore页面
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 0%
---
# 正在将[!DNL Marketo Measure]脚本添加到Sitecore页面 {#adding-marketo-measure-script-to-sitecore-pages}

除了标准脚本实施之外，内容管理系统可能还需要其他步骤，以便[!DNL Marketo Measure]识别表单提交。 以下流程概述了如何将[!DNL Marketo Measure] JavaScript添加到您的[!DNL Sitecore]页面。

对于具有Sitecore页面的网站：

1. 登录Sitecore并导航到您的网站。 找到与[!UICONTROL Home]项目和[!UICONTROL Metadata]文件夹位于同一级别的[!UICONTROL Configuration]文件夹。
1. 单击[!UICONTROL Configuration]文件夹旁边的&#x200B;**[!UICONTROL +]**。
1. 单击[!UICONTROL Tools]文件夹旁边的&#x200B;**[!UICONTROL +]**。
1. 选择[!UICONTROL Javascript]项。
1. 在[!UICONTROL Content]选项卡中，单击&#x200B;**[!UICONTROL Lock and Edit]**&#x200B;链接以解锁要编辑的项目。
1. 查找[!UICONTROL 'JavaScript']部分。 如果尚未展开，请单击&#x200B;**[!UICONTROL +]**。
1. 输入我们的脚本： `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. 单击左上角的&#x200B;**[!UICONTROL Save]**。
