---
unique-page-id: 42762749
description: '"[!DNL Marketo Engage] 活动集成 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Engage] 活动集成”'
exl-id: 463ad9b2-e1bd-49dd-8bf5-0da7b7132f05
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 0%

---

# [!DNL Marketo Engage] 活动集成 {#marketo-engage-activities-integration}

作为整体的 [!DNL Marketo Measure] 和 [!DNL Marketo Engage] 集成，这种引入Marketo活动的努力将发挥巨大作用。 通过Marketo Activities，系统会跟踪点击电子邮件、更改得分或更改进度状态等事件 — 可以缩小这些活动类型并将其定义为选择符合接触点条件的子集。 在这些活动上创建接触点后，即会在参与历程中进行跟踪，并与您的其他营销渠道（如付费搜索或合作伙伴营销）一起衡量。

## 要求 {#requirements}

* 生产Marketo实例
* 生产 [!DNL Salesforce] 或 [!DNL Microsoft Dynamics] 实例
* 任何付费 [!DNL Marketo Measure] 订阅
* Marketo人员同步已启用([!DNL Marketo Measure] 设置)
* 已启用Marketo程序([!DNL Marketo Measure] 设置)
* Marketo活动已启用([!DNL Marketo Measure] 设置)

## 设置 {#setup}

1. 要开始设置Marketo活动，请导航至 **我的帐户** > **设置** > **活动**.

   ![](assets/one-1.png)

   ![](assets/two-1.png)

   首先需要选择计划构建规则的活动类型列表。 没有硬性数量的活动类型是必需的，但我们还建议您不要让接触点过载并淡化重要里程碑的重要性。 话虽如此，您无需超过5种活动类型即可跟踪相关参与。

1. 单击下面的下拉菜单 [!UICONTROL Select Activities Types] 开始选择各种类型。

   ![](assets/three-1.png)

1. 选择所有需要的活动后，您也会看到它们已填充到您的 [!UICONTROL Selected Activities List] 以及下 [!UICONTROL Define Rules].

   ![](assets/four-1.png)

1. 对于每个活动类型，您将需要定义一个或多个规则来确定哪些记录符合接触点条件。 例如，我们将为“更改得分”活动类型添加规则，以便系统在Marketo人员达到90分或更高的分数时创建一个接触点。

1. 首先，根据活动类型，您可能需要设置 [!DNL Marketo Measure] 稍后可用于渠道映射的营销活动名称。 [!DNL Marketo Measure] 营销活动名称可以在多个规则中重复使用。 这有助于在单个渠道规则中使用更广泛的名称。 并非所有活动类型都包含Marketo程序，因此第一步，需要指定一个名称。

   以下是该额外步骤的示例：

   ![](assets/five-1.png)

1. 在我们的“更改得分”示例中，我们不需要输入促销活动名称，因为我们可以从Marketo项目中提取该信息。 现在，您可以创建规则表达式。 按照我们的示例，我们要选择字段&quot;[!UICONTROL New Value]带有运算符“”的“[!UICONTROL is greater than]”创建URL。

   您可以展开规则，并通过添加“and”或“or”语句来缩小结果范围，从而添加其他过滤器或标准。

   ![](assets/six-1.png)

   ![](assets/seven-1.png)

1. 最后，选择我们应该使用什么作为接触点日期。 所有可用的日期或日期/时间字段都将在此处显示Marketo。 除非您有自定义日期字段，否则您将会看到&quot;[!UICONTROL Activity Date]“

   ![](assets/eight-1.png)

1. 请务必单击 **[!UICONTROL Save As Draft]** 这样您就不会丢失所做的更改。

   ![](assets/nine-1.png)

1. 导航至 **[!UICONTROL Attribute Mapping]** 选项卡。

   ![](assets/ten-1.png)

1. 对于您选择的每个活动类型，您可以选择将其他Marketo属性映射到接触点字段，以便在以下位置查看和报告这些值： [!DNL Marketo Measure Discover] 或CRM中的。

   许多字段已自动映射，无法更改以便与我们的其他集成保持一致。 引用下面的字段映射部分以查找这些值。 对于某些活动类型，Marketo包括登陆页面、反向链接页面或浏览器的属性，您可以选择将这些属性映射到接触点字段。 在以下示例中，我们提出了一些其他建议，这些建议可以删除。

1. 从左栏中选择要映射到的买方接触点字段。 然后，在“买方接触点”字段中选择要填充的Marketo属性。 请记住，这些是可选的附加映射，位于 [!DNL Marketo Measure] 已建立。

   可映射的字段：

   * 城市
   * 国家
   * 区域
   * 登陆页面
   * 反向链接页面
   * 表单页面
   * 表单日期
   * 平台
   * 浏览器

   >[!NOTE]
   >
   >此列表中没有广告内容或关键词等广告字段，因为它们是为我们的广告平台集成保留的。

## 活动类型 {#activity-types}

有些活动类型会向我们提供项目ID和项目名称，因此可以轻松将其映射到买方接触点上的促销活动ID和促销活动名称。 对于其他人，没有程序关联，因此部分规则定义将要求您创建 [!DNL Marketo Measure] 营销活动名称。 以下是每个类别的列表：

**具有项目ID的活动类型**

发送电子邮件(6)\
电子邮件已送达(7)\
电子邮件退回(8)\
取消订阅电子邮件(9)\
打开电子邮件(10)\
单击电子邮件(11)\
更改数据值(13)\
更改得分(22)\
添加到列表(24)\
进度中的更改状态(104)\
添加到培养(113)\
更改培养节奏(115)

>[!NOTE]
>
>在我们期望获得项目ID的活动类型中，如果检测到没有项目的活动， [!DNL Marketo Measure] 将不接受该接触点作为符合条件的接触点，因为我们的Campaign值不能为空。

**没有程序ID的活动类型**

单击链接(3)\
新潜在客户(12)\
将潜在客户同步到SFDC (19)\
转化商机(21)\
更改所有者(23)\
从列表中删除(25)\
SFDC活动(26)\
电子邮件软退回(27)\
从SFDC删除Lead (29)\
合并潜在客户(32)\
添加到机会(34)\
从机会中删除(35)\
更新机会(36)\
删除潜在客户(37)\
发送警报(38)\
发送销售电子邮件(39)\
打开销售电子邮件(40)\
单击Sales Email (41)\
添加到SFDC Campaign (42)\
从SFDC Campaign删除(43)\
在SFDC Campaign中更改状态(44)\
接收销售电子邮件(45)\
请求营销活动(47)\
销售电子邮件已退回(48)\
更改收入阶段(101)\
手动更改收入阶段(102)\
更改区段(108)\
调用Webhook (110)\
转发给朋友的电子邮件(111)\
已收到转发给朋友的电子邮件(112)\
更改培养轨迹(114)\
将潜在客户推送到Marketo (145)\
将潜在客户同步到Microsoft (300)\
共享内容(400)已参与对话(158)与(159)已计划对话约会(160)已实现对话目标(161)自定义活动(xxx)交互的文档

## 渠道映射 {#channel-mapping}

对于具有项目ID的活动类型中的任意规则，Marketo项目渠道由项目确定。 我们使用项目频道来映射到您的自定义离线频道，因此您需要确保正确配置您的频道 [按照此处的说明](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping).

对于没有项目ID的活动类型中的任何规则，您的第一步是创建营销活动名称。 使用此Campaign名称设置自定义在线渠道 [此处布局](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

如果未正确配置Marketo活动的渠道，则您的新接触点可能会归入“其他”渠道下。

## 计划成本 {#program-costs}

通过Marketo程序的数据导入，成本将自动从期间成本中下载，Marketo中报告的成本将在整个分配的月份中分发。 例如，如果为2021年1月报告$1000，则将$1000拆分为31天。 成本可在以下位置找到： [!DNL Marketo Measure Discover].

## Cookie映射 {#cookie-mapping}

由于 [!DNL Marketo Measure] 与Marketo集成， [!DNL Marketo Measure] Cookie ID现在也已映射并与 [!DNL Marketo Munchkin Id]. 这有助于弥合将匿名首次接触归因于Web会话的差距，而不是将FT和LC接触都归因于Marketo活动。 设想一下这种情形：

Mark点击了一下Facebook广告，然后登陆了wayneenterprises.com ，在那里他受到了 [!DNL Marketo Measure] Id 123和 [!DNL Marketo Munchkin Id] 456。 没有表单填写。

Wayne Enterprises营销团队会向特定的目标潜在客户发送电子邮件爆炸邮件，其中一个潜在客户是 `mark@email.com`.

`mark@email.com` 接收电子邮件，点击并登陆 `wayneenterprises.com`. 它变为 `mark@email.com's` 第二次访问 `wayneenterprise.com` 相同的Cookie ID，但表单没有填写，因此 [!DNL Marketo Measure]，则他们仍为匿名访客。

Wayne Enterprises营销团队创建一个Marketo活动规则，以生成“点击电子邮件”活动类型的接触点。

今天的实施将创建一个FT和LC接触点，用于 `mark@email.com` 从“Click Email”活动类型访问Marketo活动。

通过这个Cookie映射增强功能，英国《金融时报》将回到Facebook广告中获取点数，而LC将获取该电子邮件的点数。

>[!NOTE]
>
>通过Cookie映射行为，您可能会找到一些来自Web访问的LC接触点。 Marketo中显示的商机可能没有任何相关活动，那么 [!DNL Marketo Measure] 下载该商机，将其与关联的Cookie相匹配，然后将其跟踪到最近的Web会话，即使不存在创建该商机的表单活动也是如此。

## 常见问题解答 {#faq}

**如何知道是创建Marketo项目规则还是Marketo活动规则？**

此 [!DNL Marketo Engage] 项目集成是一种根据人员是否为项目群成员来生成接触点的简单方法。 如果您有兴趣根据人员更改为特定项目群状态的时间来定义规则， [!DNL Marketo Engage] 活动集成将是您想要的设置，尤其是“进度更改状态”活动类型，这样您的接触点日期可以映射到系统生成的活动日期。

**为什么我的接触点类型的名称会被截断？**

“接触点类型”字段创建于 [!DNL Marketo Measure] 包含16个字符的包。 不幸的是，更改字段的字符限制将需要弃用现有字段并创建新字段。 “接触点类型”的值是“活动类型”，同样在“媒介”字段中进行了设置。

**为什么我的自定义活动类型没有显示在可用活动列表中？**

我们仅显示“已批准”自定义活动类型，而不显示“草稿”或“已批准且具有草稿”。

**如何确定要为其生成接触点的活动类型？**

尽管您可以创建的活动类型数量没有限制，但我们通常建议创建的活动类型不超过5个。 确定哪些营销活动相关程度足以成为接触点历程的一部分需要时间。 例如，“取消订阅电子邮件”可能不是要跟踪的重要接触点，但包含其他过滤器的“点击电子邮件”可能是一个很好的接触点。 这因每个组织和每个团队而异，因此我们建议您与团队合作，一起脑力激荡此处的最佳方法。

**为何我的浏览器名称被截断？**

此 [!DNL Marketo Measure] 浏览器名称的硬限制为20个字符，不过我们从Marketo获取的用户代理值通常为较长的字符串。

BrowserInfo.Name\
BrowserInfo.Version\
PlatformInfo.Name\
PlatformInfo.Version
