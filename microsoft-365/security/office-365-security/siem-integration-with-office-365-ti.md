---
title: SIEM 与 Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: ''
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 将组织的 SIEM 服务器与 Microsoft Defender 集成，Office 365活动管理 API 中的Office 365威胁事件。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3dbb175ba169c9bb8f4d7240d59d9886391167c3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176351"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM 与 Microsoft Defender for Office 365

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


如果你的组织使用 SIEM (安全信息和事件) ，你可以将适用于 Office 365 的 Microsoft Defender 与 SIEM 服务器集成。 可以使用活动管理 API Office 365[此集成](/office/office-365-management-api/office-365-management-activity-api-reference)。

SIEM 集成使你能够在 SIEM 服务器报告中查看信息，如 Microsoft Defender for Office 365 检测到的恶意软件或网络钓鱼。

- 若要查看 SIEM 与 Microsoft Defender for Office 365 集成的示例，请参阅[Tech Community blog： Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。
- 若要了解有关管理 API Office 365，请参阅 Office 365 管理[API 概述](/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 集成的工作原理

活动Office 365 API 从组织的活动日志和活动日志中检索有关用户、管理员、系统和策略操作Microsoft 365 Azure Active Directory的信息。 如果你的组织拥有适用于计划 1 Office 365 2 的 Microsoft Defender，Office 365 E5，可以使用 Microsoft Defender[进行Office 365架构](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。

最近，来自 Microsoft Defender for Office 365[计划 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)中的自动调查和响应功能的事件已添加到 Office 365 活动 API。 除了包含有关核心调查详细信息（如 ID、名称和状态）的数据之外，API 还包含有关调查操作和实体的高级别信息。

SIEM 服务器或其他类似的系统轮询 **audit.general** 工作负载以访问检测事件。 若要了解更多信息，请参阅Office 365 [API 入门](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="enum-auditlogrecordtype---type-edmint32"></a>枚举：AuditLogRecordType - 类型：Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

下表汇总了与 Microsoft Defender for Office 365 事件相关的 **AuditLogRecordType** 值：<br/><br/>

| 值 | 成员名称 | 说明 |
|---|---|---|
| 28| ThreatIntelligence | Exchange Online Protection 和 Microsoft Defender for Office 365 中的网络钓鱼和恶意软件事件。 |
| 41| ThreatIntelligenceUrl | 保险箱链接 Microsoft Defender for Office 365 的阻止时间和阻止覆盖Office 365。 |
| 47| ThreatIntelligenceAtpContent | SharePoint Online、OneDrive for Business 和 Microsoft Teams（来自 Microsoft Defender for Office 365）中的文件的网络钓鱼和恶意软件Office 365。 |
| 64| AirInvestigation | 来自 Microsoft Defender for Office 365计划 2 的自动调查和响应事件，例如调查详细信息和相关项目。 |

> [!IMPORTANT]
> 你必须在 Microsoft 365 Defender 门户中分配全局管理员或安全管理员角色，才能设置 SIEM 与 Microsoft Defender Office 365。 有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。
>
> 必须为你的环境启用审核Microsoft 365日志记录。 若要获取有关此内容的帮助，请参阅打开 [审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>另请参阅

[Office 365 威胁调查和响应](office-365-ti.md)

[自动调查和响应 (AIR) 中Office 365](automated-investigation-response-office.md)