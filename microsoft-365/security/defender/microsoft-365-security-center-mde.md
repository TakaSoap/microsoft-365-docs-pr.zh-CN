---
title: 安全中心中的 Microsoft Defender Microsoft 365终结点
description: 了解从安全中心Microsoft Defender 安全中心安全Microsoft 365更改
keywords: 入门：Microsoft 365安全中心、适用于 Office 365 的 Microsoft Defender、适用于终结点的 Microsoft Defender、MDO、MDE、单窗格的门户、聚合门户、安全门户、Defender 安全门户
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: bad31160bb27c79f672ddd28a5fced3bf8c2ee1b
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51943037"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>安全中心中的 Microsoft Defender Microsoft 365终结点

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

改进的安全[Microsoft 365](overview-security-center.md)中心结合使用了保护、检测、调查和响应电子邮件、协作、标识 [https://security.microsoft.com](https://security.microsoft.com) 和设备威胁的管理功能。 此安全中心将现有 Microsoft 安全门户的功能汇集在一起，Microsoft Defender 安全中心安全Office 365安全&中心。

如果您熟悉本文中的Microsoft Defender 安全中心，本文可帮助描述改进的安全中心中的一Microsoft 365改进。 但是，要注意一些新的和更新的元素。

过去[，Microsoft Defender 安全中心](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)一直是 Microsoft Defender for Endpoint 的主页。 Enterprise安全团队已使用它监视和帮助响应潜在高级永久性威胁活动或数据泄露的警报。 为了帮助减少门户数量，Microsoft 365安全中心将是监视和管理 Microsoft 标识、数据、设备、应用和基础结构的安全性的主页。

Microsoft 365安全中心中的 Microsoft Defender for Endpoint 支持以在 Microsoft Defender 安全中心中授予访问权限的相同方式向托管安全服务提供商[ (MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)授予[访问权限](mssp-access.md)。


> [!IMPORTANT]
> 在安全中心Microsoft 365取决于你的当前订阅。 例如，如果你没有 Microsoft Defender for Office 365 许可证，将不会显示"电子邮件&协作"部分。

>[!Note]
>新的统一门户不适用于：
>- 美国政府社区云 (GCC) 
>- 美国政府社区云高 (GCC高) 
>- 美国国防部
>- 所有拥有商业许可证的美国政府机构

查看改进的安全 [https://security.microsoft.com](https://security.microsoft.com) Microsoft 365：。

了解优点：Microsoft 365 [概述](overview-security-center.md)

## <a name="whats-changed"></a>更改内容

下表快速引用了安全中心Microsoft Defender 安全中心安全Microsoft 365更改。

### <a name="alerts-and-actions"></a>警报和操作

|**区域**  |**更改说明** |
|---------|---------|
| [事件&警报](incidents-overview.md)  | 在Microsoft 365安全中心，可以跨所有终结点、电子邮件和标识管理事件和警报。 我们已将体验融合在一起，帮助你更轻松地查找相关事件。 有关详细信息，请参阅 [事件概述](incidents-overview.md)。   |
| [搜寻](advanced-hunting-overview.md)  |  修改在 Microsoft Defender for Endpoint 中创建的自定义检测规则，以包含标识和电子邮件表会自动将它们Microsoft 365 Defender。 其相应的警报也会显示在 Microsoft 365 Defender 中。 有关这些更改的更多详细信息，请阅读迁移 [自定义检测规则](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。 <br><br>高级 `DeviceAlertEvents` 搜寻的表在 Microsoft 365 Defender 中不可用。 若要在 Microsoft 365 Defender 中查询特定于设备的警报信息，可以使用 和 表来容纳来自各种源 `AlertInfo` `AlertEvidence` 集的更多信息。 通过以下不含 [DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)的 Write 查询制作下一个与设备相关的查询。|
|[操作中心](m365d-action-center.md)    | 列出在自动调查和修正操作之后采取的挂起和已完成的操作。 以前，"操作中心"Microsoft Defender 安全中心列出仅对设备上采取的修正操作挂起和已完成的操作，而自动调查列出了警报和状态。 在改进的安全Microsoft 365，操作中心将电子邮件、设备和用户之间的修正操作和调查汇集在一起，所有这些操作都位于一个位置。  |
| [威胁分析](threat-analytics.md) |  移动到导航栏顶部，以便更轻松地发现和使用。 现在包括终结点以及电子邮件和协作的威胁信息。    |

### <a name="endpoints"></a>终结点

|**区域**  |**更改说明**  |
|---------|---------|
|搜索   |  Microsoft Defender for Endpoint 搜索栏不是位于标题中，而是在"终结点"部分下移动。 你可以继续搜索设备、文件、用户、URL、IP、漏洞、软件和建议。  |
|[仪表板](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  这是安全操作仪表板。 请参阅触发的活动警报数、处于风险中的设备、处于风险中的用户以及警报、设备和用户的严重性级别。 还可以查看任何设备是否具有传感器问题、整体服务运行状况，以及如何检测到任何未解决的警报。 |
|设备清单 | 无更改。 |
|[漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    已缩短名称以适合导航窗格。 它与"页面"部分危险和漏洞管理相同，所有页面位于下方。     |
| 合作伙伴和 API | 无更改。 |
| 评估&教程    |     新的测试和学习功能。     |
| 配置管理   |  无更改。  |

> [!NOTE]
> **自动调查和修正** 现在是事件的一部分。 You can see Automated investigation and remediation events in the **Incident > Investigation** tab.

> [!TIP]
> 设备搜索从 Endpoints > Search 完成。

### <a name="access-and-reporting"></a>访问和报告

|**区域**  |**更改说明**  |
|---------|---------|
| 报表  | 请参阅终结点和电子邮件报告&协作，包括威胁防护、设备运行状况和合规性以及易受攻击的设备。 |
| 健康  |  当前链接到管理中心 中的"服务运行状况["Microsoft 365页面](https://admin.microsoft.com/)。 |
| 设置 |  管理安全中心、Microsoft 365 Defender、Microsoft 365、电子邮件&协作、标识和设备发现的设置。   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365安全导航和功能

左侧导航栏或快速启动栏将看起来熟悉。 但是，这个安全中心中有些新增和更新的元素。

### <a name="incidents-and-alerts"></a>事件和警报

将跨电子邮件、设备和标识的事件和警报管理结合起来。 警报页面通过组合攻击信号来构造详细的情景，为警报提供完整的上下文。 全新的统一体验现在汇集了跨工作负荷的一致警报视图。 您可以快速分案、调查，以及采取有效措施。

- [详细了解事件](incidents-overview.md)
- [深入了解如何管理警报](investigate-alerts.md)

![通知和操作快速启动栏](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>搜寻

通过使用 [高级搜索查询来在终结点、Office 365 邮箱等位置主动搜索威胁、恶意软件和恶意](advanced-hunting-overview.md)。 这些强大的查询可用于查找和查看威胁指示器和实体，了解已知威胁和潜在威胁。

[自定义检测](custom-detection-rules.md) 规则可以从高级搜寻查询构建，以帮助你主动监视可能表示泄露活动和错误配置设备的事件。


### <a name="action-center"></a>操作中心

操作中心显示自动调查和响应功能创建调查。 Microsoft 365 Defender 中的自动自恢复功能可自动响应特定事件，帮助团队实现安全。

[详细了解操作中心](m365d-action-center.md)

### <a name="threat-analytics"></a>威胁分析

从 Microsoft 安全研究人员获取威胁智能。 威胁分析可帮助安全团队在面对新兴威胁时更有效率。 威胁分析包括：

- Microsoft Defender for Office 365 的与电子邮件相关的检测和缓解措施。 除了从 Microsoft Defender for Endpoint 中可用的终结点数据外，还有一个终结点数据。
- 与威胁相关的事件视图。
- 增强的体验，可快速识别和使用报告中的可操作信息。

你可以从安全中心的左上角导航Microsoft 365访问威胁分析，也可以从显示组织的主要威胁的专用仪表板卡访问威胁分析。

深入了解如何使用威胁 [跟踪和响应新兴威胁](./threat-analytics.md)

### <a name="endpoints-section"></a>终结点部分

查看和管理组织中终结点的安全性。 如果你已使用Microsoft Defender 安全中心，它看起来会很熟悉。

![终结点快速启动栏](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>访问和报告

查看报表、更改设置和修改用户角色。

!["访问和报告快速启动"栏](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API 连接

如果你使用 [适用于终结点 SIEM API 的 Defender，](../defender-endpoint/enable-siem-integration.md)你可以继续这样做。 我们已在 API 负载上添加了指向安全门户中的警报页面或事件Microsoft 365链接。 新的 API 字段包括 LinkToMTP 和 IncidentLinkToMTP。 有关详细信息，请参阅将帐户从[Microsoft Defender for Endpoint 重定向到Microsoft 365中心](./microsoft-365-security-mde-redirection.md)。

### <a name="email-alerts"></a>电子邮件警报

你可以继续使用 Defender for Endpoint 的电子邮件警报。 我们已在电子邮件中添加指向安全中心内警报页面或事件Microsoft 365链接。 有关详细信息，请参阅将帐户从[Microsoft Defender for Endpoint 重定向到Microsoft 365中心](./microsoft-365-security-mde-redirection.md)。

## <a name="related-information"></a>相关信息

- [Microsoft 365 安全中心](overview-security-center.md)
- [安全中心中的 Microsoft Defender Microsoft 365终结点](microsoft-365-security-center-mde.md)
- [将帐户从 Microsoft Defender for Endpoint 重定向到 Microsoft 365 安全中心](microsoft-365-security-mde-redirection.md)