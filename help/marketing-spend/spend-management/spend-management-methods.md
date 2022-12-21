---
description: 支出管理方法 —  [!DNL Marketo Measure]  — 产品文档
title: 支出管理方法
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# 支出管理方法 {#spend-management-methods}

支出数据是ROI报告成功与 [!DNL Marketo Measure]. 为了在所有渠道和子渠道中获得准确且全面的ROI报告，您需要确保将适当的支出数据提取到 [!DNL Marketo Measure].

有三种方法可将支出数据导入 [!DNL Marketo Measure]. 每种方法都设计为从特定数据输入中提取支出数据。

**1)API连接帐户**

您连接到的任何广告帐户 [!DNL Marketo Measure] 通过API自动将其支出提取到 [!DNL Marketo Measure] ROI报表。 要检查您连接了哪些帐户并因此而吸引了支出，请转到 [!DNL Marketo Measure] 应用程序，然后选择 [!UICONTROL Connections] 选项卡 [!UICONTROL Integrations] 中。 有关如何设置API连接的更多详细信息，请查看我们的 [集成广告平台](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) 文章。

**2)CRM促销活动成本同步**

每 [!DNL Marketo Measure] 帐户有权访问名为 [同步CRM促销活动成本](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). 默认情况下，此功能位设置为“否”，但可以随时打开。

![](assets/spend-management-methods-1.png)

启用此功能后，将自动从满足以下条件的任何CRM促销活动/项目中提取支出

i. [!DNL Marketo Measure] 首先查看营销活动/项目是否正在创建接触点，即 [促销活动同步规则](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) 已创建，或匹配 [程序同步规则](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) 创建的，或 [启用买方接触点值](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) 为“包含所有营销活动成员”或“包含‘已响应’营销活动成员”。

ii. 必须在营销活动/项目群中填充开始日期

三。 营销活动/项目还必须填充结束日期

四。 最后，必须指定“实际成本”（对于SFDC中的促销活动）或“期间成本”(对于Marketo中的项目)。

**3)人工成本上传**

此方法允许您 [手动上载支出数据](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) 适用于API连接帐户或CRM促销活动成本同步未涵盖的渠道和子渠道。 导航到 [!DNL Marketo Measure] 设置时，您可以通过CSV文件为任何渠道上传支出数据。

客户可以结合使用以下三种方法来管理其支出，具体取决于 [!DNL Marketo Measure]. 因为有三种方法可以将支出导入 [!DNL Marketo Measure]，我们强烈建议您利用位于Discover的营销支出展示板全面了解所有支出数据。 在此展示板中，您将能够看到所有渠道及其相关支出。 营销支出展示板可以帮助您快速确定支出数据中可能存在的缺口，以及如何提高ROI报告。
