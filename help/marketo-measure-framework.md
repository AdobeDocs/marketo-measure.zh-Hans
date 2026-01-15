---
description: Marketo Measure框架
title: Marketo Measure框架
exl-id: fa6de27c-cdd2-4fd9-ac35-7286fe2752d8
feature: Fundamentals
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---


# Marketo Measure框架 {#marketo-measure-framework}

详细了解构成Marketo Measure框架的四个主要组件。 Marketo Measure依靠这些应用程序跟踪、整理和存放数据，并提供报表功能。 组成Marketo Measure框架的四个组件包括：

* Marketo Measure的JavaScript
* CRM集成
* 第三方应用程序/系统
* Marketo Measure应用程序

## Marketo Measure JavaScript {#marketo-measure-javascript}

Marketo Measure JavaScript跟踪潜在客户/潜在客户与您的组织之间的所有在线营销互动（也称为接触点）。 它是一个自定义脚本，添加到网站每个页面的结束`</head>`标记之前。

`<script type="text/javascript" src="//[cdn.bizible.com/scripts/bizible.js](http://cdn.bizible.com/scripts/bizible.js)" async=""></script>`

>[!NOTE]
>有关如何添加Marketo Measure JS的说明，[单击此处](/help/marketo-measure-tracking/adding-marketo-measure-script.md)。

Marketo Measure的JS捕获来自Web访问（包括匿名Web访问）、常规流量/页面导航、内容下载和表单提交的数据。 此数据将推送到您的CRM中，并且每次营销交互都显示为接触点。

## CRM集成 {#crm-integrations}

Marketo Measure与CRM集成，以存放和管理Marketo Measure JS捕获的所有数据。 目前，Marketo Measure已与两个CRM集成API：

![Marketo Measure与CRM集成以存放和组织所有数据](assets/overview-resources-14.png)

通过在CRM中显示Marketo Measure数据，您可以查看与每个接触点相关的粒度信息，并生成报告以了解您的渠道的执行情况。

## 第三方应用程序 {#third-party-applications}

大多数营销人员依靠一些不同的应用程序来开展营销工作。 除了Salesforce和MS Dynamics之外，Marketo Measure还与13个第三方应用程序（如下所列）集成。

![大多数营销人员依赖一些不同的应用程序来运行其营销活动](assets/overview-resources-15.png)

如果您使用上述应用程序运行任何营销工作，则可以将这些帐户关联到您的Marketo Measure帐户。 这样即可轻松跟踪数据并将其传输到您的Marketo Measure帐户。

## Marketo Measure应用程序 {#marketo-measure-application}

Marketo Measure应用程序用于查看和报告归因数据、配置帐户设置以及更新帐户信息。 Marketo Measure应用程序中的主菜单项包括：

**帐户配置**

您可以在此处更新公司的常规信息并访问Marketo Measure Javascript。

**设置**

利用此菜单项，可配置归因和渠道映射设置、管理与CRM和第三方应用程序的集成、查看/添加Marketo Measure帐户用户以及更新计费信息。

**营销ROI仪表板**

在营销ROI仪表板菜单项中，您可以根据渠道性能、活动和成本来可视化您的数据。
