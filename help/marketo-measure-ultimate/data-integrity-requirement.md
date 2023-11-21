---
description: ’[!DNL Marketo Measure] 最终数据完整性要求 —  [!DNL Marketo Measure]  — 产品文档'
title: ’[!DNL Marketo Measure] 终极数据完整性要求
hide: true
hidefromtoc: true
feature: Integration, Tracking, Attribution
source-git-commit: 89b50552455dbd4c9b60d101eaf6e1b0ff22c0c4
workflow-type: tm+mt
source-wordcount: '1465'
ht-degree: 18%

---

# [!DNL Marketo Measure] 最终数据完整性要求 {#marketo-measure-ultimate-data-integrity-requirement}

[!DNL Marketo Measure] 验证传入的AEP数据集，以确保数据充足且一致用于归因。 如果不满足数据完整性要求，则会导致数据集被拒绝 [!DNL Marketo Measure] 系统。 本文档详细说明数据完整性要求，提供数据检查的查询示例，并推荐具有空值的必填字段的解决方案。

## 实体对象 {#entity-object}

<table style="table-layout:auto">
  <tr>
    <th>XDM类</th>
    <th>XDM字段组</th>
    <th>XDM路径</th>
    <th>XDM类型</th>
    <th>数据源字段</th>
    <th>必需?</th>
    <th>备注</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>帐户</strong> (Marketo的Salesforce、公司和/或指定帐户帐户)</td>
    </tr>
    <tr>
      <td rowspan="6">XDM业务帐户</td>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>字符串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 123</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期时间</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期时间</td>
      <td>修改日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>XDM业务帐户详细信息</td>
      <td>帐户名称</td>
      <td>字符串</td>
      <td>名称</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>营销活动</strong> (Campaign for Salesforce、Marketo项目)</td>
    </tr>
    <tr>
      <td rowspan="8">XDM商业营销活动</td>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>字符串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 55555</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期时间</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期时间</td>
      <td>修改日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignName</td>
      <td>字符串</td>
      <td>名称</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignType</td>
      <td>字符串</td>
      <td>营销活动类型</td>
      <td>否</td>
      <td>用于渠道映射</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM商业营销活动详细信息</td>
      <td>channelname</td>
      <td>字符串</td>
      <td>频道名称</td>
      <td>否</td>
      <td>用于渠道映射</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignStartDate</td>
      <td>日期时间</td>
      <td>开始日期</td>
      <td>否</td>
      <td>对于促销活动成本</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignEndDate</td>
      <td>日期时间</td>
      <td>结束日期</td>
      <td>否</td>
      <td>对于促销活动成本</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.amount</td>
      <td>数字</td>
      <td>成本</td>
      <td>否</td>
      <td>对于促销活动成本</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.currencyCode</td>
      <td>
        <p>字符串</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>否</td>
      <td>对于促销活动成本</td>
    </tr>
    <tr>
      <td colspan="7"><strong>营销活动成员</strong> (Salesforce的Campaign成员，Marketo的项目成员)</td>
    </tr>
    <tr>
      <td rowspan="14">XDM商业营销活动成员</td>
      <td></td>
      <td>campaignMemberKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 987654321@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceID</td>
      <td>字符串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 987654321</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期时间</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期时间</td>
      <td>修改日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>字符串</td>
      <td>潜在客户ID或联系人ID</td>
      <td>是</td>
      <td>
        <p>例如 — 333，根据数据源表，这或者是Lead ID，或者是Contact ID。</p>
        <p>要潜在客户或联系人的外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>字符串</td>
      <td>营销活动ID</td>
      <td>是</td>
      <td>
        <p>例如 — 55555。</p>
        <p>营销活动外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM商业营销活动成员详细信息</td>
      <td>b2b.personType</td>
      <td>字符串</td>
      <td>“潜在客户”或“联系人”</td>
      <td>是</td>
      <td>根据数据源表，这应该设置为“潜在客户”或“联系人”。 对于大多数用例，我们建议将其设置为“联系”</td>
    </tr>
    <tr>
      <td></td>
      <td>memberstatus</td>
      <td>字符串</td>
      <td>状态</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>hasResponsed</td>
      <td>布尔值</td>
      <td>HasResponsed</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>firstRespondedDate</td>
      <td>日期时间</td>
      <td>FirstRespondedDate</td>
      <td>否</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>人员</strong> (Salesforce、Marketo人员的联系人或主管)</td>
    </tr>
    <tr>
      <td>XDM 配置文件</td>
      <td rowspan="11">XDM业务人员详细信息</td>
      <td>b2b.personKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceID</td>
      <td>字符串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 333，根据数据源表，这或者是商机ID，或者是联系人ID</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>workEmail.address</td>
      <td>
        <p>字符串</p>
        <p>电子邮件</p>
      </td>
      <td>电子邮件</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personStatus</td>
      <td>字符串</td>
      <td>状态</td>
      <td>是，仅适用于Lead personType</td>
      <td>仅当b2b.personType为“潜在客户”时才需要</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期时间</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期时间</td>
      <td>修改日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.isConverted</td>
      <td>布尔值</td>
      <td>IsConverted</td>
      <td>是，仅适用于Lead personType</td>
      <td>仅当b2b.personType为“潜在客户”时才需要</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personType</td>
      <td>字符串</td>
      <td>“潜在客户”或“联系人”</td>
      <td>是</td>
      <td>根据数据源表，这应该设置为“潜在客户”或“联系人”。 对于大多数用例，我们建议将其设置为“联系”</td>
    </tr>
    <tr>
      <td></td>
      <td>extendedWorkDetails.jobTitle</td>
      <td>字符串</td>
      <td></td>
      <td>否</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM业务人员组件</td>
      <td>personComponents.sourceAccountKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>否</td>
      <td>
        <p>例如 — 123@999-abc-888.Marketo。</p>
        <p>sourceAccountKey字段集仅对于真正的联系人记录“必填”，即定义为链接到帐户的人员记录。 缺少它不会导致数据集被拒绝，但归因结果将关闭。</p>
        <p>personComponents是一个数组，但Marketo Measure仅采用第一个元素personComponents[0]</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceID</td>
      <td>字符串</td>
      <td>帐户 ID</td>
      <td>否</td>
      <td>
        <p>例如 — 123。</p>
        <p>帐户的外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>否</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>否</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td colspan="7"><strong>机会</strong> (Opportunity for Salesforce， Opportunity for Marketo)</td>
    </tr>
    <tr>
      <td rowspan="13">XDM商业机会</td>
      <td></td>
      <td>opportunityKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>字符串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 77777</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期时间</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期时间</td>
      <td>修改日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>字符串</td>
      <td>帐户 ID</td>
      <td>是</td>
      <td>
        <p>例如 — 123。</p>
        <p>帐户的外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>机会名称</td>
      <td>字符串</td>
      <td>名称</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityStage</td>
      <td>字符串</td>
      <td>阶段</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityType</td>
      <td>字符串</td>
      <td></td>
      <td>否</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM业务机会详细信息</td>
      <td>isWon</td>
      <td>布尔值</td>
      <td>IsWon</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isClosed</td>
      <td>布尔值</td>
      <td>IsClosed</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>expectedCloseDate</td>
      <td>date</td>
      <td>关闭日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.amount</td>
      <td>数字</td>
      <td>数量</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.currencyCode</td>
      <td>
        <p>字符串</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>机会联系人角色（仅当计划使用机会联系人角色作为购买组进行归因时才需要）</strong></td>
    </tr>
    <tr>
      <td rowspan="16">XDM业务机会人员关系</td>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>字符串</td>
      <td>联系人ID</td>
      <td>是</td>
      <td>
        <p>例如 — 333。</p>
        <p>要联系的外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>isPrimary</td>
      <td>布尔值</td>
      <td>IsPrimary</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>字符串</td>
      <td>机会 ID</td>
      <td>是</td>
      <td>
        <p>例如 — 77777。</p>
        <p>机会的外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 222222@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceID</td>
      <td>字符串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 222222</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personRole</td>
      <td>字符串</td>
      <td>角色</td>
      <td>否</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期时间</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期时间</td>
      <td>修改日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>转换率(仅当使用多种货币时需要；只能将一个转换率数据集激活到Marketo Measure)</strong></td>
    </tr>
    <tr>
      <td rowspan="7">转化</td>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 8888@0x012345.Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceId</td>
      <td>字符串</td>
      <td>ID</td>
      <td>是</td>
      <td>例如 — 8888</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceInstanceId</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 0x012345</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>日期时间</td>
      <td>CreatedDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>日期时间</td>
      <td>修改日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isDeleted</td>
      <td>布尔值</td>
      <td></td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">货币兑换率详细信息</td>
      <td>conversionRate</td>
      <td>数字</td>
      <td>ConversionRate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>endDate</td>
      <td>date</td>
      <td>NextStartDate</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>startDate</td>
      <td>date</td>
      <td>开始日期</td>
      <td>是</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>sourceISOode</td>
      <td>字符串</td>
      <td>ISOCode</td>
      <td>是</td>
      <td>例如EUR</td>
    </tr>
    <tr>
      <td></td>
      <td>targetisocode</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>Marketo Measure中设置的默认货币代码，例如USD</td>
    </tr>
  </tbody>
</table>

## ExperienceEvent {#experienceevent}

<table style="table-layout:auto">
  <tr>
    <th>XDM类</th>
    <th>XDM字段组</th>
    <th>XDM路径</th>
    <th>XDM类型</th>
    <th>数据源字段</th>
    <th>必需?</th>
    <th>备注</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>活动</strong></td>
    </tr>
    <tr>
      <td rowspan="3">XDM ExperienceEvent</td>
      <td></td>
      <td>_ID</td>
      <td>字符串</td>
      <td>ID</td>
      <td>是</td>
      <td>是</td>
    </tr>
    <tr>
      <td></td>
      <td>事件类型</td>
      <td>字符串</td>
      <td>活动类型</td>
      <td>是</td>
      <td>是</td>
    </tr>
    <tr>
      <td></td>
      <td>时间戳</td>
      <td>日期时间</td>
      <td>活动日期</td>
      <td>是</td>
      <td>是</td>
    </tr>
    <tr>
      <td></td>
      <td>人员标识符</td>
      <td>personKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceID</td>
      <td>字符串</td>
      <td>潜在客户ID或联系人ID</td>
      <td>是</td>
      <td>
        <p>例如 — 333，根据数据源表，这或者是Lead ID，或者是Contact ID。</p>
        <p>要潜在客户或联系人的外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>是</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>添加到营销活动</td>
      <td>leadOperation.addToCampaign.campaignKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>仅对于leadOperation.addToCampaign类型为“是”</td>
      <td>例如 — 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceId</td>
      <td>字符串</td>
      <td>营销活动ID</td>
      <td>仅对于leadOperation.addToCampaign类型为“是”</td>
      <td>
        <p>例如 — 55555。</p>
        <p>营销活动外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceInstanceId</td>
      <td>字符串</td>
      <td></td>
      <td>仅对于leadOperation.addToCampaign类型为“是”</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>仅对于leadOperation.addToCampaign类型为“是”</td>
      <td>例如 — Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>营销活动进程中的状态已更改</td>
      <td>leadOperation.campaignProgression.campaignKey.sourceKey</td>
      <td>字符串</td>
      <td></td>
      <td>仅对于leadOperation.campaignProgression类型为是</td>
      <td>例如 — 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceId</td>
      <td>字符串</td>
      <td>营销活动ID</td>
      <td>仅对于leadOperation.campaignProgression类型为是</td>
      <td>
        <p>例如 — 55555。</p>
        <p>营销活动外键</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceInstanceId</td>
      <td>字符串</td>
      <td></td>
      <td>仅对于leadOperation.campaignProgression类型为是</td>
      <td>例如 — 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceType</td>
      <td>字符串</td>
      <td></td>
      <td>仅对于leadOperation.campaignProgression类型为是</td>
      <td>例如 — Marketo</td>
    </tr>
  </tbody>
</table>

## 支持的体验事件类型 {#experienceevent-type-supported}

<table style="table-layout:auto">
  <tr>
    <th>事件类型</th>
    <th>XDM事件类型</th>
    <th>描述</th>
  </tr>
  <tbody>
    <tr>
      <td>新建潜在客户</td>
      <td>leadOperation.newLead</td>
      <td>用于记录新营销商机的创建和详细信息</td>
    </tr>
    <tr>
      <td>转化商机</td>
      <td>leadOperation.convertLead</td>
      <td>当营销商机转化为分配给销售用户的符合销售条件的联系人时使用</td>
    </tr>
    <tr>
      <td>有趣的时刻</td>
      <td>leadOperation.interestingMoment</td>
      <td>用于跟踪潜在客户的高价值活动</td>
    </tr>
    <tr>
      <td>填写表单</td>
      <td>web.formFilledOut</td>
      <td>用于在人员填写网页上的表单时捕获详细信息</td>
    </tr>
    <tr>
      <td>取消订阅电子邮件</td>
      <td>directMarketing.emailUnsubscribed</td>
      <td>用于在人员取消订阅电子邮件时捕获详细信息</td>
    </tr>
    <tr>
      <td>打开电子邮件</td>
      <td>directMarketing.emailOpened</td>
      <td>用于在人员打开营销电子邮件时捕获详细信息</td>
    </tr>
    <tr>
      <td>单击电子邮件</td>
      <td>directMarketing.emailClicked</td>
      <td>用于在人员单击营销电子邮件中的链接时捕获详细信息</td>
    </tr>
    <tr>
      <td>进程中的更改状态</td>
      <td>leadOperation.statusInCampaignProgressionChanged</td>
      <td>用于在营销活动中的商机状态发生变化时捕获详细信息</td>
    </tr>
    <tr>
      <td>添加到参与计划（添加到培养）</td>
      <td>leadOperation.addToCampaign</td>
      <td>用于将人员添加到特定营销活动。</td>
    </tr>
  </tbody>
</table>

对于上表中不支持的事件类型，请使用“有趣的时刻”事件类型。 添加自定义字段以指示子类型“有趣的时刻”。

## 数据检查的查询示例 {#query-examples-for-data-inspection}

以下列出了用于检查AEP数据湖中摄取的数据集的查询示例。 要对数据集使用这两个查询表名称，请将以下查询示例中的表名称替换为您实际的数据集表名称。

我们预计所有数量均为0。

对于personType字段，我们预计只有“潜在客户”或“联系人”值，并且没有空值。

对于所有“联系人”人员记录，我们希望有一个帐户外键。

对于“潜在客户”人员记录，帐户外键不存在并且不是必需的。 如果选择将“潜在客户”人员记录摄取为“联系人”人员记录（建议使用），则不需要此类人员记录上的“帐户”外键。

### XDM业务帐户 {#xdm-business-account}

```
select 'account source id', count(*) from salesforce_account where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_account where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_account where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_account where accountKey.sourceKey is null
union all
select 'account name', count(*) from salesforce_account where accountName is null
union all
select 'created date', count(*) from salesforce_account where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_account where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM商业营销活动 {#xdm-business-campaign}

```
select 'campaign source id', count(*) from salesforce_campaign where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign where campaignKey.sourceKey is null
union all
select 'campaign name', count(*) from salesforce_campaign where campaignName is null
union all
select 'created date', count(*) from salesforce_campaign where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM商业营销活动成员 {#xdm-business-campaign-member}

```
select 'campaign member source id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceId is null
union all
select 'campaign member source type', count(*) from salesforce_campaign_member where campaignMemberKey.sourceType is null
union all
select 'campaign member source instance id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceInstanceId is null
union all
select 'campaign member source key', count(*) from salesforce_campaign_member where campaignMemberKey.sourceKey is null
union all
select 'campaign source id', count(*) from salesforce_campaign_member where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign_member where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign_member where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign_member where campaignKey.sourceKey is null
union all
select 'person source id', count(*) from salesforce_campaign_member where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_campaign_member where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_campaign_member where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_campaign_member where personKey.sourceKey is null
union all
select distinct 'person type', b2b.personType from salesforce_campaign_member
union all
select 'member status', count(*) from salesforce_campaign_member where memberStatus is null
union all
select 'has responded', count(*) from salesforce_campaign_member where hasResponded is null
union all
select 'created date', count(*) from salesforce_campaign_member where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign_member where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM业务人员 {#xdm-business-person}

```
select 'person source id', count(*) from marketo_person where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_person where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_person where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_person where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from marketo_person where workEmail.address is null
union all
select 'Lead - person status', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from marketo_person
union all
select 'created date', count(*) from marketo_person where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from marketo_person where extSourceSystemAudit.lastUpdatedDate is null;
```

```
select 'person source id', count(*) from salesforce_contact where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_contact where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_contact where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_contact where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from salesforce_contact where workEmail.address is null
union all
select 'Lead - person status', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from salesforce_contact
union all
select 'account source id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM商业机会 {#xdm-business-opportunity}

```
select 'opportunity source id', count(*) from salesforce_opportunity where opportunityKey.sourceId is null
union all
select 'opportunity source type', count(*) from salesforce_opportunity where opportunityKey.sourceType is null
union all
select 'opportunity source instance id', count(*) from salesforce_opportunity where opportunityKey.sourceInstanceId is null
union all
select 'opportunity source key', count(*) from salesforce_opportunity where opportunityKey.sourceKey is null
union all
select 'account source id', count(*) from salesforce_opportunity where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_opportunity where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_opportunity where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_opportunity where accountKey.sourceKey is null
union all
select 'opportunity name', count(*) from salesforce_opportunity where opportunityName is null
union all
select 'opportunity stage', count(*) from salesforce_opportunity where opportunityStage is null
union all
select 'is won', count(*) from salesforce_opportunity where isWon is null
union all
select 'is closed', count(*) from salesforce_opportunity where isClosed is null
union all
select 'expected close date', count(*) from salesforce_opportunity where expectedCloseDate is null
union all
select 'opportunity amount', count(*) from salesforce_opportunity where opportunityAmount.amount is null
union all
select 'currency code', count(*) from salesforce_opportunity where opportunityAmount.currencyCode is null
union all
select 'created date', count(*) from salesforce_opportunity where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_opportunity where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM ExperienceEvent {#xdm-experienceevent}

```
select 'id', count(*) from marketo_activity where _id is null
union all
select 'event type', count(*) from marketo_activity where eventType is null
union all
select 'timestamp', count(*) from marketo_activity where timestamp is null
union all
select 'person source id', count(*) from marketo_activity where personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_activity where personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_activity where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_activity where personKey.sourceKey is null
union all
select 'addToCampaign campaign id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceId is null
union all
select 'addToCampaign campaign type', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceType is null
union all
select 'addToCampaign campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceInstanceId is null
union all
select 'addToCampaign campaign key', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceKey is null
union all
select 'statusInCampaignProgressionChanged campaign id', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceId is null
union all
select 'statusInCampaignProgressionChanged campaign type', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceType is null
union all
select 'statusInCampaignProgressionChanged campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceInstanceId is null
union all
select 'statusInCampaignProgressionChanged campaign key', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceKey is null;
```

```
select 'id', count(*) from salesforce_task where _id is null
union all
select 'event type', count(*) from salesforce_task where eventType is null
union all
select 'timestamp', count(*) from salesforce_task where timestamp is null
union all
select 'person source id', count(*) from salesforce_task where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_task where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_task where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_task where personKey.sourceKey is null;
```

### 转化 {#conversion}

```
select 'conversion rate', count(*) from currency_conversion_rate where conversionRate is null
union all
select 'end date', count(*) from currency_conversion_rate where endDate is null
union all
select 'start date', count(*) from currency_conversion_rate where startDate is null
union all
select 'source ISO Code', count(*) from currency_conversion_rate where sourceISOCode is null
union all
select 'target ISO Code', count(*) from currency_conversion_rate where targetISOCode is null
union all
select 'source id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceId is null
union all
select 'source type', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceType is null
union all
select 'source instance id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceInstanceId is null
union all
select 'source key', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

## 具有NULL值的必填字段的建议解决方案 {#recommended-solution-for-required-fields-with-a-null-value}

我们建议在字段映射中使用计算字段将该字段默认为非NULL值。 以下是两个示例：

* 如果某些opportunity记录的opportunityName为null ，请在字段映射中创建并使用以下计算字段
   * `iif(name != null && name != "", name, "Unknown")`

* 如果某些experienceevent记录的leadOperation.campaignProgression.campaignID为空，请在字段映射中创建并使用以下计算字段
   * `iif(leadOperation.campaignProgression.campaignID != null && leadOperation.campaignProgression.campaignID != "" , to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", leadOperation.campaignProgression.campaignID, "sourceKey", concat(leadOperation.campaignProgression.campaignID,"@123-abc-321.Marketo")), iif(eventType == "leadOperation.statusInCampaignProgressionChanged", to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", "Unknown", "sourceKey", "Unknown@123-abc-321.Marketo"), null))`

