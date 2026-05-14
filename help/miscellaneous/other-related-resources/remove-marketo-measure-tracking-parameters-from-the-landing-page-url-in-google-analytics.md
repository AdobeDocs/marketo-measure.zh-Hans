---
unique-page-id: 18874736
description: 从Google Analytics中的登陆页面URL中删除 [!DNL Marketo Measure] 跟踪参数 —  [!DNL Marketo Measure]
title: 从Google Analytics中的登陆页面URL中删除 [!DNL Marketo Measure] 跟踪参数
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
TQID: https://experienceleague.adobe.com/vKhwWUT0VQ1Kr-3-dWVWt08S4848Q0Bn4HYrGgHawb8
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 109
ht-degree: 0%

---

# 从Google Analytics中的登陆页面URL中删除[!DNL Marketo Measure]跟踪参数 {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

有时在查看[!DNL Google Analytics]中的登陆页面时，您需要从URL中删除跟踪参数。 否则，它们将拆分为单独的行。

幸运的是，这是一个简单的解决办法。

1. 在[!DNL Google Analytics]中，转到[!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters]。
1. 在框中键入“_bt，_bk，_bm，_bn，_bg”（减去引号）。
1. 向下滚动并单击&#x200B;**[!UICONTROL Save]**。

   请记住，[!DNL Google Analytics]不会重新处理数据。 因此，此更改只会反映在以后的更改中，并且您过去的数据仍会与bt、bk和bm参数一起显示。
