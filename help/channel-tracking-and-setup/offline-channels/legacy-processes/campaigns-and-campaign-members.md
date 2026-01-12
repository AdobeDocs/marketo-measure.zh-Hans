---
description: 营销活动和营销活动成员 —  [!DNL Marketo Measure]
title: 营销活动和营销活动成员
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
feature: Channels
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 0%

---


# 营销活动和营销活动成员 {#campaigns-and-campaign-members}

[!DNL Salesforce]营销活动旨在跟踪与营销计划或活动关联的潜在客户和联系人列表。 例如，这通常是网络研讨会、注册或两次访问。 营销人员可以选择是否应在接触点历程中计入营销活动。

>[!NOTE]
>本文介绍了一个过时的流程。 我们鼓励用户使用[新的、改进的应用程序内进程](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}。

## 启用接触点 {#enabling-touchpoints}

[!DNL Marketo Measure] [!DNL Salesforce]包将在营销活动对象中包含一个标记为“启用购买者接触点”的字段。 将字段添加到页面布局后，它将显示为以下形式：

![Salesforce促销活动页面布局显示“启用买方接触点”字段](assets/1.png)

选择列表中可用的选项包括：

![启用具有营销活动成员包含选项的买方接触点选取列表下拉列表](assets/2.png)

* 包括所有营销活动成员 — 添加到营销活动的每个潜在客户或联系人都将收到与该营销活动关联的接触点。
* 仅包括“已回复”营销活动成员 — 仅营销活动成员状态为“已回复”的潜在客户或联系人将收到与该营销活动关联的接触点。
* 排除所有营销活动成员 — 任何潜在客户或联系人都不会收到与该营销活动关联的接触点。

请注意，营销活动成员必须具有与其记录关联的电子邮件地址，才能[!DNL Marketo Measure]创建接触点。 如果没有电子邮件地址，[!DNL Marketo Measure]将不会向营销活动成员分配接触点。

## Campaign同步日期 {#campaign-sync-dates}

在安装包时，[!DNL Marketo Measure]还将包含Campaign对象上的2个日期字段：接触点开始日期和接触点结束日期。

这些日期告知[!DNL Marketo Measure]我们应何时开始或停止将营销活动中的营销活动成员纳入接触点历程。 您可以设置一个日期，也可以同时设置这两个日期，或者根本不设置任何日期。

## 接触点开始日期的用例 {#use-case-for-touchpoint-start-date}

开始日期可用于以下情况：现有营销活动用于跟踪潜在客户和联系人，但用户希望仅在实施新系统或流程后开始衡量，因此他们决定设置开始日期一次[!DNL Marketo Measure]应开始跟踪这些营销活动成员。

## 接触点结束日期的用例 {#use-case-for-touchpoint-end-date}

如果在使用[!DNL Marketo Measure]之前，您使用营销自动化平台跟踪了商机的数字交互（即表单提交），然后将这些商机上传到[!DNL Saleforce]营销活动中，则可以使用接触点结束日期字段。 您应该将接触点结束日期设置为开始日期[!DNL Marketo Measure]并启用买方接触点，然后这些商机的每个数字交互都将创建为接触点。 您通过[!DNL Marketo Measure]将接触点结束日期设置为开始日期的原因是，从今以后，我们将通过javascript跟踪这些数字交互。

![显示接触点开始日期和接触点结束日期字段的营销活动记录](assets/3.png)

## 营销活动成员 {#campaign-members}

营销活动成员嵌套在[!UICONTROL Campaigns]下，并与潜在客户或联系人相关。 一个商机或联系人只能添加到营销策划中一次，根据Campaign的用例，这可能有问题。 同步营销活动时，营销活动成员资格用作营销活动，该活动会放入接触点历程中，并被视为表单填充。

## Buyer Touchpoint状态 {#buyer-touchpoint-status}

如果启用，[!DNL Marketo Measure]将通过4个包含在已安装包中的不同字段将状态值推送到Campaign成员上：接触点状态（潜在客户）、接触点状态（联系人）、接触点状态（机会）和接触点状态日期。 这有助于客户审核接触点是否已创建为Buyer Touchpoint或Buyer Attribution Touchpoint，具体取决于其相关的对象。 接触点状态日期只是营销活动成员上次更新状态的日期。

![显示潜在客户、联系人、商机和状态日期的接触点状态字段的营销活动成员记录](assets/4.png)

## Buyer Touchpoint日期 {#buyer-touchpoint-date}

在安装包时，[!DNL Marketo Measure]在营销活动成员上还包含一个标记为“Buyer Touchpoint日期”的字段。 这允许用户覆盖[!DNL Marketo Measure]在接触点记录上的接触点日期所使用的日期。

如果在实际发生事件后的数天/数周/数月上传列表，则可能必须执行此操作。 有多种方法可一次更新所有记录，具体说明如下。

![包含Buyer Touchpoint日期字段的促销活动成员记录以进行日期覆盖](assets/5.png)

为了了解是否需要使用Buyer Touchpoint日期，以下是[!DNL Marketo Measure]根据为营销活动选择的[!UICONTROL Sync Type]来确定日期的方式。

如果[!UICONTROL Sync Type]设置为“包括所有营销活动成员”，则设置接触点日期的优先级为从上到下：

* Buyer Touchpoint日期
* 营销活动成员创建日期

如果[!UICONTROL Sync Type]设置为“仅包括‘已响应’营销活动成员”，则设置接触点日期的优先级为从上到下：

* Buyer Touchpoint日期
* 首次响应日期
   * 一旦状态更改为“已响应”，就会自动设置第一个响应日期，并且该日期是无法更改的标准[!DNL Salesforce]字段

* 营销活动成员创建日期

## 批量更新接触点日期 {#bulk-update-touchpoint-date}

批量更新接触点日期包含在已安装的[!DNL Marketo Measure] [!DNL Salesforce]包中，并且按钮需要添加到页面布局中。

![具有批量更新接触点日期按钮的营销活动页面布局](assets/6.png)

如果需要更新大量营销活动成员记录，您可以使用[!UICONTROL Bulk Update Touchpoint Date]按钮进行成批编辑。

如果此界面未涵盖某些独特用例，您还可以使用[数据加载器](https://dataloader.io/){target="_blank"}导出记录、进行更改并将记录重新上传。

首先，搜索记录并筛选要为其设置Buyer Touchpoint日期的记录。

>[!CAUTION]
>有一个搜索不起作用，如下面的示例所示。 UI不支持搜索空的Buyer Touchpoint日期（以下搜索不起作用）：

![批量更新界面显示不支持的搜索null Buyer Touchpoint日期](assets/7.png)

如果您不需要使用搜索并将日期仅应用于每个促销活动成员记录，请使用&quot;[!UICONTROL Include All Records]&quot;复选框（见下面的屏幕快照），这将检查所有页面上的所有记录。

从日历选取器中选择日期和时间。 如果要选择当前日期和时间，请单击日历选取器旁边显示的日期/时间。

设置日期和时间后，单击&#x200B;**[!UICONTROL Update Selected Records]**&#x200B;按钮以应用更改。

![使用日历选择器批量更新接触点日期界面并更新选定的记录按钮](assets/8.png)

## 营销活动成本 {#campaign-costs}

请参阅本文[以了解有关Campaign成本](/help/marketing-spend/crm-campaign-costs.md){target="_blank"}的所有信息。

## 活动成员删除 {#campaign-member-removal}

[!DNL Marketo Measure]与Salesforce中所有已删除的记录（无论这些记录是已删除的潜在客户、客户还是商机）保持同步的方法是查看API中的这些记录，并跟踪条目是否标记为“IsDeleted”。 不幸的是，对于营销活动成员，Salesforce引入了一种从营销活动中删除这些营销活动成员的不同方式，实际上，这些成员仅标记为“已删除”，而不是“已删除”，因此问题在于接触点仍然存在于Salesforce中，并且与已删除的营销活动成员相关。

为了解决此问题，[!DNL Marketo Measure]创建了一个[!DNL Marketo Measure]历史记录对象和一个触发器，用于在移除营销活动成员时进行跟踪，然后删除相应的接触点。 **您需要[!DNL Marketo Measure] Marketing Analytics V6.15或更高版本**&#x200B;才能使用此功能。

>[!CAUTION]
>请记住，此触发器不会跟踪过去删除的任何营销活动成员，因此这仅适用于以后的营销活动。 如果您需要移除大量过去促销活动成员的接触点，请联系[Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。

>[!MORELIKETHIS]
>[[!DNL Marketo Measure] 教程： Campaign对象字段](https://experienceleague.adobe.com/zh-hans/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/campaign-object-fields){target="_blank"}
>[[!DNL Marketo Measure] 教程：映射脱机渠道](https://experienceleague.adobe.com/zh-hans/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
