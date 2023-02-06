---
unique-page-id: 18874554
description: 接触点生成和映射 —  [!DNL Marketo Measure]  — 产品文档
title: 接触点生成和映射
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# 接触点生成和映射 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] 归因故事取决于两个流程：

* 接触点生成，它创建的接触点代表某人与您的营销和销售工作的互动
* 接触点映射，将接触点归因到相应的渠道和子渠道

为了让你 [!DNL Marketo Measure]您应该 [!DNL Marketo Measure] rep可自定义这两个流程以满足贵组织的需求。

接触点生成方法

接触点生成过程回答了“如何 [!DNL Marketo Measure] 会知道这发生了吗？” 根据您的功能集以及潜在客户可以进行的交互类型，最多有三种方式 [!DNL Marketo Measure] 可以选取交互并创建一个接触点来表示它。

| **交互类型** | **示例** | **接触点生成方法** |
|---|---|---|
| 在线，在您的网站上 | 表单填充 | [!DNL Marketo Measure] JavaScript |
| 离线；不在您的网站上在线 | 展会；内容整合合作伙伴提供一个参与您内容的潜在客户列表 | CRM Campaign会员资格已同步到 [!DNL Marketo Measure]，方法是直接在营销活动中设置营销活动同步类型，或在 [!DNL Marketo Measure] |
| 销售活动 | SDR的叫客呼叫 | CRM活动（任务或事件）记录已同步到 [!DNL Marketo Measure]，通过逻辑 [!UICONTROL Activities] 页面 [!DNL Marketo Measure] |

接触点映射方法

接触点映射流程回答了以下问题：“创建此接触点后，如何 [!DNL Marketo Measure] 想知道它属于哪个渠道和子渠道？” 每个接触点生成方法都有其自己的接触点映射方法。

| **交互类型** | **生成方法** | **映射方法** |
|---|---|---|
| 在线，在您的网站上 | [!DNL Marketo Measure] JavaScript | 通过 [!DNL Online Channels] 页面 [!DNL Marketo Measure]，方法是引用UTM值、登陆页面和引荐页面信息 |
| 离线；在线，不在您的网站上 | CRM Campaign会员资格同步 | 通过 [!UICONTROL Offline Channels] 页面 [!DNL Marketo Measure]，通过引用Campaign类型 |
| 销售活动 | CRM活动同步 | 通过 [!UICONTROL Online Channels] 页面 [!DNL Marketo Measure]，方法是引用 [!UICONTROL Activities] 页面 |

>[!MORELIKETHIS]
>
>* [将在线接触点映射到 [!DNL Marketo Measure] 渠道/子渠道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [在SFDC内同步CRM促销活动](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [从内同步CRM促销活动 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [将CRM促销活动映射到 [!DNL Marketo Measure] 渠道/子渠道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [从销售活动创建接触点](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [活动常见问题解答和将活动接触点映射到渠道/子渠道](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)


