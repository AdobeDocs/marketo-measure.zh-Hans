---
description: 面向Marketo Measure用户的支出管理方法指导
title: 支出管理方法
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# 支出管理方法 {#spend-management-methods}

支出数据对于[!DNL Marketo Measure]的ROI报表的成功至关重要。 要对所有渠道和子渠道进行准确而全面的ROI报告，您必须确保将适当的支出数据提取到[!DNL Marketo Measure]中。

有三种方法可将支出数据导入[!DNL Marketo Measure]。 每种方法都设计为从特定数据输入中提取支出数据。

**1个API连接的帐户**

您通过API连接到[!DNL Marketo Measure]的任何广告帐户其支出会自动提取到[!DNL Marketo Measure]中以生成ROI报表。 要检查您已连接并因此拉入支出的帐户，请转到您的[!DNL Marketo Measure]应用程序并选择[!UICONTROL Connections]部分下的[!UICONTROL Integrations]选项卡。 有关设置API连接的更多详细信息，请查看[集成的广告平台](/help/api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms)。

**2 CRM Campaign成本同步**

每个[!DNL Marketo Measure]帐户都可以访问名为[同步CRM促销活动成本](/help/marketing-spend/crm-campaign-costs.md#availability)的功能。 默认情况下，此功能位设置为“否”，但可以随时打开。

![](assets/spend-management-1.png)

启用此功能后，将自动从符合以下条件的任何CRM营销活动/项目中拉入花费：

i. [!DNL Marketo Measure]首先查看促销活动/项目是否通过已创建的匹配[促销活动同步规则](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)或已创建的匹配[项目同步规则](/help/marketo-measure-and-marketo/marketo-engage-programs-integration.md)创建接触点，或者[启用购买者接触点值](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints)是“包括所有促销活动成员”或“包括‘已回复’促销活动成员”。

二、 必须在营销活动/项目群中填充开始日期

三、 必须在营销活动/项目群中填充结束日期

四、 必须指定实际成本(对于SFDC中的营销活动)或期间成本(对于Marketo中的项目)。

**3手动成本上传**

此方法允许您[手动上传API连接帐户或CRM Campaign成本同步未涵盖的渠道和子渠道的支出数据](/help/marketing-spend/marketing-channel-costs.md#uploading-marketing-costs)。 通过导航到[!DNL Marketo Measure]设置中的“营销支出”部分，您可以通过CSV文件上传任何渠道的支出数据。

客户可以使用这三种方法的组合来管理他们的支出，具体取决于[!DNL Marketo Measure]的特定设置。 由于有三种方法可将支出导入[!DNL Marketo Measure]，因此我们强烈建议您使用位于Discover中的营销支出展示板全面了解所有支出数据。 此展示板是您能够查看所有渠道及其相关支出的唯一位置。 营销支出委员会可帮助您快速识别支出数据中可能存在差距的地方，以及如何改进ROI报告。
