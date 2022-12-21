---
unique-page-id: 18874781
description: 通过归因配置双击营销活动管理器视图 —  [!DNL Marketo Measure]  — 产品文档
title: 通过归因配置Doubleclick Campaign Manager视图
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# 通过归因配置Doubleclick Campaign Manager视图 {#configuring-doubleclick-campaign-manager-view-through-attribution}

## 通过归因测量视图 {#measuring-view-through-attribution}

>[!NOTE]
>
>如果您使用 [!DNL Marketo Measure] 和DoubleClick Campaign Manager集成，我们需要 [API连接](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) 这样，我们就可以下载营销活动和创意的详细信息来解析广告。

要开始通过Doubleclick Campaign Manager进行跟踪，从视图到视图获得更精细的洞察信息，需要配置我们的跟踪像素。

请 [单击此处](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md) 以了解有关 [!DNL Marketo Measure] 通过归因功能查看。

[!DNL Marketo Measure] 被视为“猪背标记”，因为它是通过DCM广告标记发起的第三方调用。 背包标记不适用于图像标记，仅适用于iframe或javascript标记。 根据DCM支持，这种情况最近没有改变，而且一直是如此。 标准标记已于2017年10月2日被弃用，但不会影响 [!DNL Marketo Measure] 以跟踪展示次数。

如果您在DCM中利用父级和子级层次结构，则我们需要将我们的标记应用于所有级别以进行展示次数跟踪。

## 如何添加图像标记 {#how-to-add-the-image-tag}

您将将标记添加到广告商设置下的Doubleclick中，并且您将要创建展示事件标记。

1. 将以下代码添加为1x1图像像素。

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. 添加分隔符后，请按如下方式确认分隔符。 在应用标记后，此操作应会自动执行：

   v = %eadv! 展开广告商Id\
   a = %eaid! 展开广告Id\
   c = %ecid! 展开创作ID\
   s = %esid! 展开网站Id\
   p = %epid! 展开版面Id\
   m = %m匹配代码宏\
   n = %n随机数宏

   ![](assets/1.png)

## 常见问题解答 {#faq}

**问：图像标记是否安全？**

答：是的。 它不是JavaScript标记，而是图像标记。

**问：连接的用户需要哪些权限？**

答：dfatfrafficing， dfareporting， userinfo.email

**问：导入支出数据需要多长时间？**

答：最多6小时

**问：导入广告数据需要多长时间？**

答：最多6小时
