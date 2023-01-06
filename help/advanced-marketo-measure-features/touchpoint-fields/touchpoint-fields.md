---
unique-page-id: 37355835
description: 接触点字段 —  [!DNL Marketo Measure]  — 产品文档
title: 接触点字段
exl-id: d6c2bd60-5341-4a52-939a-942afc093306
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 0%

---

# 接触点字段 {#touchpoint-fields}

过去，当客户使用 [!DNL Marketo Measure] 如果我们没有直接标记集成，我们的客户成功团队会向客户介绍如何正确标记其登陆页面，以便他们使用正确的UTM格式并且我们可以解决其广告。 其中一些客户不使用UTM，而是使用自己的标记参数，这意味着使用新的标记结构在其所有广告网络中编辑其所有登陆页面可能会非常耗时 [!DNL Marketo Measure] 强制执行。 为了适应其标记结构，我们现在接受可与规则定义映射的自定义参数。 我们的目标是根据客户对其自定义跟踪参数的使用情况进行相应调整，这样我们就不必要求他们更改其URL结构。

>[!AVAILABILITY]
>
>现在可在第2层和第3层通过完全分段获得。

>[!NOTE]
>
>这是一项高级功能，只应由Professional Services设置。

## 启用功能 {#enabling-the-feature}

从 [!DNL Marketo Measure] 设置菜单，导航到“接触点字段”页面。 从此处，您可以通过选择 **是** 在 **启用计算字段**. 启用该功能后，您便可以自由创建接触点字段。

![](assets/one.png)

## 操作方法 {#how-to}

要创建计算字段，请记住用户可以执行三个不同的操作：提取、映射到并连接。 它们也称为用于定义计算字段的运算符。

提取

提取运算符会从其他位置提取字段的值，例如：促销活动字段、潜在客户字段或更高级的用例中， [从登陆页面提取自定义参数](https://docs.google.com/document/d/1NRViyCsXvPKbCTfGW32Yi2vWBjMDRF7bzkzKj9s2DDA/edit?ts=5e20b482#heading=h.xxwtissvw4){target=&quot;_blank&quot;}。 然后，它将其放置到接触点字段(请参阅 [映射到示例](https://docs.google.com/document/d/1NRViyCsXvPKbCTfGW32Yi2vWBjMDRF7bzkzKj9s2DDA/edit?ts=5e20b482#heading=h.xxwtissvw4){target=&quot;_blank&quot;} #2)。

**示例#1**

联系人上有一个自定义字段，即campaign_source__c，客户希望将该字段放入接触点以进行报告。 您可以定义一个规则以创建名为“促销活动源”的计算字段，并将值放入该字段中。

目标：使用自定义字段的值并将其置于接触点对象上，以便更轻松地进行报告。

* 创建计算字段并将其标记为“促销活动源”
* 通过从搜索Contact.Campaign_Source__c字段开始定义规则
* 使用运算符“提取”，因为我们需要从参数中提取值
* 要从字段中提取完整字符串，我们将使用表达式“(.&#42;)&quot;

   * **(** 标记提取的开始
   * **)** 标记提取的结尾
   * **.&#42;** 告诉我们，我们正在提取

![](assets/two.png)

**示例#2**

此功能支持的常见用例是从URL字符串的自定义参数中提取值。 如果您使用UTM以外的参数，但想要将值解析到接触点字段，则此功能非常有用。

**链接：** `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=5OFF` 或 `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=25OFF`.\
**目标：** 创建一个名为“折扣代码”的自定义字段，并在值“5OFF”或“25OFF”中放入任何传递的值。

* 创建计算字段并将其标记为“折扣代码”
* 从搜索Touchpoint.Session.LandingPage字段开始定义规则
* 使用运算符“提取”，因为我们需要从参数中提取值
* 要提取促销活动的值，我们将该值定义为“promo=(\w+)”

   * **(** 标记提取的开始
   * **)** 标记提取的结尾
   * **\w** 告诉我们，我们正在提取一个包含0-9的“单词”
   * **+** 将提取参数的完整值，字符没有限制
   * 请注意，您使用的是正斜杠而不是反斜杠

![](assets/three.png)

**示例#3**

让我们试试一个类似的示例，其中我们提取跟踪代码，例如： `https://www.adobe.com/blog/marketing-revenue-reporting-overview?cid=123456`.

**目标：** 创建一个计算字段，并使用cid参数的值将其标记为“Adobe Campaign Id”。

* 创建计算字段并将其标记为“Adobe Campaign Id”
* 从搜索Touchpoint.Session.LandingPage字段开始定义规则
* 使用运算符“提取”，因为我们需要从参数中提取值
* 要提取“123456”值，我们将该值定义为“cid=(\d{6})”

   * **(** 标记提取的开始
   * **)** 标记提取的结尾
   * **\d** 告诉我们，我们正在提取一个“数字”
   * **{6}** 是我们提取的字符数

![](assets/four.png)

**示例#4**

由于登陆页面变得越来越复杂，并且您有多个跟踪参数，因此您可能需要构建多个接触点字段并多次提取值，例如：
`https://www.adobe.com/blog/marketing-revenue-reporting-overview?trackID=123456&country=US&campaign_ID=7890`.

**目标：** 使用参数中的相应值为“目标国家/地区”和“自定义促销活动ID”创建多个计算字段。

* 创建计算字段并将其标记为“目标国家/地区”
* 从搜索Touchpoint.Session.LandingPage字段开始定义规则
* 使用运算符“提取”，因为我们需要从参数中提取值
* 要提取“US”值，我们将将该值定义为“country=(\w{2})”

   * **(** 标记提取的开始
   * **)** 标记提取的结尾
   * **\w** 告诉我们，我们在提一个“单词”
   * **{2}** 是我们提取的字符数

* 创建计算字段并将其标记为“自定义促销活动ID”
* 从搜索Touchpoint.Session.LandingPage字段开始定义规则
* 使用运算符“提取”，因为我们需要从参数中提取值
* 要提取“123456”值，我们将将该值定义为“campaign_ID=(\d{6})”

   * **(** 标记提取的开始
   * **)** 标记提取的结尾
   * **\d** 告诉我们，我们正在提取一个“数字”
   * **{6}** 是我们提取的字符数

![](assets/five.png)

**映射到**

映射到运算符会创建一个需要转换或存储到其他值的值表。 通常，这采用键值的形式，其中代码表示友好名称，需要将代码映射到该友好名称。

**示例#1**

您为“夏末促销活动结束”和“黑色星期五促销活动”创建了多个渠道的促销活动。 您要创建一个名为“计划”的计算字段，并且除了其他可能的值外，您还希望将具有“夏季结束促销”或“黑色星期五促销”的任何接触点映射到“计划”值，如“促销”。

![](assets/six.png)

**示例#2**

既然我们已经学习了如何提取字段并映射到字段，让我们结合这些操作以便首先从参数中提取值，然后将其映射到一个更有意义的友好名称。 让我们从此登陆页面开始： `https://www.adobe.com/blog/marketing-revenue-reporting-overview?BZ=04-01-09-03-10`.

**目标：** 创建多个计算字段，其中第一个数字映射到区域，第二个数字映射到产品，第三个数字映射到方案，第四个数字映射到人物，第五个数字映射到媒体平台。 然后，将数字值映射为“友好名称”。

* 创建计算字段并将其标记为“区域”
* 从搜索Touchpoint.Session.LandingPage字段开始定义规则
* 使用运算符“[!UICONTROL extracts]“ ”，因为我们需要从参数中提取值
* 要提取“04”值，我们将将该值定义为“BZ=(\d{2})-\d{2}-\d{2}-\d{2}-\d{2}”

   * **(** 标记提取的开始

      * 请注意，由于我们仅提取4，因此只有前位数具有左括号
   * **)** 标记提取的结尾

      * 请注意，由于我们仅提取4，因此只有前位数的括号为
   * **\d** 告诉我们，我们正在提取一个“数字”
   * **{2}** 是我们提取的字符数



* 单击 [!UICONTROL Save]. 您必须保存新字段，然后才能将其用于下一个规则！
* 接下来，我们要将前位的所有可能值映射到其友好名称
* 创建计算字段并将其标记为“Region_Name”
* 通过从搜索提取的字段开始定义规则。 在本例中，为Touchpoint.Region
* 使用运算符“[!UICONTROL maps to]“ ”，因为我们希望为每个数字创建到其值的映射
* 您将看到一个表格，其中列出了每个映射。 最后，它将如下所示：
* 根据映射和上述URL，与此登陆页面接触点的“Region_Value”将为“EMEA”
* 对剩余的4位集重复提取和映射

   * 要提取01，您应将值定义为“BZ=\d{2}-**(\d{2})**-\d{2}-\d{2}-\d{2}&quot;
   * 要提取09，您应将值定义为“BZ=\d{2}-\d{2}-**(\d{2})**-\d{2}-\d{2}&quot;
   * 要提取03，您应将值定义为&quot;BZ=\d{2}-\d{2}-\d{2}-**(\d{2})**-\d{2}&quot;
   * 要提取10，您应将值定义为&quot;BZ=\d{2}-\d{2}-\d{2}-\d{2}-\d{2}-**(\d{2})**&quot;

![](assets/seven.png)

**串联**

串联运算符将多个字段中的值合并为单个字段。 这对于创建跨不同字段提取数据的自定义值以便生成

**示例#1**

Segment__c和Grade__c的Opportunity对象上有不同的字段，用户希望将这些字段合并到Touchpoint对象上的单个字段中以用于报告目的。 通过关联字段，您将看到Enterprise_A或Mid-Market_B等值。

![](assets/eight.png)

## 接触点字段和区段 {#touchpoint-fields-and-segments}

现在，您URL中的值已解析出并存在于接触点上，因此无论在何处使用接触点字段，例如创建区段或定义接触点删除规则，您都将看到新字段。

此产品版本中提供了使用接触点字段创建区段的功能。 无法在之前使用接触点字段生成区段。

![](assets/nine.png)

为了更轻松地构建区段，现在可以从之前创建的接触点字段创建动态区段。 例如，如果您创建了一个接触点字段，该字段解析了某个地理区域，而不是为每个可能的区域创建一个区段，则可以设置一个区段，我们将为每个实例创建区段，此时会显示一个新值。 如果需要将邮政编码等属性解析并用作区段，则此功能会非常有用！

您的设置将类似于下面的屏幕截图。 区段名称可使用大括号动态提取接触点字段值，以搜索您的字段。

![](assets/ten.png)

规则引用相同的接触点字段，并搜索“不等于null”的值。

![](assets/eleven.png)

## 常见问题解答 {#faq}

**我们可以创建的接触点字段是否最大数量？**

限制为100个字段。

**我在挑选列表中没有看到我刚刚创建的新接触点字段。 它在哪里？**

创建规则后，请不要忘记保存规则。 如果看不到新字段，请检查是否保存了。 您必须先保存新字段，然后才能将其用于下一个规则。

>[!NOTE]
>
>由于复杂性级别，无法在其他接触点字段中使用使用“映射到”运算符的接触点字段。

**我使用什么表达式从单个登陆页面提取多个参数？**

与提取示例#4中的一样，您需要创建多个字段以提取每个参数。 因此，如果您有五个不同的值，您将创建五个接触点字段以提取每个值。

**为什么在 [!DNL Marketo Measure] 模式？**

在 [!DNL Marketo Measure] data warehouse模式。 目前，字段会通过设置和配置公开，以便您能够在生成区段或创建“接触点删除”规则时使用接触点字段。

**如何验证我的提取表达式是否有效并提取正确的值？**

有一个在线工具([https://regex101.com/](https://regex101.com/){target=&quot;_blank&quot;})，以运行并测试表达式。 如果表达式有效，则显示为绿色；如果表达式无效，则显示为红色。 此外，右上方的说明框也很有帮助，它会告诉您提取的内容。

![](assets/twelve.png)

![](assets/thirteen.png)