---
unique-page-id: 42762600
description: 快照功能板文档 —  [!DNL Marketo Measure]  — 产品文档
title: 快照功能板文档
exl-id: 4dfc92d2-ccab-4726-a869-3ae32aa89a5f
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# 快照功能板文档 {#snapshot-dashboard-documentation}

快照功能板让您能够查看CRM在任何给定时间点的状态，以及在潜在客户/联系和机会阶段之间的记录分发。

此功能板有两个图块：

* **潜在客户/联系人快照：** 选定日期每个阶段中潜在客户或联系人记录的数量。

>[!NOTE]
>
>在所有Discover功能板中，只能报告一个人员对象（潜在客户或联系人）。 在中设置 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

* **机会快照：** 在选定的日期，每个阶段中的Opportunity记录数。

此功能板支持以下过滤器（所有过滤器都适用于两个图块）：

* 快照日期：选择快照日期。
* CRM帐户ID/名称：按CRM帐户ID或名称过滤记录。

>[!NOTE]
>
>建议仅显示名称。

* 渠道：按渠道筛选记录。 如果某个记录的任何接触点与该渠道相关联，则该记录与该渠道相关联。
* 子渠道：按子渠道筛选记录。 如果记录的任何接触点与子渠道相关联，则记录与子渠道相关联。
* 营销活动：按营销活动过滤记录。 如果某个记录的任何接触点与该营销活动相关联，则该记录会与该营销活动关联。
* 促销活动来源：按促销活动源过滤记录。 促销活动源示例包括 [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn]等。 如果某个记录的任何接触点与该促销活动源关联，则该记录会与该促销活动源关联。
* 广告帐户ID/名称：按广告帐户ID或名称过滤记录。 如果某个记录的任何接触点与来自选定广告帐户的营销活动相关联，则该记录会与该广告帐户关联。

>[!NOTE]
>
>建议仅显示名称。

* 区段过滤器：按自定义区段过滤记录。 如果某个记录的任何接触点与该区段相关联，则该记录会与该区段关联。

在所有过滤器中，都使用“与”逻辑。

>[!NOTE]
>
>如果记录在选定日期发生更改阶段，则记录将被计为开始和结束阶段以及所有传递阶段的记录。

## 潜在客户/联系人快照 {#lead-contact-snapshot}

![](assets/one.png)

阶段包括FT、LC和“开放潜在客户/联系”阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

您可以从每个栏向下展开，以查看每个阶段的潜在客户/联系人记录。

## 机会快照 {#opportunity-snapshot}

![](assets/two.png)

阶段包括FT、LC、在开放潜在客户/联系阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。 和Open Opportunity阶段中的OC和选定的漏斗阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

您可以从每个栏向下展开以查看每个阶段的Opportunity记录。
