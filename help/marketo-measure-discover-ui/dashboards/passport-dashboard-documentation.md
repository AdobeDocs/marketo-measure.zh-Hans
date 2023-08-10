---
unique-page-id: 42762628
description: Passport仪表板文档 —  [!DNL Marketo Measure]  — 产品文档
title: Passport仪表板文档
exl-id: 43cb01a8-d02e-4086-af57-d7ec9275f87a
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Passport仪表板文档 {#passport-dashboard-documentation}

Passport仪表板使营销人员能够查看在给定时间段内经历了每个管道阶段的潜在客户/联系人和机会。

此仪表板有两个图块：

* Opportunities：在给定时间范围内每个阶段传递的Opportunity记录数。
* 潜在客户/联系人：在给定时间范围内通过每个阶段的Lead或Contact记录数。

>[!NOTE]
>
>在所有Discover功能板中，只能报告一个人员对象，即潜在客户或联系人。 此参数设置于 [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

此仪表板支持以下筛选器（所有筛选器都应用于两个图块）：

* 日期：选择时间范围。
* 渠道：按渠道筛选记录。 如果某个渠道的任何接触点与该渠道相关联，则记录与该渠道相关联。
* 子渠道：按子渠道筛选记录。 如果记录的任何接触点与子渠道相关联，则该记录与子渠道相关联。
* 促销活动：按促销活动过滤记录。 如果记录的任何接触点与营销活动关联，则记录与该营销活动关联。
* 促销活动来源：按促销活动来源筛选记录。 促销活动源示例包括Adwords、BingAds、Facebook、LinkedIn等。 如果记录的任何接触点与促销活动源关联，则记录与促销活动源关联。
* CRM帐户名称：按CRM帐户名称筛选记录。
* 区段过滤器：按自定义区段过滤记录。 如果记录的任何接触点与区段相关联，则该记录与区段相关联。

在所有过滤器中，都会使用“与”逻辑。

>[!NOTE]
>
>如果记录在选定日期更改阶段，则记录将被计入起始和终止阶段以及所有传递阶段。

## 机会 {#opportunities}

![](assets/one-1.png)

阶段包括OC，未结机会阶段中的选定漏斗阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])和成功的机会阶段([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping])。

>[!NOTE]
>
>对于成功的阶段，记录计数仅适用于在选定的时间范围内转换为阶段的记录。

您可以从每个栏向下展开以查看每个阶段的Opportunity记录。

## 潜在客户/联系人 {#leads-contacts}

![](assets/two-1.png)

阶段包括FT、LC、在设置上的开放潜在客户/联系人阶段中选择的漏斗阶段 — CRM — 阶段映射，以及在设置上的转化后的潜在客户/联系人阶段 — CRM — 阶段映射。

>[!NOTE]
>
>对于已转换的阶段，记录计数仅适用于在选定时间范围内转换为阶段的记录。

您可以从每个栏向下展开以查看每个阶段的Lead/Contact记录。
