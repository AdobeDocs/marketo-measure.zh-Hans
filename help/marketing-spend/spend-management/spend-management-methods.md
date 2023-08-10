---
description: 支出管理方法 —  [!DNL Marketo Measure]  — 产品文档
title: 支出管理方法
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# 支出管理方法 {#spend-management-methods}

支出数据是投资回报率报告成功的关键 [!DNL Marketo Measure]. 要对所有渠道和子渠道生成准确而全面的ROI报表，您需要确保将适当的支出数据提取到中 [!DNL Marketo Measure].

有三种方法可将支出数据导入 [!DNL Marketo Measure]. 每种方法都设计为从特定数据输入中提取支出数据。

**1) API连接帐户**

您连接到的任何广告帐户 [!DNL Marketo Measure] 通过API将让其支出自动提取到 [!DNL Marketo Measure] （对于ROI报告）。 要检查您连接了哪些帐户，从而拉入了支出，请转到 [!DNL Marketo Measure] 应用并选择 [!UICONTROL Connections] 选项卡 [!UICONTROL Integrations] 部分。 有关如何设置API连接的更多详细信息，请参阅我们的 [集成式广告平台](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) 文章。

**2) CRM Campaign成本同步**

每 [!DNL Marketo Measure] 帐户有权访问名为的功能 [同步CRM Campaign成本](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). 默认情况下，此功能位设置为“否”，但可以随时打开。

![](assets/spend-management-methods-1.png)

启用此功能后，将自动从满足以下条件的任何CRM营销活动/项目中拉入支出

i. [!DNL Marketo Measure] 首先查看促销活动/项目是否通过匹配项创建接触点 [Campaign同步规则](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) 已创建，或匹配的 [程序同步规则](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) 创建的任何对象，或 [启用买方接触点值](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) 是“包括所有营销活动成员”或“包括‘已响应’营销活动成员”。

二、 必须在营销活动/项目群中填充开始日期

三、 还必须在营销策划/项目群中填充结束日期

四、 最后，必须指定实际成本（对于SFDC中的促销活动）或期间成本(对于Marketo中的项目群)。

**3)人工成本上传**

此方法允许您 [手动上传支出数据](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) API连接帐户或CRM Campaign Cost Sync未涵盖的那些渠道和子渠道。 导航到 [!DNL Marketo Measure] 设置，您可以通过CSV文件上传任何渠道的支出数据。

客户可以使用这三种方法的组合来管理他们的支出，具体取决于 [!DNL Marketo Measure]. 因为有三种方法可以将支出汇入 [!DNL Marketo Measure]，我们强烈建议您利用位于发现中的营销支出展示板，全面了解所有支出数据。 此展示板是您能够查看所有渠道及其相关支出的唯一位置。 营销支出委员会可帮助您快速识别支出数据中可能存在差距的地方，以及如何改进ROI报告。
