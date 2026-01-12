---
description: Marketo Measure归因模型
title: Marketo Measure归因模型
exl-id: d8f76f29-e7c9-4b2d-b599-e80fd93c4687
feature: Attribution
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 0%

---


# Marketo Measure归因模型 {#marketo-measure-attribution-models}

Marketo Measure提供六种类型的归因模型：

* 首次接触
* 潜在客户创建
* U型
* W型
* 完整路径
* 自定义模型

这些模型的复杂性各异。 首次接触和潜在客户创建是简单的单接触模型。 其余4种是更复杂的多点接触模型。 Marketo Measure归因模型的结构反映了客户历程中出现的四个主要接触点：

* 首次联系（英尺）
* 商机创建(LC)
* 机会创建(OC)
* 非公开交易(CW)

![客户历程时间线显示四个里程碑接触点：首次联系、潜在客户创建、商机创建以及成功闭关](assets/1-1.png)

在&#x200B;**单次接触模型**中，归因点数仅归因于一个里程碑接触点，因此名称为“单次接触”。
在**多点接触模型**&#x200B;中，大多数归因点数分配给两个或更多里程碑接触点。 剩余的点数归于里程碑接触点之间的接触点。

接下来的几个部分介绍了每个归因模型以及归因点数的分配方式。

## 单触点模型 {#single-touch-models}

**首次联系模型**

首次联系模型仅关注商机与您的组织的首次交互。 此模型将100%的归因点数归因于商机首次了解您的公司情况，即首次联系(FT)。

假设Kate第一次通过Adwords广告访问`www.adobe.com`并查看白皮书。 Adwords渠道将从该Opportunity接收100%的归因点数。

![首次联系模型图显示了100%归因点数到Adwords渠道](assets/2.png)

**潜在客户创建模型**

当潜在客户提供其联系信息并成为潜在客户时，“Lead Creation”模型会将归因点数的100%归因于LC接触点。

继续上一个示例，在Kate首次通过Adwords访问`www.adobe.com`后，Austin通过Linkedin帖子访问该网站。 奥斯汀填写表格并成为销售线索。 在此模型中，Linkedin将获得100%的归因点数。

![潜在客户创建模型图显示了LinkedIn渠道的100%归因点数](assets/3.png)

## 多点触控模型 {#multi-touch-models}

多点触控模型适用于更长、更复杂的销售周期。 如果客户/公司的多个人员参与了购买者的历程，则这些模型特别有用。

**U形模型**

U形模型同时关注于FT和LC接触点。 在此模型中，英国《金融时报》和信用证接触点各自获得收入点数的50%。

Kate第一次通过Adwords广告访问`www.adobe.com`将获得50%的归因点数。 其余50%将被归属于迫使奥斯汀填写表格并成为潜在客户的领英帖子。

![U形模型图显示50%的点数归于Adwords，50%的点数归于LinkedIn](assets/4.png)

**W形模型**

三个里程碑接触点包含在W形模型中。 在此模型中，FT、LC和OC接触点分别归因于30%的归因点数。 其余10%按比例归属于三个里程碑接触点之间发生的任何中间接触点。

凯特和奥斯汀向同事希拉里提到了Marketo Measure。 她通过谷歌搜索找到一段内容，然后填写表格。 后来，奥斯汀收到了一封网络研讨会注册电子邮件，并填写了网站上的注册表。 Kate与销售代表谈到了Marketo Measure产品。

Hillary会收到一封包含定价页面链接的电子邮件，然后会访问该页面。 然后，为其帐户创建一个Opportunity。 Hillary对定价页的Web访问获得Opportunity Creation的点数，因为这是与Opportunity Creation日期最接近的营销交互。 每个里程碑接触点均分配了30%的归因点数，而中间接触点则分配了剩余10%的归因点数。

![W形模型图显示30%的点数分别归于FT、LC和OC接触点，10%归于中间接触点](assets/5.png)

**完整路径模型**

完整路径模型包含所有四个里程碑接触点。 FT、LC、OC和CW各获得22.5%的收入信用，其余10%在中间接触之间平均分配。

在机会创造之后，凯特、奥斯汀和希拉里决定将Marketo Measure推荐给他们的首席运营官伊丽莎白。 伊丽莎白出席由Marketo Measure主办的会议。 Kate在Linkedin上看到一篇关于案例研究的帖子，并填写表格下载内容。 伊丽莎白出席了Marketo Measure举办的一场销售晚宴。 晚饭后，她决定购买Marketo Measure并成为客户。 在这种情况下，销售晚餐将归入最终交易收入点数的22.5%。 FT、LC和OC接触点也各获得22.5%的点数。 中间接触点平均分配了剩余的10%收入点数。

![完整路径模型图显示为FT、LC、OC和CW接触点各有22.5%的点数，中间接触点各有10%的点数](assets/6.png)

**自定义归因模型**

Marketo Measure还提供了一个自定义归因模型，该模型允许用户选择要在其模型中包含的接触点或自定义阶段。 此外，用户能够控制归因到这些接触点和阶段的归因点数的百分比。 如果Opportunity没有专门的中间接触，则该百分比会平均分配到其他位置。
