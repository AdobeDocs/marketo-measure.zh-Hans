---
unique-page-id: 18874736
description: 删除 [!DNL Marketo Measure] 在中跟踪登陆页面URL中的参数 — Google Analytics [!DNL Marketo Measure]  — 产品文档
title: 删除 [!DNL Marketo Measure] 在Google Analytics中跟踪登陆页面URL中的参数
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# 删除 [!DNL Marketo Measure] 在Google Analytics中跟踪登陆页面URL中的参数 {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

有时，在 [!DNL Google Analytics]，则需要从URL中删除跟踪参数。 否则，它们将拆分为单个行。

幸运的是，这是个容易的办法。

1. 在 [!DNL Google Analytics]，转到 [!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters].
1. 在框中键入“_bt，_bk，_bm，_bn，_bg”（减去引号）。
1. 向下滚动并单击 **[!UICONTROL Save]**.

   请记住 [!DNL Google Analytics] 不会重新处理数据。 因此，此更改将仅反映在未来，并且您的过去数据仍将使用bt、bk和bm参数显示。
