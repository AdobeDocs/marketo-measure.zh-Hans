---
description: 正在将 [!DNL Marketo Measure] 脚本添加到Lightbox Forms - [!DNL Marketo Measure]
title: 正在将 [!DNL Marketo Measure] 脚本添加到Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---


# 将[!DNL Marketo Measure]脚本添加到Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

了解如何将[!DNL Marketo Measure] JavaScript正确添加到灯箱中的表单。

当访客执行特定操作（即，单击页面的特定部分、在页面上花费特定时间等）时，灯箱会打开内容前面的表单。 通常情况下，我们要求将[!DNL Marketo Measure]JavaScript放置在登陆页面的标题中，但对于Lightbox中的表单，还需要执行一个额外步骤。

由于灯箱中的表单基本上是iFrame中的表单，因此脚本会放置在该iFrame中。

首先，找到[!UICONTROL lightbox]表单所在的iFrame。

![在页面源中查找灯箱表单iFrame](assets/1.png)

接下来，将[!DNL Marketo Measure]JavaScript放置在iFrame中。

置于Lightbox iFrame中的![Marketo Measure脚本](assets/2.png)

最后，在添加JavaScript时，将按照以下说明跟踪验证表单提交：

1. 复制包含[!UICONTROL lightbox]表单的登陆页面的URL。
1. 打开无痕浏览器并粘贴URL。
1. 使用唯一的电子邮件地址提交表单。
1. 通过检查您的CRM中是否使用唯一的电子邮件地址，确认跟踪了测试，确保正在填充接触点数据。
