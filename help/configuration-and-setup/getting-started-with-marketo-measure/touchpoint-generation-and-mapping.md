---
unique-page-id: 18874554
description: 接触点生成和映射 —  [!DNL Marketo Measure]
title: 接触点生成和映射
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# 接触点生成和映射 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure]归因故事依赖于两个流程：

* 接触点生成，这将创建表示个人与您的营销和销售工作的互动的接触点
* 接触点映射，将接触点归因于相应的渠道和子渠道

为了充分利用[!DNL Marketo Measure]，您应该与您的[!DNL Marketo Measure]代表合作，以自定义这两个进程以满足您组织的需求。

接触点生成方法

接触点生成过程回答了以下问题：“如何让[!DNL Marketo Measure]知道发生了这种情况？” 根据您的功能集和潜在客户可以进行的交互类型，[!DNL Marketo Measure]最多有三种方式可以选取交互并创建接触点来表示它。

>[!IMPORTANT]
>
>[!DNL Marketo Measure]在每个会话中仅生成一个接触点。 如果填写了多个表单，则仅捕获第一个表单填写。

| **交互类型** | **示例** | **接触点生成方法** |
|---|---|---|
| 在线，在您的网站上 | 表单填写 | [!DNL Marketo Measure] JavaScript |
| 脱机；不在您的网站上联机 | 商展；内容整合合作伙伴提供参与您内容的潜在客户列表 | CRM Campaign成员资格已同步到[!DNL Marketo Measure]，方法是直接在营销活动中设置Campaign同步类型，或在[!DNL Marketo Measure]的“营销活动”页面上设置规则 |
| 销售活动 | 按SDR出站调用 | CRM活动（任务或事件）记录已通过[!DNL Marketo Measure]中[!UICONTROL Activities]页面上的逻辑同步到[!DNL Marketo Measure] |

接触点映射方法

接触点映射流程回答以下问题：“创建此接触点后，[!DNL Marketo Measure]如何知道它属于哪个渠道和子渠道？” 接触点的生成方法各有自己的接触点映射方法。

| **交互类型** | **生成方法** | **映射方法** |
|---|---|---|
| 在线，在您的网站上 | [!DNL Marketo Measure] JavaScript | 通过引用UTM值、登陆页面和引荐页面信息，在[!DNL Online Channels]中通过[!DNL Marketo Measure]页面 |
| 离线；在线，不在您的网站上 | CRM Campaign成员资格同步 | 通过[!UICONTROL Offline Channels]中的[!DNL Marketo Measure]页面，通过引用营销活动类型 |
| 销售活动 | CRM活动同步 | 通过[!UICONTROL Online Channels]中的[!DNL Marketo Measure]页面，通过引用[!UICONTROL Activities]页面上分配的营销活动名称 |

>[!MORELIKETHIS]
>
>* [将在线接触点映射到 [!DNL Marketo Measure] 渠道/子渠道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [从SFDC同步CRM营销活动](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [正在从 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)内同步CRM营销活动
>* [将CRM营销活动映射到 [!DNL Marketo Measure] 渠道/子渠道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [从销售活动创建接触点](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [活动常见问题解答和将活动接触点映射到渠道/子渠道](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

