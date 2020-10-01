---
title: SIEM 与高级威胁防护的集成
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
description: 将组织的 SIEM 服务器与 office 365 高级威胁防护以及 Office 365 活动管理 API 中相关的威胁事件集成。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 544093960570fe0e68ac47dc7bf9965fba2d30a1
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327161"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM 与高级威胁防护的集成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


如果您的组织使用安全事件和事件管理 (SIEM) server，则可以将 Office 365 高级威胁防护 (Office 365 ATP) 与 SIEM 服务器集成。 您可以使用 [Office 365 活动管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)设置这种集成。 

通过 SIEM 集成，可以查看 SIEM 服务器报告中的 Office 365 ATP 检测到的信息，例如恶意软件或网络钓鱼。 

- 若要查看 SIEM 与 Office 365 ATP 集成的示例，请参阅 [技术社区博客：使用 Office 365 ATP 和 O365 管理 API 提高 SOC 的有效性](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

- 若要了解有关 Office 365 管理 Api 的详细信息，请参阅 [office 365 管理 api 概述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 集成的工作原理

Office 365 活动管理 API 检索组织的 Microsoft 365 和 Azure Active Directory 活动日志中的用户、管理员、系统和策略操作以及事件的相关信息。 如果您的组织具有 Office 365 ATP 计划1或2或 Office 365 E5，则可以使用 [office 365 atp 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。  

最近， [office 365 ATP 计划 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) 中的来自自动调查和响应功能的事件已添加到 Office 365 管理活动 API 中。 除了包含有关核心调查详细信息（如 ID、名称和状态）的数据之外，API 还包含有关调查操作和实体的高级信息。

SIEM 服务器或其他类似的系统会轮询 **审核。常规** 工作负荷以访问检测事件。 若要了解详细信息，请参阅 [Office 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>枚举：AuditLogRecordType - 类型：Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

下表汇总了与 Office 365 ATP 事件相关的 **AuditLogRecordType** 的值：

|值|成员名称|说明|
|---|---|---|
|28|ThreatIntelligence|来自 Exchange Online Protection 和 Office 365 ATP 的网络钓鱼和恶意软件事件。|
|41|ThreatIntelligenceUrl|来自 Office 365 ATP 的安全链接时间段和阻止覆盖事件。|
|47|ThreatIntelligenceAtpContent|Office 365 ATP 中的 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件的网络钓鱼和恶意软件事件。|
|64|AirInvestigation|来自 Office 365 ATP 计划2的自动化调查和响应事件，如调查详细信息和相关项目。|
|

> [!IMPORTANT]
> 您必须是全局管理员或已为安全 & 合规中心分配的安全管理员角色，才能设置与 Office 365 高级威胁防护的 SIEM 集成。<br/>必须为你的 Microsoft 365 环境启用审核日志记录。 若要获取有关此功能的帮助，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>另请参阅

[Office 365 威胁调查和响应](office-365-ti.md)

[Office 365 中的自动调查和响应 (空中) ](automated-investigation-response-office.md)


