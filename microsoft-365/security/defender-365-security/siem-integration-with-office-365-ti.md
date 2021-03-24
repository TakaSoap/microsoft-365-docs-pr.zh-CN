---
title: SIEM 与 Microsoft Defender for Office 365 集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 将组织的 SIEM 服务器与适用于 Office 365 的 Microsoft Defender 以及 Office 365 活动管理 API 中的相关威胁事件集成。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a456ee970015aea5936ae86ec009cb2ff46e99c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055509"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM 与 Microsoft Defender for Office 365 集成

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


如果你的组织使用 SIEM (安全信息和事件) ，你可以将适用于 Office 365 的 Microsoft Defender 与 SIEM 服务器集成。 可以使用 Office [365](/office/office-365-management-api/office-365-management-activity-api-reference)活动管理 API 设置此集成。

SIEM 集成使你能够在 SIEM 服务器报告中查看信息，如 Microsoft Defender for Office 365 检测到的恶意软件或网络钓鱼。

- 若要查看 SIEM 与 Microsoft Defender for Office 365 集成的示例，请参阅技术社区 [博客：使用适用于 Office 365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)的 Defender 提高 SOC 的有效性和 O365 管理 API。

- 若要详细了解 Office 365 管理 API，请参阅 [Office 365 管理 API 概述](/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 集成的工作原理

Office 365 活动管理 API 从组织的 Microsoft 365 和 Azure Active Directory 活动日志中检索有关用户、管理员、系统和策略操作和事件的信息。 如果你的组织拥有 Microsoft Defender for Office 365 计划 1 或 2，或 Office 365 E5，可以使用 [Microsoft Defender for Office 365 架构](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。

最近，来自 Microsoft Defender for Office [365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 计划 2 中的自动调查和响应功能的事件已添加到 Office 365 管理活动 API。 除了包含有关核心调查详细信息（如 ID、名称和状态）的数据之外，API 还包含有关调查操作和实体的高级别信息。

SIEM 服务器或其他类似的系统轮询 **audit.general** 工作负载以访问检测事件。 若要了解更多信息，请参阅 [Office 365 管理 API 入门](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="enum-auditlogrecordtype---type-edmint32"></a>枚举：AuditLogRecordType - 类型：Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

下表汇总了与 Microsoft Defender for Office 365 事件相关的 **AuditLogRecordType** 值：

|值|成员名称|说明|
|---|---|---|
|28|ThreatIntelligence|Exchange Online Protection 和 Microsoft Defender for Office 365 中的网络钓鱼和恶意软件事件。|
|41|ThreatIntelligenceUrl|来自 Microsoft Defender for Office 365 的安全链接阻止时间和阻止覆盖事件。|
|47|ThreatIntelligenceAtpContent|来自 Microsoft Defender for Office 365 的 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中文件的网络钓鱼和恶意软件事件。|
|64|AirInvestigation|来自 Microsoft Defender for Office 365 计划 2 的自动调查和响应事件，如调查详细信息和相关项目。|
|

> [!IMPORTANT]
> 你必须是全局管理员或分配有安全与合规中心的安全&角色，才能设置 SIEM 与 Microsoft Defender for Office 365 的集成。
>
> 必须为 Microsoft 365 环境启用审核日志记录。 若要获取有关此内容的帮助，请参阅打开 [审核日志或关闭搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>另请参阅

[Office 365 威胁调查和响应](office-365-ti.md)

[Office 365 中的 AIR (自动调查和) 响应](automated-investigation-response-office.md)