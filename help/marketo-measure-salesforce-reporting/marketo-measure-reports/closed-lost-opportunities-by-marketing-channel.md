---
description: 按营销渠道列出的已关闭的丢失机会 —  [!DNL Marketo Measure]
title: 按营销渠道列出的已关闭的丢失机会
exl-id: 010169fc-f7e7-4ab2-92fe-87e4250dd536
feature: Channels, Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---


# 按营销渠道列出的已关闭的丢失机会 {#closed-lost-opportunities-by-marketing-channel}

尽管此报表可能取决于您的机会阶段，但此报表将揭示哪些营销渠道促成了未成功的机会。

1. 在Salesforce中单击您的&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡并选择&#x200B;**[!UICONTROL New Report]**。

   ![突出显示了“新报告”按钮的“Salesforce报告”选项卡](assets/1-3.jpg)

1. 在“Bizible归因”中的快速查找类型中，选择&#x200B;**[!UICONTROL Bizible Attribution Touchpoint with Opportunity]**&#x200B;报表类型，然后选择&#x200B;**[!UICONTROL Create]**。

   ![显示带有Opportunity选项的Bizible Attribution接触点的报告类型选择](assets/2-3.jpg)

1. 从报表顶部开始，显示“[!UICONTROL All Bizible Attribution Touchpoints]”，并根据要报告的时间范围调整日期字段。 在我们的示例中，我们一直都在查看。 此外，将报告格式从“表格”更改为“摘要”。

   ![显示具有日期范围选择器的所有Bizible归因接触点的报告过滤器](assets/3-3.jpg)

   ![选定的摘要格式的报告格式选项](assets/4-2.jpg)

1. 现在，我们将向报告添加字段。 在左侧的快速查找中，键入“Marketing Channel”并将其添加到报表中的摘要分组。

   ![Report Builder显示正在添加到摘要分组中的“营销渠道”字段](assets/5.jpg)

1. 接下来，我们将添加一个过滤器，以便仅查看“已关闭的丢失的打开”。 在左侧的快速查找中，搜索“Stage”字段并将其拖到筛选区域中。

   ![将阶段字段拖入筛选器节的报告筛选器区域](assets/6.jpg)

1. 从那里，您将选择放大镜来选择用于“已关闭的丢失”机会的任何阶段。 在我们的示例中，我们将使用标准的“已关闭的丢失”命名。

   ![阶段筛选器选取器显示“已关闭的丢失”阶段选择选项](assets/7.jpg)

1. 现在，继续运行报告！

   这是由营销渠道汇总的、用于衡量跨渠道已关闭的已错失销售机会的销售渠道报表。 通过此报告，您可以了解哪些渠道可能表现不佳。 欢迎您随时添加任何要报告的过滤器或字段。

>[!MORELIKETHIS]
>[[!DNL Marketo Measure] 教程：其他SFDC报告](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/addtional-salesforce-reports)
