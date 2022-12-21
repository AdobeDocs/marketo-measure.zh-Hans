---
unique-page-id: 18874594
description: 集成广告平台 —  [!DNL Marketo Measure]  — 产品文档
title: 集成广告平台
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 0%

---

# 集成广告平台 {#integrated-ad-platforms}

[!DNL Marketo Measure] 具有与Google AdWords、Microsoft BingAds、 [!DNL Facebook] 广告和DoubleClick促销活动管理器。 通过这些API连接， [!DNL Marketo Measure] 能够轻松提取数据，并将其与外部“购买者”应用程序一起推送到CRM。 无需手动上传成本或数据。 相反，您的帐户只需连接到 [!DNL Marketo Measure] 应用程序。 [!DNL Marketo Measure] 之后，将自动从平台下载营销成本，并将其加载到 [!DNL Marketo Measure] 应用程序。 如果您选择为AdWords、BingAds或 [!DNL Facebook] 广告， [!DNL Marketo Measure] 会自动将其参数附加到您广告的URL。

## 如何连接广告平台 {#how-to-connect-ad-platforms}

在了解每个平台的具体信息之前，我们将介绍如何将这些帐户中的任何帐户连接到 [!DNL Marketo Measure]. 首先登录 [!DNL Marketo Measure] 应用程序，然后导航到 **[!UICONTROL Settings]** 选项 **[!UICONTROL My Account]** 选项卡。 接下来，选择 **[!UICONTROL Connections]** 下 **[!UICONTROL Integrations]** 中。

如下图所示，您将看到一个用于设置新广告连接的按钮。

![](assets/2.png)

在单击 [!UICONTROL Set up New Ads Connection] 按钮上，将弹出一个窗口（如下所示），其中包含四个广告 [!UICONTROL connect]离子类型。 单击连接，此时将显示另一个窗口，要求提供凭据。 输入凭据并单击 [!UICONTROL authorize] 将帐户连接到 [!DNL Marketo Measure].

![](assets/select-account-type.png)

## Google AdWords {#google-adwords}

在中创建广告时 [!DNL Google AdWords]，我们鼓励您采用以下三种方法之一来标记营销活动：手动标记、自动标记或创建跟踪模板。 手动标记AdWords URL取决于您在广告URL的末尾定义和添加参数。 手动标记允许任何非Google平台轻松读取参数收集的数据。

跟踪模板是Google提供的用于添加其调用的ValueTrack参数的工具。 它们的工作方式与UTM和其他标记参数相同。

## 启用自动标记后会发生什么情况 {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure] 在 [!DNL AdWords] 帐户：

* *选项A*:找到跟踪模板。 [!DNL Marketo Measure] 将其参数添加到模板。
* *选项B*:找到第三方重定向。 如果在跟踪模板中找到第三方重定向， [!DNL Marketo Measure] 无法执行任何操作。 您需要手动添加 [!DNL Marketo Measure] 标记。 第三方重定向的一个示例是诸如Kenshoo或Marin之类的竞价管理工具。 详细了解如何 [竞价管理工具影响 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target=&quot;_blank&quot;}。

* *选项C*:未找到跟踪模板。 [!DNL Marketo Measure] 将扫描您的所有广告目标URL，以 [!DNL Marketo Measure] 参数。 根据扫描，如果：
   * 找到参数：设置完成！
   * 未找到参数： [!DNL Marketo Measure] 会将其参数附加到广告目标URL的末尾。 [!DNL Marketo Measure] 在创建新广告后的两小时内附加新广告。 请记住，参数将不会添加到模板中。

进一步了解我们的 [[!DNL AdWords] 自动标记功能](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md){target=&quot;_blank&quot;}。

## 如何启用 [!DNL Marketo Measure] Adwords自动标记 {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

启用前 [!DNL Marketo Measure] 自动标记， **请确保您的Adwords帐户中在帐户、促销活动或广告组级别启用了跟踪模板。 对于将具有 [!DNL Marketo Measure] 自动标记。** 启用跟踪模板可防止广告性能历史记录数据中的任何丢失。 请注意，在关键词、网站链接或广告级别启用跟踪模板将导致广告完成审核和批准过程，并可能会重新启动广告的性能历史记录。 如果根本未启用跟踪模板， [!DNL Marketo Measure] 将附加 [!DNL Marketo Measure] 跟踪参数直接到广告的“最终URL”，这也可能会导致广告历史数据丢失。

在您设置了跟踪模板后，请按照以下说明启用 [!DNL Marketo Measure] 自动标记。 注意： [!DNL Marketo Measure] 还将自动标记您帐户中任何暂停的广告。

1. 登录到 [!DNL Marketo Measure] 帐户 [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}。

1. 转到 [!UICONTROL My Account] > [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Connections].

   ![](assets/4.png)

1. 单击将具有 [!DNL Marketo Measure] 自动标记。

   ![](assets/5.png)

1. 在右上角，切换 **[!UICONTROL Autotagging]** 切换到 **[!UICONTROL Yes]**. 在页面底部，单击 **[!UICONTROL Learn More]** 展开文本框并单击 **[!UICONTROL Save]**. 自动标记设置已完成。

   ![](assets/6.png)

## 如何在AdWords中设置跟踪模板 [!DNL Marketo Measure] 参数 {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

请记住，您应在 [!UICONTROL Account], [!UICONTROL Campaign] 或AdWords中的广告组级别。 如果您向关键词、网站链接或广告级别添加跟踪模板，则您的广告将需要经过审核和批准过程，并且您有可能重新启动广告的性能历史记录。 详细了解 [创建跟踪模板](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target=&quot;_blank&quot;}。

1. 登录到 [!DNL Google AdWords] 帐户。
1. 转到 [!UICONTROL Campaigns] 从左侧导航栏中查看
1. 导航到“[!UICONTROL Settings]”，也位于左侧导航栏中
1. 切换到“[!UICONTROL Account Settings]“查看顶部
1. 展开“[!UICONTROL Tracking]“ ”部分
1. 在跟踪模板中粘贴以下文本字符串之一以设置模板值：

   * 如果所有URL中都有问号，请使用以下URL文本：

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * 如果您的任何URL上没有问号，请添加以下URL文本：

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   为防止在手动标记URL时发生错误，通常建议自动生成UTM参数。 这不一定意味着使用AdWords或 [!DNL Marketo Measure] 参数中，有多种工具可根据您提供的信息自动为URL生成参数，从而简化流程。

   >[!TIP]
   >
   >如果您收到错误，指出跟踪模板无效，请尝试清除浏览器缓存并重试 — 这通常可以解决此问题。

## 如何为自动生成UTM标记 [!DNL Google AdWords] {#how-to-automatically-generate-utm-tags-for-google-adwords}

起初创建UTM标记可能比较困难，但有许多工具可用于使用UTM参数轻松构建URL。 您可以使用以下任何一种资源或在Web上搜索更多工具。 请记住 [!DNL Marketo Measure] 使用这些平台和工具，不会对任何内容提供支持或保证。

**[!DNL Google URL]Builder**

Google URL生成器是用于使用UTM标记构建格式正确的URL的标准工具。 只需输入每个参数的URL和所需值，然后单击“[!UICONTROL Generate URL]&quot; 如果要标记的URL只有几个，则使用此工具非常理想。 访问该工具 [此处](https://support.google.com/analytics/answer/1033867?hl=en){target=&quot;_blank&quot;}。

**Google由EpikOne生成电子表格**

此电子表格具有一个公式，该公式将自动生成标记的目标URL。 如果需要标记大量链接，此工具非常有用。 访问电子表格 [此处](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&amp;hl=en){target=&quot;_blank&quot;}。

**Rafflecopter链接标记工具**

由Rafflecopter创建的电子表格是 [!DNL EpikOne's] 电子表格。 它还包含一个公式，该公式将自动生成标记的目标链接以供您使用。

每个工具都提供了有关如何使用和修改以满足您需求的详细说明。 工具可用 [此处](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target=&quot;_blank&quot;}。

**令人惊叹的UTM生成器**

此工具是Chrome扩展，允许您快速生成UTM标记。 找到它 [此处](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target=&quot;_blank&quot;}。

## Bing Ads {#bing-ads}

Bing Ads是一个集成平台，允许您为URL启用自动标记或使用第三方工具，例如 [!DNL Marketo Measure]，以标记广告。 [!DNL Bing Ads] 也依赖于UTM参数。

Bing Ads的自动标记功能添加了以下UTM参数：

* Utm_source
* Utm_medium
* Utm_term

Bing Ads的自动标记还会添加以下自定义参数：

`_bt={adid}`

该字符串将如下所示：

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

请务必注意 [!DNL Bing Ads] 允许您根据需要，通过在最终URL中使用其自定义标记来添加更多参数，以获得更多粒度。

如果需要，可以使用跟踪模板，但无需 [!DNL Bing Ads] 和 [!DNL Marketo Measure] 集成。 这是因为 [!DNL Bing] 允许在不更改历史记录的情况下编辑广告，因此 [!DNL Marketo Measure] 能够更新目标URL。

应通过 [!DNL Marketo Measure] 这样， [!DNL Marketo Measure] 可以自动附加参数。 使用Bing Ads不会丢失过去的广告效果历史记录。

访问 [[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target=&quot;_blank&quot;}网站，以了解有关在其平台上添加标记的更多信息。

## Facebook Ads {#facebook-ads}

的 [!DNL Marketo Measure] 集成 [!DNL Facebook] 允许它自动下载广告信息并使用其参数标记URL。 [!DNL Marketo Measure] 将通过我们的自动标记来提取营销活动和广告集信息。 广告集将填充我们的广告组名称字段。 有关在 [!DNL Facebook] 平台，访问 [!DNL Facebook] [业务](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target=&quot;_blank&quot;}页。

在启用自动标记之前 [!DNL Facebook Ads]，则务必要将以前的性能历史记录导出为CSV。 此时，当 [!DNL Marketo Measure] 标记 [!DNL Facebook Ads] 带有_bf参数， [!DNL Facebook] 将广告读作全新广告，并擦除性能历史记录。 因此，如果之前的性能记录对您和您的组织具有一定价值，则务必导出该记录。

请注意，您可以将 [!DNL Facebook] 帐户 [!DNL Marketo Measure] 应用程序，并且不会丢失任何数据 — 只有在启用自动标记后，性能历史记录才会被擦除。

[请参阅本文](https://www.facebook.com/business/help/393890194130036)从Facebook中{target=&quot;_blank&quot;}以获取有关导出的详细信息 [!DNL Facebook] 广告报表。

## linkedIn赞助内容 {#linkedin-sponsored-content}

LinkedIn集成允许 [!DNL Marketo Measure] 标记 [!DNL LinkedIn] 赞助内容，最终允许 [!DNL Marketo Measure] 跟踪用户完成其整个接触点历程，并将活动映射回特定 [!DNL LinkedIn] Campaign和Creative。 这为客户提供了有关其ROI的洞察 [!DNL LinkedIn] 活动。 [!DNL Marketo Measure] 将搜索具有唯一 [!DNL LinkedIn] 共享和添加 `?_bl={creativeId}` 参数。

因为 [!DNL LinkedIn] 共享内容可以跨多个促销活动和创意使用，为此，我们要求客户不要复制/克隆/复制现有创意内容，以便保持其独特性。 如果找到共享，并且检测到共享仅用于一个创作元素， [!DNL Marketo Measure] 可以按原样标记共享，而无需重新创建任何创意或共享，并且所有广告历史记录（展示次数、点击次数、共享次数）都将保留。

一旦发现共享内容可在多个创作元素之间共享， [!DNL Marketo Measure] 必须执行暂停、复制和重新标记过程，才能设置唯一值。 [!DNL Marketo Measure] 将暂停并存档实时创作元素，这意味着包含展示次数、点击次数和社交共享的创作元素也会被存档。

## 非集成平台 {#non-integrated-platforms}

对于未与 [!DNL Marketo Measure], [!DNL Marketo Measure] 无法使用自动标记功能。 需要手动添加参数。
