---
unique-page-id: 18874704
description: 活动归因常见问题解答 —  [!DNL Marketo Measure]
title: 活动归因常见问题解答
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: e5931d783d8aad9ab0b32b4e30bbbfdfd46230dd
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# 活动归因常见问题解答 {#activities-attribution-faq}

[!DNL Marketo Measure]活动导入您的所有活动记录并为它们生成接触点，从而允许这些活动接收归因点数。 最常见的用例是跟踪Sales团队的活动，因为它们通常会创建发送给潜在客户的电话或电子邮件记录。 可以跟踪的其他独特内容是内容交互，如资源下载或视频查看。

>[!AVAILABILITY]
>
>此功能仅对第2层客户启用。 要申请更高的客户层，请联系Adobe客户团队（您的客户经理）。

**这与离线营销活动有何不同？**

最大的区别是，促销活动只能提供一个接触点，因为促销活动只允许每个潜在客户或联系人拥有一个促销活动成员。 这意味着您无法跟踪出站呼叫、演示或网络研讨会与会者等定期事件，除非您为每个分组创建单独的营销活动。 利用活动，可测量每个事件。

**任务、事件和活动之间是否存在差异？**

Activities对象作为Task和Event对象的伞形或父对象。 活动基本上同时包含任务和事件。 任务通常用于记录快速的一次性项目，如电话或电子邮件。 事件通常用于可能有开始或结束日期的项目，例如会议或会议。

**如果我有具有相同周期性任务的潜在客户或联系人，我是否会看到所有这些任务的买方接触点？**

可以。已同步的活动与创建的接触点之间存在1:1的关系。

**我如何知道哪些记录导致创建了接触点？**

一个有效的建议是，首先在CRM中使用Activity对象设置过滤器。 根据筛选规则，这会为您提供符合该条件的记录数方面的良好信息，然后您可以根据需要对其进行优化。 虽然这不是必需的，但是通过此方式可以帮助用户了解在设置活动规则后将创建多少活动接触点。

**什么是[!DNL Marketo Measure]促销活动名称？**

由于这些活动会产生接触点，因此[!DNL Marketo Measure]必须知道他们属于哪个渠道和子渠道。 对于每个规则，您需要提供一个[!DNL Marketo Measure]营销活动名称。 创建后，使用在线渠道CSV将[!DNL Marketo Measure]促销活动名称映射到其相应的渠道。 [!DNL Marketo Measure]促销活动名称也出现在接触点本身的[!UICONTROL Ad Campaign Name]字段中。

**填充了哪些其他接触点字段？**

| **接触点字段** | **值** |
|---|---|
| 潜在客户/联系人 | 所有活动都与潜在客户或联系人相关 |
| Campaign | Channel.Subchannel [[!DNL Marketo Measure]] |
| 接触点Source | CRM活动 |
| 媒介 | Activity.Type |
| 接触点类型 | Activity.Type |
| 广告营销活动名称 | [!DNL Marketo Measure]营销活动名称 |
| 广告内容 | 活动主题 |
| 广告ID | 活动外部Id |
| 接触点日期 | [自定义 — 在应用]中设置 |

**如果需要为每个销售代表创建不同的规则怎么办？ 是否需要为每个创建不同的[!DNL Marketo Measure]营销活动？**

不，你没有。 “动态促销活动名称”允许您使用引用活动对象字段的“替换参数”来填写[!DNL Marketo Measure]促销活动名称的一部分（或全部）。 例如，如果您有一个标题为“出站呼叫”的[!DNL Marketo Measure]促销活动名称，但希望将销售代表列在末尾，则采用CRM字段名称并将[!DNL Marketo Measure]促销活动名称命名为“出站呼叫{AssignedTo}”或“出站呼叫{CreatedBy}”。

**如何在[!DNL Marketo Measure]应用程序中设置活动？**

有关如何在[!UICONTROL Marketo]度量值应用程序中配置活动的说明，请参阅[!DNL Marketo Measure]活动支持文章。

**不同的运算符表示什么？**

* 等于：与值的精确匹配（又称：social）
* 包含：文本位于中间（也称为： &#42;social&#42;）
* 开头为：值开头为文本（也称为： social&#42;）
* 结尾为：值以文本结尾（也称为： &#42;social）
* 匹配任意：可添加多个以逗号分隔的值。 如果必须应用[!UICONTROL starts with]、[!UICONTROL ends with]或contains运算符，请使用通配符(&#42;)
* 大于：用于数字字段或日期/时间字段
* 小于：用于数字字段或日期/时间字段

**这些活动通过哪个渠道进行？**

创建活动规则及其对应的[!DNL Marketo Measure]营销活动名称后，请使用在线渠道定义将这些营销活动放在正确的营销渠道下。 [!DNL Marketo Measure]不仅可以使用媒体和来源定义渠道，还可以使用营销活动定义渠道。

在上述示例中，要将“出站调用{Assigned To}”营销活动分配到BDR渠道，请在BDR渠道的在线渠道CSV中插入一行，其营销活动定义为“出站调用&#42;”，星号表示通配符值，因此所有以“出站调用”开头的营销活动都将位于BDR渠道下，而不必为每个营销活动名称创建单独的行。
