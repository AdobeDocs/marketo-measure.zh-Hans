---
unique-page-id: 18874594
description: 集成的广告平台 —  [!DNL Marketo Measure]
title: 集成式广告平台
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
feature: APIs, Integration
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '1644'
ht-degree: 0%

---

# 集成式广告平台 {#integrated-ad-platforms}

[!DNL Marketo Measure]具有与Google AdWords、Microsoft BingAds、[!DNL Facebook]个广告和DoubleClick促销活动管理器的API连接。 通过这些API连接，[!DNL Marketo Measure]能够轻松地提取数据，并将其与外部买方应用程序一起推送到您的CRM。 无需手动上传成本或数据。 您的帐户只需连接到[!DNL Marketo Measure]应用程序并获得授权即可。 然后，[!DNL Marketo Measure]将自动从平台下载您的营销成本，并将其加载到[!DNL Marketo Measure]应用程序中。 如果选择为AdWords、BingAds或[!DNL Facebook]广告启用自动标记，[!DNL Marketo Measure]将自动将其参数附加到广告的URL。

## 如何连接Ad平台 {#how-to-connect-ad-platforms}

在详细了解每个平台之前，我们将讨论如何将这些帐户中的任意帐户连接到[!DNL Marketo Measure]。 首次登录[!DNL Marketo Measure]应用并导航到屏幕左上角&#x200B;**[!UICONTROL My Account]**&#x200B;选项卡下的&#x200B;**[!UICONTROL Settings]**&#x200B;选项。 接下来，选择左侧&#x200B;**[!UICONTROL Integrations]**&#x200B;部分下的&#x200B;**[!UICONTROL Connections]**。

如下图所示，您将看到用于设置新广告连接的按钮。

![](assets/2.png)

单击[!UICONTROL Set up New Ads Connection]按钮后，将会弹出一个窗口（如下所示），其中包含四个广告[!UICONTROL connect]离子类型。 单击连接，将出现另一个窗口询问凭据。 输入凭据并单击[!UICONTROL authorize]以将帐户连接到[!DNL Marketo Measure]。

![](assets/select-account-type.png)

## Google AdWords {#google-adwords}

在[!DNL Google AdWords]中创建广告时，建议您通过三种方式之一来标记营销活动：手动标记、自动标记或创建跟踪模板。 手动标记AdWords URL取决于您在广告URL末尾定义和添加参数。 通过手动标记，任何非Google平台都可以轻松读取通过参数收集的数据。

“跟踪模板”是Google提供的一款工具，用于添加它调用的ValueTrack参数。 它们的工作方式与UTM和其他标记参数相同。

## 启用自动标记后发生的情况 {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure]在您的[!DNL AdWords]帐户中搜索跟踪模板：

* *选项A*：找到跟踪模板。 [!DNL Marketo Measure]将其参数添加到模板。
* *选项B*：找到第三方重定向。 如果在跟踪模板中找到第三方重定向，则[!DNL Marketo Measure]无法执行任何操作。 您需要手动将[!DNL Marketo Measure]标记添加到第三方系统。 第三方重定向的一个示例是竞价管理工具，如Kenshoo或Marin。 详细了解[竞价管理工具如何影响 [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}。

* *选项C*：未找到跟踪模板。 [!DNL Marketo Measure]将扫描[!DNL Marketo Measure]参数的所有Ad目标URL。 根据扫描，如果：
   * 找到参数：设置完成！
   * 未找到参数： [!DNL Marketo Measure]会将其参数附加到广告目标URL的末尾。 [!DNL Marketo Measure]在创建新广告后的两小时内追加这些广告。 请记住，不会将参数添加到模板中。

详细了解[[!DNL AdWords] 自动标记功能](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md){target="_blank"}。

## 如何为Adwords启用[!DNL Marketo Measure]自动标记 {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

在启用[!DNL Marketo Measure]自动标记之前，**请确保在Adwords帐户中的帐户、营销活动或广告组级别启用了跟踪模板。 任何已启用[!DNL Marketo Measure]自动标记的Adwords帐户都需要此项。**&#x200B;启用跟踪模板可防止广告效果历史记录数据出现任何丢失。 请注意，在关键词、站点链接或广告级别启用跟踪模板将导致广告完成审阅和批准流程，并可能重新启动广告的性能历史记录。 如果根本未启用跟踪模板，则[!DNL Marketo Measure]会将[!DNL Marketo Measure]跟踪参数直接附加到广告的“最终URL”，这也会导致广告历史记录数据丢失。

设置跟踪模板后，请按照以下说明启用[!DNL Marketo Measure]自动标记。 注意：[!DNL Marketo Measure]还将自动标记您帐户中所有暂停的广告。

1. 在[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}登录到您的[!DNL Marketo Measure]帐户。

1. 转到[!UICONTROL My Account] > [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Connections]。

   ![](assets/4.png)

1. 单击将启用[!DNL Marketo Measure]自动标记的Adwords帐户旁边的铅笔图标。

   ![](assets/5.png)

1. 在右上角，将&#x200B;**[!UICONTROL Autotagging]**&#x200B;开关切换到&#x200B;**[!UICONTROL Yes]**。 在页面底部，单击&#x200B;**[!UICONTROL Learn More]**&#x200B;以展开文本框并单击&#x200B;**[!UICONTROL Save]**。 自动标记设置完成。

   ![](assets/6.png)

## 如何使用[!DNL Marketo Measure]参数在AdWords中设置跟踪模板 {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

请记住，您应在AdWords中的[!UICONTROL Account]、[!UICONTROL Campaign]或广告组级别添加跟踪模板。 如果您将跟踪模板添加到关键词、站点链接或广告级别，则您的广告将需要经过审查和批准过程，并且您可能会重新启动广告的性能历史记录。 了解有关[创建跟踪模板](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}的详细信息。

1. 登录到您的[!DNL Google AdWords]帐户。
1. 从左侧导航栏转到您的[!UICONTROL Campaigns]视图
1. 导航到左侧导航栏中的&quot;[!UICONTROL Settings]&quot;
1. 从顶部切换到&quot;[!UICONTROL Account Settings]&quot;视图
1. 展开“[!UICONTROL Tracking]”部分
1. 将以下文本字符串之一粘贴到跟踪模板中以设置模板的值：

   * 如果您在所有URL中都带有问号，请使用以下URL文本：

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * 如果您的URL中没有问号，请添加以下URL文本：

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   要防止在手动标记URL时出现错误，通常建议自动生成UTM参数。 这不一定需要使用AdWords或[!DNL Marketo Measure]参数自动标记，因为有多个工具可根据您提供的信息自动生成URL的参数，从而简化此过程。

   >[!TIP]
   >
   >如果您收到错误消息指出跟踪模板无效，请尝试清除浏览器缓存并重试 — 这通常可解决此问题。

## 如何自动为[!DNL Google AdWords]生成UTM标记 {#how-to-automatically-generate-utm-tags-for-google-adwords}

UTM标记最初可能看起来难以创建，但有许多工具可用于使用UTM参数轻松构建URL。 您可以使用以下任一资源或在Web上搜索更多工具。 请记住，[!DNL Marketo Measure]不认可或担保这些平台和工具的任何内容。

**[!DNL Google URL]生成器**

Google URL Builder是用于使用UTM标记构建格式正确的URL的标准工具。 输入URL和每个参数的所需值，然后单击“[!UICONTROL Generate URL]”。 如果要标记的URL非常少，那么这是一个理想的工具。 访问[此处](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"}的工具。

由EpikOne生成的&#x200B;**Google电子表格**

此电子表格具有一个公式，可自动生成标记的目标URL。 如果需要标记大量链接，这是一个非常有用的工具。 在[此处](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&hl=en){target="_blank"}访问电子表格。

**Rafflecopter链接标记工具**

Rafflecopter创建的电子表格是[!DNL EpikOne's]电子表格的修改版本。 它还包含一个公式，它将自动生成标记的目标链接供您使用。

其中每个工具都提供了有关如何使用和修改它以满足您的需求的详细说明。 此工具可在[此处](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}使用。

**Effin令人惊叹的UTM生成器**

此工具是一个Chrome扩展，允许您快速生成UTM标记。 在[此处](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target="_blank"}查找它。

## Bing Ads {#bing-ads}

Bing Ads是一个集成平台，允许您为URL启用自动标记或使用第三方工具（如[!DNL Marketo Measure]）标记广告。 [!DNL Bing Ads]也依赖于UTM参数。

我们的集成支持以下广告类型：

* 文本广告
* 移动广告
* 扩展的文本广告


Bing Ads的自动标记功能会添加以下UTM参数：

* Utm_source
* Utm_medium
* Utm_term

Bing Ads的自动标记还会添加以下自定义参数：

`_bt={adid}`

字符串将如下所示：

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

需要注意的是，如果需要，[!DNL Bing Ads]允许您通过在最终URL中使用其自定义标记来添加更多参数，以获得更多粒度。

如果需要，可以使用跟踪模板，但[!DNL Bing Ads]和[!DNL Marketo Measure]不必集成。 这是因为[!DNL Bing]允许在不更改历史记录的情况下编辑广告，因此[!DNL Marketo Measure]能够更新目标URL。

应通过[!DNL Marketo Measure]启用自动标记，以便能够自动附加自定义[!DNL Marketo Measure]参数。 使用Bing Ads不会丢失过去的广告效果历史记录。

访问[[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target="_blank"}网站，了解有关在其平台上添加标记的详细信息。

## facebook Ads {#facebook-ads}

与[!DNL Facebook]的[!DNL Marketo Measure]集成允许它自动下载广告信息并使用其参数标记URL。 [!DNL Marketo Measure]将通过我们的自动标记提取营销活动和广告集信息。 广告集将填充我们的广告组名称字段。 有关在[!DNL Facebook]平台上设置URL标记的详细信息，请访问[!DNL Facebook] [业务](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target="_blank"}页面。

在使用[!DNL Facebook Ads]启用自动标记之前，必须将先前的性能历史记录导出为CSV。 此时，当[!DNL Marketo Measure]使用其_bf参数标记[!DNL Facebook Ads]时，[!DNL Facebook]会将广告读取为全新并擦除性能历史记录。 因此，如果导出以前的绩效记录对您和您的组织有价值，那么导出该记录就很重要。

请注意，您可以随时将您的[!DNL Facebook]帐户连接到[!DNL Marketo Measure]应用，并且不会丢失任何数据 — 仅当启用了自动标记时，才会擦除性能历史记录。

有关导出[!DNL Facebook]广告报表的更多信息，请参阅Facebook中的[本文](https://www.facebook.com/business/help/393890194130036){target="_blank"}。

## linkedIn赞助内容 {#linkedin-sponsored-content}

linkedIn集成允许[!DNL Marketo Measure]在[!DNL LinkedIn]赞助的内容上标记目标URL，这最终允许[!DNL Marketo Measure]跟踪用户完成其整个接触点历程并将活动映射回特定的[!DNL LinkedIn]营销活动和创意。 这可以为客户提供有关其[!DNL LinkedIn]活动ROI的分析。 [!DNL Marketo Measure]将搜索具有唯一[!DNL LinkedIn]共享的创意，并在其末尾添加`?_bl={creativeId}`参数。

由于[!DNL LinkedIn]共享可以在多个营销活动和创意中使用，因此我们要求客户不要复制/克隆/复制现有创意以保持其唯一性。 如果发现并检测到共享仅用于一个创意，[!DNL Marketo Measure]可以按原样标记共享，而无需重新创建任何创意或共享，并且所有广告历史记录（展示次数、点击次数、共享）都将保留。

一旦发现共享在多个创意人员之间共享，[!DNL Marketo Measure]就必须运行暂停、复制和重新标记的过程，才能创建唯一的集。 [!DNL Marketo Measure]将暂停并存档实时创意内容，这意味着包含展示次数、点击次数和社交共享的创意内容也会存档。

## 非集成平台 {#non-integrated-platforms}

对于未与[!DNL Marketo Measure]集成的平台，无法使用[!DNL Marketo Measure]自动标记功能。 需要手动添加参数。
