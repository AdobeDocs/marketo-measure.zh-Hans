---
unique-page-id: 18874747
description: 添加 [!DNL Marketo Measure] 脚本到Sitecore页面 —  [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] 脚本到Sitecore页面
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] 脚本到Sitecore页面 {#adding-marketo-measure-script-to-sitecore-pages}

内容管理系统可能需要执行标准脚本实施之外的其他步骤，以便 [!DNL Marketo Measure] 以识别表单提交。 以下过程概述了如何添加 [!DNL Marketo Measure] javascript [!DNL Sitecore] 页面。

对于具有Sitecore页面的站点：

1. 登录Sitecore并导航到您的网站。 找到 [!UICONTROL Configuration] 位于与 [!UICONTROL Home] 项目和 [!UICONTROL Metadata] 文件夹。
1. 单击 **[!UICONTROL +]** 旁边 [!UICONTROL Configuration] 文件夹。
1. 单击 **[!UICONTROL +]** 旁边 [!UICONTROL Tools] 文件夹。
1. 选择 [!UICONTROL Javascript] 项目。
1. 在 [!UICONTROL Content] ，单击 **[!UICONTROL Lock and Edit]** 链接以解锁要编辑的项目。
1. 查找 [!UICONTROL 'JavaScript'] 中。 如果尚未展开，请单击 **[!UICONTROL +]**.
1. 输入我们的脚本： `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. 单击 **[!UICONTROL Save]** 中。
