---
unique-page-id: 18874799
description: 页面布局说明 —  [!DNL Marketo Measure]  — 产品文档
title: 页面布局说明
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 1%

---

# 页面布局说明 {#page-layout-instructions}

>[!NOTE]
>
>您可能会看到指定“[!DNL Marketo Measure]“ ”，但仍会在您的CRM中看到“Bizible”。 我们正在努力更新该版本，并且该品牌重命名将很快地反映在您的CRM中。

轻松查看 [!DNL Marketo Measure] 数据，建议更新 [!UICONTROL Account], [!UICONTROL Contact], [!UICONTROL Lead], [!UICONTROL Opportunity]和 [!UICONTROL Campaign] 对象。 下面针对每个“对象页面布局”说明进行了说明。

要开始，请首先导航到 [!DNL Salesforce] 设置设置并找到 [!UICONTROL Customize] 选项卡。

## 营销活动对象 {#campaign-object}

我们建议将 [!DNL Marketo Measure] 仅针对沙盒的SFDC Campaign字段。 这些字段可用于测试接触点生成。 在生产中，我们建议仅将 [!DNL Marketo Measure] 批量更新接触点日期按钮。 我们不建议将 [!DNL Marketo Measure] 字段，因为您可以创建Campaign同步规则规则。

1. 在“生成”选项中，选择 **[!UICONTROL Campaigns]**.

1. 单击 **[!UICONTROL Page Layouts]**.

   ![](assets/1-1.jpg)

1. 单击 **[!UICONTROL Edit]** 页面布局旁边。

   ![](assets/2-1.jpg)

1. 在 [!UICONTROL fields] 选项，选择 **[!UICONTROL Enable Buyer Touchpoints]** 字段，并将其拖动到页面上的任意位置。 接下来，添加 **[!UICONTROL Touchpoint Start Date]** 和 **[!UICONTROL Touchpoint End Date]** 字段。

   ![](assets/3-2.png)

1. 接下来，在页面顶部单击[!UICONTROL Buttons]“快速查找”菜单中的“ ”选项。

1. 拖动 **[!UICONTROL Bulk Update Touchpoint Date]** 按钮。

   ![](assets/4-1.jpg)

1. 单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多个营销活动记录类型，则 **[!UICONTROL Enable Buyer Touchpoints]** 字段。 请参考 [本文](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md) 中。

## 潜在客户 {#leads}

1. 在“生成”选项中，选择 **[!UICONTROL Leads]**.

1. 单击 **[!UICONTROL Page Layouts]**.

1. 单击 **[!UICONTROL Edit]** 页面布局旁边。 请记住，多个页面布局可以包含“买方接触点”部分。

1. 单击快速查找菜单左侧的VisualForce页面选项。

1. 创建新部分，并将其命名为“购买者接触点”。

   >[!NOTE]
   >
   >为每个部分选择“一列”格式。

1. 拖动 **[!UICONTROL Marketo Measure Lead Related List]** 将VisualForce页面放入页面布局部分。

   ![](assets/5-1.png)

1. 单击 [!DNL VisualForce] 页面并将高度更改为100并启用滚动条。

1. 返回菜单，选择 [!UICONTROL Canvas Apps] 部分，并在接触点下方创建一个名为“Marketo Measure分析”的新部分 [!DNL VisualForce] 区域。

   >[!NOTE]
   >
   >为每个部分选择“一列”格式。

1. 拖动 [!DNL Marketo Measure Insights] 将Canvas应用程序移入新创建的部分。 单击 **保存**. 有时，在放入画布应用程序之前，需要先保存页面布局，因为Salesforce无法立即识别它。 因此，在创建新部分后，保存页面布局，然后重新编辑以拖动该部分中的画布应用程序。 这适用于每个对象。

   >[!NOTE]
   >
   >对于 [!DNL Marketo Measure Insights] Canvas应用程序正常运行， [需要正确配置权限](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

   >[!TIP]
   >
   >大多数客户不会使用以(FT)或(LC)结尾的字段，因为它们是 [!DNL Marketo Measure] 接触点作为对象存在。

如果您使用 [!DNL Marketo Measure] 反弹道导弹特征， [请单击此处获取其他页面布局说明](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).

## 联系人 {#contacts}

1. 在“生成”选项中，选择 **[!UICONTROL Contacts]**.

1. 单击 **[!UICONTROL Page Layouts]**.

1. 选择要编辑的页面布局。

   转到快速查找菜单中的“相关列表”选项，然后添加 **[!UICONTROL Buyer Touchpoints]** 相关列表。

1. 单击扳手图标，按此顺序添加以下列：

   * 买方接触点
   * 营销渠道
   * 接触点源
   * 广告促销活动名称
   * 接触点位置
   * 接触点日期

1. 排序依据：接触点日期，升序。

   ![](assets/6.jpg)

1. 展开按钮选项并取消选择 **[!UICONTROL New]**.

   ![](assets/7.png)

1. 返回到 [!UICONTROL Related List] 选项，现在将 **[!UICONTROL Buyer Attribution Touchpoint]** 相关列表。

1. 单击扳手图标，按此顺序添加以下列：

   * 归因接触点
   * 营销渠道
   * 机会
   * 广告促销活动名称
   * 接触点类型
   * 接触点位置
   * 归因% W型(_或最可靠的归因模型（如完整路径或自定义）_)
   * 收入W型(_或最可靠的归因模型（如完整路径或自定义）_)
   * 接触点日期

1. 按接触点排序 [!UICONTROL Date] > [!UICONTROL Ascending].

1. 展开按钮部分并取消选择 **[!UICONTROL New]**.

1. 单击 **[!UICONTROL Save]**.

## 机会 {#opportunities}

1. 在“生成”选项中，选择 **[!UICONTROL Opportunities]**.

1. 单击 **[!UICONTROL Page Layouts]**.

1. 选择要编辑的页面布局。

1. 添加 **[!UICONTROL Buyer Attribution Touchpoint]** Related List（相关列表）并单击扳手，为Opportunity添加以下列：

   * 归因接触点
   * 营销渠道
   * 联系人
   * 广告促销活动名称
   * 接触点类型
   * 接触点位置
   * 归因% W型(_或最可靠的归因模型（如完整路径或自定义）_)
   * 收入W型(_或最可靠的归因模型（如完整路径或自定义）_)
   * 接触点日期

1. 排序依据 [!UICONTROL Touchpoint Date] > [!UICONTROL Ascending].

1. 取消选择 **[!UICONTROL New]** 在 [!UICONTROL Buttons] 中。

1. 单击 **[!UICONTROL Save]**.

## 帐户 {#accounts}

1. 在“生成”选项中，选择 **[!UICONTROL Accounts]**.

1. 单击 **[!UICONTROL Page Layouts]**.

1. 选择要编辑的页面布局。

1. 添加 **[!UICONTROL Buyer Attribution Touchpoint]** “相关列表”(Related List)，然后单击扳手以添加以下列：

   * 归因接触点
   * 营销渠道
   * 机会
   * 广告促销活动名称
   * 接触点类型
   * 接触点位置
   * 归因% W型(_或最可靠的归因模型（如完整路径或自定义）_)
   * 收入W型(_或最可靠的归因模型（如完整路径或自定义）_)
   * 接触点日期

1. 按接触点日期>升序排序。

1. 取消选择 **[!UICONTROL New]** 在 [!UICONTROL Buttons] 中。

1. 单击 **[!UICONTROL Save]**.

如果您使用 [!DNL Marketo Measure] 反弹道导弹特征，  [请单击此处获取其他页面布局说明](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).
