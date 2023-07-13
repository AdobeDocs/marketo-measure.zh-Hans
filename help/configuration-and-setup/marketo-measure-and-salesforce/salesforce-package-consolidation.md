---
description: ‘[!DNL Salesforce] 包整合 —  [!DNL Marketo Measure]  — 产品文档'
title: ‘[!DNL Salesforce] 包整合
exl-id: f1bd5dcb-d021-4140-b6b9-cdb40e566c4b
source-git-commit: dd3795288b1d579b078a32c78c9f08fd67a5f0e1
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# [!DNL Salesforce] 包整合 {#salesforce-package-consolidation}

我们很高兴地宣布即将对Marketo Measure Salesforce包进行的更改。 为了增强用户体验并简化使用，我们将所有现有产品包整合到一个全面的产品包中。

## 包弃用 {#package-retirement}

作为此整合的结果，当前的V1 、 V2_EXT 、 V2_Security和所有报告包将在2023年8月之后停用。 如果已安装V2软件包，则必须将其更新为新的统一版本。

## 新的合并包 {#new-consolidated-package}

新的整合V2软件包结合了以前软件包的所有特性和功能，提供了改进的用户体验。 此更新的产品包实现了更高效的营销和销售业绩跟踪，并提供了对客户行为的更深入洞察。

我们新增了两个字段来增强您的报告功能：

* form_name：现在BT/BAT对象中提供了此字段，可让用户根据表单名称创建报表。
* user_touchpoint_id：此字段允许用户创建具有独特用户接触点计数的报表。

## 支持和过渡 {#support-and-transition}

我们理解，这一更改可能需要您做出调整，并且我们致力于在整个过程中为您提供支持。 我们的 [支持团队](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 随时解答任何问题，并帮助确保顺利过渡到新的整合包。

## 必需操作 {#retired-actions}

* 如果已安装V2软件包，则必须将其更新为新的统一版本。
* 如果您具有来自任何报告包的报告或功能板，则可以轻松地重新创建它们，而无需进行任何修改，因为使用的所有字段都存在于合并包中。
* 如果您的报表使用V2_EXT包中的字段，则可通过以下步骤在统一包中重新创建它们：
   * V2_EXT字段中的所有数据在接触点字段中均可用，因此您可以修改报表，通过在接触点位置添加过滤器来从相应的V2接触点字段中提取数据。
   * 使用Ad Content FT获取包含“外联”文本的所有潜在客户的示例报告。
      * V2_EXT查询：
         * bizible2_ext__Ad_Content_FT__c包含外联

![](assets/package-consolidation-1.png)

* 统一包中的相应查询：
   * bizible2__Touchpoint_Position__c包含FT和
   * bizible2__Ad_Content__c包含外联

![](assets/salesforce-package-consolidation-2.png)

## 常见问题解答 {#faq}

**合并的包是否会与我现有包中的字段冲突？**

在安装统一包之前，您不需要卸载包。 字段中没有冲突，因为它们将位于不同的命名空间中。

**如何从当前包回填数据？**

您可以提交票证 [支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 用于回填和重新处理BT/BAT数据以填写接触点ID和表单ID字段。

**V1和V2_EXT包中的字段是否可以在整合的包中使用？**

是. 整合的包将包含V1中的相同字段，并通过接触点字段进一步按对象和V2_EXT字段进行划分。

**能否在统一包中重新创建使用V2_EXT字段的报表？**

是. 请按照 [必需操作](#retired-actions) 部分。
