---
description: API连接最佳实践 —  [!DNL Marketo Measure]  — 产品文档
title: API连接最佳实践
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 0%

---

# API连接最佳实践 {#best-practices-for-api-connections}

## 概述 {#overview}

[!DNL Marketo Measure] 提供与 [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads]和LinkedIn。 这些API连接启用 [!DNL Marketo Measure] 从广告平台中提取各种数据，然后在购买者接触点数据中报告这些数据。 这些API连接的一个关键功能是它们能够自动提取支出数据，从而节省您和您的团队手动上传数据以实现ROI报表所花费的时间和精力。 对于 [!DNL Marketo Measure] 来跟踪这些渠道，但它们确实提供了可增强报表的有价值的详细信息。

的 [!DNL Marketo Measure] API连接是您帐户中非常宝贵的一个方面，我们的最佳实践建议将帮助您和您的团队最大限度地利用我们的连接。

## 最佳实践 {#best-practice}

无论您连接的广告平台如何，请牢记以下准则！

* 使用管理员连接
* 您可以为一个平台连接多个广告帐户
* 连接所有可能的广告帐户，以尽可能自动化您的支出报告
* 如果可用，请始终实施跟踪模板。 模板可确保即使广告帐户断开连接， [!DNL Marketo Measure] 仍然能够提取粒度广告详细信息

优化每个 [!DNL Marketo Measure] API，请遵循以下最佳实践。

**[!DNL Facebook]**:通过自动标记连接

在启用自动标记之前，请将您的广告历史记录导出到CSV。 启用自动标记将重置所有由标记的广告的转化历史记录和社交校样 [!DNL Marketo Measure].

通过遵循我们的最佳实践建议， [!DNL Marketo Measure] [!DNL Facebook] API将能够：

* 自动标记全部 [!DNL Facebook] 具有必要 [!DNL Marketo Measure] 参数 `_bf ={creative}`
* 在所有活动中下载广告成本信息 [!DNL Facebook] 广告

>[!NOTE]
>
>没有的跟踪模板 [!DNL Facebook]，则API会依赖自动标记(_bf)参数来收集广告详细信息。

**AdWords**:在帐户级别实施跟踪模板并启用自动标记

[!DNL Marketo Measure] 建议使用帐户级别、促销活动级别或广告组级别跟踪模板，因为它允许对所有广告添加和减除参数，而不会有广告历史记录中断或删除的风险。

通过遵循我们的最佳实践建议， [!DNL Marketo Measure] AdWords API将能够：

* 使用 [!DNL Marketo Measure] 参数 `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* 下载所有活动AdWords广告中的广告成本信息

**兵**:在帐户级别实施跟踪模板并启用自动标记

在设置 [!DNL Bing] API连接，与我们的其他一些API连接不同。

通过遵循我们的最佳实践建议， [!DNL Marketo Measure] Bing API将能够：
* 使用以下参数自动标记所有Bing Ads `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* 下载所有活动Bing广告中的广告成本信息

**linkedIn**:通过自动标记连接

启用自动标记会重新创建共享并将其放置到新的创作元素中，从而将旧的创作元素存档。

通过遵循我们的最佳实践建议， [!DNL Marketo Measure] linkedIn API将能够：

* 自动标记所有属于广告类型的LinkedIn广告，其中包含必要的赞助内容 [!DNL Marketo Measure] 参数_bl={creativeId}。 此参数可提取创作ID，以允许 [!DNL Marketo Measure] 以解析营销活动和创意信息。
* 下载所有活动和受支持的广告成本信息 [!DNL LinkedIn] 广告

>[!NOTE]
>
>没有的跟踪模板 [!DNL LinkedIn]，则API会依赖自动标记(_bl)参数来收集所有可能的广告详细信息。

## 维护最佳实践 {#best-practice-for-maintenance}

尽管遵循我们的最佳实践可在断开连接时保护您免受数据丢失的影响，但我们仍建议您定期（如果可能）每月审查您的连接。 这是对 [!UICONTROL Connections] 的 [!DNL Marketo Measure] 应用程序来确保不存在红色键图标，从而发出断开的帐户信号。

当连接的API帐户断开连接时， [!DNL Marketo Measure] 无法提取支出数据或标记新广告。 因此，我们始终建议尽可能实施跟踪模板。 模板可确保即使广告帐户断开连接， [!DNL Marketo Measure] 仍然能够标记广告并提取粒度广告详细信息。 重新连接后，支出数据将回填，并且对付费渠道报表的中断微乎其微。

断开连接和重新授权的原因包括……

* 对已连接的个人帐户更改密码
* 那人不再在公司了
* API的更新

如果您的团队经历过上述任何情况，请在 [!DNL Marketo Measure] 应用程序，以确保无需重新授权。

>[!MORELIKETHIS]
>
>* [集成广告平台(API)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [竞价管理工具如何影响 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API参数说明](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Facebook API概述](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] 集成概述](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [AdWords集成概述](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [重新授权连接的API帐户](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)

