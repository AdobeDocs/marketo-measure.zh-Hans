---
unique-page-id: 18874704
description: 活动归因常见问题解答 —  [!DNL Marketo Measure]  — 产品文档
title: 活动归因常见问题解答
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---

# 活动归因常见问题解答 {#activities-attribution-faq}

的 [!DNL Marketo Measure] 活动功能允许我们导入您的所有活动记录并为其生成接触点，从而允许这些活动获得归因点数。 最常见的用例是跟踪销售团队中的活动，因为活动通常会创建发送给潜在客户的电话或电子邮件记录。 可跟踪的其他独特内容包括内容交互（如资产下载或视频查看）。

**这与离线营销活动有何不同？**

最大的区别在于，促销活动只能提供一个接触点，因为促销活动仅允许每个潜在客户或联系人有一个促销活动成员。 这意味着您无法跟踪定期事件，如叫客呼叫或演示或网络研讨会与会者，除非您为每个分组创建单独的营销活动。 利用活动，可测量每个事件。

**“任务”、“事件”和“活动”之间是否有区别？**

“活动”对象充当“任务”和“事件”对象的伞形或父对象。 活动主要同时包含任务和事件。 任务通常用于记录快速的一次性项目，如电话或电子邮件。 事件通常用于可能具有开始日期或结束日期的内容，如会议或会议。

**如果我的潜在客户或联系人具有与电子邮件或电话等相同的定期任务，那么我是否会看到所有这些任务的买方接触点？**

是. 已同步的活动与创建的接触点之间将存在1:1的关系。

**我如何知道哪些记录将导致创建接触点？**

建议您先使用CRM中的活动对象设置过滤器。 根据筛选规则，您可以很好地知道有多少记录符合该标准，然后可以根据需要对其进行优化。 这不是必需的，但这对于用户来说是一种非常有用的方法，可帮助他们了解在设置活动规则后将创建多少活动接触点。

**什么是 [!DNL Marketo Measure] 营销活动名称？**

由于这些活动将产生接触点， [!DNL Marketo Measure] 需要知道它们属于哪个渠道和子渠道。 对于每个规则，您将需要提供 [!DNL Marketo Measure] 营销活动名称。 创建该渠道后，您可以使用在线渠道CSV来映射该渠道 [!DNL Marketo Measure] 促销活动名称中的相应渠道。 的 [!DNL Marketo Measure] 促销活动名称还将显示在 [!UICONTROL Ad Campaign Name] 字段。

**填充了哪些其他接触点字段？**

| **接触点字段** | **值** |
|---|---|
| 潜在客户/联系人 | 所有活动均与潜在客户或联系人相关 |
| Campaign | Channel.Subchannel [[!DNL Marketo Measure]] |
| 接触点源 | CRM活动 |
| 中 | Activity.Type |
| 接触点类型 | Activity.Type |
| 广告促销活动名称 | [!DNL Marketo Measure] 营销活动名称 |
| 广告内容 | 活动主体 |
| 广告Id | 活动外部Id |
| 接触点日期 | [自定义 — 在应用程序中设置] |

**如果我需要为每个销售代表创建一个不同的规则，该怎么办？ 是否需要创建其他 [!DNL Marketo Measure] 是否针对每个促销活动？**

不，你没有。 我们引入了“动态营销活动名称”的概念。 这样，您就可以填充 [!DNL Marketo Measure] 促销活动名称，使用引用活动对象中字段的“替换参数”。 例如，如果您的 [!DNL Marketo Measure] 标题为“叫客呼叫”的营销活动名称，但您希望销售代表位于末尾，您需要使用CRM字段名称并调用 [!DNL Marketo Measure] 促销活动名称“叫客调用{AssignedTo}”或“叫客调用{CreatedBy}”。

**如何在 [!DNL Marketo Measure] 应用程序？**

有关如何在 [!UICONTROL Marketo] 可以在 [!DNL Marketo Measure] 活动支持文章。

**不同的运算符是什么意思？**

* 等于：与值精确匹配(即：social)
* 包含：文本位于中间(即： &#42;社交&#42;)
* 开头为：值以文本开头(即：社交&#42;)
* 结束于：值以文本结尾(即： &#42;social)
* 匹配任意：可以添加以逗号分隔的多个值。 如果 [!UICONTROL starts with], [!UICONTROL ends with]，或包含运算符时，需要使用通配符(&#42;)
* 大于：用于数字字段或日期/时间字段
* 小于：用于数字字段或日期/时间字段

**这些活动将位于哪个渠道？**

活动规则一次，及其对应 [!DNL Marketo Measure] 促销活动名称，将使用在线渠道定义将这些促销活动置于正确的营销渠道下。 [!DNL Marketo Measure] 不仅可以使用媒介和来源定义渠道，还可以使用营销活动定义渠道。

在以上示例中，要将“出站呼叫{已分配给}”营销活动分配给BDR渠道，您需要在BDR渠道的在线渠道CSV中为营销活动定义为“出站呼叫”的行&#42;“ — 星号表示通配符值，因此以“出站调用”开头的所有营销活动都将位于BDR渠道下，而不必为每个营销活动名称创建单独的行。