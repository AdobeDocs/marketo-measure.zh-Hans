---
unique-page-id: 18874614
description: 具有买方接触点的潜在客户报表 —  [!DNL Marketo Measure]  — 产品文档
title: 具有买方接触点的潜在客户报表
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# 具有买方接触点的潜在客户报表 {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>您可能会看到指定“[!DNL Marketo Measure]“ ”，但仍请参阅“[!DNL Bizible]”。 我们正在努力更新该版本，并且该品牌重命名将很快地反映在您的CRM中。

开箱即用地提供许多报告功能，只要您指手可及 [!DNL Marketo Measure]，但是我们建议构建一些其他报表类型。 了解如何在下面创建具有买方接触点的包容性潜在客户报表类型。

1. 导航到 [!DNL Salesforce]. 从此处，展开“创建”分组并选择 **[!UICONTROL Report Types]**.

   ![](assets/1.jpg)

1. 选择 **[!UICONTROL New Custom Report Type]**.

   ![](assets/2.jpg)

1. 将主对象设置为“潜在客户”，并在“报表类型标签”输入“具有买方接触点的潜在客户 — 包括”中。 将报表存储在“潜在客户”类别中，并将部署状态更改为 **[!UICONTROL Deployed]**. 然后选择 **[!UICONTROL Next]**.

   ![](assets/3.jpg)

1. 对于对象关系，选择 **[!DNL Marketo Measure]人员** 对象作为辅助对象。 将A到B关系选择为，“每个‘A’记录必须至少具有一个相关的‘B’记录。” 从此处，您将关联“买方接触点”对象，并选择B和C对象之间的相同关系。

   ![](assets/4.jpg)

1. 保存并开始构建一些报表！
