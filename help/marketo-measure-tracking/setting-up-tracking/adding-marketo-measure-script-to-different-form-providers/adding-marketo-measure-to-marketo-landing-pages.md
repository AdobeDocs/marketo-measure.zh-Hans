---
unique-page-id: 18874755
description: 正在添加 [!DNL Marketo Measure] 到 [!DNL Marketo] 登陆页面 —  [!DNL Marketo Measure]  — 产品文档
title: 正在添加 [!DNL Marketo Measure] 到Marketo登录页面
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# 正在添加 [!DNL Marketo Measure] 到Marketo登录页面 {#adding-marketo-measure-to-marketo-landing-pages}

了解如何将跟踪添加到 [!DNL Marketo Engage] 登陆页面，因为它们需要额外的处理。 [!DNL Marketo Measure] 需要在登陆页面和 [!DNL Marketo Engage] 形成自身。 为此，您需要加载 [!DNL Marketo Measure] JavaScript到 [!DNL Marketo Engage] 如以下说明中所述。

>[!NOTE]
>
>如果要通过标签管理提供程序（例如）部署JavaScript，请执行以下操作 [!DNL Google Tag Manager]，您无需手动添加 [!DNL Marketo Measure] JS到 [!DNL Marketo Engage].

## 如何添加 [!DNL Marketo Measure] 编写脚本至 [!DNL Marketo Engage] 登陆页面 {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. 登录 [!DNL Marketo Engage] 帐户。
1. 选择您的登陆页面，然后单击 **[!UICONTROL Edit Draft]**.
1. 拖入HTML元素。
1. 输入 [!DNL Marketo Measure] 将JavaScript导入 [!UICONTROL head] 部分：

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

以下屏幕快照中的示例

1. 单击 **[!UICONTROL Save]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## 其他说明 {#additional-notes}

* 您可能已经设置了其他跟踪代码片段，例如 [!DNL Google Analytics] 代码。 这没有任何问题，请务必用分号分隔它们 `;` 和单一空间。 下面是这样的一个示例：

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* 您可能使用了多个登陆页面模板，请务必将代码添加到所有包含表单的模板中。

* 有时，在编辑登陆页面的模板时，您需要重新批准登陆页面由使用的页面。 本文介绍 [如何成批审批](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
