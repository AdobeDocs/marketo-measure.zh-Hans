---
unique-page-id: 18874716
description: 归因映射方法 —  [!DNL Marketo Measure]  — 产品文档
title: 归因映射方法
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# 归因映射方法 {#attribution-mapping-methodology}

归因映射方法是在您的CRM（联系人、机会、帐户）中查找特定对象以将归因接触点创建到关联的机会的过程。 换句话说，是 [!DNL Marketo Measure] 了解基于您当前CRM流程在归因模型中包含哪些接触点的方式。

## 帐户ID映射 {#account-id-mapping}

开箱即用， [!DNL Marketo Measure] 提供帐户ID映射。 这意味着 [!DNL Marketo Measure] 查看帐户及其联系人营销信息，以创建与该商机关联的归因接触点。 下面是该过程的简单表示。

![](assets/1-1.png)

请记住 **不全** 您联系人的接触点将作为归因接触点推送到Opportunity中。 Opportunity的时间表（首次接触日期 — 结束日期）将确定接触点是否将计为Opportunity的影响者。 因此，如果在Opportunity关闭成功/丢失后，Contact A上的接触点发生， [!DNL Marketo Measure] 不会将该接触点推送到Opportunity。 在所有其他归因对象映射中，将遵循此时间轴过程。

优点：这种归因方法对大多数公司都非常有效。 营销团队无需依赖销售团队将所有联系人与特定机会关联（这通常是一个问题）。 此外，即使销售团队关联联系角色，也可能会遗漏其他许多联系人与营销材料的交互。 最后，这种方法有助于旨在影响账户总数而非具体影响者的反导战略。

缺点：如果有强大的营销和销售SLA来定义谁应该获得什么信用，则此方法可能会出现问题。 此外，如果人员不使用帐户层次结构来定义较大帐户内的特定业务单位(例如：IBM)，则特定于某个业务部门的营销互动可能会在其他业务部门机会之间传播。

## 机会联系人角色映射 {#opportunity-contact-role-mapping}

虽然大多数客户都使用帐户ID映射， [!DNL Marketo Measure] 能够查找Opportunity中的联系人角色（与Opportunity关联的联系人）以划分归因过程。 这意味着 [!DNL Marketo Measure] 将仅将与Opportunity上的联系角色关联的营销互动作为Buyer Attribution接触点推送。 下面是此过程的表示形式。

![](assets/2-1.png)

优点：如果您的团队具有定义非常明确的联系角色流程，则此类归因映射可能非常适合您。 它将有助于更好地协调销售和营销，因为每个人都会完全了解归因的划分方式。 当组织针对大型公司内的多个业务部门以及同时销售不同产品时，此过程也非常有用。

缺点：但是，如果没有建立联系角色流程，营销将丢失大量营销数据，并且团队最终会因他们影响销售机会的营销工作而收到的信用将大大降低。

## 机会主要联系人角色映射 {#opportunity-primary-contact-role-mapping}

除了简单地查看机会上的联系人角色， [!DNL Marketo Measure] 可以更集中地查看Opportunity上的主要联系人。 考虑到这个安排， [!DNL Marketo Measure] 将仅获取与某个机会上的主要联系人关联的营销接触点，并将该信息推送到该特定机会的归因故事中。 请参阅下图。

![](assets/3.png)

优点：如果您的团队只希望了解对在业务机会中设置为“主要”的联系人的营销影响，则此类映射将最适合团队。

缺点：这无疑是最不常用的测绘过程，并且极大地削弱了营销影响力，而这种影响正在让其他人有机会接触。
