---
unique-page-id: 18874797
description: 添加 [!DNL Marketo Measure] 通过 [!DNL Google Tag Manager] - [!DNL Marketo Measure]  — 产品文档
title: 添加 [!DNL Marketo Measure] 通过 [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---

# 添加 [!DNL Marketo Measure] 通过 [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

安装 [!DNL Marketo Measure] javascript，我们强烈建议 [对剧本进行硬编码](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} 直接进入您的网站。 但是，如果这不可能，您也可以使用 [!DNL Google Tag Manager] (GTM)来加载 [!DNL Marketo Measure] JS。 请注意 [!DNL Marketo Measure] 通过GTM加载的JS容易出现滞后。 延迟会导致脚本加载时间延迟，这可能导致大约3-5%的表单提交丢失。

如果您决定通过GTM添加我们的脚本，请将 [!DNL Marketo Measure] 脚本，并确保前面没有同步脚本 [!DNL Marketo Measure] 标记，以减少GTM滞后带来的任何影响。

>[!NOTE]
>
>请使用此 [Google支持文章](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} 以了解更多。

## 如何添加 [!DNL Marketo Measure] 通过 [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. 打开GTM并添加 [!DNL Marketo Measure] 脚本。 确保选择 **[!UICONTROL Custom HTML tag]**.

1. 使用 [!DNL Marketo Measure] 并将其合并到容器中。

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. 单击 **[!UICONTROL Add a Firing Rule]** 以便让Google在 *所有页面*.

1. 转到左侧的“容器草稿概述”部分。 单击按钮以创建容器的新版本并发布更改。
