---
title: 带有 SIEM 解决方案的通信合规性
description: 了解与 SIEM 解决方案的通信合规性集成。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: d957b5fec4341cd7335f5c5a49b6654ffaf51f68
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111431"
---
# <a name="communication-compliance-with-siem-solutions"></a>带有 SIEM 解决方案的通信合规性

[通信合规性](communication-compliance.md)是组织中内部风险Microsoft 365，通过帮助你检测、捕获和操作组织中不适当的邮件，帮助最大程度地降低通信风险。 SIEM 安全信息和事件 (SIEM) 解决方案（如 Microsoft [Sentinel](https://azure.microsoft.com/services/azure-sentinel) 或 [Splunk）](https://www.splunk.com/) 通常用于聚合和跟踪组织内部的威胁。

组织常见的需要是集成通信合规性警报和这些 SIEM 解决方案。 通过此集成，组织可以在 SIEM 解决方案中查看通信合规性警报，然后在通信合规性工作流和用户体验中修正警报。 例如，员工向另一名员工发送冒犯性消息，并且通信合规性策略监控检测到该邮件包含不适当的内容。 这些事件通过通信合规性解决方案Microsoft 365审核 (称为"统一 审核日志") ，并导入 SIEM 解决方案。 然后，在组织的 SIEM 解决方案中，从与通信合规性警报Microsoft 365审核中监视的事件触发警报。 调查人员在 SIEM 解决方案中收到警报通知，然后调查并修正通信合规性解决方案中的警报。

## <a name="communication-compliance-alerts-in-microsoft-365-audit"></a>审核中的通信合规性Microsoft 365警报

所有通信合规性策略匹配项都捕获在Microsoft 365审核中。 以下示例显示所选通信合规性策略匹配活动的详细信息：

**"不审核日志策略模板匹配的条目示例：**

```xml
RunspaceId: 5c7bc9b0-7672-4091-a112-0635bd5f7732
RecordType: ComplianceSupervisionExchange
CreationDate: 7/7/2021 5:30:11 AM
UserIds: user1@contoso.onmicrosoft.com
Operations: SupervisionRuleMatch
AuditData: {"CreationTime":"2021-07-07T05:30:11","Id":"44e98a7e-57fd-4f89-79b8-08d941084a35","Operation":"SupervisionRuleMatch","OrganizationId":"338397e6\-697e-4dbe-a66b-2ea3497ef15c","RecordType":68,"ResultStatus":"{\\"ItemClass\\":\\"IPM.Note\\",\\"CcsiResults\\":\\"\\"}","UserKey":"SupervisionStoreDeliveryAgent","UserType":0,"Version":1,"Workload":"Exchange","ObjectId":"\<HE1P190MB04600526C0524C75E5750C5AC61A9@HE1P190MB0460.EURP190.PROD.OUTLOOK.COM\>","UserId":"user1@contoso.onmicrosoft.com","IsPolicyHit":true,"SRPolicyMatchDetails":{"SRPolicyId":"53be0bf4-75ee-4315-b65d-17d63bdd53ae","SRPolicyName":"Adult images","SRRuleMatchDetails":\[\]}}
ResultIndex: 24
ResultCount: 48
Identity: 44e98a7e-57fd-4f89-79b8-08d941084a35
IsValid: True
ObjectState: Unchanged
```

**自定义关键字Microsoft 365匹配策略的审核日志条目示例 (自定义敏感信息类型) ：**

```xml
RunspaceId: 5c7bc9b0-7672-4091-a112-0635bd5f7732
RecordType: ComplianceSupervisionExchange
CreationDate: 7/6/2021 9:50:12 PM
UserIds: user2@contoso.onmicrosoft.com
Operations: SupervisionRuleMatch
AuditData: {"CreationTime":"2021-07-06T21:50:12","Id":"5c61aae5-26fc-4c8e-0791-08d940c8086f","Operation":"SupervisionRuleMatch","OrganizationId":"338397e6\-697e-4dbe-a66b-2ea3497ef15c","RecordType":68,"ResultStatus":"{\\"ItemClass\\":\\"IPM.Note\\",\\"CcsiResults\\":\\"public\\"}","UserKey":"SupervisionStoreDeliveryAgent","UserType":0,"Version":1,"Workload":"Exchange","ObjectId":"\<20210706174831.24375086.807067@sailthru.com\>","UserId":"user2@contoso.onmicrosoft.com","IsPolicyHit":true,"SRPolicyMatchDetails":{"SRPolicyId":"a97cf128-c0fc-42a1-88e3-fd3b88af9941","SRPolicyName":"Insiders","SRRuleMatchDetails":\[{"SRCategoryName":"New insiders lexicon"}\]}}
ResultIndex: 46
ResultCount: 48
Identity: 5c61aae5-26fc-4c8e-0791-08d940c8086f
IsValid: True
ObjectState: Unchanged
```

> [!NOTE]
> 目前，在 Microsoft 365 审核中记录策略匹配的时间与调查通信合规性中的策略匹配项的时间之间可能最多存在 24 小时延迟。

## <a name="configure-communication-compliance-and-microsoft-sentinel-integration"></a>配置通信合规性和 Microsoft Sentinel 集成

使用 Microsoft Sentinel 聚合通信合规性策略匹配项时，Sentinel Microsoft 365 Audit 作为数据源。 若要将通信合规性警报与 Sentinel 集成，请完成以下步骤：

1. [载入到 Microsoft Sentinel](/azure/sentinel/quickstart-onboard)。 作为载入过程的一部分，您将配置数据源。
2. 配置 Microsoft Sentinel [Microsoft Office 365数据连接器，在](/azure/sentinel/data-connectors-reference#microsoft-office-365)连接器配置下，选择 *"Exchange"。*
3. 配置搜索查询以检索通信合规性警报。 例如：

    *|OfficeActivity |其中 OfficeWorkload == "Exchange" and Operation == "SupervisionRuleMatch" |按 TimeGenerated 排序*

    若要筛选特定用户，请使用以下查询格式：

    *|OfficeActivity |其中 OfficeWorkload == "Exchange" and Operation == "SupervisionRuleMatch" and UserId == "User1@Contoso.com" |按 TimeGenerated 排序*

有关 Microsoft Sentinel 收集Microsoft 365审核日志Office 365，请参阅[Azure Monitor Logs reference](/azure/azure-monitor/reference/tables/OfficeActivity)。

## <a name="configure-communication-compliance-and-splunk-integration"></a>配置通信合规性和 Splunk 集成

若要将通信合规性警报与 Splunk 集成，请完成以下步骤：

1. 安装[Splunk 加载项Microsoft Office 365](https://docs.splunk.com/Documentation/AddOns/released/MSO365/ConfigureinputsmanagementAPI)
2. 在 Azure AD 中为 Splunk 加载项配置集成Microsoft Office 365
3. 在 Splunk 解决方案中配置搜索查询。 使用以下搜索示例标识所有通信合规性警报：

    *index= \* sourcetype="o365：management：activity" Workload=Exchange Operation=SupervisionRuleMatch*

若要筛选特定通信合规性策略的结果，可以使用 *SRPolicyMatchDetails.SRPolicyName* 参数。

例如，以下搜索示例将返回与名为"不当内容"的通信合规性策略 *匹配的警报*：

  *index= \* sourcetype='o365：management：activity' Workload=Exchange Operation=SupervisionRuleMatch SRPolicyMatchDetails.SRPolicyName=\<Inappropriate content\>*

下表显示了不同策略类型的示例搜索结果：

| 策略类型 | 示例搜索结果 |
| :------------------ | :--------------------------------------- |
| 检测自定义敏感信息类型关键字列表的策略 | { <br> CreationTime：2021-09-17T16：29：57 <br> ID：4b9ce23d-ee60-4f66-f38d-08d979f8631f <br> IsPolicyHit： true <br> ObjectId： <CY1PR05MB27158B96AF7F3AFE62E1F762CFDD9@CY1PR05MB2715.namprd05.prod.outlook.com> <br> 操作：SupervisionRuleMatch <br> OrganizationId：d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType：68 <br> ResultStatus： {"ItemClass"："IPM.注意"，"CcsiResults"："leak"} <br> SRPolicyMatchDetails： { [+] } <br> UserId：user1@contoso.OnMicrosoft.com <br> UserKey：SupervisionStoreDeliveryAgent <br> UserType：0 <br> 版本：1 <br> 工作负载：Exchange <br> } |
| 策略检测不当语言 | { <br> CreationTime：2021-09-17T23：44：35 <br> ID：e0ef6f54-9a52-4e4c-9584-08d97a351ad0 <br> IsPolicyHit： true <br> ObjectId： <BN6PR05MB3571AD9FBB85C4E12C1F66B4CCDD9@BN6PR05MB3571.namprd05.prod.outlook.com> <br> 操作：SupervisionRuleMatch <br> OrganizationId：d6a06676-95e8-4632-b949-44bc00f0793f <br> RecordType：68 <br> ResultStatus：{"ItemClass"："IPM.Yammer。Message"，"CcsiResults"：""} <br> SRPolicyMatchDetails： { [+] } <br> UserId：user1@contoso.com <br> UserKey：SupervisionStoreDeliveryAgent <br> UserType：0 <br> 版本：1 <br> }  |

## <a name="configure-communication-compliance-with-other-siem-solutions"></a>配置与其他 SIEM 解决方案的通信合规性

若要从审核中检索通信合规性Microsoft 365匹配，可以使用 PowerShell 或[Office 365 管理 API。](/office/office-365-management-api/office-365-management-activity-api-reference)

使用 PowerShell 时，您可以将这些参数中的任一参数与 **Search-UnifiedAuditLog** cmdlet 一审核日志通信合规性活动筛选事件。

| 审核日志参数 | 通信合规性参数值 |
| :------------------ | :--------------------------------------- |
| 运营          | SupervisionRuleMatch                     |
| RecordType          | ComplianceSupervisionExchange            |

例如，下面是使用 **Operations** 参数和 *SupervisionRuleMatch* 值的示例搜索：

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch | ft CreationDate,UserIds,AuditData
```
下面是使用 **RecordsType** 参数和 *ComplianceSupervisionExchange* 值的示例搜索：

```powershell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType ComplianceSuperVisionExchange | ft CreationDate,UserIds,AuditData
```
## <a name="resources"></a>资源

- [通信合规性审核](communication-compliance-reports-audits.md#audit)
- [Microsoft 365 高级审核](advanced-audit.md)
- [Office 365 管理活动 API 参考](/office/office-365-management-api/office-365-management-activity-api-reference)
