---
unique-page-id: 18874614
description: 具有买方接触点的潜在客户报告 —  [!DNL Marketo Measure]
title: 具有采购员接触点的潜在客户报表
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# 具有采购员接触点的潜在客户报表 {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但在您的CRM中仍会看到“[!DNL Bizible]”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

在涉及[!DNL Marketo Measure]时，您开箱即用地拥有许多报告功能，但我们建议构建其他一些报告类型。 了解如何创建具有买方接触点的内含性潜在客户报告类型。

1. 导航到[!DNL Salesforce]中的设置选项。 从那里，展开“创建”分组并选择&#x200B;**[!UICONTROL Report Types]**。

   ![](assets/1.jpg)

1. 选择&#x200B;**[!UICONTROL New Custom Report Type]**。

   ![](assets/2.jpg)

1. 将主要对象设置为“Leads”，并在“Report Type Label”输入“Leads with Buyer Touchpoints - Inclusive”中设置。 将报告存储在“潜在客户”类别中并将部署状态更改为&#x200B;**[!UICONTROL Deployed]**。 然后选择&#x200B;**[!UICONTROL Next]**。

   ![](assets/3.jpg)

1. 对于对象关系，选择&#x200B;**[!DNL Marketo Measure]人员**&#x200B;对象作为辅助对象。 选择A到B的关系，因为“每个‘A’记录必须至少有一个相关的‘B’记录。” 从该位置，您将会关联“Buyer Touchpoint”对象，并在B对象和C对象之间选择相同的关系。

   ![](assets/4.jpg)

1. 保存并开始构建一些报告！
