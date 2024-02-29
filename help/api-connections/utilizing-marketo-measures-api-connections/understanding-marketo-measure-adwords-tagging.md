---
unique-page-id: 18874678
description: 了解 [!DNL Marketo Measure] AdWords标记 —  [!DNL Marketo Measure]
title: 了解 [!DNL Marketo Measure] AdWords标记
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# 了解 [!DNL Marketo Measure] AdWords标记 {#understanding-marketo-measure-adwords-tagging}

要在非常精细的级别跟踪您的广告，广告目标URL必须是唯一的。 要完成此操作， [!DNL Marketo Measure] 自动标记会自动将跟踪参数添加到的Ad Destination URL [!DNL AdWords] 广告。 让我们看一下下面的示例。

以下URL不提供任何粒度数据：

* `http://example.com/landing-page?myParam=foo`

但是，同一URL将提供细粒度的数据，因为 [!DNL Marketo Measure] 参数：

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## 如何 [!DNL Marketo Measure] 自动标记功能 {#how-marketo-measure-auto-tagging-works}

**如果 [!DNL Marketo Measure] 查找跟踪模板：**

* [!DNL Marketo Measure] 会将其参数添加到跟踪模板。
* 如果在跟踪模板中找到第三方重定向，例如Kenshoo或Marin， [!DNL Marketo Measure] 不会采取任何操作。 相反，您必须 [添加 [!DNL Marketo Measure] 参数到您帐户中的第三方工具](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

但是，如果未找到跟踪模板， [!DNL Marketo Measure] 将：

* 扫描我们的所有Ad目标URL [!DNL Marketo Measure] 参数。
* 如果找到了，就马上行动。
* 如果未找到， [!DNL Marketo Measure] 会将其参数附加到广告目标URL的末尾。 对于新广告， [!DNL Marketo Measure] 在创建后的两个小时内，会将其参数附加到广告目标URL。
* 在启用自动标记之前，必须准备好跟踪模板，以便 [!DNL Marketo Measure] 可以附加到该页面并阻止广告历史记录重置。

[!DNL Marketo Measure] 建议使用帐户级别、营销活动级别或广告组级别跟踪模板，因为它允许为所有广告添加和减除参数，而无广告历史记录中断或删除的风险。

## 跟踪模板 {#tracking-templates}

如以下内容所述 [!DNL Google AdWords]，跟踪模板是用于访问登陆页面的URL。 收集到的跟踪信息将用于了解您的广告流量。 [单击此处](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} 以了解有关Google的更多信息。

[!DNL Marketo Measure] 建议使用帐户级别、促销活动级别或广告组级别跟踪模板，因为它允许为所有广告添加和减除参数，而不会造成广告历史记录中断或删除的风险。

有两种跟踪模板 [!DNL Marketo Measure] 建议使用。 使用以下内容确定适合您的版本：

* 如果您的所有广告URL都有一个“？” 在其中，使用此URL：

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* 如果您的任何广告URL都不包含“？” 在其中，使用此URL：

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## 在帐户级别设置跟踪模板 {#setting-up-a-tracking-template-at-the-account-level}

1. 登录 [!DNL Google AdWords] 帐户。

1. 单击 **[!UICONTROL All campaigns]** 然后 **[!UICONTROL Settings]** 在展开的窗口中。

   ![](assets/1.png)

1. 单击 **[!UICONTROL Account Settings]** 在顶部，然后 **[!UICONTROL Tracking Template]**. 输入 [!DNL Marketo Measure] 跟踪模板。

   ![](assets/2-1.png)

1. 单击 **[!UICONTROL Save]**.

## 在营销活动级别设置跟踪模板 {#setting-up-a-tracking-template-at-the-campaign-level}

1. 单击 **[!UICONTROL All campaigns]** 然后 **[!UICONTROL Campaigns]** 在展开的窗口中。

   ![](assets/3.png)

1. 选择所有适用的营销活动或 **[!UICONTROL Select All]**，单击 **[!UICONTROL Edit]**，然后单击 **[!UICONTROL Change Tracking Templates]**.

   ![](assets/4-1.png)

1. 输入 [!DNL Marketo Measure] 跟踪模板并单击 **[!UICONTROL Apply]**.

## 在广告组级别设置跟踪模板： {#setting-up-a-tracking-template-at-the-ad-group-level}

1. 单击 **[!UICONTROL All campaigns]** 然后 **[!UICONTROL Ad Groups]** 在展开的窗口中。

   ![](assets/5-1.png)

1. 选择所有适用的广告组或全选，单击 **[!UICONTROL Edit]** 然后单击 **[!UICONTROL Change Tracking Templates]**.

1. 输入 [!DNL Marketo Measure] 跟踪模板并单击 **[!UICONTROL Apply]**.

   ![](assets/6-1.png)

## 常见问题 {#faq}

**问：连接的用户需要哪些权限？**

答：userinfo.email

**问：导入支出数据需要多长时间？**

答：6小时

**问：导入广告数据需要多长时间？**

答：4小时

**问：对于动态搜索广告，我们能否在提供的创意内容中跟踪标题、描述等的组合？**

答：我们无法为动态搜索广告检索单个创意详细信息，但如果启用了自动标记，我们仍可以获得创意ID和属性收入。

>[!NOTE]
>
>完成更改后，即表示您已经完成。 欢迎您随时联系 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} 如果在设置过程中有任何问题，请执行以下操作。

[单击此处](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} 有关Google有关创建帐户级跟踪模板的说明。
