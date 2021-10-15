---
title: Microsoft 365 审核解决方案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: 了解如何审核 Microsoft 365 组织中用户和管理员的活动。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 726aa84157b82b3f4a5ea6ddfe1fed9734b3991b
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "60363974"
---
# <a name="auditing-solutions-in-microsoft-365"></a>Microsoft 365 中的审核解决方案

Microsoft 365 审核解决方案提供集成解决方案，帮助组织有效响应安全事件、调查、内部调查和合规责任。 数千名 Microsoft 365 服务和解决方案中执行的用户和管理员操作被捕获、记录并保留在组织的统一审核日志中。 这些事件的审核记录通过安全运营、IT 管理员、预览体验计划团队以及合规与法律支持人员进行搜索。 此功能可跨 Microsoft 365 组织查看执行的活动。

## <a name="microsoft-365-auditing-solutions"></a>Microsoft 365 审核解决方案

Microsoft 365 提供两种审核解决方案：基本审核和高级审核。

![基本审核和高级审核的关键功能。](..\media\AuditingSolutionsComparison.png)

### <a name="basic-audit"></a>基本审核

通过基本审核，可以记录和搜索经审核的活动，并支持法务、IT、合规性和法律调查。

- **默认情况下启用**。 默认为具有适当订阅的所有组织启用基本审核。 这意味着将捕获并搜索经审核的活动的记录。 只需分配访问审核日志搜索工具（及相应 cmdlet）所需的权限，并确保用户获得使用高级审核功能的相应许可证。
- **数以千计的可搜索审计事件**。 可搜索组织中大多数 Microsoft 365 服务中经审核的活动。 有关可搜索的活动的部分列表，请参阅 [经审核活动](search-the-audit-log-in-security-and-compliance.md#audited-activities)。 有关支持经审核活动的服务和功能的列表，请参阅 [审核日志记录类型](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。
- **Microsoft 365 合规中心内审核**。 使用 Microsoft 365 合规中心中的审核日志搜索工具搜索审核记录。 可以搜索特定活动、特定用户执行的活动以及按日期范围发生的活动。 下面是合规中心中审核搜索工具的屏幕截图。

   ![Microsoft 365 合规中心的审核日志搜索工具。](../media/AuditLogSearchToolMCC.png)

- **Search-UnifiedAuditLog cmdlet**。你也可以在 Exchange Online PowerShell（搜索工具的基础 cmdlet）中使用 **Search-UnifiedAuditLog** cmdlet 来搜索审核事件或在脚本中使用。有关详细信息，请参阅：

  - [Search-UnifiedAuditLog cmdlet 参考](/powershell/module/exchange/search-unifiedauditlog)
  - [使用 PowerShell 脚本搜索审核日志](audit-log-search-script.md)

- **将审核记录导出为 CSV 文件**。 在合规中心内运行审核日志搜索工具后，可以将搜索返回的审核记录导出到 CSV 文件。 这将允许对不同的审核记录属性使用 Microsoft Excel 排序和筛选。 还可使用 Excel Power Query 转换功能将 AuditData JSON 对象中的每个属性拆分为其自己的列。 通过此操作可有效查看和比较不同事件的类似数据。 有关详细信息，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。

- **通过Office 365管理活动API访问审核日志**。 用于访问和检索审核记录的第三种方法就是使用 Office 365 管理活动 API。 这使组织可以审核数据超过默认 90 天的时间，并可以将其审核数据导入 SIEM 解决方案。 有关详细信息，请参阅 [Office 365 管理活动 API 参考](/office/office-365-management-api/office-365-management-activity-api-reference)。

- **90 天审核日志保留期**。 当用户或管理员执行审核活动时，将生成审核记录并将其存储在组织的审核日志中。 在基本审核中，记录将保留 90 天，这意味着可以搜索过去三个月内发生的活动。

### <a name="advanced-audit"></a>高级审核

高级审核以基本审核功能为基础，提供审核日志保留策略、较长的审核记录保留时间、高价值关键事件，以及对于 Office 365 管理活动 API 的更高带宽访问。

- **审核日志保留策略**。 可创建自定义审核日志保留策略，将审核记录保留更长一年（对于需要附加设备许可证的用户，最多保留 10 年）。 可创建一个策略，以保留基于被审核活动、经审核的特定活动或执行经审核活动的用户的服务的审核记录。

- **审核记录被延长的保留**。 默认情况下，Exchange、SharePoint 和 Azure Active Directory 审核记录将保留一年。 默认情况下，所有其他活动的审核记录将保留 90 天，或者可以使用审核日志保留策略来配置较长的保留期。

- **高价值、重要的高级审核事件**。 关键事件的审计记录可以帮助组织进行法务调查和合规调查，方法是提供事件的可见性，如访问邮件时间、回复和转发邮件时间、用户在 Exchange Online 和 Sharepoint Online 中搜索的时间和内容。 这些关键事件可以帮助你调查可能的违规行为，并确定泄露的范围。

- **Office 365管理活动API的更高带宽**。 高级审核为组织提供了更多的带宽来通过 Office 365 管理活动 API 访问审核日志。 虽然所有组织（具有基本审核或高级审核）最初都分配了每分钟 2000 个请求的基线，但根据组织的席位数及其许可订阅，此限制将动态增加。 这导致采用高级审核的组织获得的带宽是采用基本审核的组织的两倍。

有关高级审核功能的更多详细信息，请参阅 [365 高级审核](advanced-audit.md)。

## <a name="comparison-of-key-capabilities"></a>比较关键功能

下表比较了基本审核和高级审核中提供的关键功能。 高级审核包含所有基本审核功能。

|功能|基本审核|高级审核|
|:------|:-------------|:-------------|
|默认情况下启用|![支持。](../media/check-mark.png)|![支持。](../media/check-mark.png)|
|数千个可搜索的审核事件|![支持。](../media/check-mark.png)|![支持。](../media/check-mark.png)|
|Microsoft 365 合规中心的审核搜索工具|![支持。](../media/check-mark.png)|![支持。](../media/check-mark.png)|
|Search-UnifiedAuditLog cmdlet|![支持。](../media/check-mark.png)|![支持。](../media/check-mark.png)|
|将审核记录导出到 CSV 文件|![支持。](../media/check-mark.png)|![支持。](../media/check-mark.png)|
|通过 Office 365 管理活动 API <sup>1</sup> 访问审核日志|![支持。](../media/check-mark.png)|![支持。](../media/check-mark.png)</sup>|
|90 天审核日志保留|![支持。](../media/check-mark.png)|![支持。](../media/check-mark.png)|
|1 年审核日志保留期||![支持。](../media/check-mark.png)|
|10 年审核日志保留期 <sup>2</sup>||![受支持](../media/check-mark.png)|
|审核日志保留策略||![受支持](../media/check-mark.png)|
|高价值的、关键事件||![受支持](../media/check-mark.png)|
||||
> [!NOTE]
> <sup>1</sup> 高级审核包括更高的 Office 365 管理活动 API 访问带宽，可更快地访问审核数据。<br/><sup>2</sup> 除了高级审核所需的许可（下一节中介绍）外，必须为用户分配 10 年审核日志保留期的许可证，才能保留其审核记录 10 年。

## <a name="licensing-requirements"></a>许可要求

以下部分确定了基本审核和高级审核的许可要求。 高级审核中包括基本审核功能。

### <a name="basic-audit"></a>基本审核

- Microsoft 365 企业版 E3 订阅
- Microsoft 365 商业高级版
- Microsoft 365 教育版 A3 订阅
- Microsoft 365 政府版 G3 订阅
- Microsoft 365 政府版 G1 订阅
- Microsoft 365 Frontline F1 或 F3 订阅，或 F5 安全加载项
- Office 365 企业版 E3 订阅
- Office 365 企业版 E1 订阅
- Office 365 教育版 A1 订阅
- Office 365 教育版 A3 订阅

### <a name="advanced-audit"></a>高级审核

- Microsoft 365 企业版 E5 订阅
- Microsoft 365 企业版 E3 订阅 + Microsoft 365 E5 合规性附加内容
- Microsoft 365 企业版 E3 订阅 + Microsoft 365 E5 电子数据展示和审核附加项
- Microsoft 365 教育版 A5 订阅
- Microsoft 365 教育版 A3 订阅 + Microsoft 365 A5 合规性加载项
- Microsoft 365 教育版 A3 订阅 + Microsoft 365 A5 电子数据展示和审核加载项
- Microsoft 365 政府版 G5 订阅
- Microsoft 365 政府版 G3 订阅 + Microsoft 365 G5 合规加载项
- Microsoft 365 政府版 G3 订阅 + Microsoft 365 G5 电子数据展示和审核加载项
- Microsoft 365 Frontline F5 合规性或 F5 安全与合规加载项
- Office 365 企业版 E5 订阅
- Office 365 教育版 A5 订阅
- Office 365 企业版 E3 订阅和 Office 365 高级合规版附加设备（不再适用于新订阅）

## <a name="set-up-microsoft-365-auditing-solutions"></a>设置 Microsoft 365 审核解决方案

若要开始在 Microsoft 365 使用审核解决方案，请参阅以下设置指南。

### <a name="set-up-basic-audit"></a>设置基本审核

第一步是设置基本审核，然后开始运行审核日志搜索。

![设置基本审核的工作流。](../media/BasicAuditingWorkflow.png)

1. 验证组织是否具有支持基本审核的订阅，以及支持高级审核的订阅（如果适用）。

2. 将 Exchange Online 中的权限分配给组织中将使用 Microsoft 365 合规中心中的审核日志搜索工具，或将使用 **Search-UnifiedAuditLog** cmdlet 的人员。 具体而言，必须向用户分配 Exchange Online 中的仅查看审核日志或审核日志角色。

3. 搜索审核日志。完成步骤 1 和步骤 2 后，组织中的用户可以使用审核日志搜索工具（或相应的 cmdlet）搜索经审核的活动。

有关更详细的说明，请参阅 [设置基本审核](set-up-basic-audit.md)。

### <a name="set-up-advanced-audit"></a>设置高级审核

如果组织具有支持高级审核的订阅，请执行以下步骤来设置和使用高级审核中的其他功能。

![设置高级审核的工作流。](../media/AdvancedAuditWorkflow.png)

1. 为用户设置高级审核。 此步骤包括以下任务：

   - 验证用户分配了用于高级审核的适当许可证或附加设备许可证。
  
   - 必须为这些用户启用"高级审核应用/服务"计划。
  
   - 对关键事件启用审核，然后为这些用户启用高级审核应用/服务计划。

2. 启用高级审核事件，以便用户在 Exchange Online 和 SharePoint Online 中执行搜索时记录。

3. 设置审核记录保留策略。除了将 Exchange、SharePoint 和 Azure AD 审核记录保留一年的默认策略外，可以创建其他审核日志保留策略以满足组织安全操作、IT 和合规团队的要求。

4. 执行法务调查时，搜索关键高级审核事件和其他活动。完成步骤 1 和步骤 2 后，可在审核日志中搜索高级审核事件和调查已泄露帐户以及其他类型的安全或合规性调查期间的其他活动。

有关更详细的说明，请参阅 [高级审核](set-up-advanced-audit.md)。

## <a name="training"></a>培训

在“基本审核”和“高级审核”的基础上培训安全运营团队、IT 管理员和合规调查团队，可帮助组织更快开始使用审核来帮助完成调查。 Microsoft 365 提供了以下资源来帮助组织中这些用户开始进行审核: [描述 Microsoft 365 的 eDiscovery 和审核功能](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365)。
