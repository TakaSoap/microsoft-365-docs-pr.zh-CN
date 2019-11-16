---
title: SIEM server 与 Microsoft 365 服务和应用程序的集成
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 阅读本文，了解 SIEM server 与 Microsoft 365 集成的概述。
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677505"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM server 与 Microsoft 365 服务和应用程序的集成

## <a name="summary"></a>Summary

如果您的组织使用的是安全信息和事件管理（SIEM）服务器，或者您打算马上获取 SIEM 服务器，那么您可能会想知道如何将与 Microsoft 365 或 Office 365 集成。 本文提供了可用于设置 SIEM server 与 Microsoft 365 服务和应用程序集成的资源的列表。

> [!TIP]
> 如果你还没有 SIEM 服务器并且正在浏览你的选项，请考虑使用**[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>我是否需要 SIEM 服务器？

您是否需要 SIEM 服务器取决于多个因素，例如组织的安全要求和数据所在的位置。 Microsoft 365 包括各种安全功能，这些功能可满足许多组织的安全需要，而无需其他服务器（如 SIEM 服务器）。 某些组织具有需要使用 SIEM 服务器的特殊情况。 下面是一些示例：

- *Fabrikam*在本地有一些内容和应用程序，而有些在云中（它们具有混合云部署）。 若要在其所有内容和应用程序中获取安全报告，Fabrikam 已实现 SIEM 服务器。 

- *Contoso*是一种具有特别严格的安全要求的金融服务组织。 他们已将 SIEM 服务器添加到其环境中，以充分利用他们所需的额外安全保护。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM server 与 Microsoft 365 的集成

SIEM 服务器可以接收来自各种 Microsoft 365 服务和应用程序的数据。 下表列出了几个 Microsoft 365 服务和应用程序以及 SIEM 服务器输入和资源，以详细了解 SIEM server 集成。 

| Microsoft 365 服务或应用程序 | SIEM 服务器输入 | 了解详细信息的资源 |
| --- | --- | --- |
| [Office 365 高级威胁防护](office-365-atp.md)  | 审核日志 | [SIEM 与 Office 365 高级威胁防护的集成](siem-integration-with-office-365-ti.md) |
| [Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/) | Azure 中托管的 HTTPS 终结点 <br/>REST API| [将警报拉入 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 日志集成 | [SIEM 与 Microsoft Cloud App Security 的集成](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> 查看[Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)，它附带了许多连接器（适用于 Microsoft 解决方案），现成且提供了实时集成（包括 Microsoft 威胁防护解决方案）和 microsoft 365 源（包括 Office 365、azure AD、azure ATP 和 Microsoft 云应用安全性等）。

### <a name="audit-logging-must-be-turned-on"></a>必须打开审核日志记录

在配置 SIEM server 集成之前，请确保审核日志记录已打开。 

- 对于 SharePoint Online、OneDrive for business 和 Azure Active Directory，[审核日志记录在安全 & 合规性中心中打开](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。

- 对于 Exchange Online，[审核日志记录是使用 Windows PowerShell 打开](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)的。
 
## <a name="additional-resources"></a>其他资源

[在 Azure 安全中心集成安全解决方案](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[将 Microsoft Graph 安全性 API 警报与 SIEM 集成](https://docs.microsoft.com/graph/security-integration)