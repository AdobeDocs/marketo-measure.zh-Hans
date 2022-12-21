---
description: 域管理 —  [!DNL Marketo Measure]  — 产品文档
title: 域管理
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# 域管理 {#domain-management}

对于运行的启用IMS的租户 [!DNL Marketo Measure] 在统一外壳中， [!DNL Marketo Measure] 提供了一个界面，允许用户管理自己的域列表。 [!DNL Marketo Measure] 用户必须首先验证他们希望跟踪的任何域 [Adobe Admin Console](https://adminconsole.adobe.com/). 在Admin Console中验证域后，用户可以管理 [!DNL Marketo Measure] 使用这些域来跟踪网站流量。

## 在Admin Console中添加域 {#adding-domains-in-admin-console}

有权访问Adobe Admin Console的IMS用户可以添加和验证他们拥有的域。 域验证包括为每个域添加DNS记录，然后允许Admin Console验证该记录。

![](assets/domain-management-1.png)

有关添加域的说明，请参阅 [Admin Console文档](https://helpx.adobe.com/enterprise/using/set-up-identity.html#setup-domains). 添加域后，必须 [链接到目录](https://helpx.adobe.com/enterprise/using/set-up-identity.html#link-domains-to-directories).

## 在中管理域 [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

在Admin Console中添加域后， [!DNL Marketo Measure] 会定期将此记录同步到我们的数据库中。 此同步每晚进行，也是在用户每次访问 **[!UICONTROL Domains]** 页面 [!DNL Marketo Measure] UI。 默认情况下， [!DNL Marketo Measure] 导入将被禁用，租户必须手动启用每个域。

![](assets/domain-management-2.png)

在 **[!UICONTROL Integration]** > **[!UICONTROL Domains]** 页面，用户将看到他们在Admin Console中注册的所有域及其状态。 可以启用或禁用每个域。 如果域已启用， [!DNL Marketo Measure] 跟踪将收集该域上显示的任何流量。 如果域被禁用， [!DNL Marketo Measure] 将忽略来自该域的任何流量，并且不会创建接触点或其他数据。 [!DNL Marketo Measure] 还将确认域的禁用并警告结果：

![](assets/domain-management-3.png)

切换域的影响是立竿见影的，而且更改不具有追溯性。 未来， [!DNL Marketo Measure] 将在设置的时间段后从禁用的域中清除数据。

## 状态 {#statuses}

Admin Console状态分类如下：

* **已验证**:此域已在Admin Console中验证
* **未验证**:此域未在Admin Console中完全验证，并且不符合在中进行跟踪的条件 [!DNL Marketo Measure]
* **无效**:此域可能已过期或已从Admin Console中删除。 在中跟踪数据 [!DNL Marketo Measure] 已标记为删除
* **旧版**:此域是在 [!DNL Marketo Measure] 和不存在于Admin Console中

跟踪状态可以如下所示：

* **活动**: [!DNL Marketo Measure] 当前正在从此域接收数据
* **已禁用**:此域可用于跟踪，但当前已禁用
* **不可用**:此域不可用于跟踪，因为它未验证

将鼠标悬停在任何单个状态项目上将触发工具提示，进一步说明该状态。

## 常见问题解答 {#faq}

**在Admin Console中删除域后会发生什么情况？**

在Admin Console中删除域时， [!DNL Marketo Measure] 会将域标记为已删除。 [!DNL Marketo Measure] 将立即停止跟踪此域上的流量，但不会删除之前收集的任何数据。

**为什么我无法启用域？**

此页面上不允许选择域的原因有多种。 如果Admin Console中未验证域，则该域在 [!DNL Marketo Measure]. 同样，如果该域由与当前域不同的Adobe组织拥有 [!DNL Marketo Measure] 租户，则可能无法选择。

**如何从此列表中删除域？**

如果域已关闭“已启用”开关， [!DNL Marketo Measure] 将忽略它，并从 [!DNL Marketo Measure]. 从中永久删除域 [!DNL Marketo Measure]，则必须在 [!DNL Marketo Measure]，然后将其从Admin Console中删除。
