---
description: 面向Marketo Measure用户的自定义Campaign同步指南
title: 自定义Campaign同步
exl-id: 66f0e4e3-c1b6-443e-8ffa-06b67862b855
feature: Channels
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 1%

---

# 自定义Campaign同步 {#custom-campaign-sync}

现在，通过已安装的[!DNL Marketo Measure]包，您可以指定要作为合格接触点包含哪些营销活动。 与以前一样，这方面存在多个障碍。 在CRM中安装[!DNL Marketo Measure]包后，您的安全团队批准该包可能需要一些时间。 此外，在Campaign对象中使用单个选取列表时缺乏灵活性。 使用此新功能，无需安装软件包，即可开始使用Campaign和Campaign成员记录。 可以构建规则以明确定义可以构建的记录以明确定义哪些记录符合条件。

## 要求 {#requirements}

* Campaign同步在所有层都可用
* 要导入数据，您仍需要将CRM连接到您的[!DNL Marketo Measure]帐户

## 工作原理 {#how-it-works}

1. 使用AccountAdmin权限，您可以导航到&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Campaigns]**，并查看同步促销活动成员规则UI。
1. 单击&#x200B;**+**&#x200B;图标开始创建规则。

   ![1. 单击+图标开始创建规则。](assets/offline-channels-1.png)

1. 您可以选择从[!UICONTROL Campaign]或[!UICONTROL Campaign Member]字段创建规则。 使用我们应验证的运算符和值填写规则的其余部分。 在下面的示例中，我们将按名称检查特定Campaign。

   ![1. 您可以选择从Campaign](assets/offline-channels-10.jpg)创建规则

   >[!NOTE]
   >
   >公式字段不能在规则中使用，也不会显示在选择列表中。 由于公式在后台计算且不会修改记录，因此[!DNL Marketo Measure]无法检测记录是否符合规则。

1. 选择接触点日期。 输入大括号`{`后，将显示可能日期的列表 — 然后，您可以选择要应用于通过规则创建的所有接触点的日期。

   ![1. 选择接触点日期。 将显示可能的日期列表](assets/offline-channels-11.png)

   >[!NOTE]
   >
   >如果您使用自定义Campaign同步规则，[!DNL Marketo Measure]将不会读取您使用“批量更新接触点日期”按钮所做的任何更新。

1. 单击复选标记，然后根据需要为其他营销活动添加其他规则。

   ![1. 单击复选标记，然后将其他营销活动的其他规则添加为](assets/offline-channels-12.png)

   >[!NOTE]
   >
   >现在，规则已与CRM同步一起定义，声明的规则自然将开始冲突。 如果选择继续使用自定义Campaign同步&#x200B;_和_ CRM同步类型，请务必创建规则，以免忽略您的CRM同步类型。

   ![现在，规则已与CRM同步一起定义，即](assets/offline-channels-13.png)的规则

   >[!NOTE]
   >
   >如果您考虑最终停止[!UICONTROL CRM Sync Type]的用户，则最好创建不引用“同步类型”但&#x200B;_仍然_&#x200B;保留当前CRM接触点的规则。 这样，当进行切换时，规则仍然有效。

下面是一个示例，其中显示了任何现有的CRM接触点都不会丢失：

## 验证 {#validation}

您可以在Campaign中轻松检查买方接触点和Buyer Attribution Touchpoint记录，以确保规则正常工作。 这是[!DNL Marketo Measure]使用适当的动态接触点日期创建的BAT，从营销活动中提取。 “创建日期”字段位于其下图。

![您可以轻松检查购买者接触点和Buyer Attribution Touchpoint记录](assets/offline-channels-14.png)

## 测试 {#testing}

1. Campaign同步功能附带测试功能，以便您检查已创建的规则是否实际符合Campaign条件。 单击[!UICONTROL Test]按钮开始。 必须先保存规则，然后才能开始测试。

   ![1. Campaign同步功能具有测试功能，因此](assets/offline-channels-15.jpg)

   此时将显示一个弹出窗口，您可以在其中输入营销活动ID（CRM中的15或18个字符）以进行测试。 关键是输入您尝试同步的CRM中的促销活动ID，以确保该ID与您创建的规则相匹配。

   ![将显示一个弹出窗口，您可以在其中输入促销活动ID （或](assets/offline-channels-16.png)）

1. 单击[!UICONTROL Test]后，您将看到符合接触点条件的营销活动名称和营销活动成员数量。 下表将显示与您的促销活动ID匹配的所有规则。 只显示匹配项。

   ![1. 单击“测试”后，您会看到](assets/offline-channels-17.png)的名称

1. 您还可以单击成员数以查看属于Campaign规则资格的销售线索和联系人及其ID的列表。 这只是一个示例集，最多可显示50个记录，以便您了解哪些记录符合条件。

   ![1. 您还可以单击“成员数”查看列表](assets/offline-channels-18.jpg)
