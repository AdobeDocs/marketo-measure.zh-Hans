---
description: 对Marketo Measure用户使用自定义收入额字段指南
title: 使用自定义收入金额字段
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
feature: Custom Revenue Amount
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 2%

---

# 使用自定义收入金额字段 {#using-a-custom-revenue-amount-field}

默认情况下，采购员归因接触点将从以下两个字段之一提取机会金额：

* 金额(SFDC默认)
* [!DNL Marketo Measure]机会金额（自定义）

如果您在您的Opportunities中使用自定义Amount字段，我们将需要配置工作流以计算Buyer Touchpoint收入。 这需要进一步了解[!DNL Salesforce]，因此可能需要SFDC管理员的帮助。

首先，我们需要以下信息：

* 金额字段的API名称

从这里，我们将开始创建工作流。

## 在Salesforce Lightning中创建工作流 {#create-the-workflow-in-salesforce-lightning}

以下步骤适用于Salesforce Lightning用户。 如果您仍使用Salesforce Classic，则下面的步骤[将列出](#create-the-workflow-in-salesforce-classic)。

1. 从“设置”中，在快速查找框中键入“流”，然后选择&#x200B;**[!UICONTROL Flows]**&#x200B;以启动流生成器。 从右侧面板中单击&#x200B;**[!UICONTROL New Flow]**&#x200B;按钮。

   ![1. 在“设置”中，在“快速查找”框中键入“Flows”，然后选择](assets/custom-amount-1.png)

1. 选择&#x200B;**[!UICONTROL Record-Triggered Flow]**&#x200B;并单击右下角的&#x200B;**[!UICONTROL Create]**。

   ![1. 选择记录触发的流量并单击底部的“创建”](assets/custom-amount-10.png)

1. 在“配置开始”窗口中，选择Opportunity对象。 从[!UICONTROL Configure Trigger]部分中，选择&#x200B;**[!UICONTROL A record is created or updated]**。

   ![1. 在“配置开始”窗口中，选择Opportunity对象。 从](assets/custom-amount-11.png)

1. 在设置进入条件部分的[!UICONTROL Condition Requirements]下，选择&#x200B;**[!UICONTROL Custom Condition Logic Is Met]**。
   * 从搜索字段中，选择您的自定义金额字段。
   * 将运算符设置为&#x200B;**Is Null**，将值设置为&#x200B;**[!UICONTROL False]**。
   * 将评估条件设置为&#x200B;**[!UICONTROL Every time a record is updated and meets the condition requirements]**。

   ![将评估标准设置为“每次更新记录时”](assets/custom-amount-12.png)

1. 在“优化流量”部分下，选择&#x200B;**[!UICONTROL Fast Field Updates]**。 单击右下方的&#x200B;**[!UICONTROL Done]**。

   ![1. 在“优化流量”部分下，选择快速字段](assets/custom-amount-13.png)

1. 要添加该元素，请单击加号(+)图标并选择&#x200B;**[!UICONTROL Update Triggering Record]**。

   ![1. 要添加该元素，请单击加号(+)图标并选择](assets/custom-amount-14.png)

1. 在“新建更新记录”窗口中，输入以下内容：

   * 输入标签 — 将自动生成API名称
   * 在“如何查找记录以更新并设置其值”下，选择&#x200B;**[!UICONTROL Use the opportunity record that triggered the flow]**。
   * 在“[!UICONTROL Set Filter Conditions]”部分中，选择&#x200B;**[!UICONTROL Always Update Record]**&#x200B;作为更新记录的条件要求。
   * 在“[!UICONTROL Set Field Values for the Campaign Record]”的“从”字段中，选择Marketo Measure Opportunity Amount和“从”值。 然后选择您的自定义金额字段。
   * 单击 **[!UICONTROL Done]**。

   ![单击“完成”。](assets/custom-amount-15.png)

1. 单击&#x200B;**[!UICONTROL Save]**。 此时会出现一个弹出窗口。 在保存流量窗口中键入“流量标签”（将自动生成流量API名称）。 再次单击&#x200B;**[!UICONTROL Save]**。

   ![1. 单击“保存”。 此时会出现一个弹出窗口。 在](assets/custom-amount-2.png)中键入“流量标签”

1. 单击&#x200B;**[!UICONTROL Activate]**&#x200B;按钮以激活流。

   ![1. 单击“激活”按钮以激活流。](assets/custom-amount-3.png)

## 在Salesforce Classic中创建工作流 {#create-the-workflow-in-salesforce-classic}

以下步骤适用于Salesforce Classic用户。 如果您已切换到Salesforce Lightning，则可以在上面[找到这些步骤](#create-the-workflow-in-salesforce-lightning)。

1. 导航到&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**。

   ![1. 导航到设置创建工作流和批准](assets/custom-amount-4.png)

1. 选择&#x200B;**[!UICONTROL New Rule]**，将对象设置为“Opportunity”，然后单击&#x200B;**[!UICONTROL Next]**。

   ![1. 选择新规则，将对象设置为“Opportunity”，然后单击](assets/custom-amount-5.png)

   ![1. 选择新规则，将对象设置为“Opportunity”，然后单击](assets/custom-amount-6.png)

1. 配置工作流。 将规则名称设置为“更新[!DNL Marketo Measure]机会金额”。 将评估标准设置为“已创建，并且每次都进行编辑”。 对于规则条件，请选择您的自定义金额字段，然后选择运算符[!UICONTROL as "Not Equal To"]，并将“值”字段留空。

   ![1. 配置工作流。 将规则名称设置为“更新Marketo](assets/custom-amount-7.png)”

1. 添加工作流操作。 将此选取列表设置为“[!UICONTROL New Field Update]”。
   ![1. 添加工作流操作。 将此选取列表设置为“新建字段](assets/custom-amount-8.png)”

1. 您将在此处填写字段信息。 在“名称”字段中，我们建议使用此命名：“[!DNL Marketo Measure] Opp数量”。 “唯一名称”将根据“名称”字段自动填充。 在“要更新的字段”选取列表中，选择“[!DNL Marketo Measure]机会金额”。 选择字段后，选中“字段更改后重新评估工作流规则”框。 在“指定新字段值”中，选择“使用公式设置新值”。 在空框中，放置自定义金额字段的API名称。 单击 **[!UICONTROL Save]**。

   ![1. 您将在此处填写字段信息。 在“名称”字段中，](assets/custom-amount-9.png)

1. 系统会将您带回工作流的汇总页面，请确保“激活”，此时您将没有发现问题。 要激活，请单击新工作流旁边的&#x200B;**[!UICONTROL Edit]**，然后单击&#x200B;**[!UICONTROL Activate]**。

   完成这些步骤后，需要更新机会以触发工作流以使用[!UICONTROL custom opportunity]字段中的新值。

   这可以通过在SFDC中通过Data Loader运行您的销售机会来实现。 在[本文](/help/channel-tracking-and-setup/using-data-loader-to-update-marketo-measure-custom-amount-field.md)中查找有关使用数据加载器的详细信息。

如果过程中有任何问题，请随时联系Adobe客户团队（您的客户经理）或[[!DNL Marketo] 支持团队](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}。
