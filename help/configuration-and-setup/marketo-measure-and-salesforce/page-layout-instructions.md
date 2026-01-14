---
description: 面向Marketo Measure用户的页面布局说明指南
title: 页面布局说明
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# 页面布局说明 {#page-layout-instructions}

>[!NOTE]
>
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但仍可在CRM中看到“Bizible”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

为了轻松查看[!DNL Marketo Measure]数据，建议更新[!UICONTROL Account]、[!UICONTROL Contact]、[!UICONTROL Lead]、[!UICONTROL Opportunity]和[!UICONTROL Campaign]对象的页面布局。 下面的每个“对象页面布局”的说明都进行了细分。

要开始，请先导航到您的[!DNL Salesforce]设置并找到[!UICONTROL Customize]选项卡。

## 营销活动对象 {#campaign-object}

建议您仅针对沙盒将[!DNL Marketo Measure]字段添加到SFDC Campaign。 这些字段可用于测试接触点生成。 在生产环境中，建议仅添加[!DNL Marketo Measure]批量更新接触点日期按钮。 不建议将[!DNL Marketo Measure]字段添加到生产环境，因为您可以创建Campaign同步规则。

1. 在“生成”选项中，选择&#x200B;**[!UICONTROL Campaigns]**。

1. 单击 **[!UICONTROL Page Layouts]**。

   ![](assets/marketo-salesforce-7.jpg)

1. 单击要更新的页面布局旁边的&#x200B;**[!UICONTROL Edit]**。

   ![](assets/marketo-salesforce-1.jpg)

1. 在[!UICONTROL fields]选项中，选择&#x200B;**[!UICONTROL Enable Buyer Touchpoints]**&#x200B;字段，并将其拖动到页面上所需的任何位置。 接下来，添加&#x200B;**[!UICONTROL Touchpoint Start Date]**&#x200B;和&#x200B;**[!UICONTROL Touchpoint End Date]**&#x200B;字段。

   ![](assets/bizible-full-1.png)

1. 接下来，在页面顶部单击快速查找菜单中的“[!UICONTROL Buttons]”选项。

1. 将&#x200B;**[!UICONTROL Bulk Update Touchpoint Date]**&#x200B;按钮拖动到自定义按钮部分。

   ![](assets/bizible-taxonomy-1.png)

1. 单击 **[!UICONTROL Save]**。

   >[!NOTE]
   >
   >如果您使用多个Campaign记录类型，则必须更新&#x200B;**[!UICONTROL Enable Buyer Touchpoints]**&#x200B;字段的选取列表值。 有关说明，请参阅[本文](/help/channel-tracking-and-setup/offline-channels/configurations-record-types.md)。

## 潜在客户 {#leads}

1. 在“生成”选项中，选择&#x200B;**[!UICONTROL Leads]**。

1. 单击 **[!UICONTROL Page Layouts]**。

1. 单击要更新的页面布局旁边的&#x200B;**[!UICONTROL Edit]**。 请记住，多个页面布局可以包含“买方接触点”部分。

1. 单击快速查找菜单左侧的VisualForce页面选项。

1. 创建一个部分并将其命名为“购买者接触点”。

1. 将&#x200B;**[!UICONTROL Marketo Measure Lead Related List]** VisualForce页面拖动到页面布局分区中。

   ![](assets/connect-salesforce-1.png)

1. 单击[!DNL VisualForce]页面中的扳手，然后将高度更改为100并启用滚动条。

1. 返回菜单，选择[!UICONTROL Canvas Apps]分区，并在您创建的接触点[!DNL VisualForce]分区下创建名为“Marketo Measure Insights”的分区。

1. 将[!DNL Marketo Measure Insights]画布应用程序拖入新创建的分区。 单击 **Save**。有时，在放入画布应用程序之前必须先保存页面布局，因为Salesforce无法立即识别此布局。 因此，在创建部分后，保存页面布局，然后重新编辑以将画布应用程序拖动到该部分中。 这适用于每个对象。

   >[!NOTE]
   >
   >要使[!DNL Marketo Measure Insights] Canvas应用正常运行，必须正确配置[权限](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md)。

如果您使用的是[!DNL Marketo Measure] ABM功能，[请单击此处获取其他页面布局说明](/help/advanced-features/account-based-marketing/account-based-marketing-overview.md)。

## 联系人 {#contacts}

1. 在“生成”选项中，选择&#x200B;**[!UICONTROL Contacts]**。

1. 单击 **[!UICONTROL Page Layouts]**。

1. 选择要编辑的页面布局。

   转到快速查找菜单中的“相关列表”选项，然后添加&#x200B;**[!UICONTROL Buyer Touchpoints]**&#x200B;相关列表。

1. 单击扳手图标，并按此顺序添加以下列：

   * Buyer Touchpoint
   * 营销渠道
   * 接触点Source
   * 广告营销活动名称
   * 接触点位置
   * 接触点日期

1. 排序依据：接触点日期，升序。

   ![](assets/marketo-salesforce-15.jpg)

1. 展开按钮选项并取消选择&#x200B;**[!UICONTROL New]**。

   ![](assets/marketo-salesforce-12.png)

1. 返回菜单中的[!UICONTROL Related List]选项，现在添加&#x200B;**[!UICONTROL Buyer Attribution Touchpoint]**&#x200B;相关列表。

1. 单击扳手图标，并按此顺序添加以下列：

   * 归因接触点
   * 营销渠道
   * 机会
   * 广告营销活动名称
   * 接触点类型
   * 接触点位置
   * 归因% W型（_或最可靠的归因模型，如完整路径或自定义_）
   * 收入W型（_或最可靠的归因模型，如Full Path或Custom_）
   * 接触点日期

1. 按接触点[!UICONTROL Date] > [!UICONTROL Ascending]排序。

1. 展开“按钮”部分并取消选择&#x200B;**[!UICONTROL New]**。

1. 单击 **[!UICONTROL Save]**。

## 商机 {#opportunities}

1. 在“生成”选项中，选择&#x200B;**[!UICONTROL Opportunities]**。

1. 单击 **[!UICONTROL Page Layouts]**。

1. 选择要编辑的页面布局。

1. 添加&#x200B;**[!UICONTROL Buyer Attribution Touchpoint]**&#x200B;相关列表并单击扳手为机会添加以下列：

   * 归因接触点
   * 营销渠道
   * 联系人
   * 广告营销活动名称
   * 接触点类型
   * 接触点位置
   * 归因% W型（_或最可靠的归因模型，如完整路径或自定义_）
   * 收入W型（_或最可靠的归因模型，如Full Path或Custom_）
   * 接触点日期

1. 按[!UICONTROL Touchpoint Date] > [!UICONTROL Ascending]排序。

1. 在&#x200B;**[!UICONTROL New]**&#x200B;部分中取消选择[!UICONTROL Buttons]。

1. 单击 **[!UICONTROL Save]**。

## 帐户 {#accounts}

1. 在“生成”选项中，选择&#x200B;**[!UICONTROL Accounts]**。

1. 单击 **[!UICONTROL Page Layouts]**。

1. 选择要编辑的页面布局。

1. 添加&#x200B;**[!UICONTROL Buyer Attribution Touchpoint]**&#x200B;相关列表并单击扳手以添加以下列：

   * 归因接触点
   * 营销渠道
   * 机会
   * 广告营销活动名称
   * 接触点类型
   * 接触点位置
   * 归因% W型（_或最可靠的归因模型，如完整路径或自定义_）
   * 收入W型（_或最可靠的归因模型，如Full Path或Custom_）
   * 接触点日期

1. 按接触点日期>升序排序。

1. 在&#x200B;**[!UICONTROL New]**&#x200B;部分中取消选择[!UICONTROL Buttons]。

1. 单击 **[!UICONTROL Save]**。

如果您使用的是[!DNL Marketo Measure] ABM功能，请查看[其他页面布局说明](/help/advanced-features/account-based-marketing/account-based-marketing-overview.md)。
