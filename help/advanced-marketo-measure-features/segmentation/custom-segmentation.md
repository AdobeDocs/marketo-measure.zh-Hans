---
unique-page-id: 18874604
description: 自定义分段 —  [!DNL Marketo Measure]
title: 自定义分段
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
feature: Segmentation
source-git-commit: e1ad563aac12ceb6bea6c28621ebd1cb7ec0a923
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---

# 自定义分段 {#custom-segmentation}

通过区段，可以过滤以下位置的数据 [!DNL Marketo Measure] ROI仪表板，以进一步深入了解特定数据集。 例如，区段可以按地理区域或评分系统定义。

**为何选择自定义分段？**

自定义分段允许您按类别（过滤器名称）和规则（过滤器值）过滤接触点。 第1层客户获得一个区段，第2层及更高层获得十个。 根据您的ROI Dash指向的对象（潜在客户或联系人），您可以根据Lead/Contact对象上的字段创建区段。 另外，您还可以根据在Opportunity对象上找到的任何字段来创建区段。

**自定义分段功能何时有用？**

自定义分段可用于查看特定记录类型的数据。 映射筛选器逻辑后，您应该能够在 [!DNL Marketo Measure] 功能板的需求瀑布视图 — 您在CRM中看到的相同数据。

**我该如何设置？**

>[!NOTE]
>
>更新区段规则将重新处理历史数据。

第1步 — 确定要查看的信息。

在使用此功能之前，请确定您想要过滤的接触点信息。 请记住在CRM中为您的记录类型使用准确的值。 该设置将从营销漏斗的顶部到底部过滤接触点。

第2步 — 登录并找到 [!UICONTROL Segments] 功能。

* 转到 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} 并登录
* 在 [!UICONTROL My Account] 选项卡，选择 [!UICONTROL Settings]
* 选择 [!UICONTROL Segments] 左侧边栏中的选项，下方的 [!UICONTROL Reporting] 部分

步骤3 — 了解组件。

* 使用此图例可了解此页面上的各种图标

![](assets/1.png)

步骤4 — 添加筛选规则。

* 首先，输入类别名称。 [!UICONTROL Business Type] 就是一个例子。 完成后，单击复选标记。 在添加区段之前，需要输入类别名称
* 单击加号以添加区段
* 输入区段名称。 例如，您可以有一个区段用于新业务、合作伙伴、续订或追加销售

![](assets/2.png)

* 单击加号图标以显示规则输入字段。 字段选取列表中的选项直接从您的CRM中提取字段

![](assets/3.png)

>[!NOTE]
>
>公式字段不能在规则中使用，也不会显示在选择列表中。 因为公式在后台计算且不会修改记录， [!DNL Marketo Measure] 无法检测记录是否适合规则。

* 此 [!UICONTROL Value] 选项不是下拉列表，必须手动输入其值。 请务必查看Salesforce组织中的值
* 对Opportunity区段规则重复此流程
* “其他”类别是将捕获任何未定义接触点的默认区段。 您可以更改默认区段的名称
* 单击垃圾桶图标可删除整个类别或类别中的单个规则。 或者，单击铅笔图标以编辑类别或规则
* 请注意，您拥有&quot;[!UICONTROL Save]”按钮和“保存并处理”按钮。 使用“保存”按钮可保存您所做的工作以及随时间发生的更改。 仅在确保以下各项后使用“保存并处理”按钮：

   * 您的映射是准确的
   * 您已添加要在一个类别中跟踪的所有区段
   * “保存并处理”按钮触发 [!DNL Marketo Measure] 以同步所有接触点并应用您添加的新信息。 此过程需要7天，在此期间，无法更改规则

**_其他说明：_**

如果未同时为Lead/Contacts和Opportunity设置规则，您将只看到部分数据。 更具体地说，如果您未设置Opportunities规则，您将只看到Lead/Contact数据，而不显示与其关联的Opportunities。 如果您没有为“销售线索/联系人”设置规则，则同样如此 — 您只会看到没有关联销售线索/联系人的销售机会。

完成后，单击 [!UICONTROL Save] 首先，双击所有内容，然后单击 [!UICONTROL Save and Process]. 请记住，在保存并处理之后的7天内，您无法编辑设置，因为 [!DNL Marketo Measure] 正在重新格式化此期间的数据。

如果您是Marketo Measure Ultimate客户并将您的默认功能板对象设置为Contact，请不要使用下面两个特定于Lead的字段([了解详情](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"})。

* b2b.personStatus
* b2b.isConverted

**如何保存生成的报表？**

不能直接在用户界面中保存生成的报表。 但是， [!DNL Marketo Measure] 将区段名称保存在URL中，以便您可以通过为页面添加书签来保留每个报表的记录。
