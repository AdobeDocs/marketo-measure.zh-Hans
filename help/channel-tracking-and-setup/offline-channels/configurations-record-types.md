---
description: 多个营销活动记录类型的配置 —  [!DNL Marketo Measure]
title: 多个营销活动记录类型的配置
exl-id: 10499556-a591-4630-9149-ae676e6494af
feature: Channels
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---


# 多个营销活动记录类型的配置 {#configurations-for-multiple-campaign-record-types}

**“启用购买者接触点”字段中缺少挑选列表值**

如果您的SFDC组织使用多种促销活动记录类型，则必须为每个记录类型添加“启用采购员接触点”的选择列表值。 要添加选项，请执行以下步骤。

1. 转到&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Record Types]**。

   ![Salesforce促销活动记录类型列表](assets/1.jpg)

1. 通过单击&#x200B;**[!UICONTROL Record Type Label]**&#x200B;而不是[!UICONTROL edit]按钮选择营销活动记录类型。

   ![营销活动记录类型详细信息页面](assets/2.jpg)

1. 此时您会看到该记录类型的可用选择列表。 选择“启用买方接触点”字段旁边的&#x200B;**[!UICONTROL Edit]**。

   显示“启用买方接触点”字段的![选择列表部分](assets/3.jpg)

1. 将“可用值”分组中的所有三个值添加到“选定值”分组。

   ![正在编辑启用购买者接触点选取列表值](assets/4.jpg)

1. 将默认值设置为“无”并单击&#x200B;**[!UICONTROL Save]**。 对任何其他Campaign记录类型重复此操作。
