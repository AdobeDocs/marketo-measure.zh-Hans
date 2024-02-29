---
unique-page-id: 18874554
description: 接触点生成和映射 —  [!DNL Marketo Measure]
title: 接触点生成和映射
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# 接触点生成和映射 {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] 归因故事取决于两个过程：

* 接触点生成，这将创建表示个人与您的营销和销售工作的互动的接触点
* 接触点映射，将接触点归因于相应的渠道和子渠道

为了让您充分利用 [!DNL Marketo Measure]，您应该使用 [!DNL Marketo Measure] 代表根据贵组织的需要自定义这两个流程。

接触点生成方法

接触点生成过程回答了“如何 [!DNL Marketo Measure] 会知道这件事发生了吗？” 根据您的功能集和潜在客户可以进行的交互类型，最多有三种方法 [!DNL Marketo Measure] 可以了解某个交互并创建一个接触点来表示它。

>[!IMPORTANT]
>
>[!DNL Marketo Measure] 每个会话只生成一个接触点。 如果填写了多个表单，则仅捕获第一个表单填写。

| **交互类型** | **示例** | **接触点生成方法** |
|---|---|---|
| 在线，在您的网站上 | 表单填写 | [!DNL Marketo Measure] JavaScript |
| 脱机；不在您的网站上联机 | 商展；内容整合合作伙伴提供参与您内容的潜在客户列表 | CRM Campaign会员资格已同步到 [!DNL Marketo Measure]，方法是直接在促销活动中设置Campaign同步类型，或在的“促销活动”页面上设置规则 [!DNL Marketo Measure] |
| 销售活动 | 按SDR出站调用 | CRM活动（任务或事件）记录已同步到 [!DNL Marketo Measure]，通过 [!UICONTROL Activities] 页面位置 [!DNL Marketo Measure] |

接触点映射方法

接触点映射流程回答以下问题：“创建此接触点后，如何 [!DNL Marketo Measure] 知道它属于哪个渠道和哪个子渠道吗？” 接触点的生成方法各有自己的接触点映射方法。

| **交互类型** | **生成方法** | **映射方法** |
|---|---|---|
| 在线，在您的网站上 | [!DNL Marketo Measure] JavaScript | 通过 [!DNL Online Channels] 页面位置 [!DNL Marketo Measure]，通过引用UTM值、登陆页面和引荐页面信息 |
| 离线；在线，不在您的网站上 | CRM Campaign成员资格同步 | 通过 [!UICONTROL Offline Channels] 页面位置 [!DNL Marketo Measure]，通过引用营销活动类型 |
| 销售活动 | CRM活动同步 | 通过 [!UICONTROL Online Channels] 页面位置 [!DNL Marketo Measure]，方法是：引用上分配的促销活动名称 [!UICONTROL Activities] 页面 |

>[!MORELIKETHIS]
>
>* [将在线接触点映射到 [!DNL Marketo Measure] 渠道/子渠道](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [从SFDC内同步CRM营销活动](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [正在从内部同步CRM营销活动 [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [将CRM营销活动映射到 [!DNL Marketo Measure] 渠道/子渠道](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [从销售活动创建接触点](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [活动常见问题解答和将活动接触点映射到渠道/子渠道](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

