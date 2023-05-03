---
description: '"[!DNL Salesforce] 资源包整合 —  [!DNL Marketo Measure]  — 产品文档”'
title: '"[!DNL Salesforce] 资源包整合”'
hide: true
hidefromtoc: true
source-git-commit: 502a08b9a670c0b9a997a0fbb238a4db865f79d2
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---

# [!DNL Salesforce] 资源包整合 {#salesforce-package-consolidation}

我们很高兴地宣布即将更改Marketo Measure Salesforce包。 为了增强用户体验并简化使用过程，我们将所有现有资源包整合到一个全面的资源包中。

## 包报废 {#package-retirement}

由于此整合，当前的V1、V2_EXT、V2_Security和所有报表包将在2023年8月之后停用。 如果您已安装V2包，则必须将其更新到新的整合版本。

## 新的整合包 {#new-consolidated-package}

新的整合的V2包整合了先前包的所有特性和功能，从而提供了更好的用户体验。 此更新的产品包支持更高效的营销和销售绩效跟踪，并允许对客户行为进行更深入的分析。

## 支持和过渡 {#support-and-transition}

我们知道，这项变更可能需要做出调整，我们承诺在整个过程中为您提供支持。 我们的 [支持团队](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 可随时回答任何问题，并协助确保顺利过渡到新的整合包。

## 必需操作 {#retired-actions}

* 如果您已安装V2包，则必须将其更新到新的整合版本。
* 如果您有来自任何报表包的报表或功能板，则无需进行任何修改即可轻松重新创建报表或功能板，因为统一包中已使用的所有字段都存在。
* 如果您有使用V2_EXT包中字段的报表，则可通过以下步骤在整合的包中重新创建它们：
   * V2_EXT字段中的所有数据在接触点字段中均可用，因此您可以修改报表以通过在接触点位置添加过滤器，从相应的V2接触点字段获取数据。
   * 示例报表使用包含“外联”文本的广告内容FT获取所有潜在客户。
      * V2_EXT查询：
         * bizible2_ext__Ad_Content_FT__c包含Eveloging

![](assets/salesforce-package-consolidation-1.png)

* 统一资源包中的相应查询：
   * bizible2__Touchpoint_Position__c包含FT AND
   * bizible2__Ad_Content__c包含外联

![](assets/salesforce-package-consolidation-2.png)

## 常见问题解答 {#faq}

**整合包是否与我现有包中的字段冲突？**

在安装整合的包之前，您无需卸载包。 字段中不会发生冲突，因为它们将位于不同的命名空间中。

**如何回填当前包中的数据？**

您可以提交票证 [支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 用于回填和重新处理BT/BAT数据，以填充接触点ID和表单ID字段。

**V1和V2_EXT包中的字段是否可在统一包中使用？**

是. 统一包将包含V1中的相同字段，以及通过接触点字段按对象和V2_EXT字段进行进一步划分。

**能否在整合的包中重新创建使用V2_EXT字段的报表？**

是. 请按照 [必需操作](#retired-actions) 部分。
