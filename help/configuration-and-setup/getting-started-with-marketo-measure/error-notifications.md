---
description: 错误通知 —  [!DNL Marketo Measure]  — 产品文档
title: 错误通知
feature: Fundamentals
source-git-commit: 969cb2b4fb85aeb5c3a3aa21ead3eb5f4ff15ad9
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---

# 错误通知 {#error-notifications}

以下是您可以通过应用程序内通知或电子邮件收到的错误列表。 如果您收到其中的任何信息，请按照相应的故障排除步骤操作。 如果这些步骤不能解决问题，请联系 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support).

<table>
  <tbody>
    <tr>
      <th>错误代码</th>
      <th>通知示例</th>
      <th>描述</th>
      <th>疑难解答步骤</th>
    </tr>
    <tr>
      <td>API已禁用</td>
      <td>Crm导入期间出错： API_DISABLED ：已为此用户禁用API调用</td>
      <td>已为Marketo Measure用户禁用API权限。</td>
      <td>请参阅以下Salesforce文档，了解有关 <a href="https://help.salesforce.com/s/articleView?id=sf.branded_apps_commun_api_permset.htm&amp;type=5">如何启用API访问</a>.</td>
    </tr>
    <tr>
      <td>API_LIMIT_EXCEEDED</td>
      <td>Crm导出期间出错：PI_LIMIT_EXCEEDED</td>
      <td>已超出CRM的API限制（24小时）。</td>
      <td>有关调整API信用分配的帮助，请参阅以下CRM文档：</p>
          <ul>
            <li><a href="https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/service-protection-monitoring">动态</a>
            </li>
            <li><a href="https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm">Salesforce</a>
            </li>
          </ul>
          <p>您还可以按照以下步骤调整Marketo Measure使用的CRM积分：</p>
          <ul>
            <li>导航到CRM → General→设置</li>
            <li>更新每日CRM API限制<br/>
              <ul>
                <li><b>注意</b>：默认值为100,000</li>
              </ul>
            </li>
          </ul>
          <p>
            屏幕快照
          </p>
      </td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>AdobeAnalytics导出期间出错： INVALID_ANALYTICS_CONFIGURATION_ADOBE：错误：不允许上传。 请先确认数据源架构，然后再上传。 数据源Id：1234</td>
      <td>Adobe Analytics集成配置不正确。</td>
      <td>请参阅以下帮助文章以确保正确配置：
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Marketo Measure与Adobe Analytics的集成</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html">创建客户属性来源并上传数据文件</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INVALID_CURRENCY_ISO_CODE</td>
      <td>广告导入期间出错： INVALID_CURRENCY_ISO_CODE： Marketo Measure不支持货币XXX。
      <p>
      广告导入期间出错： INVALID_CURRENCY_ISO_CODE ： Marketo Measure不支持帐户1234的货币XXX。</td>
      <td>遇到不受支持的货币。</td>
      <td>在通知(Ad、Crm、Marketo)中指示的源系统中，确保与记录关联的货币具有受支持的有效货币。 支持的货币源自ISO货币标准。</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Crm导出期间出错： MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure缺少“查看/编辑已转换的潜在客户”权限</td>
      <td>有关在CRM中启用此权限的相关帮助，请参阅以下Experience League文档<br/>
          <a href="/help/marketo-measure-salesforce-reporting/additional-functionality/enabling-the-permission-to-edit-converted-leads.md">启用该权限以编辑已转换的潜在客户</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>Crm导入期间出错： MISSING_FIELD_READ_PERMISSION ：实体类型“Event”： INVALID_FIELD：<br/>
    SystemModstamp，IsDeleted，WhoId，bizible2__Bizible_Touchpoint_Date__c</td>
      <td>Marketo Measure缺少对必填字段的读取权限。</td>
      <td>有关Marketo Measure所需的权限的指导，请参阅以下帮助文章：
        <ul>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">动态</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_ISREPLICATEABLE_PERMISSION</td>
      <td>Crm导入期间出错： MISSING_ISREPLICATEABLE_PERMISSION ：我们缺少Campaign的IsReplicateable权限</td>
      <td>我们需要在Salesforce对象上获得此权限，我们才能使您的Marketo Measure和Salesforce保持同步。</td>
      <td>请联系Salesforce支持人员，以获取设置对象的可复制权限方面的帮助。</td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_READ_PERMISSION</td>
      <td>Crm导入期间出错： MISSING_OBJECT_READ_PERMISSION ：实体类型Campaign'： CRM错误代码： MISSING_PERMISSION</td>
      <td>Marketo Measure缺少对所需对象的读取权限。</td>
      <td rowspan="2">有关Marketo Measure所需的权限的指导，请参阅以下帮助文章：
          <ul>
            <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">动态</a>
            </li>
            <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
            </li>
          </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_WRITE_PERMISSION</td>
      <td>Crm导出期间出错： MISSING_OBJECT_WRITE_PERMISSION ：实体类型“bizible2_Bizible_Attribution_Touchpoint”： CRM错误代码： MISSING_PERMISSION</td>
      <td>Marketo Measure缺少对所需对象的写入权限。</td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          在Crm导入期间出错：NULL_EMPTY_CURRENCY_ISO_CODE：为RecordId 1234启用MultiCurrency时，货币ISO代码为NULL或为空
      </td>
      <td>货币必须是受支持的ISO货币代码。</td>
      <td>在通知(Ad、Crm、Marketo)中指示的源系统中，确保与记录关联的货币具有受支持的有效货币。 支持的货币源自ISO货币标准。</td>
    </tr>
    <tr>
      <td>OPERATION_TO_LARGE</td>
      <td>Crm导入期间出错：OPERATION_TOO_LARGE ：我们需要“查看所有数据”权限才能成功查询活动。</td>
      <td>CRM设置不允许Marketo Measure查询足够大的数据集</td>
      <td>授予Marketo Measure对指定对象的“查看所有数据”权限。
      <p>
      有关“查看所有数据”权限的更多信息 <a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">可在此处找到</a>.</td>
    </tr>
    <tr>
      <td>不支持的_CRM_PACKAGE_VERSION</td>
      <td>Crm导入期间出错：UNSUPPORTED_CRM_PACKAGE_VERSION ：请更新您的CRM包</td>
      <td>不再支持检测到的当前包。</td>
      <td>将您的包升级到最新版本：
        <ul>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/best-practices-for-marketo-measure-crm-package.md">最佳实践</a>
          </li>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md">动态</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
