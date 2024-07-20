---
description: “[!DNL Salesforce]包合并 —  [!DNL Marketo Measure]”
title: “[!DNL Salesforce]包合并”
exl-id: ae559f5f-91bf-4504-9d5a-af47f95ca01f
feature: Salesforce
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# [!DNL Salesforce]包合并 {#salesforce-package-consolidation}

为了增强用户体验并简化使用，正在将现有包编译为单个综合包。

## 包弃用 {#package-retirement}

作为此合并的结果，当前的V1、V2_EXT、V2_Security和所有报告包将在2023年8月之后停用。 如果已安装V2软件包，则必须将其更新为新的统一版本。

## 新的合并包 {#new-consolidated-package}

新的整合V2软件包整合了以前软件包的所有特性和功能，提供了改进的用户体验。 此更新后的产品包能够更有效地跟踪营销和销售业绩，并且能够对客户行为进行更深入的洞察。

可使用两个新字段来增强报表功能：

* form_name：此字段现在可在BT/BAT对象中使用，它使用户能够根据表单名称创建报表。
* user_touchpoint_id：此字段允许用户创建具有独特用户接触点计数（Salesforce中为`bizible2__User_Touchpoint_V2__c`）的报告。

## 支持和过渡 {#support-and-transition}

[支持团队](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}可以回答任何问题并帮助确保顺利过渡到新的合并包。

## 必需操作 {#retired-actions}

* 如果已安装V2软件包，则必须将其更新为新的统一版本。
* 如果您具有来自任何报告包的报告或功能板，则可以轻松地重新创建它们，而无需进行任何修改，因为合并包中已存在所有字段。
* 如果您的报表使用V2_EXT包中的字段，则可通过以下步骤在统一包中重新创建它们：
   * V2_EXT字段中的所有数据在接触点字段中均可用，因此您可以通过在接触点位置添加过滤器来修改报表，以从相应的V2接触点字段中提取数据。
   * 使用包含“外联”文本的广告内容FT获取所有潜在客户的示例报告。
      * V2_EXT查询：
         * bizible2_ext__Ad_Content_FT__c包含外联

![](assets/package-consolidation-1.png)

* 合并包中的相应查询：
   * bizible2__Touchpoint_Position__c包含FT和
   * bizible2__Ad_Content__c包含外联

![](assets/salesforce-package-consolidation-2.png)

## 常见问题 {#faq}

**合并包是否会与我现有包中的字段冲突？**

在安装统一包之前，您不需要卸载包。 字段中不会出现冲突，因为它们位于不同的命名空间中。

**如何从当前包回填数据？**

您可以提交支持票证[](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}以回填和重新处理BT/BAT数据以填写接触点ID和表单ID字段。

**V1和V2_EXT包中的字段在统一包中是否可用？**

是的。 统一包在V1中包含相同的字段，这些字段通过接触点字段进一步按对象和V2_EXT字段进行划分。

**能否在合并包中重新创建使用V2_EXT字段的报告？**

是的。 按照[必需操作](#retired-actions)部分中的步骤操作。
