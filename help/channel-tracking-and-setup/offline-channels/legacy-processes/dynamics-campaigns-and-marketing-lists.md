---
unique-page-id: 18874610
description: Dynamics营销活动和营销列表 —  [!DNL Marketo Measure]  — 产品文档
title: Dynamics活动和营销列表
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
feature: Microsoft Dynamics
source-git-commit: 38c721d10ac33ae85da1d425b6af53b9e3dfd0a1
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---

# Dynamics活动和营销列表 {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>本文介绍了一个过时的流程。 我们鼓励用户使用 [新的、改进的应用程序内流程](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

## 营销活动 {#campaigns}

Dynamics营销活动有助于跟踪离线营销活动，并将其包含在全渠道历程中。 营销活动必须与潜在客户或联系人关联，并可通过“营销活动响应”或“营销活动列表”汇总到营销活动。

## 营销活动响应 {#campaign-responses}

将潜在客户或联系人直接添加到Campaign时，输入为Campaign响应记录。

![](assets/1.png)

## 启用接触点 {#enable-touchpoints}

要在接触点历程中包含这些记录，可通过几个选项来选择要同步的Campaign响应类型。 在Campaign记录上，安装的解决方案中应该有一个自定义字段，标签为“[!UICONTROL Enable Buyer Touchpoints]“ 如果没有看到此内容，则需要通过表单编辑器添加字段。

![](assets/2.png)

您可以选择在营销策划中包含具有营销策划响应的所有记录，或者仅包含响应为“感兴趣”的记录，或者在默认情况下，您根本不能包含营销策划响应。 您可以将此字段留空或明确选择将其排除。

[!DNL Marketo Measure] 不支持自定义响应值。

![](assets/3.png)

这些是Campaign响应的库存响应值：

![](assets/4.png)

根据您的选择，这些记录现在有资格使用Lead 、 Contact或Opportunity历程中的接触点。 如果他们符合条件，则历程中将显示“Dynamics Campaign”接触点。

Campaign响应可能不会显示的一个原因是，已记录潜在客户/联系人的首次接触和/或潜在客户创建接触活动，并且“PostLC”功能已禁用或已达到其最大接触点数。

## 接触点日期 {#touchpoint-date}

营销活动的接触点日期通常是向营销活动添加营销活动响应的日期。 如果填充了来自已安装解决方案中标记为“购买者接触点日期”的自定义字段，则可以覆盖此字段。 如果没有看到此内容，则需要通过表单编辑器添加字段。

此字段的一个常见示例适用于以下事件：事件的徽章扫描列表在事件发生后添加到CRM中，因此用户实际上可以将“购买者接触点日期”更改回事件发生时。

![](assets/5.png)

## 营销列表 {#marketing-lists}

营销列表是将潜在客户或联系人包含在营销历程中的另一种方式。 市场营销列表对于一组潜在客户或联系人是唯一的，这意味着用户必须选择其列表是一组潜在客户还是一组联系人。

[!DNL Marketo Measure] 仅支持静态营销列表。 我们不支持动态营销列表，因为我们的处理要求我们检查记录的修改日期，但由于动态列表经常更改，因此没有的修改日期 [!DNL Marketo Measure] 以对其进行检查。 这将需要在一天中持续下载完整数据集。

![](assets/6.png)

上面的屏幕截图是潜在客户的营销列表。 营销列表与营销活动关联，并可与多个营销活动关联。 除非您只为一个营销活动创建一个营销列表， [!DNL Marketo Measure] 不建议客户使用营销列表来跟踪其营销活动。 同一组商机/联系人不太可能适用于多个促销活动中的接触点。

## 启用接触点 {#enable-touchpoints-1}

要为接触点启用营销列表，营销活动记录上有一个单独的设置，标记为“[!UICONTROL Sync Marketing Lists]，这是一个简单的yes/no开关。 如果没有看到此内容，则需要通过表单编辑器添加字段。 在促销活动记录中，您可以查看哪些营销列表与促销活动相关，这样您便知道要启用多少列表。

![](assets/7.png)

## 接触点日期 {#touchpoint-date-1}

营销列表的接触点日期通常是ListMember的创建日期，因此是将潜在客户或联系人添加到营销列表的日期。 如果填充了来自已安装解决方案中标记为“购买者接触点日期”的自定义字段，则可以覆盖此字段。 如果没有看到此内容，则需要通过表单编辑器添加字段。

![](assets/8.png)

## 渠道映射 {#channel-mapping}

Dynamics营销活动使用“营销活动类型”字段在自定义营销渠道中进行分段。 可以在Dynamics的“自定义”菜单中更改这些设置。

促销活动类型菜单中的值将提取到 [!DNL Marketo Measure] 应用程序。 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**.

对于每种营销活动类型，都可以将其映射到渠道和子渠道组合，以便从营销活动派生的每个接触点都具有正确的映射渠道和子渠道。

![](assets/9.png)

![](assets/10.png)

## Campaign同步日期 {#campaign-sync-date}

Dynamics客户无法执行此操作

## 常见问题 {#faq}

**我们能否在Dynamics中启用营销列表上的接触点或仅启用营销活动？**

您可以启用营销列表，但此列表需要与促销活动相关联，因为同步营销列表的选项存在于促销活动中。

**我们能否在营销活动中使用营销活动响应和营销列表？**

是的。 
