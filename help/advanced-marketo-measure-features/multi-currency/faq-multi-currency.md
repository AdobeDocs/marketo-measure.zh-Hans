---
unique-page-id: 27656745
description: 常见问题解答（多货币） —  [!DNL Marketo Measure]
title: 常见问题解答（多货币）
exl-id: 1d0936fb-4e66-4877-98d2-32c678a7ef3e
feature: Multi-Currency
source-git-commit: 9f374537dd3690b5c904e2ac1933ff460dc66282
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 0%

---

# 常见问题解答（多货币） {#faq-multi-currency}

**如何知道要启用哪个功能位？**

请记住，此功能有两个不同的特征位。 两者均位于 [!UICONTROL General] “设置：多个货币和高级货币”中CRM部分的选项卡。 如果客户使用多种货币，则应启用多种货币；而如果客户使用，则可以启用附加功能位“高级货币” [!DNL Salesforce]的“高级货币管理”功能，用户可以在该功能中设置基于时间的兑换率范围。

Marketo Measure会自动从客户的CRM中提取货币设置。 不再需要在Marketo Measure中手动配置以匹配CRM。 可在“常规”页面中的“CRM”下找到货币设置。

**为什么我的广告帐户会向我发送警告消息？**

如果您的广告帐户可能包含来自不受支持的货币的货币，我们会在该帐户旁边显示一条警告消息。 如果发生这种情况，您的仪表板将包含显示“混合货币”消息的磁贴。 我们建议您与CRM管理员合作，确保此未知货币在CRM中包含转化。

**我的仪表板图块上的“混合货币”表示什么？**

如果您的图块底部显示了“混合货币”消息，这意味着我们导入了一些成本，这些成本映射到我们未识别的货币。 由于我们的所有转化都必须来自具有实际转化率的CRM，这意味着您的CRM缺少该货币。 我们建议您与CRM管理员合作，确保此未知货币在CRM中包含转化。

**如何添加新的货币或兑换率？**

声明新货币或兑换率只能在 [!DNL Salesforce] 或 [!DNL Dynamics] 因此这些价值观只有一个单一的真实来源。 一旦检测到新的货币或兑换率， [!DNL Marketo Measure] 将下载并提供给您。 我们不提供输入这些费率的区域。

**货币显示格式不正确。 如何更改此设置？**

我们理解，有些国家有不同的格式设置金额（例如，1,234.00、1.234、1 234）。 但如果我们不仅要确定用户的货币，还要确定他们的原籍国，那就会引入另一个层面的复杂性，因为不同的国家和货币可以有不同的处理方式。 我们选择的一致格式为1,234.00。无法更改此设置。

**为什么不能显示我所选货币的货币符号？**

[!DNL Salesforce] 和 [!DNL Dynamics] 使用3个字母的转换代码显示其金额。 因此，为了保持一致性，我们转换后的金额还会显示为3个字母的转换代码，而不是符号。

**如果我的客户未启用多货币，他们会看到什么？**

如果客户没有多货币功能，我们将从CRM默认使用其货币区域设置，并更改以公司货币显示其支出和收入的所有ISO代码。 如果不正确，并且客户混合使用了货币，则解决方案是升级以获得多货币功能。

**此功能如何影响CRM中基于接触点的报表？**

对象 [!DNL Dynamics] 和 [!DNL Salesforce] 如果客户仅使用基本（非高级）货币管理，则应正确转换接触点收入额，因此CRM报表应按预期工作。

很遗憾，此功能对于用户的工作方式存在一些细微差别。 [!DNL Salesforce] 高级货币管理，由于长期限制 [!DNL Salesforce]. 对于“我们在此情况下应做什么”，简单的答案是，我们使用基本（即非高级）“管理货币”选项卡中定义的统一汇率来换算收入金额。 换言之，我们完全忽视了过期的汇率，尽管客户定义了过期的汇率。

对于感兴趣的读者来说，这是为什么它如此奏效。 我们的接触点使用公式字段计算收入（派生自关联的机会金额）。 [!DNL Salesforce] 这些公式计算本身支持货币转换，但仅支持其货币支持的基本用途。 我们不可能定义一个参考过时汇率的公式栏位。 [!DNL Salesforce] 根本不支持这种能力，因此我们在收入计算中无法引用过期的费率，尽管这些过期的费率存在于 [!DNL Salesforce] （这听起来很疯狂，但事情就是这样运行的。 ）

**如果我的客户使用工作流填充已转换的字段，以后应如何使用此字段？**

由于我们现在提供的产品将为客户处理转化，因此我们建议客户删除工作流和自定义字段，并允许我们导入其原始金额值。

>[!MORELIKETHIS]
>
>[错误通知](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
