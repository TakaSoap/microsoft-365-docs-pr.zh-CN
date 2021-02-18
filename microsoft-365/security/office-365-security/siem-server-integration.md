---
title: SIEM 服务器与 Microsoft 365 服务和应用程序的集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: 大致了解 SIEM (SIEM) 与 Microsoft 365 云服务和应用程序集成的安全信息和事件管理
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290377"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM (SIEM) Microsoft 365 服务和应用程序集成的安全信息和事件管理

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>摘要

组织是否正在使用或计划从 SIEM (获取安全信息和) 管理？ 你可能想知道它如何与 Microsoft 365 或 Office 365 集成。 本文提供了可用于将 SIEM 服务器与 Microsoft 365 服务和应用程序集成的资源列表。

> [!TIP]
> 如果你还没有 SIEM 服务器并且正在探索你的选项，请考虑使用 Microsoft **[Azure Sentinel。](https://docs.microsoft.com/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>是否需要 SIEM 服务器？

是否需要 SIEM 服务器取决于许多因素，例如组织的安全要求和数据所在的位置。 Microsoft 365 包括各种安全功能，无需其他服务器（如 SIEM 服务器）即可满足许多组织的安全需求。 某些组织具有需要使用 SIEM 服务器的特殊情况。 下面是一些示例：

- *Fabrikam* 具有一些本地内容和应用程序，一些位于云 (它们具有混合云部署) 。 为了跨所有内容和应用程序获取安全报告，Fabrikam 实施了 SIEM 服务器。

- *Contoso* 是一家对安全性要求特别严格的金融服务组织。 他们向环境添加了 SIEM 服务器，以利用他们需要额外的安全保护。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM 服务器与 Microsoft 365 集成

SIEM 服务器可以从各种 Microsoft 365 服务和应用程序接收数据。 下表列出了多个 Microsoft 365 服务和应用程序，以及 SIEM 服务器输入和资源以了解更多信息。

****

|Microsoft 365 服务或应用程序|SIEM 服务器输入/方法|了解详细信息的资源|
|---|---|---|
|[Microsoft Defender for Office 365](office-365-atp.md)|审核日志|[SIEM 与 Microsoft Defender for Office 365 集成](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)|托管在 Azure 中的 HTTPS 终结点 <p> REST API|[将警报拉取到 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|日志集成|[SIEM 与 Microsoft Cloud App Security 集成](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> 查看 Azure [Sentinel](https://docs.microsoft.com/azure/sentinel/overview)。 Azure Sentinel 附带了 Microsoft 解决方案的连接器。 这些连接器"开箱即用"可用，可提供实时集成。 可以将 Azure Sentinel 与 Microsoft 365 Defender 解决方案和 Microsoft 365 服务（包括 Office 365、Azure AD、Microsoft Defender for Identity、Microsoft Cloud App Security 等）一同使用。

### <a name="audit-logging-must-be-turned-on"></a>审核日志记录必须打开

在配置 SIEM 服务器集成之前，请确保审核日志记录已打开。

- 对于 SharePoint Online、OneDrive for Business 和 Azure Active Directory，审核日志记录在安全与合规中心 [&启用](../../compliance/turn-audit-log-search-on-or-off.md)。

- 对于 Exchange Online，请参阅["管理邮箱审核"。](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>更多资源

[在 Azure Defender 中集成安全解决方案](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[将 Microsoft Graph 安全性 API 警报与 SIEM 集成](https://docs.microsoft.com/graph/security-integration)
