---
unique-page-id: 18874578
description: 营销活动和营销活动成员 —  [!DNL Marketo Measure]
title: 营销活动和营销活动成员
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
feature: Channels
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 0%

---

# 营销活动和营销活动成员 {#campaigns-and-campaign-members}

[!DNL Salesforce] 营销活动旨在跟踪与营销方案或活动关联的潜在客户和联系人列表。 例如，这通常是网络研讨会、注册或两次访问。 营销人员可以选择是否应在接触点历程中计入营销活动。

>[!NOTE]
>
>本文介绍了一个过时的流程。 我们鼓励用户使用 [新的、改进的应用程序内流程](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

## 启用接触点 {#enabling-touchpoints}

此 [!DNL Marketo Measure] [!DNL Salesforce] 程序包将在Campaign对象中包含一个标记为“启用购买者接触点”的字段。 将字段添加到页面布局后，它将显示为以下形式：

![](assets/1.png)

选择列表中可用的选项包括：

![](assets/2.png)

* 包括所有营销活动成员 — 添加到营销活动的每个潜在客户或联系人都将收到与该营销活动关联的接触点。
* 仅包括“已回复”营销活动成员 — 仅营销活动成员状态为“已回复”的潜在客户或联系人将收到与该营销活动关联的接触点。
* 排除所有营销活动成员 — 任何潜在客户或联系人都不会收到与该营销活动关联的接触点。

请注意，营销活动成员必须拥有与其记录关联的电子邮件地址，才能 [!DNL Marketo Measure] 以创建接触点。 如果没有电子邮件地址， [!DNL Marketo Measure] 不会向营销活动成员分配接触点。

## Campaign同步日期 {#campaign-sync-dates}

安装软件包后， [!DNL Marketo Measure] 还将包括Campaign对象上的2个日期字段：接触点开始日期和接触点结束日期。

这些日期表明 [!DNL Marketo Measure] 开始或停止将促销活动中的促销活动成员纳入接触点历程的时间。 您可以设置一个日期，也可以同时设置这两个日期，或者根本不设置任何日期。

## 接触点开始日期的用例 {#use-case-for-touchpoint-start-date}

如果现有Campaign用于跟踪潜在客户和联系人，但用户希望仅在新系统或流程到位后开始衡量，因此他们决定设置一次开始日期，则可以使用开始日期 [!DNL Marketo Measure] 应该开始跟踪这些营销活动成员。

## 接触点结束日期的用例 {#use-case-for-touchpoint-end-date}

如果在使用之前 [!DNL Marketo Measure]，您使用了一个营销自动化平台来跟踪潜在客户的数字交互（IE表单提交），然后将这些潜在客户上传到 [!DNL Saleforce] Campaign中，您可以使用接触点结束日期字段。 您要将接触点结束日期设置为开始日期 [!DNL Marketo Measure] 并启用买方接触点，则每个潜在客户的数字交互都将创建为接触点。 您要将接触点结束日期设置为开始日期的原因 [!DNL Marketo Measure] 这是因为，展望未来，我们将通过我们的javascript跟踪这些数字交互。

![](assets/3.png)

## 营销活动成员 {#campaign-members}

活动成员嵌套在 [!UICONTROL Campaigns]、和与潜在客户或联系人相关。 一个商机或联系人只能添加到营销策划中一次，根据Campaign的用例，这可能有问题。 同步营销活动时，营销活动成员资格用作营销活动，该活动会放入接触点历程中，并被视为表单填充。

## 买方接触点状态 {#buyer-touchpoint-status}

如果启用， [!DNL Marketo Measure] 将通过4个包含在已安装资源包中的不同字段将状态值推送到Campaign成员：接触点状态(Lead)、接触点状态(Contact)、接触点状态(Opportunity)和接触点状态日期。 这有助于客户审核接触点是否已创建为买方接触点或买方归因接触点，具体取决于其相关的对象。 接触点状态日期只是营销活动成员上次更新状态的日期。

![](assets/4.png)

## 买方接触点日期 {#buyer-touchpoint-date}

安装软件包后， [!DNL Marketo Measure] 另外，促销活动成员上还有一个标有“购买者接触点日期”的字段。 这允许用户覆盖以下日期 [!DNL Marketo Measure] 会将用于接触点记录上的接触点日期。

如果在实际发生事件后的数天/数周/数月上传列表，则可能必须执行此操作。 有多种方法可一次更新所有记录，具体说明如下。

![](assets/5.png)

要了解是否需要使用“买方接触点日期”，以下是如何确定日期的 [!DNL Marketo Measure] 根据 [!UICONTROL Sync Type] 为营销活动选定的附加内容（选件大小、配置文件、值、参数等）。

如果 [!UICONTROL Sync Type] 设置为“包括所有营销活动成员”，则设置接触点日期的优先级从上到下：

* 买方接触点日期
* 营销活动成员创建日期

如果 [!UICONTROL Sync Type] 设置为“仅包括‘已响应’营销活动成员”，设置接触点日期的优先级从上到下：

* 买方接触点日期
* 首次响应日期
   * 一旦状态更改为“已响应”，就会自动设置第一个响应日期，并且该日期为标准日期 [!DNL Salesforce] 无法更改的字段

* 营销活动成员创建日期

## 批量更新接触点日期 {#bulk-update-touchpoint-date}

批量更新接触点日期包含在已安装的中 [!DNL Marketo Measure] [!DNL Salesforce] 需要将包和按钮添加到页面布局。

![](assets/6.png)

如果需要更新大量Campaign成员记录，您可以使用 [!UICONTROL Bulk Update Touchpoint Date] 按钮进行批量编辑。

如果此界面不包含某些独特用例，您还可以使用 [数据加载器](https://dataloader.io/){target="_blank"} 要导出记录，请进行更改，然后上传回记录。

首先，搜索记录并筛选要为其设置采购员接触点日期的记录。

>[!CAUTION]
>
>有一个搜索不起作用，如下面的示例所示。 UI不支持搜索空的买方接触点日期（以下搜索不起作用）：

![](assets/7.png)

如果您不需要使用搜索，只需将日期应用于每个促销活动成员记录，则使用&#39;&#39;[!UICONTROL Include All Records]”复选框（请参阅下面的屏幕快照），这将检查所有页面上的所有记录。

从日历选取器中选择日期和时间。 如果要选择当前日期和时间，请单击日历选取器旁边显示的日期/时间。

设置日期和时间后，单击 **[!UICONTROL Update Selected Records]** 按钮以应用更改。

![](assets/8.png)

## 营销活动成本 {#campaign-costs}

全面了解Campaign成本 [本文内容](/help/marketing-spend/spend-management/crm-campaign-costs.md).

## 活动成员删除 {#campaign-member-removal}

这种方式 [!DNL Marketo Measure] 与Salesforce中所有已删除的记录保持联系（无论这些记录是已删除的“潜在客户”、“客户”还是“业务机会”），就是在API中查看这些记录并跟踪条目是否标记为“IsDeleted”。 不幸的是，对于营销活动成员，Salesforce引入了另一种从营销活动中删除这些营销活动成员的方式，它们实际上只标记为“已删除”，而不是“已删除”，因此问题是，接触点仍然驻留在Salesforce中与已删除的营销活动成员相关的接触点。

要解决此问题， [!DNL Marketo Measure] 已创建 [!DNL Marketo Measure] 历史记录对象和触发器，用于在移除促销活动成员时进行跟踪，然后删除相应的接触点。 **您将需要 [!DNL Marketo Measure] Marketing Analytics包V6.15或更高版本** 以使用此功能。

>[!CAUTION]
>
>请记住，此触发器不会跟踪过去删除的任何营销活动成员，因此这仅适用于以后的营销活动。 如果您需要删除大量过去促销活动成员的接触点，请联系 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] University： Campaign对象字段](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
>
>[[!DNL Marketo Measure] 大学：映射离线渠道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
