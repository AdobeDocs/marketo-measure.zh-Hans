---
unique-page-id: 18874519
description: 正在添加 [!DNL Marketo Measure] Lightbox Forms的脚本 —  [!DNL Marketo Measure]
title: 正在添加 [!DNL Marketo Measure] Lightbox Forms的脚本
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# 正在添加 [!DNL Marketo Measure] Lightbox Forms的脚本 {#adding-marketo-measure-script-to-lightbox-forms}

了解如何正确添加 [!DNL Marketo Measure] 将JavaScript转换为灯箱中的表单。

当访客执行特定操作（即，单击页面的特定部分、在页面上花费特定时间等）时，灯箱会打开内容前面的表单。 通常，我们要求使用 [!DNL Marketo Measure] JavaScript放置在登陆页面的标题中，但对于Lightbox中的表单，还需要执行一个额外步骤。

由于灯箱中的表单基本上是iFrame中的表单，因此脚本会放置在该iFrame中。

首先，找到iFrame [!UICONTROL lightbox] 形体生活在其中。

![](assets/1.png)

接下来，放置 [!DNL Marketo Measure] iFrame中的JavaScript。

![](assets/2.png)

最后，在添加JavaScript时，将按照以下说明跟踪验证表单提交：

1. 复制包含登录页的URL [!UICONTROL lightbox] 表单。
1. 打开无痕浏览器并粘贴URL。
1. 使用唯一的电子邮件地址提交表单。
1. 通过检查您的CRM中是否使用唯一的电子邮件地址，确认跟踪了测试，确保正在填充接触点数据。
