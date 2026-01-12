---
description: 无业务机会的联系人的报表类型
title: 无业务机会的联系人的报表类型
exl-id: 255048be-16ff-4964-85fd-cc07888a05af
feature: Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---


# 无业务机会的联系人的报表类型 {#report-type-for-contacts-without-opportunities}

>[!NOTE]
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但在您的CRM中仍会看到“[!DNL Bizible]”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

要报告未与Opportunity关联的Contacts with Buyer Touchpoints ，您需要创建自定义报告类型。

1. 转到&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Report Types]**。

   Salesforce设置中的![报告类型页面](assets/1.jpg)

1. 选择 **[!UICONTROL New Custom Report Type]**。

   ![新自定义报告类型选择屏幕](assets/2.jpg)

1. 将[!UICONTROL Primary Object]设置为“[!UICONTROL Contacts]”。 将报表类型标签命名为“Contacts with Buyer Touchpoints”（具有采购员接触点的联系人）。 对报表类型名称使用相同的命名。 在描述输入“Contacts with Buyer Touchpoints（与买方接触点的联系人）”中。 将报告保存在“[!UICONTROL Other]”中，并将报告设置为“[!UICONTROL Deployed]”。

   ![报告类型详细信息，将联系人作为主要对象](assets/3.jpg)

1. 从那里，您将将Contacts对象链接到Buyer接触点对象。 确保您选择按钮“每个“A”记录必须至少有一个相关的“B”记录。

   ![对象关系配置将联系人链接到购买者接触点](assets/4.jpg)

1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;即完成！
