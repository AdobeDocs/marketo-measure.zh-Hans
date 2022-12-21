---
unique-page-id: 18874578
description: 营销活动和营销活动成员 —  [!DNL Marketo Measure]  — 产品文档
title: 营销活动和营销活动成员
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 0%

---

# 营销活动和营销活动成员 {#campaigns-and-campaign-members}

[!DNL Salesforce] 促销活动旨在跟踪与营销计划或活动关联的潜在客户和联系人列表。 这通常是网络研讨会、注册或展位访问，例如。 营销人员可以选择营销活动是否应在接触点历程中获得点数。

## 启用接触点 {#enabling-touchpoints}

的 [!DNL Marketo Measure] [!DNL Salesforce] 资源包将包括Campaign对象上标有“启用买方接触点”的字段。 将字段添加到页面布局后，将显示类似于以下内容：

![](assets/1.png)

选取列表中可用的选项包括：

![](assets/2.png)

* 包括所有营销活动成员 — 添加到营销活动的每个潜在客户或联系人都将收到与该营销活动关联的接触点。
* 仅包括“已响应”营销活动成员 — 只有具有“已响应”营销活动成员状态的潜在客户或联系人才会收到与该营销活动关联的接触点。
* 排除所有营销活动成员 — 所有潜在客户或联系人都不会收到与该营销活动关联的接触点。

请注意，促销活动成员必须具有与其记录关联的电子邮件地址，才能 [!DNL Marketo Measure] 创建接触点。 没有电子邮件地址， [!DNL Marketo Measure] 不会为营销活动成员分配接触点。

## 促销活动同步日期 {#campaign-sync-dates}

安装好包装后， [!DNL Marketo Measure] 还将在Campaign对象中包含2个日期字段：接触点开始日期和接触点结束日期。

这些日期显示 [!DNL Marketo Measure] 何时应开始或停止将营销活动成员从营销活动包含到接触点历程中。 您可以设置一个日期，或者同时设置两个日期，或者根本不设置任何日期。

## 接触点开始日期的用例 {#use-case-for-touchpoint-start-date}

如果现有促销活动用于跟踪潜在客户和联系人，但用户只想在新系统或流程到位后开始测量，因此他们决定设置一次开始日期 [!DNL Marketo Measure] 应开始跟踪这些促销活动成员。

## 接触点结束日期的用例 {#use-case-for-touchpoint-end-date}

如果在使用之前 [!DNL Marketo Measure]，则会使用营销自动化平台来跟踪潜在客户的数字交互（IE表单提交），然后将这些潜在客户上传到 [!DNL Saleforce] Campaign中，您可以使用接触点结束日期字段。 您会将“接触点结束日期”设置为您的开始日期，其中 [!DNL Marketo Measure] 并启用“购买者接触点”，则这些潜在客户的每个数字交互都将创建为接触点。 您将接触点结束日期设置为开始日期的原因，具体包括 [!DNL Marketo Measure] 因为，今后，我们将通过我们的javascript跟踪这些数字交互。

![](assets/3.png)

## 营销活动成员 {#campaign-members}

促销活动成员嵌套在 [!UICONTROL Campaigns]、和与潜在客户或联系人相关。 潜在客户或联系人只能在营销活动中添加一次，这可能会因营销活动的用例而异。 同步营销活动后，营销活动成员资格将用作营销活动，放入接触点历程中并像表单填充一样进行处理。

## 买方接触点状态 {#buyer-touchpoint-status}

如果启用， [!DNL Marketo Measure] 将在安装包中包含的4个不同字段中向营销活动成员推送状态值：接触点状态（潜在客户）、接触点状态（联系人）、接触点状态（机会）和接触点状态日期。 这有助于客户根据与接触点相关的对象，审核是否已将接触点创建为买方接触点或买方归因接触点。 接触点状态日期只是营销活动成员上状态更新的最后一个日期。

![](assets/4.png)

## 采购员接触点日期 {#buyer-touchpoint-date}

安装好包装后， [!DNL Marketo Measure] 还包括营销活动成员上标记为“采购员接触点日期”的字段。 这允许用户覆盖 [!DNL Marketo Measure] 将用于接触点记录上的接触点日期。

如果在事件实际发生后的数天/数周/数月上传了列表，则可能需要执行此操作。 有多种方法可以同时更新所有记录，具体说明如下。

![](assets/5.png)

要了解您是否需要使用买方接触点日期，请参阅以下日期的确定方式 [!DNL Marketo Measure] 取决于 [!UICONTROL Sync Type] 选定的营销活动。

如果 [!UICONTROL Sync Type] 设置为“包含所有营销活动成员”，则设置接触点日期的优先级从上到下：

* 采购员接触点日期
* 营销活动成员创建日期

如果 [!UICONTROL Sync Type] 设置为“仅包含‘响应的’营销活动成员”，则设置接触点日期的优先级从上到下：

* 采购员接触点日期
* 首次响应日期
   * 将状态更改为“已响应”且是标准日期后，系统会立即自动设置“首次响应日期” [!DNL Salesforce] 字段

* 营销活动成员创建日期

## 批量更新接触点日期 {#bulk-update-touchpoint-date}

已安装的中包含批量更新接触点日期 [!DNL Marketo Measure] [!DNL Salesforce] 包和按钮需要添加到页面布局中。

![](assets/6.png)

如果需要更新大量促销活动成员记录，则可以使用 [!UICONTROL Bulk Update Touchpoint Date] 按钮进行批量编辑。

如果此界面未涵盖的独特用例，则还可以使用 [数据加载器](https://dataloader.io/){target=&quot;_blank&quot;}以导出记录、进行更改并将记录上载回。

首先，搜索记录并筛选您要为其设置买方接触点日期的记录。

>[!CAUTION]
>
>有一个搜索不起作用，如以下示例所示。 UI不支持搜索空的买方接触点日期（以下搜索不起作用）：

![](assets/7.png)

如果您不需要使用搜索，而只需将日期应用于每个促销活动成员记录，请使用“[!UICONTROL Include All Records]“ ”复选框（请参阅下面的屏幕截图），这将检查所有页面上的所有记录。

从日历选取器中选择日期和时间。 如果要选择当前日期和时间，请单击日历选取器旁边显示的日期/时间。

设置日期和时间后，单击 **[!UICONTROL Update Selected Records]** 按钮以应用更改。

![](assets/8.png)

## 促销活动成本 {#campaign-costs}

了解营销活动成本的所有信息 [在本文中](/help/marketing-spend/spend-management/crm-campaign-costs.md).

## 删除营销活动成员 {#campaign-member-removal}

那样 [!DNL Marketo Measure] 跟踪Salesforce中任何已删除的记录，无论这些记录是被删除的Lead、帐户还是Opportunity，都是在API中查看这些记录并跟踪某个条目是否标记为“IsDeleted”。 遗憾的是，Salesforce对Campaign成员采取了不同的方式，从Campaign中删除这些Campaign成员，而实际上只是将它们标记为“已删除”，而不是“已删除”，因此问题在于接触点仍在Salesforce中，这些接触点与已删除的Campaign成员相关。

为了解决这个问题， [!DNL Marketo Measure] 已创建 [!DNL Marketo Measure] 每当删除促销活动成员时要跟踪的历史记录对象和触发器，然后删除相应的接触点。 **您将需要 [!DNL Marketo Measure] Marketing Analytics包V6.15或更高版本** 以使用此功能。

>[!CAUTION]
>
>请记住，此触发器不会跟踪过去删除的任何营销活动成员，因此它只会继续工作。 如果您需要删除大量过去的营销活动成员触点，请联系 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}。

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] 大学：促销活动对象字段](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
>
>[[!DNL Marketo Measure] 大学：映射离线渠道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
