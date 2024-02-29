---
unique-page-id: 27656737
description: 报表营销支出 —  [!DNL Marketo Measure]
title: 报告营销支出
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# 报告营销支出 {#report-marketing-spend}

## 营销支出表 {#marketing-spend-table}

“营销支出”表现在将包含一个新列，以显示每个渠道、子渠道和营销活动行的货币。 此新列将为所有客户显示，即使他们未启用多种货币。

该表现在将包含多种不同的货币。 如果您需要以单一货币获取任何渠道、子渠道或营销活动的总和，请参阅营销支出仪表板。

## 上传成本 {#upload-costs}

当用户下载成本文件时，该文件还将包含一个新列，其中为每行指定货币。 唯一可接受的货币是那些已经设置并存储在CRM中的货币。 您需要知道您货币的3个字母缩写代码（即USD、CAD、JPY、EUR），如果上传的文件使用的是无法识别的货币，则文件上传将失败。

## 广告集成成本 {#costs-from-ad-integrations}

时间 [!DNL Marketo Measure] 从AdWords、Bing、Facebook或Doubleclick等连接平台导入成本，我们也会使用报告的货币。 在“营销支出”表中显示货币时，该货币将与“渠道”、“子渠道”和“营销活动”一起显示。

如果广告提供商的货币与从CRM提取的货币不匹配，您可能会在中看到“混合货币”错误 [!DNL Marketo Measure Discover] 因为我们无法对那个货币进行转换。 要解决此问题，您的CRM管理员需要添加未知货币的转换。

## 迁移到已转化的营销支出 {#migrate-to-converted-marketing-spend}

由于我们的营销支出历来仅以单一（美元）货币计价，因此需要执行少量工作才能将所有报告支出更改为新货币。 即使您的帐户未启用多种货币，但是如果您使用美元以外的单一公司货币，则您需要进行此迁移。

1. 将当前支出文件下载到CSV
1. “货币”列将显示“[!UICONTROL USD]”作为假定货币。 您可以手动替换&#39;&#39;的所有匹配项[!UICONTROL USD]”或使用“查找+替换”更改所有“[!UICONTROL USD]“实例到您自己的公司货币，如”[!UICONTROL EUR]”或“[!UICONTROL GBP]例如。
1. 保存文件，然后将其上传回 [!DNL Marketo Measure].
1. 现在，您报告的所有成本都将显示为新货币。
