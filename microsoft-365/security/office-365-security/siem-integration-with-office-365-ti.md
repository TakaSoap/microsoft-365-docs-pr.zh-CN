---
title: SIEM 与高级威胁防护集成
f1.keywords:
- NOCSH
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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 将组织的 SIEM 服务器与 Office 365 活动管理 API 中的 Office 365 高级威胁防护和相关威胁事件集成。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e9dcf24adfb227d0c454b4f5952c879cea511f7
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860685"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM 与高级威胁防护集成

如果你的组织使用的是安全事件和事件管理 (SIEM) 服务器，则可将 Office 365 高级威胁防护 (Office 365 ATP) 与您的 SIEM 服务器集成。 可以使用 [Office 365 活动管理 API 设置此集成](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

SIEM 集成可让你在 SIEM 服务器报告中查看信息，例如 Office 365 ATP 检测到的恶意软件或网络钓鱼。 

- 若要查看 SIEM 与 Office 365 ATP 集成的示例，请参阅 [技术社区博客：通过 Office 365 ATP 和 O365 管理 API 提高 SOC 的有效性](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

- 有关 Office 365 管理 API 的详细信息，请参阅 [Office 365 管理 API 概述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 集成的工作原理

Office 365 活动管理 API 从组织的 Microsoft 365 和 Azure Active Directory 活动日志中获取用户、管理员、系统和策略操作和事件的相关信息。 如果你的组织有 Office 365 ATP 计划 1 或 2 或 Office 365 E5，则 [可以使用 Office 365 ATP 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。  

最近 [，Office 365 ATP](office-365-atp.md#office-365-atp-plan-1-and-plan-2) 计划 2 中的自动调查和响应功能中的事件已添加到 Office 365 管理活动 API。 除了包含有关核心调查详细信息的数据（如 ID、名称和状态），API 还包含有关调查操作和实体的高级信息。

SIEM 服务器或其他类似系统将轮询 **audit.general** 工作负载以访问检测事件。 若要了解详细信息，请参阅 [Office 365 管理 API 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 


## <a name="enum-auditlogrecordtype---type-edmint32"></a>枚举：AuditLogRecordType - 类型：Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

下表总结了与 Office 365 ATP 事件相关的 **AuditLogRecordType** 的值：

|值|成员名称|说明|
|---|---|---|
|28|ThreatIntelligence|Exchange Online Protection 和 Office 365 ATP 中的网络钓鱼和恶意软件事件。|
|41|ThreatIntelligenceUrl|ATP 安全链接时自动根据阻止和阻止覆盖 Office 365 ATP 中的事件。|
|47|ThreatIntelligenceAtpContent|在 Office 365 ATP 中，SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的文件的网络钓鱼和恶意软件事件。|
|64|AirInvestigation|自动调查和响应事件，例如调查详细信息和相关项目。可从 Office 365 ATP 计划 2 中进行自动调查和响应事件，例如调查详细信息和相关项目。|
|

> [!IMPORTANT]
> 要设置与 Office 365 高级威胁防护的 SIEM 集成，你必须是全局管理员或已分配安全 & 合规中心的安全管理员角色。<br/>必须为 Microsoft 365 环境启用审核日志记录。 若要获取有关此问题的帮助 [，请参阅审核日志打开还是关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>另请参阅

[Office 365 威胁调查和响应](office-365-ti.md)

[Office 365 中为 AIR (自动) 响应](automated-investigation-response-office.md)


