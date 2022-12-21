---
unique-page-id: 18874598
description: 脱机自定义渠道设置 —  [!DNL Marketo Measure]  — 产品文档
title: 脱机自定义渠道设置
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# 脱机自定义渠道设置 {#offline-custom-channel-setup}

## 快速入门 {#getting-started}

与方式比较 [!DNL Marketo Measure] 处理在线渠道规则时，您会注意到离线渠道规则不需要使用电子表格。 但是，实施计划中仍提供了一个工作表，因为这有助于深入思考组织离线渠道的方式。

电子表格包含三列：

![](assets/1-2.png)

**[!UICONTROL Salesforce]促销活动类型**  — 添加 [!DNL Salesforce] 此处

* 例如，这可以是电子邮件、网络研讨会、会议，或您为此字段创建的要归因接触点的任何值。

**[!UICONTROL Channel]**  — 在此处添加各种营销渠道

**[!UICONTROL Subchannel]**  — 在此处添加任何对应的子渠道

## 离线渠道逻辑 {#offline-channel-logic}

[!DNL Marketo Measure] 离线渠道逻辑由Campaign对象确定，特别是 [!DNL Salesforce] 促销活动类型。 每个离线工作都必须具有 [!DNL Salesforce] 促销活动类型，如晚餐或商展，因为 [!DNL Marketo Measure] 依赖此字段来了解要映射到的渠道和子渠道。

SFDC促销活动类型将显示在离线渠道的选项卡中，该选项卡列于 [!DNL Salesforce] 促销活动类型。 请注意 [!DNL Marketo Measure] 只能为具有与其关联的买方接触点的促销活动导入SFDC促销活动类型。

![](assets/2-2.png)

在这里，您可以在 [!DNL Marketo Measure] 应用程序。 这可能涉及在 [!DNL Marketo Measure] 应用程序，该操作在应用程序的创建渠道部分中完成，如下图所示。 需要为 [!DNL Marketo Measure] 以了解在何处推送接触点。 您可以决定希望如何映射营销活动类型。

![](assets/3-2.png)

## 渠道映射示例 {#channel-mapping-example}

例如，假设您参加了两个 [!DNL Salesforce] 每年召开会议。 但是，每个会议都非常不同，并且具有唯一的目标受众。 你想知道其中哪一种能带来更多价值。 在 [!DNL Salesforce] 环境中，您可以将1月事件的促销活动类型设为“会议”，将渠道命名为“[!DNL Salesforce]、和您的子渠道“一月会议”。

现在，你也想为6月的会议做同样的事。 您认为，由于这也是一个会议，因此可以为它提供相同的促销活动类型，在本例中为“会议”。 频道是一样的， [!DNL Salesforce]，第二次会议的子渠道是“六月会议”。 从组织角度讲，这是合理的。 但是，这对 [!DNL Marketo Measure] 逻辑读取和应用这些规则，因为两个营销活动具有相同的营销活动类型。 [!DNL Marketo Measure] 脚本无法将数据从一种类型映射到两个不同的子渠道。 这意味着您需要为每个子渠道创建新的促销活动类型，但子渠道可以具有相同的渠道。

以下是逻辑的示例 [!DNL Marketo Measure] 不会读：

![](assets/4-2.png)

在上述方案中，您将需要创建唯一的促销活动类型，因为您无法将相同的促销活动类型映射到两个不同的子渠道。 相反，您需要设置如下独特类型：

![](assets/5-2.png)

渠道映射中必须包含任何现有的促销活动类型，并且应添加“NULL”作为渠道。

花些时间去 [!DNL Salesforce] 确定要包括的现有记录类型的数量和性质，以及是否需要根据上述信息创建其他营销活动。 填写完所有必需信息后，即可上传。

详细了解 [正在脱机 [!DNL Salesforce] 促销活动 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md).

## 为在线营销工作处理SFDC促销活动 {#handling-sfdc-campaigns-for-online-marketing-efforts}

营销团队通常会创建 [!DNL Salesforce] 活动来跟踪各种数字营销工作。 这种做法没有问题；但是，对这些营销活动的处理方式应与真正的离线营销活动（例如直邮或会议）有所不同。 与数字事件（网站上发生的交互）相关的营销活动不应与 [!DNL Marketo Measure]. 同步这些营销活动将导致接触点重复，因为 [!DNL Marketo Measure] JavaScript已在跟踪在线工作。

处理在线活动促销活动的另一个提示是映射 [!DNL Salesforce] 促销活动类型为NULL。 为此，请先在 [!DNL Marketo Measure] 名为NULL的应用程序，如下图所示。 这位于 [!DNL Marketo Measure] 应用程序 **创建渠道** 中。 当某个不应同步的营销活动意外同步时，此功能将非常有用。 通过查看存储在NULL下的所有内容，可以轻松找到营销活动并更正同步状态。

![](assets/6-2.png)

## 在应用程序中输入离线渠道规则 {#entering-your-offline-channel-rules-to-the-app}

使用自定义规则编辑并更新电子表格后，下一步是在 [!DNL Marketo Measure] 应用程序 — 您实际上不会为离线渠道上传电子表格。 相反，您将在选取列表框中输入如下图所示的信息。 可通过单击 **[!UICONTROL Offline Channels]** 下 **[!UICONTROL Channels]** 中。

![](assets/7-2.png)

>[!TIP]
>
>想要确定 _when_ a [!DNL Salesforce] 促销活动类型会被拉入 [!DNL Marketo Measure] 渠道映射？ 只需转到 **[!UICONTROL Setup]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Fields]** > **[!UICONTROL Type]**. 然后，您可以在选取列表中查看哪些值以及哪些值不活动。 不活动的用户不会在“”中显示为可选类型[!UICONTROL Offline Channels]“ ”部分。 请注意，此过程可能需要花费几分钟到48小时的时间。

单击 **[!UICONTROL Save]** 等你完成并 [!DNL Marketo Measure] 将上传更改并重新处理数据。

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] 大学：映射离线渠道](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>* [[!DNL Marketo Measure] 大学：正在同步离线营销活动](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63286e34d9f0367662b78b)
>
>* [Marketo Engage程序集成](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping)

