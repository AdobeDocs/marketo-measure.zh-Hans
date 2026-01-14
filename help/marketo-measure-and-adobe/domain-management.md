---
description: Marketo Measure用户的域管理指南
title: 域管理
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# 域管理 {#domain-management}

对于在Experience Cloud界面中运行[!DNL Marketo Measure]且启用了IMS的租户，[!DNL Marketo Measure]提供了一个允许用户管理自己的域列表的界面。 [!DNL Marketo Measure]用户必须首先验证他们希望在[Adobe Admin Console](https://adminconsole.adobe.com/)中跟踪的任何域。 在Admin Console中验证域后，用户可以管理[!DNL Marketo Measure]是否使用这些域来跟踪网站流量。

## 在Admin Console中添加域 {#adding-domains-in-admin-console}

有权访问Adobe Admin Console的IMS用户可以添加和验证他们拥有的域。 域验证涉及为每个域添加DNS记录，然后允许Admin Console验证该记录。

![](assets/domain-management-4.png)

有关添加域的说明可在[Admin Console文档](https://helpx.adobe.com/enterprise/using/add-domains-directories.html)中找到。 添加域后，该域必须[链接到目录](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies)。

## 管理[!DNL Marketo Measure]中的域 {#managing-domains-in-marketo-measure}

将域添加到Admin Console后，[!DNL Marketo Measure]会定期将此记录同步到数据库中。 此同步每夜进行，也可在用户每次在&#x200B;**[!UICONTROL Domains]** UI中访问[!DNL Marketo Measure]页面时进行。 默认情况下，[!DNL Marketo Measure]导入的任何记录都将被禁用，租户必须手动启用每个域。

![](assets/domain-management-2.png)

在&#x200B;**[!UICONTROL Integration]** > **[!UICONTROL Domains]**&#x200B;页面上，用户会看到已在Admin Console中注册的所有域及其状态。 可以启用或禁用每个域。 如果启用了某个域，[!DNL Marketo Measure]跟踪将收集在该域上看到的任何流量。 如果域被禁用，[!DNL Marketo Measure]将忽略来自该域的任何流量，并且不会创建接触点或其他数据。 [!DNL Marketo Measure]确认域被禁用，并警告任何后果：

![](assets/domain-management-3.png)

切换域的影响是即时的，更改不具有追溯性。 将来，[!DNL Marketo Measure]将在设定的时间段后清除禁用域中的数据。

## 状态 {#statuses}

Admin Console状态可按如下方式分类：

* **已验证**：此域已在Admin Console中验证
* **未验证**：此域未在Admin Console中完全验证，因此不符合[!DNL Marketo Measure]中的跟踪条件
* **无效**：此域可能已过期或已从Admin Console中删除。 [!DNL Marketo Measure]中的跟踪数据已标记为删除
* **旧版**：此域创建于[!DNL Marketo Measure]，在Admin Console中不存在

跟踪状态可以如下所示：

* **活动**： [!DNL Marketo Measure]正在从该域接收数据
* **已禁用**：此域可用于跟踪，但已禁用
* **不可用**：此域未验证，因此无法进行跟踪

将鼠标悬停在任何单个状态项上会触发工具提示，该提示将进一步说明该状态。

## 常见问题解答 {#faq}

**在Admin Console中删除域后会出现什么情况？**

在Admin Console中删除域时，[!DNL Marketo Measure]将该域标记为已删除。 [!DNL Marketo Measure]将立即停止跟踪此域上的流量，但不会删除任何以前收集的数据。

**为什么我无法启用域？**

在此页面上可能不允许选择域的原因有多种。 如果未在Admin Console中验证域，则该域在[!DNL Marketo Measure]中不可用。 同样，如果域由当前[!DNL Marketo Measure]租户以外的其他Adobe组织拥有，则该域可能无法选择。

**如何从该列表中删除域？**

如果域关闭了“已启用”开关，[!DNL Marketo Measure]将忽略该开关并将其从[!DNL Marketo Measure]中有效移除。 要从[!DNL Marketo Measure]中永久删除域，您必须在[!DNL Marketo Measure]中禁用它，然后从Admin Console中删除它。
