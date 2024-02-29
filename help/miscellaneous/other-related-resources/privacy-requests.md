---
description: 隐私请求 —  [!DNL Marketo Measure]
title: 隐私请求
exl-id: 883e475f-9868-412a-b505-230556f38484
feature: APIs, Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# 隐私请求 {#privacy-requests}

本文档概述如何管理可发送到的单个数据隐私请求 [!DNL Marketo Measure] 通过 [!DNL Privacy Service] UI和 **[!DNL Privacy Service]API**.

您可以提交单个请求，以从中访问和删除消费者数据 [!DNL Marketo Measure] 有两种方式：

* 通过 [[!DNL Privacy Service] UI](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target="_blank"}.
* 通过 **[!DNL Privacy Service]API**. 请参阅文档 [此处](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target="_blank"} and the API reference [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}.

此 [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"} 支持两种类型的请求：数据访问和数据删除。

我们来看看如何创建访问和删除请求。

## 发送Marketo Measure请求所需的设置 {#required-setup-to-send-requests-for-marketo-measure}

请求访问和删除以下项的数据： [!DNL Marketo Measure]，您必须：

1. 识别以下内容：

   a. IMS组织ID

   b.要执行操作的人员的电子邮件地址

   IMS组织ID是由24个字符组成的字母数字字符串，其后附加有@AdobeOrg。 如果您的营销团队或内部Adobe系统管理员不知道您组织的IMS组织ID，请通过gdprsupport@adobe.com联系Adobe客户关怀团队。 您需要IMS组织ID才能向隐私API提交请求。

1. 在 [!DNL Privacy Service]，您可以将访问和删除请求提交到 [!DNL Marketo Measure]，并检查现有请求的状态。

## 中的必填字段值 [!DNL Marketo Measure] JSON请求 {#required-field-values-in-marketo-measure-json-requests}

“companyContexts”：

* &quot;namespace&quot;： **imsOrgID**
* &quot;value&quot;： `<Your IMS Org ID Value>`

&quot;users&quot;：

* &quot;action&quot;： [!UICONTROL access] 或删除
* &quot;userIDs&quot;：
   * &quot;namespace&quot;：电子邮件
   * &quot;type&quot;：标准
   * &quot;value&quot;： `<Data Subject's Email Address>`

&quot;include&quot;：

* **marketoMeasure** (适用于该请求的Adobe产品)

“监管”：

* **gdpr**， **ccpa**， **pdpa**， **lgpd_bra**，或 **nzpa_nzl** （即适用于该请求的隐私法规）

## 示例1：GDPR删除请求 {#gdpr-delete-request}

JSON请求

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "delete"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "gdpr",
}
```

JSON响应

```text
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": [
            "delete"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```

## 示例二：CCPA访问请求 {#ccpa-access-request}

JSON请求

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "access"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "ccpa",
}
```

JSON响应

```text
{
  "requestId": "16329573462631890RX-207",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "3115e42d-011b-47ab-a2b0-ed4356af4d3e",
      "customer": {
        "user": {
          "action": [
            "access"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
