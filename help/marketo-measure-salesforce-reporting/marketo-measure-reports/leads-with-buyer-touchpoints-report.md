---
unique-page-id: 18874614
description: 具有买方接触点的潜在客户报表 —  [!DNL Marketo Measure]  — 产品文档
title: 具有采购员接触点的潜在客户报表
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# 具有采购员接触点的潜在客户报表 {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>您可能会看到说明“[!DNL Marketo Measure]”已添加到我们的文档中，但仍会看到“[!DNL Bizible]”（在您的CRM中）。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

开箱即用地提供多种报告功能，触手可及 [!DNL Marketo Measure]，但是我们建议构建其他一些报表类型。 了解如何创建具有买方接触点的内含性潜在客户报告类型。

1. 导航到中的设置选项 [!DNL Salesforce]. 从那里，展开“创建”分组并选择 **[!UICONTROL Report Types]**.

   ![](assets/1.jpg)

1. 选择 **[!UICONTROL New Custom Report Type]**.

   ![](assets/2.jpg)

1. 将主要对象设置为“Leads”，并在“Report Type Label”输入“Leads with Buyer Touchpoints - Inclusive”中设置。 将报告存储在“潜在客户”类别中，并将部署状态更改为 **[!UICONTROL Deployed]**. 然后选择 **[!UICONTROL Next]**.

   ![](assets/3.jpg)

1. 对于对象关系，选择 **[!DNL Marketo Measure]人员** 对象作为辅助对象。 选择A到B的关系，因为“每个‘A’记录必须至少有一个相关的‘B’记录。” 从那里，您将关联“买方接触点”对象并在B和C对象之间选择相同的关系。

   ![](assets/4.jpg)

1. 保存并开始构建一些报告！
