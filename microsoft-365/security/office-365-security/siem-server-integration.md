---
title: SIEM server 与 Microsoft 365 服务和应用程序的集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: 获取安全信息和事件管理 (SIEM) server 与 Microsoft 365 云服务和应用程序集成的概述
ms.openlocfilehash: 6d657990417cab2a8cbb1b03b8b79a65c095d1a5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202199"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>与 Microsoft 365 服务和应用程序的安全信息和事件管理 (SIEM) server 集成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a>摘要

您的组织是使用还是计划在 SIEM) server 中获取安全信息和事件管理 (吗？ 您可能想知道它是如何与 Microsoft 365 或 Office 365 集成的。 本文提供了可用于将 SIEM 服务器与 Microsoft 365 服务和应用程序相集成的资源的列表。

> [!TIP]
> 如果你还没有 SIEM 服务器并且正在浏览你的选项，请考虑使用 **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>我是否需要 SIEM 服务器？

您是否需要 SIEM 服务器取决于多个因素，例如组织的安全要求和数据所在的位置。 Microsoft 365 包括各种安全功能，这些功能可满足许多组织的安全需要，而无需其他服务器（如 SIEM 服务器）。 某些组织具有需要使用 SIEM 服务器的特殊情况。 下面是一些示例：

- *Fabrikam* 在本地拥有一些内容和应用程序，而其中一些内容和应用程序 (其具有混合云部署) 。 若要在其所有内容和应用程序中获取安全报告，Fabrikam 已实现 SIEM 服务器。

- *Contoso* 是一种具有特别严格的安全要求的金融服务组织。 他们已将 SIEM 服务器添加到其环境中，以充分利用他们所需的额外安全保护。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM server 与 Microsoft 365 的集成

SIEM 服务器可以接收来自各种 Microsoft 365 服务和应用程序的数据。 下表列出了几个 Microsoft 365 服务和应用程序，以及 SIEM 服务器输入和资源，以了解详细信息。

****

|Microsoft 365 服务或应用程序|SIEM 服务器输入/方法|了解详细信息的资源|
|---|---|---|
|[Office 365 高级威胁防护](office-365-atp.md)|审核日志|[SIEM 与 Office 365 高级威胁防护的集成](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/)|Azure 中托管的 HTTPS 终结点 <br/>REST API|[将警报拉入 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|日志集成|[SIEM 与 Microsoft Cloud App Security 的集成](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> 请看一下 [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)。 Azure Sentinel 附带有 Microsoft 解决方案连接器。 这些连接器可用于 "开箱即用" 并提供实时集成。 您可以将 Azure Sentinel 与 Microsoft 威胁防护解决方案和 Microsoft 365 服务（包括 Office 365、Azure AD、Azure ATP、Microsoft 云应用安全性等）结合使用。

### <a name="audit-logging-must-be-turned-on"></a>必须打开审核日志记录

在配置 SIEM server 集成之前，请确保已启用审核日志记录。

- 对于 SharePoint Online、OneDrive for business 和 Azure Active Directory， [审核日志记录在安全 & 合规性中心中打开](../../compliance/turn-audit-log-search-on-or-off.md)。

- 有关 Exchange Online，请参阅 [管理邮箱审核](../../compliance/enable-mailbox-auditing.md)。

## <a name="more-resources"></a>更多资源

[在 Azure 安全中心集成安全解决方案](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[将 Microsoft Graph 安全性 API 警报与 SIEM 集成](https://docs.microsoft.com/graph/security-integration)
