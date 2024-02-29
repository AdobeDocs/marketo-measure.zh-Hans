---
unique-page-id: 18874793
description: 使用自定义收入金额字段 —  [!DNL Marketo Measure]
title: 使用自定义收入金额字段
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
feature: Custom Revenue Amount
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '590'
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

1. 在“设置”中，在“快速查找”框中键入“流”，然后选择 **[!UICONTROL Flows]** 以启动流量生成器。 从右侧面板中，单击 **[!UICONTROL New Flow]** 按钮。

   ![](assets/using-a-custom-revenue-amount-field-1.png)

1. 选择 **[!UICONTROL Record-Triggered Flow]** 并单击 **[!UICONTROL Create]** 在右下角。

   ![](assets/using-a-custom-revenue-amount-field-2.png)

1. 在“配置开始”窗口中，选择Opportunity对象。 从 [!UICONTROL Configure Trigger] 部分，选择 **[!UICONTROL A record is created or updated]**.

   ![](assets/using-a-custom-revenue-amount-field-3.png)

1. 在“设置录入条件”部分中，在 [!UICONTROL Condition Requirements]，选择 **[!UICONTROL Custom Condition Logic Is Met]**.
   * 从搜索字段中，选择您的自定义金额字段。
   * 将运算符设置为 **为空**，其值为 **[!UICONTROL False]**.
   * 将评估标准设置为 **[!UICONTROL Every time a record is updated and meets the condition requirements]**.

   ![](assets/using-a-custom-revenue-amount-field-4.png)

1. 在“优化流量”部分下，选择 **[!UICONTROL Fast Field Updates]**. 单击 **[!UICONTROL Done]** 在右下角。

   ![](assets/using-a-custom-revenue-amount-field-5.png)

1. 要添加元素，请单击加号(+)图标并选择 **[!UICONTROL Update Triggering Record]**.

   ![](assets/using-a-custom-revenue-amount-field-6.png)

1. 在“新建更新记录”窗口中，输入以下内容：

   * 输入标签 — 将自动生成API名称
   * 在“如何查找记录以更新并设置其值”下，选择 **[!UICONTROL Use the opportunity record that triggered the flow]**.
   * 在&quot;[!UICONTROL Set Filter Conditions]”部分，选择 **[!UICONTROL Always Update Record]** 作为更新记录的条件要求。
   * 在&quot;[!UICONTROL Set Field Values for the Campaign Record]，”从字段中，选择Marketo Measure Opportunity Amount和from value。 然后选择您的自定义金额字段。
   * 单击 **[!UICONTROL Done]**.

   ![](assets/using-a-custom-revenue-amount-field-7.png)

1. 单击 **[!UICONTROL Save]**. 此时会出现一个弹出窗口。 在保存流量窗口中键入“流量标签”（将自动生成流量API名称）。 单击 **[!UICONTROL Save]** 再来一次。

   ![](assets/using-a-custom-revenue-amount-field-8.png)

1. 单击 **[!UICONTROL Activate]** 按钮以激活流。

   ![](assets/using-a-custom-revenue-amount-field-9.png)

## 在Salesforce Classic中创建工作流 {#create-the-workflow-in-salesforce-classic}

以下步骤适用于Salesforce Classic用户。 如果已切换到Salesforce Lightning，则这些步骤 [可在上找到](#create-the-workflow-in-salesforce-lightning).

1. 导航到 **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**.

   ![](assets/using-a-custom-revenue-amount-field-10.png)

1. 选择 **[!UICONTROL New Rule]**，将对象设置为“Opportunity” ，然后单击 **[!UICONTROL Next]**.

   ![](assets/using-a-custom-revenue-amount-field-11.png)

   ![](assets/using-a-custom-revenue-amount-field-12.png)

1. 配置工作流。 将规则名称设置为“更新” [!DNL Marketo Measure] 机会金额。” 将评估标准设置为“已创建，并且每次都进行编辑”。 对于规则标准，选择您的自定义“金额”字段并选择运算符 [!UICONTROL as "Not Equal To"] 并将“Value”字段留空。

   ![](assets/using-a-custom-revenue-amount-field-13.png)

1. 添加工作流操作。 将此选取列表设置为&quot;[!UICONTROL New Field Update]“
   ![](assets/using-a-custom-revenue-amount-field-14.png)

1. 您将在此处填写字段信息。 在“名称”字段中，我们建议使用此命名：“[!DNL Marketo Measure] Opp金额。” “唯一名称”将根据“名称”字段自动填充。 在“要更新的字段”选取列表中，选择“[!DNL Marketo Measure] 机会金额。” 选择字段后，选中“字段更改后重新评估工作流规则”框。 在“指定新字段值”中，选择“使用公式设置新值”。 在空框中，放置自定义金额字段的API名称。 单击 **[!UICONTROL Save]**.

   ![](assets/using-a-custom-revenue-amount-field-15.png)

1. 系统会将您带回工作流的汇总页面，请确保“激活”，此时您将没有发现问题。 要激活，请单击 **[!UICONTROL Edit]** ，然后单击 **[!UICONTROL Activate]**.

   完成这些步骤后，需要更新机会以触发工作流以从中获取新值 [!UICONTROL custom opportunity] 字段。

   这可以通过在SFDC中通过Data Loader运行您的机会来实现。 查找有关在中使用数据加载器的详细信息 [本文](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

如果过程中有任何问题，请随时联系Adobe客户团队（您的客户经理）或 [[!DNL Marketo] 支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
