---
unique-page-id: 18874704
description: 活动归因常见问题解答 —  [!DNL Marketo Measure]
title: 活动归因常见问题解答
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 0%

---

# 活动归因常见问题解答 {#activities-attribution-faq}

[!DNL Marketo Measure] 活动会导入您的所有活动记录并为它们生成接触点，从而允许这些活动接收归因点数。 最常见的用例是跟踪Sales团队的活动，因为它们通常会创建发送给潜在客户的电话或电子邮件记录。 可以跟踪的其他独特内容是内容交互，如资源下载或视频查看。

**这与“离线营销活动”有何不同？**

最大的区别是，促销活动只能提供一个接触点，因为促销活动只允许每个潜在客户或联系人拥有一个促销活动成员。 这意味着您无法跟踪出站呼叫、演示或网络研讨会与会者等定期事件，除非您为每个分组创建单独的营销活动。 利用活动，可测量每个事件。

**任务、事件和活动之间是否有区别？**

Activities对象作为Task和Event对象的伞形或父对象。 活动基本上同时包含任务和事件。 任务通常用于记录快速的一次性项目，如电话或电子邮件。 事件通常用于可能有开始或结束日期的项目，例如会议或会议。

**如果我有一个销售线索或联系人与同一个重复执行任务，我是否会看到所有这些任务的买方接触点？**

是的。 已同步的活动与创建的接触点之间存在1:1的关系。

**我如何知道哪些记录会导致创建接触点？**

一个有效的建议是，首先在CRM中使用Activity对象设置过滤器。 根据筛选规则，这会为您提供符合该条件的记录数方面的良好信息，然后您可以根据需要对其进行优化。 虽然这不是必需的，但是通过此方式可以帮助用户了解在设置活动规则后将创建多少活动接触点。

**什么是 [!DNL Marketo Measure] 促销活动名称？**

由于这些活动会产生接触点， [!DNL Marketo Measure] 必须知道他们属于哪个渠道和子渠道。 对于每个规则，您需要提供 [!DNL Marketo Measure] 营销活动名称。 创建之后，使用在线渠道CSV映射该 [!DNL Marketo Measure] 促销活动名称到相应的渠道。 此 [!DNL Marketo Measure] Campaign Name也会出现在中的接触点上 [!UICONTROL Ad Campaign Name] 字段。

**填充了哪些其他接触点字段？**

| **接触点字段** | **值** |
|---|---|
| 潜在客户/联系人 | 所有活动都与潜在客户或联系人相关 |
| Campaign | Channel.Subchannel [[!DNL Marketo Measure]] |
| 接触点源 | CRM活动 |
| 中 | Activity.Type |
| 接触点类型 | Activity.Type |
| 广告营销活动名称 | [!DNL Marketo Measure] 营销活动名称 |
| 广告内容 | 活动主题 |
| 广告ID | 活动外部Id |
| 接触点日期 | [自定义 — 在应用程序中设置] |

**如果需要为每个销售代表创建不同的规则，该怎么办？ 我是否需要创建其他 [!DNL Marketo Measure] 促销活动？**

不，你没有。 “动态营销活动名称”允许您填写部分（或全部） [!DNL Marketo Measure] 促销活动名称，使用引用活动对象中的字段的“替换参数”。 例如，如果您拥有 [!DNL Marketo Measure] 促销活动名称为“Outbound Call” ，但您希望销售代表位于末尾，请获取CRM字段名称并调用 [!DNL Marketo Measure] 营销活动名称“出站呼叫” {AssignedTo}“或”出站呼叫 {CreatedBy}“

**如何在中设置活动 [!DNL Marketo Measure] 应用程序？**

关于如何在中配置活动的说明 [!UICONTROL Marketo] 可以在以下位置找到测量应用程序： [!DNL Marketo Measure] 活动支持文章。

**不同的运算符表示什么？**

* 等于：与值的精确匹配（又称：social）
* 包含：文本位于中间(又称： &#42;社交&#42;)
* 始于：值以文本开头(也称为： social&#42;)
* 结尾为：值以文本结尾(又称： &#42;social)
* 匹配任意：可添加多个以逗号分隔的值。 如果 [!UICONTROL starts with]， [!UICONTROL ends with]，或包含运算符，使用通配符(&#42;)
* 大于：用于数字字段或日期/时间字段
* 小于：用于数字字段或日期/时间字段

**这些活动通过什么渠道进行？**

活动规则及其相应 [!DNL Marketo Measure] 将创建营销活动名称，使用在线渠道定义将这些营销活动放在正确的营销渠道下。 [!DNL Marketo Measure] 不仅可以使用媒体和来源定义渠道，还可以使用营销活动定义渠道。

在上述示例中，要将“出站调用{Assigned To}”营销活动分配给BDR渠道，请在BDR渠道的联机渠道CSV中插入一行，其营销活动定义为“出站调用”&#42;“ — 星号表示通配符值，因此所有以“出站调用”开头的营销活动都将属于BDR渠道下，而不必为每个营销活动名称创建单独的行。
