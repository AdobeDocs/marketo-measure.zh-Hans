---
description: 创建自定义 [!DNL Marketo Measure] 报表类型
title: 创建自定义 [!DNL Marketo Measure] 报表类型
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---


# 创建自定义[!DNL Marketo Measure]报表类型 {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>您可能会在文档中看到指定“[!DNL Marketo Measure]”的说明，但在您的CRM中仍会看到“[!DNL Bizible]”。 我们正在努力更新品牌，并且品牌重塑很快将会反映在您的CRM中。

了解如何创建自定义[!DNL Marketo Measure] [!DNL Salesforce]报告类型。 我们建议创建三种不同的报表类型：具有购买者接触点的潜在客户（自定义）、[!DNL Marketo Measure]具有购买者接触点的人员（自定义）、具有Buyer Attribution Touchpoint的业务机会（自定义）。

## 具有买方接触点的潜在客户（自定义） {#leads-with-buyer-touchpoints-custom}

1. 转到&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**。

   ![Salesforce设置菜单导航到新的自定义报表类型](assets/1.png)

1. 定义自定义报表类型。

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]]：潜在客户
   * 标识> [!UICONTROL Report Type Label]：具有买方接触点的潜在客户（自定义）
   * [!UICONTROL Store in Category]：其他报告
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]：已部署

   ![自定义报告类型定义表单，Lead作为主要对象](assets/2.png)

1. 定义对象关系。

   * 将Lead对象(A)与[!DNL Marketo Measure]人员对象(B)关联，然后再与Buyer Touchpoint对象(C)关联
   * 确保已选择“[!UICONTROL Each A/B record must have at least one B/C]”记录
   * [!UICONTROL Save]

   ![对象关系图显示了Lead到Person到Touchpoint的连接](assets/3.png)

## 具有买方接触点的[!DNL Marketo Measure]人员（自定义） {#marketo-measure-person-with-buyer-touchpoints-custom}

1. 转到&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**。

   ![Salesforce设置菜单导航到新的自定义报表类型](assets/4.png)

1. 定义自定义报表类型。

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]： [!DNL Marketo Measure]人
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]：[!DNL Marketo Measure]具有购买者接触点的人员（自定义）
   * [!UICONTROL Store in Category]：其他报告
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]：已部署

   ![自定义报表类型定义表单，将Marketo Measure人员作为主要对象](assets/5.png)

1. 定义对象关系。

   * 将[!DNL Marketo Measure]人员对象(A)与Buyer Touchpoint对象(B)相关联
   * 确保已选择“[!UICONTROL Each A record must have at least one B]”记录
   * [!UICONTROL Save]

   ![显示人员与接触点连接的对象关系图](assets/6.png)

## Buyer Attribution Touchpoint销售机会（自定义） {#opportunities-with-buyer-attribution-touchpoint-custom}

1. 转到&#x200B;**[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**。

   ![Salesforce设置菜单导航到新的自定义报表类型](assets/7.png)

1. 定义自定义报表类型。

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]：机会
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]：Buyer Attribution Touchpoint的销售机会（自定义）
   * [!UICONTROL Store in Category]：其他报告
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]：已部署

   ![自定义报告类型定义表单，将机会作为主要对象](assets/8.png)

1. 定义对象关系。

   * 将机会对象(A)关联到Buyer Attribution Touchpoint对象(B)
   * 确保已选择“[!UICONTROL Each A record must have at least one B]”记录
   * [!UICONTROL Save]

   ![显示归因接触点连接机会的对象关系图](assets/9.png)

## 将自定义字段添加到自定义报表类型 {#adding-custom-fields-to-custom-report-types}

1. 创建报告后，您将被重定向到报告类型的概述。 单击 **[!UICONTROL Edit Layout]**。

   ![带有“编辑布局”按钮的报告类型概述屏幕](assets/10.png)

1. 确保要添加到报表的自定义字段显示在字段布局属性部分中。 如果您希望添加任何其他字段，请使用&quot;[!UICONTROL Add fields related via lookup]&quot;选项。

   ![具有可用自定义字段的字段布局属性部分](assets/11.png)
