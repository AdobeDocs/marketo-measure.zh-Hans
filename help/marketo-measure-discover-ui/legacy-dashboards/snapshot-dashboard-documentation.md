---
unique-page-id: 42762600
description: 快照功能板文档 —  [!DNL Marketo Measure]
title: 快照功能板文档
exl-id: 4dfc92d2-ccab-4726-a869-3ae32aa89a5f
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---

# 快照功能板文档 {#snapshot-dashboard-documentation}

Snapshot仪表板允许您查看CRM在任何给定时间点的状态，以及记录在Lead/Contact和Opportunity阶段中的分布。

此仪表板有两个图块：

* **潜在客户/联系人快照：** 在选定日期的每个阶段中的Lead或Contact记录数。

>[!NOTE]
>
>在所有Discover功能板中，只能报告一个人员对象，即潜在客户或联系人。 此参数设置于 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

* **机会快照：** 在选定日期每个阶段中的Opportunity记录数。

此仪表板支持以下筛选器（所有筛选器都应用于两个图块）：

* 快照日期：选择快照日期。
* CRM帐户ID/名称：按CRM帐户ID或名称筛选记录。

>[!NOTE]
>
>建议仅显示名称。

* 渠道：按渠道筛选记录。 如果某个渠道的任何接触点与该渠道相关联，则记录与该渠道相关联。
* 子渠道：按子渠道筛选记录。 如果记录的任何接触点与子渠道相关联，则该记录与子渠道相关联。
* 促销活动：按促销活动过滤记录。 如果记录的任何接触点与营销活动关联，则记录与该营销活动关联。
* 促销活动来源：按促销活动来源筛选记录。 促销活动源示例包括 [!DNL Adwords]， [!DNL BingAds]， [!DNL Facebook]， [!DNL LinkedIn]，等等。 如果记录的任何接触点与促销活动源关联，则记录与促销活动源关联。
* 广告帐户ID/名称：按广告帐户ID或名称筛选记录。 如果记录的任何接触点与所选广告帐户中的营销活动相关联，则将其关联到广告帐户。

>[!NOTE]
>
>建议仅显示名称。

* 区段过滤器：按自定义区段过滤记录。 如果记录的任何接触点与区段相关联，则该记录与区段相关联。

在所有过滤器中，都会使用“与”逻辑。

>[!NOTE]
>
>如果记录在选定日期更改阶段，则记录将被计入起始和终止阶段以及所有传递阶段。

## 潜在客户/联系人快照 {#lead-contact-snapshot}

![](assets/one.png)

阶段包括FT、LC和选定的漏斗阶段（在开放导线/接触阶段中）([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

您可以从每个栏向下展开以查看每个阶段的Lead/Contact记录。

## 机会快照 {#opportunity-snapshot}

![](assets/two.png)

阶段包括FT、LC、Open Lead/Contact阶段中的选定漏斗阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。 和Open Opportunity阶段中的OC和选定漏斗阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

您可以从每个栏向下展开以查看每个阶段的Opportunity记录。
