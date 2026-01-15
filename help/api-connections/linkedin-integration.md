---
description: 面向Marketo Measure用户的LinkedIn集成指南
title: LinkedIn集成
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
feature: APIs, Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '2694'
ht-degree: 0%

---

# LinkedIn集成 {#linkedin-integration}

## 概述 {#overview}

[!DNL Marketo Measure]与LinkedIn的集成分为两部分：

赞助内容：赞助内容集成允许[!DNL Marketo Measure]在[!DNL LinkedIn]广告上标记目标URL，这最终允许[!DNL Marketo Measure]跟踪用户完成其整个接触点历程，并将活动映射回特定的[!DNL LinkedIn]促销活动和Creative。 这可以为客户提供有关其[!DNL LinkedIn]活动ROI的分析。

Forms负责人：通过与LinkedIn的Forms负责人集成，Marketo Measure将insight纳入通过LinkedIn平台提交的表单中。 这些表单填写将与您的CRM或[!DNL Marketo Engage]实例中的潜在客户匹配，以便他们符合归因条件。 借助insight的促销活动、Creative以及帮助生成表单的表单，团队现在可以进一步优化其LinkedIn营销和广告支出。

## 可用性 {#availability}

可供所有用户使用。

## 要求 {#requirements}

### 营销活动经理角色

为了使[!DNL Marketo Measure]能够下载广告数据和广告成本数据，您在促销活动管理器中必须具有以下角色之一：

* 账单管理员
* 客户经理
* 营销活动管理器

了解详情： Campaign Manager中的[用户角色和功能](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager)。

### 付费媒体管理员角色

为了使[!DNL Marketo Measure]能够创建/更新赞助的创意，您必须具有以下付费媒体管理员角色之一：

* 赞助内容海报
* Forms负责人

了解详情：[LinkedIn页面管理员角色](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview)。

对于我们的集成，[!DNL LinkedIn]不&#x200B;**需要其他**&#x200B;角色。 这些角色经常被误认为所需的角色，因此请注意，它们存在区别！

### 页面管理员角色

为了使[!DNL Marketo Measure]能够从潜在客户群表单下载/集成潜在客户，您必须具有以下页面管理员角色：

* 超级管理员

了解详情：[LinkedIn页面管理员角色](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview)。

## LinkedIn广告类型 {#linkedin-ad-types}

[!DNL Marketo Measure]将支持：

赞助内容允许您向关注您公司的成员以外的其他成员的[!DNL LinkedIn]信息源交付内容。 赞助内容可以面向特定受众，并帮助广告商无论何时何地在[!DNL LinkedIn]平台上跨桌面、移动设备和平板电脑进行参与，都可以联系[!DNL LinkedIn]成员。 支持由Lead Gen Forms提供的赞助内容。

[!DNL Marketo Measure]支持的赞助内容广告格式类型为单幅图像广告和视频广告(通过Lead Gen Forms)。 由于架构的复杂性，我们不支持轮播广告。

[!DNL Marketo Measure]不支持赞助消息、文字广告或动态广告。

![Marketo Measure不支持赞助消息、文字广告或动态](assets/bizible-guide-1.png)

>[!TIP]
>
>对于源自非赞助内容来源的任何促销活动/支出（例如“文本广告”或“赞助的InMail”的促销活动类型），[!DNL Marketo Measure]不会&#x200B;_从本质上支持跟踪这些促销活动类型。_ 如果您希望将此类营销活动的支出与您的“赞助内容”支出一起跟踪，请务必使用我们的营销支出CSV手动记录说出的支出。

## 工作原理：赞助内容 {#how-it-works-sponsored-content}

>[!NOTE]
>
>在首次使用之前，必须通过导航到[!DNL Marketo Measure] [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Ads] > [!UICONTROL Enable LinkedIn Lead Gen Forms]来启用此功能设置。

### [!DNL LinkedIn's]独特的自动标记要求

[!DNL Marketo Measure]可以通过自动标记登陆页面来帮助跟踪[!DNL LinkedIn]营销活动效果。

[!DNL Marketo Measure]将搜索具有唯一LinkedIn共享的创意，并在其末尾添加`?_bl={creativeId}`参数。

### 复制共享

通过此[!DNL Marketo Measure/LinkedIn]集成，我们要求客户不要复制/克隆/复制现有创意内容。 如果发现共享并且检测到共享仅用于一个Creative，则[!DNL Marketo Measure]可以按原样标记共享，而无需重新创建任何创意内容或共享，并且所有广告历史记录（展示次数、点击次数、共享）都将保留。

一旦发现共享在多个创意人员之间共享，[!DNL Marketo Measure]就必须运行暂停、复制和重新标记的过程，才能创建唯一的集。 [!DNL Marketo Measure]将暂停并存档实时创意，因此将擦除广告历史记录（包括展示次数、点击次数和社交分享），以正确自动标记所有内容。

接下来，[!DNL Marketo Measure]建议您不要复制任何[!DNL LinkedIn]共享，并尽可能保持所有创意和共享的唯一性，这样我们就可以添加我们的跟踪而无需擦除广告历史记录。

### 缩短的URL

额外步骤的原因是LinkedIn允许目标URL是缩短的URL（bit.ly、goog.le等），这意味着[!DNL Marketo Measure]看不到较长且已解析的URL，[!DNL Marketo Measure]需要向已解析的URL添加跟踪参数。 为了解决此问题，[!DNL Marketo Measure]在重新创建广告之前查找缩短的URL，展开该URL，然后使用已解析的URL及其所有参数创建新广告，从而允许[!DNL Marketo Measure]添加标记。 创建新广告将擦除广告历史记录（展示次数、点击次数、共享次数），因此需要具有标记缩短URL的权限。

如果您大量使用缩短的URL，这可能会严重影响您的创意人员。 我们建议您不再使用缩短的URL，这样[!DNL Marketo Measure]便可以标记登陆页面，而无需创建新广告和擦除广告历史记录。

### 进程

让我们从一些示例开始。 假设我们有....

Creative A ：共享123\
Creative B ：共享234\
Creative C ：共享234\
Creative D ：共享234

![Creative D ：共享234](../assets/marketo-engage-activities-05.png)

`1)` [!DNL Marketo Measure]将首先查看所有状态为“活动”的营销活动、创意和共享。 [!DNL Marketo Measure]不会标记已暂停、已存档或已取消的广告。 如果广告已暂停，然后设置为[!UICONTROL active]，则一旦它再次处于活动状态，我们将对其进行标记。 如果我们能够找到唯一的共享，即该共享未在多个创意人员或营销活动之间使用(例如，Creative A ：共享123)，则[!DNL Marketo Measure]会将我们的自定义参数`>> ?_bl={creativeId}`添加到共享URL中。

`2)`现在，如果共享已共享并失去其唯一性(例如，Creative B ：共享234和Creative C ：共享234和Creative D ：共享234)，[!DNL Marketo Measure]将暂停并存档所有类似的创意(即Creative B、Creative C和Creative D)。

`3)` [!DNL Marketo Measure]将创建3个新创意，即Creative E、Creative F和Creative G，用于复制已存档的Creative B内容。

`4)` [!DNL Marketo Measure]还将创建3个复制共享234内容的新共享（共享345、共享456和共享567），但它将具有自己的唯一`?_bl`标记。

`5)` [!DNL Marketo Measure]将必须定期检查共享是否未共享，如果共享，我们将在上述步骤2中重新启动该进程。

>[!NOTE]
>
>实施此操作意味着我们的客户将丢失Creative B的广告历史记录：Share 234、Creative C ：Share 234和Creative D ：Share 234，因为现在已分别使用Creative E ：Share 345、Share F ：Share 456和Creative G ：Share 567重新创建了该服务器。

![实施此操作意味着我们的客户将丢失广告历史记录](assets/api-connections-01.png)

## 工作原理：Forms负责人 {#how-it-works-lead-gen-forms}

[!DNL Marketo Measure]可以通过自动标记登陆页面来帮助跟踪[!DNL LinkedIn]营销活动效果。

[!DNL Marketo Measure]将搜索具有唯一LinkedIn共享的创意，并在其末尾添加`?_bl={creativeId}`参数。

通过[!DNL LinkedIn's]广告表单API和广告表单响应API，我们可以收集广告帐户的表单提交数据，并将电子邮件地址与CRM或Marketo中的潜在客户关联。

LinkedIn表单可能包含多个电子邮件地址。 下载表单响应时，我们将查找具有以下优先级的电子邮件地址：工作电子邮件、电子邮件地址（主表单字段）或具有有效电子邮件值的自定义字段。

无论Campaign或Creative的状态如何，所有表单响应都将导致接触点。 [!DNL Marketo Measure]具有90天的回溯限制，因此[!DNL Marketo Measure]无法访问超过90天的表单响应，但启用[!DNL Marketo Measure]和[!DNL LinkedIn]集成的时间越长，通过[!DNL Marketo Measure]看到的潜在客户群表单接触点就越多。

>[!NOTE]
>
>LinkedIn成本仍作为赞助内容促销活动的一部分下载。


在[!DNL Marketo Measure]和LinkedIn Lead Gen Forms集成存在之前，客户通常将其表单提交推送到Marketo计划和/或CRM Campaign以跟踪表单并接收对这些活动的归因。 启用Forms销售线索生成设置后，我们希望确保不会重复计算这些表单提交。 检查以下各项：

* CRM对象上的“启用购买者接触点”字段设置为“无”或“排除所有营销活动成员”
* 更新任何相关的Marketo项目或Marketo活动规则
* 更新任何相关的CRM Campaign规则

>[!NOTE]
>
>LinkedIn API具有90天的回溯限制，因此如果您使用的是Marketo或CRM规则，建议您将规则的结束日期设置为在[!DNL Marketo Measure]中启用集成的日期之前的90天。

## 接触点详细信息 {#touchpoint-details}

在[!DNL Marketo Measure]在LinkedIn创意作品上成功标记您的登陆页面后，您就可以在接触点上查看已解析的广告数据。 以下是您应会看到的数据值的映射：

<table>
 <colgroup>
  <col>
  <col>
 </colgroup>
 <tbody>
  <tr>
   <th style="width:30%">接触点字段</th>
   <th>示例值</th>
  </tr>
  <tr>
   <td>广告ID</td>
   <td>84186224</td>
  </tr>
  <tr>
   <td>广告内容</td>
   <td>copy-1-image-2-man 95%的#B2B营销人员认为需求创建策略是成功的。 了解详情： [!DNL https]：//lnkd.in/jgdi50vKrgv</td>
  </tr>
  <tr>
   <td>广告组ID</td>
   <td>（空白）</td>
  </tr>
  <tr>
   <td>广告组名称</td>
   <td>（空白）</td>
  </tr>
  <tr>
   <td>广告营销活动ID</td>
   <td>138949954</td>
  </tr>
  <tr>
   <td>广告营销活动名称</td>
   <td>SU - COM帐户 — 需求技能</td>
  </tr>
  <tr>
   <td>广告目标URL <b>*</b></td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td>
  </tr>
  <tr>
   <td>表单URL</td>
   <td>info.bizible.com/demo</td>
  </tr>
  <tr>
   <td>表单URL — 原始</td>
   <td>info.bizible.com/demo</td>
  </tr>
  <tr>
   <td>关键字ID</td>
   <td>（空白）</td>
  </tr>
  <tr>
   <td>关键字匹配类型</td>
   <td>（空白）</td>
  </tr>
  <tr>
   <td>登陆页面</td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders</td>
  </tr>
  <tr>
   <td>登陆页面 — 原始</td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td>
  </tr>
  <tr>
   <td>营销渠道</td>
   <td>付费社交</td>
  </tr>
  <tr>
   <td>营销渠道 — 路径</td>
   <td>付费Social.LinkedIn</td>
  </tr>
  <tr>
   <td>媒介</td>
   <td>“cpc”或“潜在客户表单”</td>
  </tr>
  <tr>
   <td>反向链接页面</td>
   <td>www.linkedin.com/</td>
  </tr>
  <tr>
   <td>反向链接页面 — 原始</td>
   <td>www.linkedin.com/</td>
  </tr>
  <tr>
   <td>搜索短语</td>
   <td>（空白）</td>
  </tr>
  <tr>
   <td>接触点类型</td>
   <td>Web窗体</td>
  </tr>
  <tr>
   <td>接触点Source</td>
   <td>LinkedIn</td>
  </tr>
 </tbody>
</table>

仅为赞助内容填充&#x200B;**&#42;** _“广告目标URL”字段。 没有为Forms潜在客户代填充它。_

<br>

## 成本 {#costs}

由于[!DNL Marketo Measure]与[!DNL LinkedIn]直接集成，因此我们每天下载每个促销活动和Creative的记录支出。 客户无需再报告[!DNL LinkedIn]应用程序中的[!DNL Marketo Measure]支出。

与其他广告集成一样，[!DNL Marketo Measure]已定义营销渠道规则以放置所有[!DNL LinkedIn]营销活动、创意和成本。 要使用规则，客户需要为其“付费[!DNL LinkedIn]”工作插入一个新行。 它可以是新渠道或现有渠道。 在反向链接列中，使用定义“[[!DNL LinkedIn] Paid]”，[!DNL Marketo Measure]已将该定义定义为任何带有[!DNL Marketo Measure]标记的接触点。

![与其他广告集成一样，Marketo Measure已定义营销](../assets/marketo-engage-activities-01.png)

## [!DNL Marketo Measure]发现 {#marketo-measure-discover}

对[!DNL Marketo Measure] Discover进行了一些增强以支持Lead Gen Forms报告。

**付费媒体讨论区**

潜在客户Forms图块：包含LinkedIn表单填充数的新图块。 深入查看此计数将显示活动ID、表单日期、表单名称和电子邮件地址。

**参与路径讨论区**

事件历程：包括“活动”事件类型和媒介“潜在客户群表单”，适用于通过集成产生的表单。 穿透钻取视图包括Campaign、Creative和表单详细信息。

## 赞助内容常见问题解答 {#sponsored-content-faq}

**什么是深色共享？**

深色共享是从未在公司页面上发布的帖子，会被立即创建并直接添加为Creative。 为了让[!DNL Marketo Measure]创建的创意不会出现在公司页面顶部并再次得到提升，将使用暗色共享以便能够在后台启动。

**[!DNL Marketo Measure]实际标记了哪些状态？**

[!DNL LinkedIn]营销活动和Creative有四种不同的状态：“活动”、“已暂停”、“已存档”和“已取消”。 我们仅标记处于活动状态的营销活动和创意内容。 标记其他状态会再次将它们设置为“活动”。 [!DNL Marketo Measure]将不会标记“已暂停”、“已存档”或“已取消”营销活动或创意，但如果状态更改为“活动”，则将恢复标记。

**[!DNL Marketo Measure]用于标记的值是多少？**

在目标URL的末尾，[!DNL Marketo Measure]正在添加参数`&_bl={creativeId}`，其中`{creativeId}`是来自LinkedIn的Creative ID。 使用Creative ID，[!DNL Marketo Measure]还可以确定促销活动ID，因为[!DNL LinkedIn]具有非常基本的广告结构，因为每个Creative只能属于一个促销活动。

**在[!DNL Marketo Measure]创建其新版本后，我的旧创意会发生什么情况？**

当[!DNL Marketo Measure]重新创建共享并将其放入新的Creative时，旧的Creative将会存档。 这也是为什么[!DNL Marketo Measure]不会标记已存档的营销活动或创意 — 否则，它将与[!DNL Marketo Measure]循环并尝试无限期地标记它。

**为什么创建的广告的目标URL与我的原始广告不匹配？**

[!DNL Marketo Measure]需要将跟踪参数添加到已解析的URL中，但API中显示的URL可能是缩短的URL，不包含所有参数。 为了解决此问题，[!DNL Marketo Measure]在重新创建添加之前查找缩短的URL，解析它，然后使用解析的URL及其所有参数创建新广告，从而允许[!DNL Marketo Measure]添加标记。

**您是否在标记我的所有广告？ 我没有在所有登陆页面上看到bl参数？**

我们观察到一些营销人员将向[!DNL Marketo Measure]无法标记的目标URL中放入图像链接，因此我们在广告内容中搜索该URL。 如果[!DNL Marketo Measure]有权标记缩短的URL，我们将展开该URL并标记它，但由于LinkedIn的复制结构，它将在文本中自动缩短。 标记将存在于LinkedIn缩短的URL中，该URL将显示在接触点的“广告内容”字段中，而不是“登陆页面 — 原始”字段中。

**糟糕，我的团队中有人意外克隆了一个共享。 我可以暂停它吗？**

没关系。 [!DNL Marketo Measure]将以编程方式检查不再唯一的共享，这意味着该共享已复制到其他Creative。 检测到该副本后，[!DNL Marketo Measure]将按照常规流程标记和创建新广告。

**我的广告先前正在等待审阅。 为什么在[!DNL Marketo Measure]标记后它再次处于待审状态？**

LinkedIn要求所有创建或修改的广告在发布之前都必须经过正常的安全流程。 [!DNL Marketo Measure]尝试尽快拦截广告，因为它每6小时扫描一次新广告，但通过[!DNL LinkedIn's]额外步骤，它可能会延迟几个小时的发布。

**我的广告中有2个URL。 哪一个被标记？**

两者。 [!DNL Marketo Measure]集成允许我们从广告中的点进图像标记目标URL，但也会自动更新广告描述中缩短的URL。

![两者。 Marketo Measure集成允许我们标记目标](assets/select-type-1.png)

**我已连接我的[!DNL LinkedIn ads]帐户。 为什么[!DNL Marketo Measure]没有标记我的链接？**

连接的[!DNL LinkedIn]用户需要具有适当的编辑权限，这意味着该用户必须是帐户管理员、营销活动管理员或Creative管理员。

**如何知道我的创意是否会被复制？ 能否查看我的创意人员是否使用相同的共享？**

[!DNL LinkedIn]报表中未提供共享ID，因此没有明确明确的方法来检查创意到共享的映射。 如果您怀疑某个创意可能是副本，则可以通过在[!DNL LinkedIn]促销活动管理器中打开该广告来手动进行检查，这会在新选项卡中打开该广告，并且您可以在URL中找到共享ID。

![LinkedIn报表中未提供共享ID，因此](assets/linkedin-integration-02.png)

## Forms销售主管常见问题解答 {#lead-gen-forms-faq}

**此增强功能的成本是多少？**

此产品包含在任何付费的[!DNL Marketo Measure]订阅中。

**集成是否可追溯？**

是，我们将从LinkedIn下载历史广告表单回复，不过我们限制在90天的回看时段内。 启用[!DNL Marketo Measure]和LinkedIn集成的时间越长，通过[!DNL Marketo Measure]看到的潜在客户群体表单接触点就越多。

没有选项可设置下载的特定日期，但如果存在需要禁止的接触点，则可以选择设置接触点删除规则。

**如果我已经在使用[!DNL Marketo Measure] LinkedIn广告集成，这是否会自动启用？**

不会，我们不会自动开始为所有客户下载它，但在设置中启用此功能非常简单。

**表单数据是否可用？**

表单数据可通过[!DNL Marketo Measure] Discover获取，包括表单ID和表单名称。 表单详细信息在CRM中的接触点对象上尚不可用。

**之前已同步到Marketo项目或CRM营销活动的任何[!DNL LinkedIn]潜在客户会发生什么情况？**

建议您调整任何[!DNL Marketo Measure]规则以从这些特定项目或营销策划生成接触点以避免重复。 LinkedIn API具有90天的回溯限制，因此如果您使用的是Marketo或CRM规则，建议您将规则的结束日期设置为在[!DNL Marketo Measure]中启用集成的日期之前的90天。 从此刻起，[!DNL Marketo Measure]可以下载这些销售机会，其中包含更丰富的insight和详细信息。

**是否涉及任何自动标记或跟踪？**

否，这与其他[!DNL Marketo Measure]集成不同。 我们只是从LinkedIn下载相关信息，并将它们视为[!DNL Marketo Measure]中的活动，而不是修改登陆页面（因为没有点进登陆页面）。
