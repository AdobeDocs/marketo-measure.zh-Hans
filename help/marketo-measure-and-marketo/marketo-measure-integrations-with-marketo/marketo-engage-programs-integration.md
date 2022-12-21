---
unique-page-id: 42762729
description: '"[!DNL Marketo Engage] 程序集成 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Marketo Engage] 程序集成”'
exl-id: c26087e3-d821-4fe7-bacd-eeaa1530a4b0
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 0%

---

# [!DNL Marketo Engage] 程序集成 {#marketo-engage-programs-integration}

通过 [!DNL Marketo Measure] 集成 [!DNL Marketo Engage] 计划之后，我们的客户可以开始从Marketo计划成员资格中为归因跟踪创建接触点。 此功能允许营销人员开始跟踪电子邮件或参与计划（否则，将不会看到）中的项目成员资格 [!DNL Marketo Measure] javascript和应在归因历程中进行测量。

## 可用性 {#availability}

所有层。

## 要求 {#requirements}

* 生产Marketo实例
* Production Salesforce或Microsoft Dynamics实例
* 任何已付 [!DNL Marketo Measure] 订阅
* Marketo已启用人员同步([!DNL Marketo Measure] 设置)
* Marketo程序启用([!DNL Marketo Measure] 设置)

## 设置 {#setup}

**规则**

1. 要开始在Marketo程序中设置规则，请导航至 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Programs]**. 单击 **+** 图标以开始创建您的第一个规则。

   ![](assets/one.png)

   ![](assets/two.png)

1. 如果有助于跟踪规则，您可以选择为规则设置名称。 您将首先从项目群和项目群成员资格字段列表中选择字段以定义规则。 通过选择要检查的运算符和预期值，继续构建规则。

   ![](assets/three.png)

1. 在同一框内添加其他语句以在规则中设置“和”标准，或单击框外的+图标以设置“或”语句。

   ![](assets/four.png)

1. 选择应使用哪个日期或日期/时间字段来映射到接触点日期。 要查看Marketo中可用的值列表，请输入花括号 `{` 我们将显示可用字段。

   ![](assets/five.png)

   >[!NOTE]
   >
   >如果您的规则想要捕获活动日期或项目成员达到特定状态的日期，您将需要使用 [!DNL Marketo Engage] 活动集成，并为“按进度更改状态”活动类型设置规则。

   ![](assets/six.png)

您完成的规则应如下所示：

## 测试 {#test}

创建某些规则后，您可能需要对其进行测试以验证语句是否与“程序”匹配。

1. 要运行测试，请单击 **[!UICONTROL TEST]** 按钮，如下所示。

   ![](assets/seven.png)

1. 此时将显示一个模式窗口，您可以在该窗口中输入来自Marketo的项目ID。

   ![](assets/eight.png)

   在输入ID并单击 [!UICONTROL Test] 按钮，我们的规则引擎将检查每个规则并确定程序是否符合任何规则。 在以下示例中，您可以看到名为 [!DNL Marketo Measure] Ebook有5个项目群成员，并且因所显示的规则而符合条件。

   规则以5000个成员的样本大小运行。 如果您的程序包含的成员超过5000个，则我们可能不会检查所有成员的兼容性。 此工具仅用于检查规则是否正确构建。

   ![](assets/nine.png)

   您可以单击成员计数，以查看符合该程序条件的Marketo人员ID列表。

   ![](assets/ten.png)

## 渠道映射 {#channel-mapping}

从Marketo计划渠道列表中，您需要将值映射到 [!DNL Marketo Measure] 您在“设置”中创建的自定义营销渠道。 这些项目生成的任何接触点都将继承您在此处选择的渠道名称和子渠道名称。

1. 首先，导航到 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**.

1. 在顶部，您将可以选择映射到CRM促销活动类型，然后在下方，您将看到Marketo计划渠道的选项。

1. 首先选择应映射到值的渠道，然后（可选）选择子渠道。 完成后，单击 **[!UICONTROL Save]** 在底部。

   ![](assets/eleven.png)

## 计划成本 {#program-costs}

通过Marketo计划的数据导入，成本会自动从期间成本中下载，而Marketo中报告的成本则会在分配的整个月份进行分配。 例如，如果在2021年1月报告了$1000 ，则$1000将在31天内进行拆分。 成本可在 [!DNL Marketo Measure Discover].

## 工作原理 {#how-it-works}

**字段映射**

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>biz_ad_campaigns</th> 
   <th>Marketo</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>ID</td> 
  </tr> 
  <tr> 
   <td>IS_DELETED</td> 
   <td>（通过API检查程序是否仍然存在）</td> 
  </tr> 
  <tr> 
   <td><p>名称</p></td> 
   <td>name</td> 
  </tr> 
 </tbody> 
</table>

| biz_campaign_members | Marketo |
|---|---|
| ID | &quot;MarketoProgramMembership&quot;_ProgramId_Lead Id |
| MODIFIED_DATE | updatedAt |
| CREATED_DATE | membershDate |
| LEAD_ID | Id（列表成员资格） |
| LEAD_EMAIL | 电子邮件（列表成员资格） |
| 状态 | progressionStatus |
| HAS_RESPONDED | 已实现状态 |
| CAMPAIGN_NAME | programName |
| CAMPAIGN_ID | programId |
| CAMPAIGN_TYPE | 频道 |

## Cookie映射 {#cookie-mapping}

由于 [!DNL Marketo Measure] 与Marketo集成， [!DNL Marketo Measure] Cookie ID现在也已映射并与 [!DNL Marketo Munchkin Id]. 这有助于缩小将匿名首次接触归因于Web会话的空白，而不是将FT和LC接触归因于Marketo活动。 想象一下这种情景：

在 [!DNL Facebook] 广告，登陆wayneenterprises.com，在那里他得到Cookie [!DNL Marketo Measure] ID 123和 [!DNL Marketo Munchkin Id] 456。 不进行表单填写。

韦恩企业营销团队向特定目标线索发送电子邮件，其中一个是 `mark@email.com`.

`mark@email.com` 接收电子邮件并点进，并登陆wayneenterprises.com。 这将变为 `mark@email.com's` 第二次访问 `wayneenterprise.com` 使用相同的Cookie ID，但没有表单填充，因此 [!DNL Marketo Measure]，则仍然是匿名访客。

Wayne Enterprises营销团队创建Marketo活动规则，为“点击电子邮件”活动类型生成接触点。

今天的实施将为 `mark@email.com` 中，从Marketo活动的“单击电子邮件”活动类型。

通过这项Cookie映射增强功能，英国《金融时报》将回访并计入 [!DNL Facebook] 而LC会被记入电子邮件。

>[!NOTE]
>
>使用Cookie映射行为，您可能会发现来自Web访问的某些LC接触点。 可能在Marketo中显示一个潜在客户，但没有任何关联的活动，然后 [!DNL Marketo Measure] 下载了该潜在客户，将其与关联的cookie匹配，然后跟踪到最近的web会话，即使没有创建该潜在客户的表单活动也是如此。

## 常见问题解答 {#faq}

**如何将接触点日期设置为晋升日期或项目成员发生状态更改的日期？**

如果您的规则想要捕获活动日期或项目成员达到特定状态的日期，您将需要使用 [!DNL Marketo Engage] 活动集成，并为“按进度更改状态”活动类型设置规则。 否则， [!DNL Marketo Engage] “项目集成”仅提供“会员资格日期”，即使存在多种状态，也是将Marketo人员纳入项目的第一个日期。

**我是否可以获取接触点日期的日期选项的选取列表？**

要触发自动完成，请首先输入花括号 `{` 在文本字段中，将显示可用字段。

**如果我创建Marketo计划规则并且还具有CRM Campaign规则，它们是否会计数两次？**

这取决于您的规则定义，但可能是。 您将需要评估规则集，以便您没有涵盖项目和营销策划的规则，因为我们不会删除重复项或检测是否存在类似的成员资格。 一种可能的解决方案是，如果您希望Marketo成为唯一的真相来源，请将您的促销活动规则复制到项目中，然后删除促销活动规则。 另一个选项是在规则中添加“CreatedOn”或“CreatedDate”标准，以便特定日期之前的规则将使用Campaign规则，而特定日期之后的规则将使用项目规则。 有很多解决方法，但需要一些规划和协调。

**Marketo的项目成员资格自定义字段是否可用于定义？**

由于技术限制，目前无法支持计划成员资格自定义字段。 这些字段通过其他Marketo API可用后，将会向我们显示并可供您使用。

**如何知道是使用项目还是活动？**

的 [!DNL Marketo Engage] 程序集成是一种根据人员是否是程序的程序成员来生成触点的简单方法。 如果您有兴趣根据人员更改为特定项目状态的时间来定义规则，则 [!DNL Marketo Engage] 活动集成将是您需要的设置，特别是“按进度更改状态”活动类型。
