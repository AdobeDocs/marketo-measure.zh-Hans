---
description: 面向Marketo Measure用户的报表营销支出指南
title: 报告营销支出
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# 报告营销支出 {#report-marketing-spend}

## 营销支出表 {#marketing-spend-table}

“营销支出”表包含新列，用于显示每个渠道、子渠道和营销活动行的货币。 所有客户都会显示此新列，即使他们未启用多种货币也是如此。

此表包含多种不同的货币。 请参阅营销支出功能板，以单一货币计算任何渠道、子渠道或营销活动的总和。

## 上传成本 {#upload-costs}

当用户下载成本文件时，该文件还将包含一个新列，其中为每行指定货币。 唯一可接受的货币是那些已经设置并存储在CRM中的货币。 您需要知道货币的3个字母缩写代码(USD、CAD、JPY、EUR)，如果上传的文件使用的货币无法识别，则文件上传失败。

## 广告集成成本 {#costs-from-ad-integrations}

当[!DNL Marketo Measure]从AdWords、Bing、Facebook或Doubleclick等连接平台导入成本时，我们也会使用报告的货币。 货币在“营销支出”表中显示时，与“渠道”、“子渠道”和“营销活动”一起显示。

如果广告提供商的货币与从CRM提取的货币不匹配，您可能会在[!DNL Marketo Measure Discover]中看到“混合货币”错误。 要解决此问题，CRM管理员必须添加未知货币的转换。

## 迁移到已转化的营销支出 {#migrate-to-converted-marketing-spend}

由于营销支出历来只使用单一（美元）货币，因此需要执行少量工作才能将所有报告支出更改为新货币。 即使您的帐户未启用多种货币，但是如果您使用美元以外的单一公司货币，则应当进行此迁移。

1. 将当前支出文件下载到CSV
1. 货币列显示“[!UICONTROL USD]”为假定货币。 您可以手动替换所有出现的“[!UICONTROL USD]”，或使用“查找+替换”将所有“[!UICONTROL USD]”实例更改为您自己的公司货币，如“[!UICONTROL EUR]”或“[!UICONTROL GBP]”。
1. 保存文件，然后将其上载回[!DNL Marketo Measure]。
1. 现在，您报告的所有成本都将显示为新货币。
