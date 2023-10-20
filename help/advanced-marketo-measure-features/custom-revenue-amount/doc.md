---
description: 使用自定义收入金额字段 —  [!DNL Marketo Measure]  — 产品文档
title: 使用自定义收入金额字段
hide: true
hidefromtoc: true
feature: Custom Revenue Amount
source-git-commit: 2d2fe74998abd853f6592c5e65edfe2ce39d7ce6
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# 使用自定义收入金额字段 {#using-a-custom-revenue-amount-field}

默认情况下，采购员归因接触点将从以下两个字段之一提取机会金额：

* 金额（SFDC默认值）
* [!DNL Marketo Measure] 机会金额（自定义）

如果您在您的Opportunities上使用自定义Amount字段，我们将需要配置工作流以计算Buyer Touchpoint收入。 这需要更深入的了解 [!DNL Salesforce]，因此可能需要SFDC管理员的帮助。

首先，我们需要以下信息：

* 金额字段的API名称

从这里，我们将开始创建工作流。

## 在Salesforce Lightning中创建工作流 {#create-the-workflow-in-salesforce-lightning}

以下步骤适用于Salesforce Lightning用户。 如果您仍使用Salesforce Classic，这些步骤 [如下所示](#create-the-workflow-in-salesforce-classic).

1. 在“设置”中，在“快速查找”框中键入“流”，然后选择 **流** 以启动流量生成器。 从右侧面板中，单击 **新流量** 按钮。

   ![](assets/using-a-custom-revenue-amount-field-1.png)

1. 选择 **记录触发的流量** 然后单击 **创建** 按钮。

   ![](assets/using-a-custom-revenue-amount-field-2.png)

1. 在“配置开始”窗口中，选择Opportunity对象。 从配置触发器部分，选择 **记录已创建或更新**.

   ![](assets/using-a-custom-revenue-amount-field-3.png)

1. 在“设置录入条件”部分的“条件要求”下，选择 **满足自定义条件逻辑**.
   * 从搜索字段中，选择您的自定义金额字段。
   * 将运算符设置为 **为空**，其值为 **假**.
   * 将评估标准设置为 **每次更新记录并满足条件要求时**.

   ![](assets/using-a-custom-revenue-amount-field-4.png)

1. 在“优化流量”部分下，选择 **快速字段更新**. 单击 **完成**.

   ![](assets/using-a-custom-revenue-amount-field-5.png)

1. 要添加元素，请单击加号(+)图标并选择 **更新触发记录**.

   ![](assets/using-a-custom-revenue-amount-field-6.png)

1. 在“新建更新记录”窗口中，输入以下内容：

   * 输入标签 — 将自动生成API名称
   * 在“如何查找记录以更新并设置其值”下，选择 **使用触发流的机会记录**.
   * 在“设置过滤条件”部分，选择 **始终更新记录** 作为更新记录的条件要求。
   * 在“Set Field Values for the Campaign Record”中，从字段选择Marketo Measure Opportunity Amount ，并设置您的自定义Amount字段的值。
   * 单击 **完成**.

   ![](assets/using-a-custom-revenue-amount-field-7.png)

1. 单击&#x200B;**保存**。此时会出现一个弹出窗口。 在保存流量窗口中键入“流量标签”（将自动生成流量API名称）。 单击 **保存** 再来一次。

   ![](assets/using-a-custom-revenue-amount-field-8.png)

1. 单击 **激活** 按钮以激活流。

   ![](assets/using-a-custom-revenue-amount-field-9.png)

## 在Salesforce Classic中创建工作流 {#create-the-workflow-in-salesforce-classic}

以下步骤适用于Salesforce Classic用户。 如果已切换到Salesforce Lightning，则这些步骤 [可在上找到](#create-the-workflow-in-salesforce-lightning).

1. 导航到 **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**.

   ![](assets/1.jpg)

1. 选择 **[!UICONTROL New Rule]**，将对象设置为“Opportunity” ，然后单击 **[!UICONTROL Next]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. 配置工作流。 将规则名称设置为“更新” [!DNL Marketo Measure] 机会金额。” 将评估标准设置为“已创建，并且每次都进行编辑”。 对于规则标准，选择您的自定义“金额”字段并选择运算符 [!UICONTROL as "Not Equal To"] 并将“Value”字段留空。

   ![](assets/4.jpg)

1. 添加工作流操作。 将此选取列表设置为&quot;[!UICONTROL New Field Update]“
   ![](assets/5.jpg)

1. 您将在此处填写字段信息。 在“名称”字段中，我们建议使用此命名：“[!DNL Marketo Measure] Opp金额。” “唯一名称”将根据“名称”字段自动填充。 在“要更新的字段”选取列表中，选择“[!DNL Marketo Measure] 机会金额。” 选择字段后，选中“字段更改后重新评估工作流规则”框。 在“指定新字段值”中，选择“使用公式设置新值”。 在空框中，放置自定义金额字段的API名称。 单击 **[!UICONTROL Save]**.

   ![](assets/6.png)

1. 您将会返回到工作流的汇总页面，请确保“激活”，这样您就没问题了。 要激活，请单击 **编辑** ，然后单击 **激活**.

   完成这些步骤后，需要更新机会以触发工作流以从中获取新值 [!UICONTROL custom opportunity] 字段。

   这可以通过在SFDC中通过Data Loader运行您的机会来实现。 有关在中使用数据加载器的详细信息，请参阅 [本文](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

如果在此过程中有任何问题，请随时联系Adobe客户团队（您的客户经理）或 [[!DNL Marketo] 支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
