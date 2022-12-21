---
unique-page-id: 42762628
description: 护照仪表板文档 —  [!DNL Marketo Measure]  — 产品文档
title: 护照仪表板文档
exl-id: 43cb01a8-d02e-4086-af57-d7ec9275f87a
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# 护照仪表板文档 {#passport-dashboard-documentation}

Passport仪表板使营销人员能够查看在给定时间段内通过每个管道阶段的潜在客户/联系人和机会。

此功能板有两个图块：

* 机会：在给定时间范围内每个阶段传递的Opportunity记录数。
* 潜在客户/联系人：在给定时间范围内，每个阶段通过的潜在客户或联系人记录数。

>[!NOTE]
>
>在所有Discover功能板中，只能报告一个人员对象（潜在客户或联系人）。 在中设置 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

此功能板支持以下过滤器（所有过滤器都适用于两个图块）：

* 日期：选择时间范围。
* 渠道：按渠道筛选记录。 如果某个记录的任何接触点与该渠道相关联，则该记录与该渠道相关联。
* 子渠道：按子渠道筛选记录。 如果记录的任何接触点与子渠道相关联，则记录与子渠道相关联。
* 营销活动：按营销活动过滤记录。 如果某个记录的任何接触点与该营销活动相关联，则该记录会与该营销活动关联。
* 促销活动来源：按促销活动源过滤记录。 促销活动源示例包括Adwords、BingAds、Facebook、LinkedIn等。 如果某个记录的任何接触点与该促销活动源关联，则该记录会与该促销活动源关联。
* CRM帐户名称：按CRM帐户名过滤记录。
* 区段过滤器：按自定义区段过滤记录。 如果某个记录的任何接触点与该区段相关联，则该记录会与该区段关联。

在所有过滤器中，都使用“与”逻辑。

>[!NOTE]
>
>如果记录在选定日期发生更改阶段，则记录将被计为开始和结束阶段以及所有传递阶段的记录。

## 机会 {#opportunities}

![](assets/one-1.png)

阶段包括OC，在Open Opportunity阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])和赢得机会阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

>[!NOTE]
>
>对于Won阶段，记录计数只适用于在选定时间范围内过渡到阶段的记录。

您可以从每个栏向下展开以查看每个阶段的Opportunity记录。

## 潜在客户/联系人 {#leads-contacts}

![](assets/two-1.png)

阶段包括FT、LC、在“设置”上的“开放潜在客户/联系人”阶段中选择的漏斗阶段 — CRM — 阶段映射，以及在“设置”上的“已转换的潜在客户/联系人”阶段 — CRM — 阶段映射。

>[!NOTE]
>
>对于已转换的阶段，记录计数仅适用于在选定时间范围内转换为阶段的记录。

您可以从每个栏向下展开，以查看每个阶段的潜在客户/联系人记录。
