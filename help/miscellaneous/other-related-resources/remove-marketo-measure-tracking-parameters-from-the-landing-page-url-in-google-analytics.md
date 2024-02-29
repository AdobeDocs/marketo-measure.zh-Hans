---
unique-page-id: 18874736
description: 移除 [!DNL Marketo Measure] Google Analytics中登录页面URL的跟踪参数 —  [!DNL Marketo Measure]
title: 移除 [!DNL Marketo Measure] 从Google Analytics中的登陆页面URL跟踪参数
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---

# 移除 [!DNL Marketo Measure] 从Google Analytics中的登陆页面URL跟踪参数 {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

有时，在中查看登陆页面时 [!DNL Google Analytics]，则需要从URL中删除跟踪参数。 否则，它们将拆分为单独的行。

幸运的是，这是一个简单的解决办法。

1. 在 [!DNL Google Analytics]，转到 [!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters].
1. 在框中键入“_bt，_bk，_bm，_bn，_bg”（减去引号）。
1. 向下滚动并单击 **[!UICONTROL Save]**.

   请记住 [!DNL Google Analytics] 不会重新处理数据。 因此，此更改只会反映在以后的更改中，并且您过去的数据仍会与bt、bk和bm参数一起显示。
