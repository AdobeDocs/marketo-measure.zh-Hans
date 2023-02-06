---
unique-page-id: 18874755
description: 添加 [!DNL Marketo Measure] to [!DNL Marketo] 登陆页面 —  [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] 到Marketo登陆页面
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] 到Marketo登陆页面 {#adding-marketo-measure-to-marketo-landing-pages}

了解如何将跟踪添加到 [!DNL Marketo Engage] 登陆页面，因为需要进行其他处理。 [!DNL Marketo Measure] 需要在登陆页面和 [!DNL Marketo Engage] 形式。 为此，您需要加载 [!DNL Marketo Measure] JavaScript到 [!DNL Marketo Engage] 如以下说明中所述。

>[!NOTE]
>
>如果要通过标签管理提供程序(如 [!DNL Google Tag Manager]，则无需手动添加 [!DNL Marketo Measure] JS到 [!DNL Marketo Engage].

## 如何添加 [!DNL Marketo Measure] 脚本到 [!DNL Marketo Engage] 登陆页面 {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. 登录到 [!DNL Marketo Engage] 帐户。
1. 选择您的登陆页面并单击 **[!UICONTROL Edit Draft]**.
1. 拖入HTML元素。
1. 输入 [!DNL Marketo Measure] 将JavaScript导入 [!UICONTROL head] 部分：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

以下屏幕截图中的示例

1. 单击 **[!UICONTROL Save]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## 其他说明 {#additional-notes}

* 您可能已部署其他跟踪代码片段，例如 [!DNL Google Analytics] 代码。 这没什么问题，只要确保用分号分隔它们 `;` 和一个空间。 其结果的示例如下：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* 您可能正在使用多个登陆页面模板，请务必将代码添加到其上具有表单的所有模板。

* 有时，在编辑登陆页面的模板时，您需要重新批准登陆页面所使用的页面。 本文说明 [如何批准批量](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
