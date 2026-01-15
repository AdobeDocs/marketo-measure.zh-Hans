---
description: 面向Marketo Measure用户的自定义分段指南
title: 自定义分段
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
feature: Segmentation
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# 自定义分段 {#custom-segmentation}

区段提供筛选[!DNL Marketo Measure] ROI仪表板中数据的功能，以便进一步深入分析特定数据集。 例如，区段可以按地理区域或评分系统定义。

**为什么自定义分段？**

自定义分段允许您按类别（过滤器名称）和规则（过滤器值）过滤接触点。 第1层客户获得一个区段，第2层及更高层获得十个。 根据您的ROI Dash指向的对象（潜在客户或联系人），您可以根据Lead/Contact对象上的字段创建区段。 另外，您还可以根据在Opportunity对象上找到的任何字段来创建区段。

**自定义分段功能何时有用？**

自定义分段可用于查看特定记录类型的数据。 映射筛选器逻辑后，您应该能够在[!DNL Marketo Measure]功能板的需求瀑布视图中看到 — 与在CRM中看到的数据相同。

**如何设置？**

>[!NOTE]
>
>更新区段规则将重新处理历史数据。

第1步 — 确定要查看的信息。

在使用此功能之前，请确定您想要过滤的接触点信息。 请记住在CRM中为您的记录类型使用准确的值。 该设置将从营销型funnel的顶部到底部筛选接触点。

步骤2 — 登录并找到[!UICONTROL Segments]功能。

* 转到[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}并登录
* 在[!UICONTROL My Account]选项卡下，选择[!UICONTROL Settings]
* 从左侧边栏中[!UICONTROL Segments]部分下的选项中选择[!UICONTROL Reporting]

步骤3 — 了解组件。

* 使用此图例可了解此页面上的各种图标

![使用此图例了解此页面上的各种图标](assets/custom-segmentation-1.png)

步骤4 — 添加筛选规则。

* 首先，输入类别名称。 [!UICONTROL Business Type]是一个示例。 完成后，单击复选标记。 在添加区段之前，需要输入类别名称
* 单击加号以添加区段
* 输入区段名称。 例如，您可以有一个区段用于新业务、合作伙伴、续订或追加销售

![输入区段名称。 例如，您可以为](assets/custom-segmentation-2.png)创建一个区段

* 单击加号图标以显示规则输入字段。 字段选取列表中的选项直接从您的CRM中提取字段

![单击加号图标以显示规则输入字段。 选项](assets/custom-segmentation-3.png)

>[!NOTE]
>
>公式字段不能在规则中使用，也不会显示在选择列表中。 由于公式在后台计算且不会修改记录，因此[!DNL Marketo Measure]无法检测记录是否符合规则。

* [!UICONTROL Value]选项不是下拉列表，必须手动输入其值。 请务必查看Salesforce组织中的值
* 对Opportunity区段规则重复此流程
* “其他”类别是将捕获任何未定义接触点的默认区段。 您可以更改默认区段的名称
* 单击垃圾桶图标可删除整个类别或类别中的单个规则。 或者，单击铅笔图标以编辑类别或规则
* 请注意，您有一个&quot;[!UICONTROL Save]&quot;按钮和一个&quot;Save and Process&quot;按钮。 使用“保存”按钮可保存您所做的工作以及随时间发生的更改。 仅在确保以下各项后使用“保存并处理”按钮：

   * 您的映射是准确的
   * 您已添加要在一个类别中跟踪的所有区段
   * “保存并处理”按钮触发[!DNL Marketo Measure]同步您的所有接触点并应用您添加的新信息。 此过程需要7天，在此期间，无法更改规则

**_其他注释:_**

如果未同时为Lead/Contacts和Opportunity设置规则，您将只看到部分数据。 更具体地说，如果您未设置Opportunities规则，您将只看到Lead/Contact数据，而不显示与其关联的Opportunities。 如果您没有为“销售线索/联系人”设置规则，则同样如此 — 您只会看到没有关联销售线索/联系人的销售机会。

完成后，请先单击[!UICONTROL Save]，仔细检查所有内容，然后单击[!UICONTROL Save and Process]。 请记住，在保存并处理设置后，您无法在七天内编辑设置，因为[!DNL Marketo Measure]在此期间正在重新格式化您的数据。

如果您是Marketo Measure Ultimate客户，并且已将您的默认功能板对象设置为联系人，请不要使用以下两个特定于潜在客户的字段（[了解更多](/help/data-integrity-requirement.md){target="_blank"}）。

* b2b.personStatus
* b2b.isConverted

**如何保存生成的报告？**

不能直接在用户界面中保存生成的报表。 但是，[!DNL Marketo Measure]会将区段名称保存在URL中，这样您可以通过为页面添加书签来保留每个报表的记录。
