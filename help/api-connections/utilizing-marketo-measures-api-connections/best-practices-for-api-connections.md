---
description: API连接的最佳实践 —  [!DNL Marketo Measure]
title: API连接的最佳实践
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# API连接的最佳实践 {#best-practices-for-api-connections}

## 概述 {#overview}

[!DNL Marketo Measure] 提供的API连接与 [!DNL Google AdWords]， [!DNL Microsoft Bing Ads]， [!DNL Facebook Ads]和LinkedIn。 这些API连接启用 [!DNL Marketo Measure] 从广告平台提取各种数据，然后在买方接触点数据中报告这些数据。 这些API连接的一个关键功能是，它们能够自动提取支出数据，为您和您的团队节省手动上传数据以进行ROI报告所需的时间和精力。 对于以下情况，不必设置这些API连接： [!DNL Marketo Measure] 以跟踪这些渠道，但它们确实提供了可增强报表的有价值的细粒度详细信息。

此 [!DNL Marketo Measure] API连接是您帐户中非常宝贵的一个方面，我们的最佳实践建议将帮助您和您的团队最大程度地利用我们的连接。

## 最佳实践 {#best-practice}

无论您连接的是哪个广告平台，都必须牢记以下准则！

* 使用管理员进行连接
* 您可以为一个平台连接多个广告帐户
* 连接所有可能的广告帐户，以尽可能多地自动报告支出
* 如果可用，请始终实施跟踪模板。 该模板可确保即使广告帐户断开连接， [!DNL Marketo Measure] 仍然能够提取详细的广告详细信息

优化每个 [!DNL Marketo Measure] API，请遵循以下最佳实践。

**[!DNL Facebook]**：使用自动标记连接

在启用自动标记之前，请将广告历史记录导出到csv。 启用自动标记将重置由标记的所有广告的转化历史记录和社交证明 [!DNL Marketo Measure].

按照我们的最佳实践建议， [!DNL Marketo Measure] [!DNL Facebook] API将能够：

* 全部自动标记 [!DNL Facebook] 具有必要内容的广告 [!DNL Marketo Measure] 参数 `_bf ={creative}`
* 下载所有活动的广告成本信息 [!DNL Facebook] 广告

>[!NOTE]
>
>没有跟踪模板 [!DNL Facebook]，则API依赖自动标记(_bf)参数来收集广告详细信息。

**AdWords**：在帐户级别实施跟踪模板并启用自动标记

[!DNL Marketo Measure] 建议使用帐户级别、营销活动级别或广告组级别跟踪模板，因为它允许为所有广告添加和减除参数，而无广告历史记录中断或删除的风险。

按照我们的最佳实践建议， [!DNL Marketo Measure] AdWords API将能够：

* 使用自动标记所有AdWords广告 [!DNL Marketo Measure] 参数 `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* 下载所有有效AdWords广告的广告成本信息

**Bing**：在帐户级别实施跟踪模板并启用自动标记

设置时，不会出现丢失广告历史记录的风险 [!DNL Bing] API连接，不同于我们的一些其他API连接。

按照我们的最佳实践建议， [!DNL Marketo Measure] Bing API将能够：
* 使用以下参数自动标记所有Bing Ads `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* 下载所有活动Bing广告的广告成本信息

**linkedIn**：使用自动标记连接

启用自动标记可重新创建共享并将其放入新的创意中，旧的创意将存档。

按照我们的最佳实践建议， [!DNL Marketo Measure] linkedIn API将能够：

* 自动标记所有属于广告类型“赞助内容”的LinkedIn广告，如有必要 [!DNL Marketo Measure] 参数_bl={creativeId}. 此参数拉入创作ID，以允许 [!DNL Marketo Measure] 解决营销活动和创意信息。
* 下载所有活跃和受支持的广告成本信息 [!DNL LinkedIn] 广告

>[!NOTE]
>
>没有跟踪模板 [!DNL LinkedIn]，则API依赖自动标记(_bl)参数来收集所有可能的广告详细信息。

## 维护的最佳实践 {#best-practice-for-maintenance}

虽然按照我们的最佳做法将保护您在断开连接时不会丢失数据，但我们仍建议您定期检查您的连接，如果可能，每月检查一次。 这是对的简单直观检查 [!UICONTROL Connections] 部分在您的 [!DNL Marketo Measure] 应用程序以确保没有红色钥匙图标出现，表示帐户已断开连接。

当API连接的帐户断开连接时， [!DNL Marketo Measure] 无法提取支出数据或标记新广告。 因此，我们始终建议尽可能实施跟踪模板。 该模板可确保即使广告帐户断开连接， [!DNL Marketo Measure] 仍然能够标记广告并提取精细的广告详细信息。 重新连接后，支出数据将回填，并且您付费渠道报表的中断最小。

断开连接和重新授权的原因包括……

* 更改已连接人员帐户的密码
* 此人已不在公司
* API更新

如果您的团队经历了以上任何场景，请检查您在中的API连接 [!DNL Marketo Measure] 应用程序，确保他们无需重新授权。

>[!MORELIKETHIS]
>
>* [集成式广告平台(API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [竞价管理工具如何影响 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API参数说明](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [facebook API概述](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] 集成概述](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [AdWords集成概述](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [重新授权连接的API帐户](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
