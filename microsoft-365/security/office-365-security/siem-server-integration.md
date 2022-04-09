---
title: SIEM 服务器与Microsoft 365服务和应用程序集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: 获取安全信息和事件管理 (SIEM) 服务器与Microsoft 365云服务和应用程序集成的概述
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 978319cca91322c7eb737d89cbfc167574f14093
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "64731408"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>安全信息和事件管理 (SIEM) 服务器与Microsoft 365服务和应用程序的集成

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>摘要

你的组织是否使用或计划获取 SIEM) 服务器 (安全信息和事件管理？ 你可能想知道它如何与Microsoft 365或Office 365集成。 本文提供可用于将 SIEM 服务器与Microsoft 365服务和应用程序集成的资源列表。

> [!TIP]
> 如果还没有 SIEM 服务器，并且正在浏览你的选项，请考虑 **[Microsoft Sentinel](/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>是否需要 SIEM 服务器？

是否需要 SIEM 服务器取决于许多因素，例如组织的安全要求和数据所在的位置。 Microsoft 365包括各种安全功能，无需其他服务器（如 SIEM 服务器）即可满足许多组织的安全需求。 某些组织有需要使用 SIEM 服务器的特殊情况。 下面是一些示例：

- *Fabrikam* 在本地有一些内容和应用程序，有些在云 (有混合云部署) 。 为了获取所有内容和应用程序的安全报告，Fabrikam 已实现 SIEM 服务器。
- *Contoso* 是一个金融服务组织，具有特别严格的安全要求。 他们已将 SIEM 服务器添加到其环境中，以利用所需的额外安全保护。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM 服务器与 Microsoft 365 集成

SIEM 服务器可以从各种Microsoft 365服务和应用程序接收数据。 下表列出了多个Microsoft 365服务和应用程序，以及 SIEM 服务器输入和资源以了解详细信息。

<br/><br/>

|Microsoft 365服务或应用程序|SIEM 服务器输入/方法|了解详细信息的资源|
|---|---|---|
|[Microsoft Defender for Office 365](defender-for-office-365.md)|审核日志|[SIEM 与 Microsoft Defender for Office 365 集成](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](/windows/security/threat-protection/)|Azure 中托管的 HTTPS 终结点 <p> REST API|[将警报拉取到 SIEM 工具](../defender-endpoint/configure-siem.md)|
|[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)|日志集成|[SIEM 与 Microsoft Defender for Cloud Apps 集成](/cloud-app-security/siem)|

> [!TIP]
> 查看 [Microsoft Sentinel](/azure/sentinel/overview)。 Microsoft Sentinel 附带 Microsoft 解决方案的连接器。 这些连接器"开箱即用"可用，并提供实时集成。 可以将 Microsoft Sentinel 与Microsoft 365 Defender解决方案和Microsoft 365服务配合使用，包括 Office 365、Azure AD、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps等。

### <a name="audit-logging-must-be-turned-on"></a>必须打开审核日志记录

在配置 SIEM 服务器集成之前，请确保已启用审核日志记录。

- 有关SharePoint联机、OneDrive for Business和Azure Active Directory，请参阅[打开或关闭审核](../../compliance/turn-audit-log-search-on-or-off.md)。
- 有关Exchange Online，请参阅["管理邮箱审核](../../compliance/enable-mailbox-auditing.md)"。

## <a name="more-resources"></a>更多资源

[在 Microsoft Defender for Cloud 中集成安全解决方案](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[将 Microsoft Graph 安全性 API 警报与 SIEM 集成](/graph/security-integration)
