---
description: 了解从 [!DNL Marketo Measure] 分层订阅迁移到 [!DNL Marketo Measure] Ultimate时的迁移过程。
title: 从层迁移到 [!DNL Marketo Measure] 旗舰版
feature: Integration, Tracking, Attribution
source-git-commit: d62eb377a6abe8a01de7ad2aba34b85fb74ad461
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 1%

---

# 从第1-2层迁移到[!DNL Marketo Measure]旗舰版 {#migration-from-tier-to-marketo-measure-ultimate}

本文概述了用户从1级或2级订阅迁移到[!DNL Marketo Measure] Ultimate的迁移过程。

>[!IMPORTANT]
>
>请记住，在迁移完成之前保留现有的分层实例。

## 数据收集 {#data-collection}

### 网络流量数据 {#web-traffic-data}

* JavaScript部署无需任何更改。

* 在新的Ultimate实例中启用域。

* 如果需要，请提交工单以迁移和重新处理历史Web数据。

* 广告集成保持不变，但请记得在Ultimate中重新连接它们。 在执行此操作之前，请确保断开您在Tier租户中的广告帐户。

>[!NOTE]
>
>将不会导入历史广告成本数据。 我们仅在重新连接广告帐户后导入今后的广告成本数据。

### 企业数据连接 {#enterprise-data-connection}

在AEP中重新实施所有源数据连接，包括CRM和Marketo Engage连接。

## 数据转换 {#data-transformation}

* Account-Based Marketing功能（包括商机到帐户的匹配和预测参与度分数）在Ultimate中不可用。

   * 但是，您可以通过AEP导入商机帐户匹配结果，并在平台中使用这些结果。

* 在Ultimate中，由于没有直接CRM连接，因此会推断出CRM历史阶段过渡，而不是直接读取。

   * 我们读取机会记录和时间戳并查看当前阶段，然后推断历史阶段。

## 报告 {#reporting}

* Ultimate不会将数据推送回CRM。

   * 如果需要将数据推送回CRM，则需要自定义ETL管道以将数据从Marketo MeasureSnowflake提取到CRM。 您必须在CRM中设置自定义数据模型。

* 在添加了Attribution AI功能板的情况下，所有Discover功能板与分层解决方案中的功能板相同。
