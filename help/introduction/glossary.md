---
description: Marketo Measure字段词汇表
title: Marketo Measure字段词汇表
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
feature: Fundamentals
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '3210'
ht-degree: 0%

---


# Marketo Measure字段词汇表 {#glossary}

本文提供了从Marketo Measure Base Package添加到Salesforce的所有Marketo Measure字段的术语表。 您还会找到有关可在其中找到字段的对象以及如何使用信息填充每个字段的信息。

对于每个Marketo Measure字段都与之相关的对象，请[单击此处](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md)。

[A](#a) · [B](#b) · [C](#c) · [D](#d) · [E](#e) · [F](#f) · [G](#g) · H · I · J · [K](#k) · [L](#l) · [M](#m) · N · [O](#o) · [P](#p) · [H r](#r) · [S](#s) · [T](#t) · [U](#u) · [V](#v) · W · X · Y · Z

## A {#a}

**帐户** | 可在Buyer Attribution Touchpoint上找到

此字段使用与BAT关联的帐户名称填充。

**广告营销活动Id** | 可在Buyer Attribution Touchpoint的Buyer Touchpoint上找到

填充此字段的方式有三种：

`1)`如果接触点来自付费搜索工作（AdWords或BingAds），则来自广告平台的广告促销活动ID将显示在此处。

`2)`如果接触点并非来自付费搜索，则将使用登陆页面URL中的utm_campaign值填充该字段。

如`http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

在此示例中，广告促销活动ID将显示：__GAId__ 2014年9月营销虚拟事件

`3)`如果接触点来自离线Salesforce营销活动（会议、晚餐等），则广告营销活动ID将会显示Salesforce营销活动ID

如果以上都不包含，此字段将为空。

**广告营销活动名称** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索(AdWords/Bing Ads)，则此处将显示广告平台中的广告促销活动名称。

`2)`如果接触点并非来自付费搜索，且登陆页面URL包含utm_campaign的值，则在此处填充该值。

`3)`如果接触点来自Salesforce营销活动，则此处将显示该Salesforce营销活动的名称。

`4)`这将使用为在Marketo Measure帐户内构建的活动中生成的接触点定义的营销活动名称填充。

如果以上都不包含，此字段将为空。

**广告促销活动名称(FT)** | Buyer Touchpoint

此字段的填充方式与广告营销活动名称相同。 但是，此字段专门向您显示生成首次接触点的广告营销活动的名称。

**广告促销活动名称(LC)** | Buyer Touchpoint

此字段的填充方式与广告营销活动名称相同。 但是，此字段专门向您显示生成商机创建接触点的广告营销活动的名称。

**广告内容** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索(AdWords/Bing Ads)，则字段将显示广告平台中的完整广告副本。

`2)`如果接触点不是来自付费搜索，则此字段将在登陆页面URL中显示utm_content值。

`3)`这将使用生成接触点的相关活动中的主题值填充。

如果以上都不包含，则此字段将为空。

**广告目标URL** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索，则此字段将显示您在单击搜索引擎中的广告后定向到的URL目标。

如果接触点不是来自付费搜索，则字段将为空白。

**广告组Id** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索，则此处将显示来自AdWords/Bing Ads的广告组ID。

如果接触点不是来自付费搜索，则字段将为空白。

**广告组名称** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索，则此处将显示AdWords/Bing Ads中的广告组名称。

如果接触点不是来自付费搜索，则字段将为空白。

**广告Id** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索，则此处将显示来自AdWords/Bing Ads的广告ID。

`2)`如果接触点是从CRM活动生成的，这将使用活动外部ID填充。

如果接触点不是来自付费搜索，则字段将为空白。

**归因%自定义模型** | Buyer Attribution Touchpoint

如果您使用自定义归因模型，则此字段根据在自定义模型中设置的值显示归属于接触点的收入百分比。

如果您未使用自定义模型，则此字段将为空白。

**归因%首次联系** | Buyer Attribution Touchpoint

此字段将根据首次接触模型显示归属于接触点的收入百分比。

**归因%已满** | Buyer Attribution Touchpoint

此字段将根据完整路径模型显示归属于接触点的收入百分比。

**归因%潜在客户创建** | Buyer Attribution Touchpoint

根据商机创建模型，此字段将显示归属于接触点的收入百分比。

**归因% U型** | Buyer Attribution Touchpoint

此字段将根据U形模型显示归属于接触点的收入百分比。

**归因% W型** | Buyer Attribution Touchpoint

此字段将根据W型模型显示归属于接触点的收入百分比。

[单击此处返回页面顶部](#top)

## B {#b}

**Marketo Measure机会金额** | Salesforce机会

如果您使用自定义Amount字段来报告Opportunity收入，Marketo Measure将无法读取这些自定义Amount字段。 Marketo Measure Opportunity Amount是一个隐藏字段，用于创建工作流，以使Marketo Measure能够读取Opportunity上的自定义Amount字段。

**浏览器** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示Web会话期间使用的Web浏览器类型(Chrome、Safari、Firefox等)。

[单击此处返回页面顶部](#top)

## C {#c}

**联系人** | Buyer Touchpoint、Buyer Attribution Touchpoint

字段显示接触点所属的联系人。

**计数 — 自定义模型** | Buyer Attribution Touchpoint

如果您使用的是自定义归因模型，此字段会以小数形式显示根据自定义模型中设置的值分配给接触点的收入点数的百分比。

如果您未使用自定义模型，则此字段将为空白。

**计数 — 自定义模型** | Buyer Touchpoint

如果您使用的是自定义归因模型，此字段将以小数形式显示根据自定义模型中设置的值分配给接触点的归因点数的百分比。 由于此字段与Buyer Touchpoint对象相关，因此它并非收入点数的反映，而仅是归因点数的反映。

如果您未使用自定义模型，则此字段将为空白。

**计数 — 首次联系** | Buyer Attribution Touchpoint

此字段以小数形式显示根据首次接触模型分配给接触点的收入点数的百分比。

**计数 — 首次联系** | Buyer Touchpoint

此字段以小数形式显示根据首次接触模型分配给接触点的归因点数的百分比。 如果接触点是首次接触，则此字段将始终为1.0（表示100%归因点数）。 如果接触点不是首次接触，则此字段将始终为0（表示0 %归因点数）。

由于此字段与Buyer Touchpoint对象相关，因此它并非收入点数的反映，而仅是归因点数的反映。

**计数 — 完整路径** | Buyer Attribution Touchpoint

此字段以小数形式显示根据完整路径模型分配给接触点的收入百分比。

**计数 — 潜在客户创建触控** | Buyer Attribution Touchpoint

此字段以小数形式显示根据商机创建模型分配给接触点的收入点数的百分比。

**计数 — 潜在客户创建触控** | Buyer Touchpoint

此字段以小数形式显示根据潜在客户创建模型分配给接触点的归因点数的百分比。 如果接触点是潜在客户创建接触，则此字段将始终为1.0（表示100%归因点数）。 如果接触点不是“商机创建”接触点，则此字段将始终为0（表示0%的归因点数）。

由于此字段与Buyer Touchpoint对象相关，因此它并非收入点数的反映，而仅是归因点数的反映。

**计数 — U型** | Buyer Attribution Touchpoint

此字段以小数形式显示根据U形模型给予接触点的收入点数的百分比。

**计数 — U型** | Buyer Touchpoint

此字段以小数形式显示根据U型模型分配给接触点的归因点数的百分比。 在U形模型中，点数在首次联系、商机创建联系以及在首次联系和商机创建联系之间发生的任何中间表单提交之间分配。

由于此字段与Buyer Touchpoint对象相关，因此它并非收入点数的反映，而仅是归因点数的反映。

**计数 — W型** | Buyer Attribution Touchpoint

此字段以小数形式显示根据W型模型给予接触点的点数百分比。

[单击此处返回页面顶部](#top)

## D {#d}

报告日期 | Marketo Measure ABTest， Marketo Measure Event

Marketo Measure事件 — 用户在您的网站上执行特定操作并激活事件的日期

Marketo Measure ABTest — 用户参与您网站上的A/B测试的日期

[单击此处返回页面顶部](#top)

## E {#e}

**事件名称** | Marketo Measure事件

此字段显示触发事件的操作的名称（即页面查看）。

**事件值** | Marketo Measure事件

事件的描述（即主页）

**试验名称** | Marketo Measure ABTest

此字段显示试验的名称（即试验按钮）

**试验ID** | Marketo Measure AB测试

每个试验的唯一标识代码

[单击此处返回页面顶部](#top)

## F {#f}

表单URL | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段将显示发生表单填写的页面URL的缩短版本（无UTM参数）

表单URL — 原始 | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示表单填写发生的整个页面URL，包括UTM参数

[单击此处返回页面顶部](#top)

## G {#g}

地理城市 | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示领导/联系人访问您网站的城市的名称。 这是通过反向IP查找完成的。

地理国家/地区 | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示领导/联系人访问您网站的国家/地区。 这是通过反向IP查找完成的。

地理区域 | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示领导/联系人访问您网站的区域或州。 这是通过反向IP查找完成的。

[单击此处返回页面顶部](#top)

## K {#k}

**关键字Id** | Buyer Touchpoint、Buyer Attribution Touchpoint

如果接触点来自付费搜索，则此字段将显示广告平台(Adwords/BingAds)中的关键词ID。

如果此接触点不是来自付费搜索，则此字段将为空白。

**关键字MatchType** | Buyer Touchpoint、Buyer Attribution Touchpoint

如果接触点来自付费搜索，则此字段将显示广告平台(Adwords/Bing)中的匹配类型。

**关键字文本** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索，则此字段将显示广告平台(Adwords/BingAds)中的关键词文本或登陆页面URL中_bk参数的值。

如`http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)`如果接触点不是来自付费搜索，则此字段将显示登陆页面URL中的utm_term值。

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`。

如果接触点不是来自付费搜索或没有utm_term值，则此字段将为空白。

[单击此处返回页面顶部](#top)

## L {#l}

**登陆页面** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示在Web会话期间访问的第一个网页的URL的缩短版本（无UTM参数）。

**登陆页面 — 原始** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示在Web会话期间访问的第一个网页的整个URL（包括UTM参数）。

**潜在客户** | Buyer Touchpoint、Marketo Measure人员

此字段显示接触点所属的商机的名称。

[单击此处返回页面顶部](#top)

## M {#m}

**营销渠道** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示接触点所属的营销活动或营销渠道的一般组（即付费搜索、直接、社交等）。 根据Marketo Measure应用程序中渠道的设置方式，对接触点进行分组。 有关营销渠道或如何设置渠道的详细信息，[单击此处](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)。

**营销渠道 — 路径** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示营销渠道以及接触点所属的子渠道。 在下面的示例中，“营销渠道 — 路径”是Social.Linkedin，其中营销渠道是Social，子渠道是LinkedIn。

![ 3](assets/1-3.png)

**Medium** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索，则此处将显示来自Adwords/BingAds的媒体（即CPC）。

`2)`如果接触点不是来自付费搜索，则此字段显示登陆页面URL中的utm_medium值。

`3)`如果接触点来自离线营销活动，则此字段将在Salesforce营销活动中显示“类型”字段。

`4)`这将使用生成接触点的相关活动的Activity Type值填充。

如果以上均不提供，Marketo Measure会自动设置Medium值。

[单击此处返回页面顶部](#top)

O

**机会** | Buyer Attribution Touchpoint

此字段显示BAT所属的销售机会。

[单击此处返回页面顶部](#top)

P

**平台** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示Web会话期间使用的计算机或电话类型以及操作系统类型。

[单击此处返回页面顶部](#top)

R

**反向链接页面** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示潜在客户/联系人最近访问过的、将他们定向到您网站的URL（不带UTM参数）。

例如：

- 如果接触点来自付费/免费搜索，则字段将显示搜索引擎的URL

- 如果接触点来自Social，则字段将显示社交网站的URL（即LinkedIn）

**反向链接页面 — 原始** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示与反向链接页面相同的信息，只是此字段将显示整个反向链接URL（包括UTM参数）。

**收入 — 自定义模型** | Buyer Attribution Touchpoint

如果您使用的是自定义归因模型，此字段显示根据自定义模型中设置的归因百分比归因到接触点的美元收入金额。

如果您不使用自定义模型，则金额将为0。

**收入 — 首次联系** | Buyer Attribution Touchpoint

此字段显示根据首次接触模型中的归因百分比归因到接触点的美元收入金额。

**收入 — 完整路径** | Buyer Attribution Touchpoint

此字段显示根据全路径模型中的归因百分比归因到接触点的美元收入金额。

**收入 — 潜在客户创建触控** | Buyer Attribution Touchpoint

此字段显示根据商机创建模型中的归因百分比归因到接触点的美元收入金额。

**收入 — U型** | Buyer Attribution Touchpoint

此字段显示根据U形模型中归因百分比归因到接触点的美元收入金额。

**收入 — W型** | Buyer Attribution Touchpoint

此字段显示根据W型模型中的归因百分比归因到接触点的美元收入金额。

[单击此处返回页面顶部](#top)

S

**Salesforce促销活动** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示接触点所属的Salesforce Campaign。

**搜索短语** | Buyer Touchpoint、Buyer Attribution Touchpoint

如果接触点来自付费或免费搜索，此字段将显示在搜索引擎中键入的搜索短语。 但是，由于隐私原因，这些信息通常不可用。

**区段** | Buyer Attribution Touchpoint

此字段将显示接触点所属的区段。 这将取决于您在Marketo Measure应用程序中配置分段规则的方式。

[单击此处返回页面顶部](#top)

T

**接触点日期** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自在线源，则此字段将显示接触点发生的日期和时间。

`2)`如果接触点来自离线事件，则此字段将显示在Salesforce Campaign中设置的日期和时间，或来自在Campaign同步规则中选择的日期字段。

`3)`如果接触点来自活动，则此字段将显示在活动规则中选定为接触点日期的字段的日期和时间。

**接触点日期（英尺）** | Buyer Touchpoint

此字段与接触点日期相同，但是此字段专门显示首次接触点发生的日期和时间。

**接触点日期(LC)** | Buyer Touchpoint

此字段与接触点日期相同，但是此字段专门显示商机创建接触点发生的日期和时间。

**接触点位置** | Buyer Touchpoint、Buyer Attribution Touchpoint

此字段显示接触点的位置。 接触点的位置反映了客户历程中的主要里程碑接触点（即FT、Form、LC、OC、Closed）。 接触点的位置取决于它在客户历程中发生的时间，单个接触点可以有多个位置。 不同的接触点位置如下所示：

首次联系(FT) — 某人与您的品牌进行的首次营销互动

商机创建(LC) — 第一个已知的营销交互(通常是表单提交或Salesforce Campaign包含)

表单 — 访客填写在线表单时

机会创建(OC) — 创建Op时最接近的营销交互

已关闭 — Opp关闭时（成功或失败）与之最接近的营销交互

**接触点Source** | Buyer Touchpoint、Buyer Attribution Touchpoint

`1)`如果接触点来自付费搜索，则此字段将显示广告平台的名称(AdWords/BingAds)

`2)`如果接触点来自自然搜索，则此字段将显示搜索引擎的名称

`3)`如果不是#1或#2，并且接触点的登陆页面URL中存在utm_source值，则会在此处显示该值

`4)`如果接触点是从CRM Campaign生成的，这将填充为CRM Campaign。

`5)`如果接触点是从CRM活动生成的，这将填充为CRM活动。

如果以上都不包含，则此字段将填充为“Web直接”或“Web”。

**接触点Source (FT)** | Buyer Touchpoint

此字段与接触点Source相同，但是此字段专门显示首次接触点的来源。

**接触点Source (LC)** | Buyer Touchpoint

此字段与接触点Source相同，但此字段专门显示商机创建接触点的来源。

**接触点类型** | 可在Buyer Touchpoint和Buyer Attribution Touchpoint上找到。

此字段将显示接触点的交互类型。 它将显示为：JavaScript接触点的Web访问、Web窗体或Web聊天。 对于CRM Campaign接触点，将显示为CRM。 其中将填入“活动”接触点的任务或事件类型。

[单击此处返回页面顶部](#top)

U

**唯一标识符** | Buyer Touchpoint、Buyer Attribution Touchpoint

与每个接触点关联的唯一ID

**用户ID** | Marketo Measure ABTest

优化每次使用的唯一标识代码

[单击此处返回页面顶部](#top)

## V {#v}

**变量** | Marketo Measure ABTest

A/B测试的变体的名称

**变量ID** | Marketo Measure ABTest

每个A/B测试变体的唯一标识代码。

[单击此处返回页面顶部](#top)
