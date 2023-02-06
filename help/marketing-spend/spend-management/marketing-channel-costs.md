---
unique-page-id: 18874602
description: 营销渠道成本 —  [!DNL Marketo Measure]  — 产品文档
title: 营销渠道成本
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 0%

---

# 营销渠道成本 {#marketing-channel-costs}

使用 [!DNL Marketo Measure] 是能够将营销工作直接与收入影响相关联，并且粒度可根据需要而定。 在接触点级别，可以看到投资回报。 要利用此优势，渠道成本只需上传到 [!DNL Marketo Measure] 应用程序。 ROI报表是在 **营销ROI仪表板** in [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

[单击此处直接导航到相关说明。](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

的 [!DNL Marketo Measure] 营销支出功能允许客户跨所有渠道、子渠道和促销活动上传其支出。 客户添加的数据越多，我们在收入归因功能板中可显示的ROI报表就越多。

从直接广告连接报告和导入的成本会在最精细的级别自动提取，无需上传。 这包括我们当前与Google AdWords、Bing Ads、Doubleclick和Facebook的集成。

[单击此处直接导航到常见问题解答。](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## 定义 {#definitions}

**按促销活动支出**

在最细粒度的级别上，客户可以按各个促销活动输入支出，并将其分组到各自的渠道中。 对于CRM促销活动， [!DNL Marketo Measure] 已将促销活动ID提取到单独的列中，该列将帮助您将离线促销活动支出从CRM映射到此表。 增加此级别的支出将使客户能够查看促销活动ROI并按促销活动优化效果。

所有促销活动的总数不需要累计到在子渠道或渠道中输入的任何值，但不能超过在子渠道或渠道中输入的任何值。 如果总和小于在子渠道或渠道中输入的值， [!DNL Marketo Measure] 将自动为“其他”添加一行，以覆盖差异并填补任何空白。

**按子渠道支出**

在更高级别，客户可以按子渠道输入支出，并将其分组到其渠道下。 在此级别增加支出将使客户能够查看子渠道ROI并按子渠道优化性能。

所有子渠道的总数不需要累计到在渠道中输入的任何值，但不能超过在渠道中输入的任何值。 如果总和小于在渠道中输入的值， [!DNL Marketo Measure] 将自动为“其他”添加一行，以覆盖差异并填补任何空白。

**按渠道支出**

在最高级别，客户可以按渠道输入支出。 增加此级别的支出将使客户能够查看渠道ROI并按渠道优化性能。

**日期选取器**

默认日期范围将从您的开始日期开始，日期范围为 [!DNL Marketo Measure] 到当月为止。 为确保成本保持正确，您无法输入未来月份的成本，但您可以输入与合作之前几个月的成本 [!DNL Marketo Measure].

**筛选器**

要在“营销支出”表中缩小结果范围，请选择顶部的渠道以过滤掉其他渠道。 如果您的团队关注单个渠道，则此功能非常有用。

**搜索**

使用“搜索”框可从渠道、子渠道或促销活动中查找匹配的文本。

**下载当前成本**

下载的CSV将从您当前的屏幕中提取结果，这意味着将按原样下载所应用的任何日期、过滤器或搜索。

**上传CSV**

无论浏览器中显示的视图是哪个，如果它是过滤的视图或包含所有日期和渠道的默认视图，则可以上传任何CSV。

我们遇到的最常见错误是日期列的格式，当日期格式发生更改时会发生该格式，如果在Excel和/或Google工作表之间移动，则可能会有意发生该格式。 请记住，日期应为MM-YY，因此应在9月12日，而不是9月12日，或者5月12日，而不是05-12日。

## 开始之前 {#before-you-begin}

[!DNL Marketo Measure] 附带13个默认渠道，可供使用或展开。 此外，最多可创建40个在线和离线渠道，以适应您的独特营销结构。 在此基础上，还可以共创建200个子渠道以支持这些在线和离线渠道。

[!DNL Marketo Measure] 将自动从其与API集成的平台(如Bing Ads和Google AdWords)下载营销渠道成本。 未与集成的平台的成本 [!DNL Marketo Measure] 需要手动上传。 应先设置营销渠道，然后再上传成本数据。

## 上传营销成本 {#uploading-marketing-costs}

设置或更新营销渠道和规则后，可能会上传相关成本。 为此，请执行以下步骤：

**步骤1:导航至 [!DNL Marketo Measure] 应用程序。**

转到 **[!UICONTROL My Account]** 菜单，单击 **[!UICONTROL Settings]** 然后导航到 **[!UICONTROL Marketing Spend]** 选项 **[!UICONTROL Reporting]** 中。

![](assets/1.png)

**步骤2:下载当前成本CSV**

导航到屏幕右侧，然后单击 **[!UICONTROL Download Current Costs].** 利用此选项，可下载CSV格式的电子表格。

![](assets/2.png)

**步骤3:打开CSV文件并进行更改**

您可以导入文件并使用Google工作表、Apple编号、Microsoft Excel或您选择的软件将其打开。 [!DNL Marketo Measure] 建议使用Google工作表。

导入工作表后，进行所需的更改，如向渠道和子渠道添加成本或更新现有信息。

检查工作表中的逻辑规则。 每行应包含一个渠道及其一个以(.)分隔的子渠道 圆点。 必须始终使用此格式。

例如，要将Facebook指示为子渠道，将social指示为渠道，则应按如下方式编写规则：&quot;Social.Facebook&quot; 同样，要跟踪离线事件，渠道语法应为：“Events.Big Conference” 示例如下图所示：

![](assets/3.png)

_其他说明_:

请勿修改电子表格中的日期，因为这可能在上载文档时导致问题。

请勿将任何字段留空。 即使没有要添加的美元值，也输入$0作为美元值。

由于 [!DNL Marketo Measure] 会自动从与这些平台的API连接中提取此数据。

**步骤4:以CSV格式保存文件**

如果您在Google工作表中工作，请务必先下载文件。 请勿排除或删除任何月度数据，因为在尝试将CSV文件上传到 [!DNL Marketo Measure] 稍后。

**步骤5:上传CSV文件**

转到 **[!UICONTROL Cost]** 部分 [!DNL Marketo Measure] 应用程序，单击 **[!UICONTROL Upload.CSV]**. 系统将刷新并反映新信息。

## 常见问题解答 {#faq}

**为什么数字会显示在CSV中**

如果没有在更高级别（如渠道或子渠道）输入值， [!DNL Marketo Measure] 将自动对您的子级别求和，上传文件后将显示子级别求和。 此外，如果子代的总和小于为父代输入的值， [!DNL Marketo Measure] 将添加“其他”行以显示总数中的差异。

**如何在我看到的列表中确定营销活动？**

目前，我们的结果列出了我们看到的营销活动，这些活动被计入了接触点。 如果某个营销活动中存在活动，我们将根据该活动发生的接触点日期显示该营销活动。

**筛选的行和列过多 — 我是否可以整合视图？**

通过更改日期范围、过滤渠道或搜索值的功能，您可以整合表格结果以更好地满足您的需求。

**为什么无法上传文件？**

我们在 [!DNL Marketo Measure] 应用程序。 要上传文件，您需要是“AccountAdmin”。 要解决此问题，请代表您请求AccountAdmin访问您的帐户，或让您的AccountAdmin上传文件。 可在 **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL View/Add Account Users]**.
