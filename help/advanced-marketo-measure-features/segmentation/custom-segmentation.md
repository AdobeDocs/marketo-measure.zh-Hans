---
unique-page-id: 18874604
description: 自定义分段 —  [!DNL Marketo Measure]  — 产品文档
title: 自定义分段
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# 自定义分段 {#custom-segmentation}

区段提供在 [!DNL Marketo Measure] ROI仪表板，以便进一步深入分析特定数据集。 例如，区段可以由地理区域或分级系统定义。

**为什么选择自定义分段？**

“自定义分段”功能允许您按一个类别和最多五个区段过滤接触点。 根据ROI短划线指向的对象（潜在客户或联系人），您可以根据在潜在客户/联系人对象上找到的字段创建区段。 此外，您还将能够根据在Opportunity对象上找到的任何字段创建区段。

**自定义分段功能何时有用？**

自定义分段可用于查看特定记录类型的数据。 映射过滤器逻辑后，您应该能够在 [!DNL Marketo Measure] 功能板的“需求瀑布视图” — 您在CRM中看到的相同数据。

**如何设置它？**

步骤1 — 确定要查看的信息。

在使用此功能之前，请确定要过滤的接触点信息。 请记住在CRM中为记录类型使用准确的值。 设置将从营销漏斗的顶部到底部过滤接触点。

第2步 — 登录并找到区段功能。

* 转到 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}登录
* 在 [!UICONTROL My Account] 选项卡，选择 [!UICONTROL Settings]
* 选择 [!UICONTROL Segments] 从左侧边栏的选项下方 [!UICONTROL Reporting] 部分

第3步 — 了解组件。

* 使用此图例可了解此页面上的各种图标

![](assets/1.png)

步骤4 — 添加过滤器规则。

* 首先，输入类别名称。 业务类型就是一个示例。 完成后，单击复选标记。 在添加区段之前，您需要输入类别名称
* 单击加号以添加区段
* 输入区段名称。 例如，您可以为新业务、合作伙伴、续订或追加销售提供一个区段

![](assets/2.png)

* 单击加号图标以显示规则输入字段。 字段选取列表中的选项直接从您的CRM中提取字段

![](assets/3.png)

>[!NOTE]
>
>公式字段不能在规则中使用，也不会显示在选取列表中。 由于公式在后台计算而不修改记录， [!DNL Marketo Measure] 无法检测记录是否符合规则。

* “值”选项不是下拉列表，其值必须手动输入。 请务必检查Salesforce组织中的值
* 对Opportunitys区段规则重复此过程
* “其他”类别是默认区段，将捕获任何未定义的接触点。 您可以更改默认区段的名称
* 单击垃圾桶图标可删除整个类别或类别中的单个规则。 或者，单击铅笔图标以编辑类别或规则
* 您会注意到您有一个“保存”按钮和一个“保存并处理”按钮。 使用保存按钮可保存您的工作和随时间发生的更改。 仅当您确保：

   * 您的映射准确无误
   * 您添加了要在类别中跟踪的所有区段
   * “保存并处理”按钮触发器 [!DNL Marketo Measure] 同步所有接触点并应用您添加的新信息。 此过程需要7天，在此期间无法更改规则

**_其他说明：_**

如果未为Lead/Contact和Opportunity设置规则，您将只看到一部分数据。 要详细说明，如果您未设置Opportunity规则，您将只看到Lead/Contact数据，而没有与其关联的Opportunity。 如果您没有为潜在客户/联系人设置规则，则情况也是如此 — 您只会看到没有关联的潜在客户/联系人的Opportunity。

完成后，单击 [!UICONTROL Save] 首先，对所有内容进行复查，然后单击 [!UICONTROL Save and Process]. 请记住，在保存并处理设置后的七天内，您将无法编辑设置，如 [!DNL Marketo Measure] 正在重新格式化您的数据。

**如何保存生成的报表？**

您无法直接在用户界面中保存生成的报表。 但是， [!DNL Marketo Measure] 将区段名称保存在URL中，以便您可以通过为页面添加书签来保留每个报表的记录。
