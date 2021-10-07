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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: 大致了解 SIEM 安全信息和事件 (SIEM) 与 Microsoft 365 云服务和应用程序集成
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71fff15b1493f6e8e15becbd87ad55947c8eddc4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169415"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM 安全信息和事件 (SIEM) 与 Microsoft 365 服务和应用程序的服务器集成

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>摘要

你的组织是使用还是计划使用 SIEM (获取安全信息和事件) ？ 你可能想知道它如何与Microsoft 365或Office 365。 本文提供了可用于将 SIEM 服务器与服务和应用程序Microsoft 365列表。

> [!TIP]
> 如果你还没有 SIEM 服务器，并且正在探索你的选项，请考虑Microsoft Azure **[Sentinel](/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>是否需要 SIEM 服务器？

是否需要 SIEM 服务器取决于许多因素，例如组织的安全要求和数据所在的位置。 Microsoft 365包括各种安全功能，无需其他服务器（如 SIEM 服务器）即可满足许多组织的安全需求。 某些组织有需要使用 SIEM 服务器的特殊情况。 下面是一些示例：

- *Fabrikam* 在本地具有一些内容和应用程序，一些位于云 (它们具有混合云部署) 。 为了跨所有内容和应用程序获取安全报告，Fabrikam 实施了 SIEM 服务器。
- *Contoso* 是一家金融服务组织，其安全要求特别严格。 他们向环境添加了 SIEM 服务器，以利用他们需要额外的安全保护。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM 服务器与 Microsoft 365

SIEM 服务器可以从各种服务和应用程序Microsoft 365数据。 下表列出了几个Microsoft 365应用程序，以及 SIEM 服务器输入和资源以了解更多信息。

<br/><br/>

|Microsoft 365服务或应用程序|SIEM 服务器输入/方法|了解详细信息的资源|
|---|---|---|
|[Microsoft Defender for Office 365](defender-for-office-365.md)|审核日志|[SIEM 与 Microsoft Defender for Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](/windows/security/threat-protection/)|托管在 Azure 中的 HTTPS 终结点 <p> REST API|[将警报拉取到 SIEM 工具](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|日志集成|[SIEM 与 Microsoft Cloud App Security](/cloud-app-security/siem)|

> [!TIP]
> 查看 Azure [Sentinel](/azure/sentinel/overview)。 Azure Sentinel 附带适用于 Microsoft 解决方案的连接器。 这些连接器"开箱即用"可用，可提供实时集成。 可以将 Azure Sentinel 与 Microsoft 365 Defender 解决方案和 Microsoft 365 服务一同使用，包括 Office 365、Azure AD、Microsoft Defender for Identity Microsoft Cloud App Security等。

### <a name="audit-logging-must-be-turned-on"></a>审核日志记录必须打开

在配置 SIEM 服务器集成之前，请确保审核日志记录已打开。

- 有关 SharePoint Online、OneDrive for Business 和 Azure Active Directory，请参阅[启用或关闭审核](../../compliance/turn-audit-log-search-on-or-off.md)。
- 有关Exchange Online，请参阅[管理邮箱审核](../../compliance/enable-mailbox-auditing.md)。

## <a name="more-resources"></a>更多资源

[在 Azure Defender 中集成安全解决方案](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[将 Microsoft Graph 安全性 API 警报与 SIEM 集成](/graph/security-integration)
