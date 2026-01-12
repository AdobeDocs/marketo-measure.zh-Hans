---
description: 营销渠道成本
title: 营销渠道成本
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
feature: Channels, Spend Management
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1294'
ht-degree: 0%

---


# 营销渠道成本 {#marketing-channel-costs}

使用[!DNL Marketo Measure]的最根本优势之一是，能够根据需要尽可能详细地将营销工作与对收入的影响直接联系起来。 投资回报率有可能出现在接触点层面。 若要利用此优势，必须将渠道成本上传到[!DNL Marketo Measure]应用程序。 ROI报告会自动创建并出现在&#x200B;**experience.adobe.com/marketo-measure**&#x200B;的[营销ROI仪表板](https://experience.adobe.com/marketo-measure){target="_blank"}中。

[单击此处直接导航到说明。](/help/marketing-spend/marketing-channel-costs.md#uploading-marketing-costs)

使用[!DNL Marketo Measure]营销支出功能，客户可以跨所有渠道、子渠道和营销活动上传其支出。 客户添加的数据越多，收入归因功能板中显示的ROI报表就越多。

从直接广告连接报告和导入的成本会在最精细的级别自动拉入，无需上传。 这包括我们当前与Google AdWords、Bing Ads、Doubleclick和Facebook的集成。

[单击此处直接导航到常见问题解答。](/help/marketing-spend/marketing-channel-costs.md#faq)

## 定义 {#definitions}

按营销活动&#x200B;**支出**

在极其精细的粒度级别，客户可以按各营销活动（在其各自的渠道中分组）输入支出。 对于CRM营销活动，[!DNL Marketo Measure]已将营销活动ID提取到单独的列中，这有助于您将离线营销活动支出从CRM映射到此表中。 在此级别添加支出使客户能够查看Campaign ROI并按Campaign优化性能。

所有促销活动的总数不需要合计在子渠道或渠道中输入的任何值，但不能超过在子渠道或渠道中输入的任何值。 如果总和小于在子渠道或渠道中输入的值，[!DNL Marketo Measure]将自动为“其他”添加一行以弥补差异并填补任何空白。

**按子渠道支出**

在更高级别，客户可以按子渠道输入支出，这些支出按子渠道分组到其渠道下。 在此级别添加支出使客户能够查看子渠道ROI并按子渠道优化性能。

所有子渠道的总数不需要合计在渠道中输入的任何值，但不能超过在渠道中输入的任何值。 如果总和小于在渠道中输入的值，[!DNL Marketo Measure]将自动为“其他”添加一行以弥补差异并填补任何空白。

**按渠道支出**

在最高级别，客户可以按渠道输入支出。 在此级别增加支出使客户能够按渠道查看渠道ROI并优化性能。

**日期选取器**

默认日期范围将从您的开始日期[!DNL Marketo Measure]开始到当前月份。 为确保成本保持正确，您无法输入未来几个月的成本，但可以在与[!DNL Marketo Measure]合作之前输入几个月的成本。

**过滤器**

要在“营销支出”表中缩小结果范围，请选择顶部的一个渠道以过滤掉其他渠道。 当您的团队专注于单个渠道时，这将很有帮助。

**搜索**

使用搜索框从渠道、子渠道或营销活动中查找匹配的文本。

**下载当前成本**

下载的CSV将从当前屏幕中提取结果，这意味着应用的任何日期、过滤器或搜索都将按原样下载。

**上传CSV**

无论浏览器中处于哪个视图，如果它是筛选视图或包含所有日期和渠道的默认视图，则可以上传任何CSV。

最常见的错误是日期列的格式，如果日期格式发生更改，可能会发生此错误；如果在Excel和/或Google工作表之间移动，则可能会有意发生此错误。 请记住，日期应为MM-YY，因此9月12日而不是9月12日，或者5月12日而不是05-12日。

## 开始之前 {#before-you-begin}

[!DNL Marketo Measure]附带13个默认渠道，可以对其使用或展开。 此外，还可创建多达40个在线和离线渠道以适应您独特的营销结构。 在此基础上，可创建总计200个子渠道以支持这些在线和离线渠道。

[!DNL Marketo Measure]将自动从与API集成的平台(如Bing Ads和Google AdWords)下载营销渠道成本。 需要手动上传未与[!DNL Marketo Measure]集成的平台的成本。 在上传成本数据之前，应设置营销渠道。

## 上传营销成本 {#uploading-marketing-costs}

设置或更新营销渠道和规则后，可以上传相关成本。 为此，请执行以下步骤：

**步骤1：导航到[!DNL Marketo Measure]应用程序中的“营销支出”页面。**

转到&#x200B;**[!UICONTROL My Account]**&#x200B;菜单，单击&#x200B;**[!UICONTROL Settings]**，然后导航到&#x200B;**[!UICONTROL Marketing Spend]**&#x200B;部分下的左侧边栏上的&#x200B;**[!UICONTROL Reporting]**&#x200B;选项。

Marketo Measure中的![营销支出设置页面](assets/1.png)

**步骤2：下载当前成本CSV**

导航到屏幕右侧并单击&#x200B;**[!UICONTROL Download Current Costs]。**&#x200B;此选项允许您下载CSV格式的电子表格。

在营销支出页面上![下载当前成本选项](assets/2.png)

**步骤3：打开CSV文件并进行更改**

您可以导入文件，并使用Google Sheets、Apple Numbers、Microsoft Excel或您选择的软件将其打开。 [!DNL Marketo Measure]建议使用Google工作表。

导入工作表后，进行所需的更改，如向渠道和子渠道添加成本或更新现有信息。

检查工作表中的逻辑规则。 每一行应包含一个通道及其一个子通道，通道末尾以一个(.)点分隔。 始终如一地使用此格式很重要。

例如，要将Facebook指示为子渠道，将social指示为渠道，则规则应编写如下：“Social.Facebook”。 同样，要跟踪离线事件，渠道语法应为：“Events.Big Conference”。 示例如下图所示：

![显示渠道和子渠道成本条目的CSV示例](assets/3.png)

_其他备注_：

请勿修改电子表格中的日期，因为这会在上传文档时导致问题。

请勿将任何字段留空。 即使没有要添加的美元值，也输入$0作为美元金额。

无需输入或更新Bing Ads和Google AdWords成本，因为[!DNL Marketo Measure]会自动从与这些平台的API连接中提取此数据。

**步骤4：以CSV格式保存文件**

如果您使用Google Sheets，请务必先下载文件。 请勿排除或删除任何每月数据，因为它会在尝试稍后将CSV文件上传到[!DNL Marketo Measure]时导致困难。

**步骤5：上传CSV文件**

转到&#x200B;**[!UICONTROL Cost]**&#x200B;应用的[!DNL Marketo Measure]部分，然后单击&#x200B;**[!UICONTROL Upload.CSV]**。 系统将刷新并反映新信息。

## 常见问题解答 {#faq}

**为什么数字出现在CSV中**

如果未在更高的级别（如渠道或子渠道）输入值，则[!DNL Marketo Measure]将自动为您添加子级别的总和，上传文件后将显示这些子级别。 此外，如果子项的总和小于为父项输入的值，[!DNL Marketo Measure]将添加“其他”行以显示总数的差异。

**我看到的列表中如何确定促销活动？**

目前，我们的结果会列出我们看到的、因接触点而值得信赖的营销活动。 如果存在来自Campaign的活动，我们会根据发生的接触点日期显示Campaign。

**要筛选的行和列太多 — 能否合并视图？**

利用更改日期范围、筛选渠道或搜索值的功能，您可以合并表的结果以更好地满足您的需求。

**为什么我无法上载文件？**

我们在[!DNL Marketo Measure]应用程序中有不同的权限集。 要上传文件，您必须是“帐户管理员”。 要解决此问题，请向帐户管理员请求访问权限，或让帐户管理员代表您上传文件。 可以在&#x200B;**[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL View/Add Account Users]**&#x200B;下找到用户及其角色的列表。
