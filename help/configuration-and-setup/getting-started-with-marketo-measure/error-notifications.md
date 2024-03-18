---
description: 错误通知 —  [!DNL Marketo Measure]
title: 错误通知
feature: Fundamentals
exl-id: ed07eed6-ddeb-4856-a1ac-ea3d571283f6
source-git-commit: 2b13a518d1be768a5c312ea4abdf2039aa22cf08
workflow-type: tm+mt
source-wordcount: '1675'
ht-degree: 0%

---

# 错误通知 {#error-notifications}

以下是您可以通过应用程序内通知或电子邮件收到的错误列表。 如果收到其中的任何信息，请按照相应的故障诊断步骤操作。 如果这些步骤不能解决问题，请联系 [Marketo支持](https://nation.marketo.com/t5/support/ct-p/Support).

<table>
  <tbody>
    <tr>
      <th style="width:31%">错误代码</th>
      <th style="width:23%">通知示例</th>
      <th style="width:23%">描述</th>
      <th style="width:23%">疑难解答步骤</th>
    </tr>
    <tr>
      <td>API已禁用</td>
      <td>Crm导入期间出错： API_DISABLED ：已为此用户禁用API调用</td>
      <td>已为Marketo Measure用户禁用API权限。</td>
      <td>请参阅以下Salesforce文档，了解有关 <a href="https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.branded_apps_commun_api_permset.htm&amp;type=5">如何启用API访问</a>.</td>
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
            <li>导航到 <b>设置</b> &gt; <b>CRM</b> &gt; <b>常规</b></li>
            <li>更新每日CRM API限制<br/>
              <ul>
                <li><b>注意：默认值为100,000</b></li>
              </ul>
            </li>
          </ul>
          <p>
           <img src="assets/error-notifications-1.png">
          </p>
      </td>
    </tr>
    <tr>
      <td>CANNOT_EXECUTE_FLOW_TRIGGER</td>
      <td>Crm导出期间出错： CANNOT_EXECUTE_FLOW_TRIGGER ：实体类型“Contact”为Salesforce管理员提供这些详细信息。
限制已超过您或您的组织已超过此功能的最大限制。 错误ID：123456</td>
      <td>无法保存记录，因为它不符合Salesforce组织中设置的触发器流规则。</td>
      <td>查看通知消息的完整详细信息，并在Salesforce组织中查看流量触发器。
Salesforce有关流触发器的文档 <a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">可在此处找到</a>.
      </td>
    </tr>
    <tr>
      <td>CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY</td>
      <td>在Crm导出期间出错：CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY ：实体类型“潜在客户”：CRM错误代码：CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY，CRM错误消息：System.LimitException：超出顶级CPU时间限制，记录ID：0123456
      <p>
      在Crm导出期间出错： CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY ：实体类型“帐户”： CRM错误代码： CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY， CRM错误消息：无法更新实体类型：帐户，记录ID： 0123456</td>
      <td>触发器阻止更新或插入对象。
      <p>
      或者
      <p>
      缺少对象的权限。</td>
      <td>查看导致插入/更新失败的触发器代码。 有关触发器的更多详细信息，请参阅以下Salesforce文档：
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.code_manage_triggers.htm&amp;type=5">Apex触发器</a>
          </li>
          <li><a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">流量触发器</a>
          </li>
        </ul>
        <p>
        为提供所有必要的权限 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Marketo Measure用户</a>.
      </td>
    </tr>
    <tr>
      <td>DUPLICATES_DETECTED</td>
      <td>在Crm导出期间出错： DUPLICATES_DETECTED ：实体类型“Contact”： CRM错误代码： DUPLICATES_DETECTED， CRM错误消息：您正在创建重复记录。 我们建议您改用现有记录。，RecordId： 0123456</td>
      <td>要导入到Salesforce组织的记录已存在。</td>
      <td>
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">禁用“重复规则”设置</a> 以允许重复项。
          </li>
          <li>从排除Marketo Measure专用用户 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自定义验证规则</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>DUPLICATE_VALUE</td>
      <td>在Crm导出期间出错： DUPLICATE_VALUE ：实体类型“潜在客户”： CRM错误代码： DUPLICATE_VALUE， CRM错误消息：发现重复值： Email_Unique__c重复记录ID为123、记录ID为456的值</td>
      <td>要导入到Salesforce组织的字段不允许存在重复值。</td>
      <td>
        <ul>
          <li>取消选中 <a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">“唯一复选框”</a> 在Salesforce中。
          </li>
          <li>从排除Marketo Measure专用用户 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自定义验证规则</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>ENTITY_IS_LOCKING</td>
      <td>在Crm导出期间出错：ENTITY_IS_LOCKED ：实体类型“帐户”： CRM错误代码：ENTITY_IS_LOCKED，CRM错误消息：此记录已锁定。 如果您需要编辑它，请联系您的管理员。， RecordId： 0123456</td>
      <td>当记录处于审批流程中，并且非当前审批者或系统管理员的用户尝试编辑该记录时。</td>
      <td>
        <ul>
          <li>解决Salesforce组织中该记录的未决批准流程。</li>
          <li>从排除Marketo Measure专用用户 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自定义验证规则</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>FIELD_FILTER_VALIDATION_EXCEPTION</td>
      <td>在Crm导出期间出错：FIELD_FILTER_VALIDATION_EXCEPTION ：实体类型“潜在客户”：CRM错误代码：FIELD_FILTER_VALIDATION_EXCEPTION，字段：User__C，CRM ErrorMessage：值不存在或与筛选条件不匹配。 请选择角色为“Account Executive， Inside Sales”的用户；RecordId： 0123456</td>
      <td>修改后的记录不再满足对象上定义的查找过滤器。</td>
      <td>检查Marketo Measure尝试修改的对象上的筛选器。 请参阅 <a href="https://help.salesforce.com/s/articleView?id=000384756&amp;type=1">此Salesforce文章</a> 以了解如何检查对象上的筛选器。</td>
    </tr>
    <tr>
      <td>FIELD_INTEGRITY_EXCEPTION</td>
      <td>在Crm导出期间出错： FIELD_INTEGRITY_EXCEPTION ：实体类型“潜在客户”： CRM错误代码： FIELD_INTEGRITY_EXCEPTION，字段：国家/地区， CRM错误消息：该国家/地区存在问题，即使它看起来可能正确也是如此。 请从有效国家/地区列表中选择国家/地区。：国家/地区，记录ID：0123456</td>
      <td>记录的预期类型不匹配。</td>
      <td>这种情况的最常见情况不是遵循Salesforce组织中设置的州/国家/地区命名标准，因为“州/国家/地区”字段已经标准化，仅接受某些选择列表值。 要解决此问题，您可以：
        <ul>
          <li>更新记录以遵循组织对该字段的接受值。 请与SFDC管理员联系以获取接受值的列表。</li>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.admin_state_country_picklist_enable.htm&amp;type=5">禁用省/市/自治区选择列表</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INACTIVE_OWNER_OR_USER</td>
      <td>在Crm导出期间出错： INACTIVE_OWNER_OR_USER ：实体类型“联系人”： CRM错误代码： INACTIVE_OWNER_OR_USER， CRM错误消息：已将非活动用户[1234]作为联系人的所有者执行的操作，记录ID： 0123456</td>
      <td>Marketo Measure缺少“使用非活动所有者更新记录”权限。</td>
      <td>授予Marketo Measure "<a href="https://help.salesforce.com/s/articleView?id=000386699&amp;type=1">更新具有无效所有者的记录</a>”权限。</td>
    </tr>
    <tr>
      <td>UNFFECTED_ACCESS_OR_READONLY</td>
      <td>在Crm导出期间出错： UNSUPPORTED_ACCESS_OR_READONLY ：实体类型“Account”： CRM错误代码： UNSUPPORTED_ACCESS_OR_READONLY， CRM错误消息：对象ID的访问权限不足：[123]，记录ID： 456</td>
      <td>Marketo Measure缺少对象/字段的权限，或者该对象为只读。</td>
      <td>请参阅以下内容 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Experience League文章</a> 有关Marketo Measure所需的权限的指导。</td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>Adobe Analytics导出期间出错： INVALID_ANALYTICS_CONFIGURATION_INVALID_ADOBE：错误：不允许上传。 在上载之前确认数据源架构。 数据源Id：1234</td>
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
      <td>MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS</td>
      <td>在Crm导出期间出错： MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS ：实体类型“Campaign”： CRM错误代码： INVALID_FIELD_FOR_INSERT_UPDATE，字段： bizible2__UniqueId__c， CRM错误消息：无法创建/更新字段： bizible2__UniqueId__c。请检查此字段的安全设置，并验证是否为配置文件或权限集的读/写。</td>
      <td>Marketo Measure缺少bizible字段的权限。</td>
      <td>我们需要对以“bizible2__”为前缀的所有字段具有读写权限。 可以找到这些字段的完整列表 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">本文内容</a>.</td>
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
      <td>MISSING_RECORD_OBJECT_PERMISSIONS</td>
      <td>在Crm导出期间出错： MISSING_RECORD_OBJECT_PERMISSIONS ：实体类型“bizible2__Bizible_Touchpoint__c”： CRM错误代码： INFUNDER_ACCESS_ON_CROSS_REFERENCE_ENTITY，字段：帐户，CRM错误消息：交叉引用ID的访问权限不足：0123456</td>
      <td>Marketo Measure缺少权限。</td>
      <td>此错误有几个特定于Salesforce组织的原因。 以下是一些可以解决此问题的常见故障排除步骤：
        <ul>
          <li>查看我们为每个所需的全部权限 <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">对象和字段</a>.</li>
          <li>从排除Marketo Measure专用用户 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自定义验证规则</a>.</li>
          <li>授予Marketo Measure »<a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">全部修改</a>”权限。</li>
        </ul>
      </td>
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
      <td>RECORD_NON-COMPLIANT_WITH_VALIDATION_RULES</td>
      <td>在Crm导出期间出错：RECORD_NON-COMPLIANT_WITH_VALIDATION_RULES ：实体类型“销售线索”：CRM错误代码：FIELD_CUSTOM_VALIDATION_EXCEPTION，字段：Lead_Status_Reason__c，CRM错误消息：您必须选择销售线索状态原因，记录编号：0123456</td>
      <td>要更新的记录不符合Salesforce组织中设置的验证规则。</td>
      <td>从排除Marketo Measure专用用户 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自定义验证规则</a>.
      <p>
      更新您的 <a href="https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&amp;type=5">验证规则</a>.</td>
    </tr>
    <tr>
      <td>RESTRICT_PICKLIST_VALUES_ENABLED</td>
      <td>在Crm导出期间出错： RESTRICT_PICKLIST_VALUES_ENABLED ：实体类型“Campaign”： CRM错误代码： INVALID_OR_NULL_FOR_RESTRICTED_PICKLIST，字段： Aries_of_Interest__c， CRM错误消息：受限选取列表字段的值不正确：未知</td>
      <td>当在挑选列表字段的设置中启用“将挑选列表限制为值集中定义的值”时，或者插入到字段中的值在对象的记录类型中不可用。</td>
      <td>禁用Salesforce组织中的限制选取列表设置。
          <p>
          从排除Marketo Measure专用用户 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自定义验证规则</a>.
      </td>
    </tr>
    <tr>
      <td>REQUIRED_FIELD_MISSING</td>
      <td>在Crm导出期间出错： MISSING_REQUIRED_FIELD ：实体类型“潜在客户”： CRM错误代码： REQUIRED_FIELD_MISSING，字段： Product_Type__c， CRM ErrorMessage：必填字段缺失：[Product_Type__c]，记录ID： 0123456</td>
      <td>当验证规则指定对象需要字段时。</td>
      <td>从排除Marketo Measure专用用户 <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">自定义验证规则</a>.
      </td>
    </tr>
    <tr>
      <td>未知异常</td>
      <td>在Crm导出期间出错：UNKNOWN_EXCEPTION ：实体类型“Contact”：CRM错误代码：UNKNOWN_EXCEPTION、CRM错误消息：门户用户不能拥有合作伙伴帐户，记录ID：0123456</td>
      <td>Salesforce中发生了未处理的异常。</td>
      <td>如果问题仍然存在，请向Salesforce提交案例，并复制错误消息中的数值。</td>
    </tr>
    <tr>
      <td>不支持的_CRM_PACKAGE_VERSION</td>
      <td>Crm导入期间出错：UNSUPPORTED_CRM_PACKAGE_VERSION ：更新您的CRM包</td>
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
