---
unique-page-id: 27656737
description: 报表营销支出 —  [!DNL Marketo Measure]  — 产品文档
title: 报表营销支出
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# 报表营销支出 {#report-marketing-spend}

## 营销支出表 {#marketing-spend-table}

营销支出表现在将包含一个新列，用于显示每个“渠道”、“子渠道”和“促销活动”行的货币。 此新列将显示给所有客户，即使他们未启用多货币。

现在，表格将包含不同货币的组合。 如果您需要以单一货币获得任意渠道、子渠道或促销活动的总和，请参阅营销支出功能板。

## 上传成本 {#upload-costs}

当用户下载成本文件时，文件还将包含一个新列，其中每行使用货币。 唯一可接受的货币是已在CRM中设置和存储的货币。 您需要知道您所用货币的缩写代码（即USD、CAD、JPY、EUR），如果上传的文件包含无法识别的货币，则文件上传将失败。

## 广告集成成本 {#costs-from-ad-integrations}

When [!DNL Marketo Measure] 从连接的平台(如AdWords、Bing、Facebook或Doubleclick)导入成本，我们也会使用报告的货币。 当货币显示在“营销支出”表中时，该货币将与“渠道”、“子渠道”和“营销活动”一起显示。

如果来自广告提供商的货币与从CRM提取的货币不匹配，您可能会在 [!DNL Marketo Measure Discover] 因为我们无法对该货币进行换算。 要修复此问题，您的CRM管理员需要为未知货币添加转化。

## 迁移至转化的营销支出 {#migrate-to-converted-marketing-spend}

由于我们的营销支出过去仅使用单一（美元）货币，因此需要少量工作才能将所有报告的支出更改为新货币。 即使您的帐户未启用“多种货币”，如果您使用的是美元以外的单一公司货币，您也需要进行此迁移。

1. 将当前支出文件下载到CSV
1. 货币列将显示“[!UICONTROL USD]”作为假定货币。 您可以手动替换出现“[!UICONTROL USD]或使用Find+Replace更改所有“[!UICONTROL USD]“实例”，例如“[!UICONTROL EUR]&quot;或&quot;[!UICONTROL GBP]“ ”。
1. 保存文件，然后将其上传回 [!DNL Marketo Measure].
1. 现在，您报告的所有成本都将显示为新货币。
