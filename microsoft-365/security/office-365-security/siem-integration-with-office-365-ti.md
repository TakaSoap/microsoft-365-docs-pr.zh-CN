---
title: SIEM 与 Office 365 高级威胁防护的集成
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: 将组织的 SIEM 服务器与 office 365 高级威胁防护以及 Office 365 活动管理 API 中相关的威胁事件集成。
ms.openlocfilehash: 5b3cdfa48f64bb3d73f02b3d9b20dee510a2f409
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202433"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a>SIEM 与 Office 365 高级威胁防护的集成

如果您的组织使用的是安全事件和事件管理（SIEM）服务器，则可以将 Office 365 高级威胁防护与您的 SIEM 服务器集成。 SIEM 集成使您能够查看 SIEM 服务器报告中的 Office 365 高级保护检测到的恶意软件或网络钓鱼信息。 若要设置 SIEM 集成，请使用[Office 365 活动管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

Office 365 活动管理 API 检索组织的 Office 365 和 Azure Active Directory 活动日志中的用户、管理员、系统和策略操作以及事件的相关信息。 [Office 365 高级威胁防护架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)使用高级威胁防护功能，因此，如果您的组织具有 Office 365 高级威胁防护计划1或计划2或 Office 365 E5，您仍可以对您的 SIEM 服务器集成使用相同的 API。 

作为我们最近更新的一部分，我们还为管理 API 中的 Office 365 ATP 计划2中的自动事件响应添加了调查事件。 除了包含有关核心调查详细信息（如 ID、名称和状态）的数据之外，它还包含有关调查操作和实体的高级信息。   

SIEM 服务器或其他类似系统应轮询**审核。常规**工作负荷以访问检测事件。 若要了解详细信息，请参阅[Office 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 此外， **AuditLogRecordType**的以下值与 OFFICE 365 ATP 事件相关：

### <a name="enum-auditlogrecordtype---type-edmint32"></a>枚举：AuditLogRecordType - 类型：Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|值|成员名称|说明|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Exchange Online Protection 和 Office 365 高级威胁防护中的网络钓鱼和恶意软件事件。|
|41|ThreatIntelligenceUrl|ATP 安全链接从 Office 365 高级威胁防护的阻止时间和阻止覆盖事件。|
|47|ThreatIntelligenceAtpContent|Office 365 高级威胁防护中的 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件的网络钓鱼和恶意软件事件。|
|64|AirInvestigation|自动事件响应事件，包括调查详细信息和 Office 365 高级威胁防护计划2中的相关项目。|


> [!IMPORTANT]
> 您必须是 Office 365 全局管理员或将安全管理员角色分配给安全 & 合规性中心，以设置与 Office 365 高级威胁防护的 SIEM 集成。<br/>必须为你的 Office 365 环境启用审核日志记录。 若要获取有关此功能的帮助，请参阅[打开或关闭 Office 365 审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="related-topics"></a>相关主题

[Office 365 威胁调查和响应](office-365-ti.md)

[Office 365 中的自动事件响应（空气）](automated-investigation-response-office.md)

[Office 365 高级威胁防护](office-365-atp.md)

[Office 365 安全&amp;合规中心中的智能报告和见解](reports-and-insights-in-security-and-compliance.md)
  
[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
