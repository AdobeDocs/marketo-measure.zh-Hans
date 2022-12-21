---
unique-page-id: 18874519
description: 添加 [!DNL Marketo Measure] 脚本到Lightbox Forms - [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] 脚本到Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] 脚本到Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

了解如何正确添加 [!DNL Marketo Measure] JavaScript转换为灯箱中的表单。

当访客执行特定操作（例如，单击页面的特定部分，在页面上花费特定时间，等等）时，灯箱会在内容前面打开一个表单。 通常我们只要求 [!DNL Marketo Measure] JavaScript放置在登陆页面的标题中，但是对于灯箱中的表单，需要额外执行一个步骤。

由于灯箱中的表单基本上是iFrame中的表单，因此我们需要将脚本放置在该iFrame中。

首先，在 [!UICONTROL lightbox] 表格就在里面。

![](assets/1.png)

接下来，将 [!DNL Marketo Measure] iFrame中的JavaScript。

![](assets/2.png)

最后，在添加JavaScript时，我们建议您验证按以下说明跟踪的表单提交情况：

1. 复制包含 [!UICONTROL lightbox] 表单。
1. 打开“隐身”浏览器并粘贴URL。
1. 使用唯一的电子邮件地址提交表单。
1. 通过检查CRM中是否使用了唯一电子邮件地址来确认是否跟踪了测试，请确保接触点数据正在填充。
