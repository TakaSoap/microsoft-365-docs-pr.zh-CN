---
title: Microsoft 365 Defender中的Microsoft Defender for Endpoint
description: 了解从Microsoft Defender 安全中心到Microsoft 365 Defender的更改
keywords: Microsoft 365 Defender、Microsoft Defender for Office 365、Microsoft Defender for Endpoint、MDO、MDE、安全门户、defender 安全门户入门
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: bac70dd864e1ab72fae5fbefa2a8da12cce4f6e7
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667221"
---
# <a name="microsoft-defender-for-endpoint-in-microsoft-365-defender"></a>Microsoft 365 Defender中的Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="quick-reference"></a>快速参考

下图和下表列出了Microsoft Defender 安全中心和Microsoft 365 Defender之间的导航更改。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/mde-m3d-security-center.png" alt-text="Microsoft 365 Defender门户中的新位置" lightbox="../../media/mde-m3d-security-center.png":::

| Microsoft Defender 安全中心 | Microsoft 365 Defender |
|---------|---------|
| 仪表 板 <ul><li>安全操作</li><li>威胁分析</li></ul>  |家庭版 <ul><li>威胁分析</li></ul>   |
| 事件 | 事件和警报 |
| 设备清单 | 设备清单 |
| 警报队列 | 事件和警报 |
| 自动调查 | 操作中心 |
| 高级搜寻 | 搜寻 |
| 报表 | 报表 |
| 合作伙伴& API | 合作伙伴& API |
| 威胁&漏洞管理 | 漏洞管理 |
| 评估和教程 | 评估&教程 |
| 配置管理 | 配置管理 |
| 设置 | 设置 | 

改进[后的Microsoft 365 Defender](microsoft-365-defender.md#the-microsoft-365-defender-portal)<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>结合了保护、检测、调查和响应电子邮件、协作、标识和设备威胁的安全功能。 这会汇集现有 Microsoft 安全门户的功能，包括Microsoft Defender 安全中心和Office 365安全&合规中心。

如果你熟悉Microsoft Defender 安全中心，本文将帮助描述Microsoft 365 Defender中的一些更改和改进。 但是，需要注意一些新的和更新的元素。

从历史上看，[Microsoft Defender 安全中心](/windows/security/threat-protection/microsoft-defender-atp/portal-overview)一直是Microsoft Defender for Endpoint的家。 Enterprise安全团队已使用它来监视和帮助响应潜在高级持久威胁活动或数据泄露的警报。 为了帮助减少门户数量，Microsoft 365 Defender将成为监视和管理 Microsoft 标识、数据、设备、应用和基础结构中安全性的主机。

Microsoft 365 Defender中的Microsoft Defender for Endpoint支持[授予托管安全服务提供商 (MSSP) ](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) [的访问权限，就像在Microsoft Defender 安全中心中授予访问权限](mssp-access.md)一样。

> [!IMPORTANT]
> 你在Microsoft 365 Defender中看到的内容取决于当前订阅。 例如，如果没有Microsoft Defender for Office 365许可证，则不会显示"电子邮件&协作"部分。

> [!Note]
> Microsoft 365 Defender不可用：
>- 美国政府社区云 (GCC) 
>- 美国政府社区云高 (GCC高) 
>- 美国国防部
>- 所有具有商业许可证的美国政府机构

看看Microsoft 365 Defender。<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>

详细了解优势：[Microsoft 365 Defender概述](microsoft-365-defender.md)

## <a name="whats-changed"></a>更改内容

此表快速引用Microsoft Defender 安全中心和Microsoft 365 Defender之间的更改。

### <a name="alerts-and-actions"></a>警报和操作

| 领域 | 更改说明 |
|---------|---------|
| [事件&警报](incidents-overview.md)  | 在Microsoft 365 Defender中，可以跨所有终结点、电子邮件和标识管理事件和警报。 我们融合了体验，帮助你更轻松地查找相关事件。 有关详细信息，请参阅 [事件概述](incidents-overview.md)。   |
| [搜寻](advanced-hunting-overview.md)  |  修改在Microsoft Defender for Endpoint中创建的自定义检测规则以包含标识和电子邮件表，会自动将它们移动到Microsoft 365 Defender。 其相应的警报也将显示在Microsoft 365 Defender中。 有关这些更改的更多详细信息，请阅读 [Migrate 自定义检测规则](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)。 <br><br>高级`DeviceAlertEvents`搜寻表在Microsoft 365 Defender中不可用。 若要在Microsoft 365 Defender中查询特定于设备的警报信息，可以使用`AlertInfo`这些信息和`AlertEvidence`表来容纳来自不同源集的更多信息。 使用 [不使用 DeviceAlertEvents 的写入查询](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)创建下一个与设备相关的查询。|
|[操作中心](m365d-action-center.md)    | 列出了在自动调查和修正操作之后执行的挂起和已完成的操作。 以前，Microsoft Defender 安全中心中的操作中心列出了仅针对设备执行的修正操作的挂起和已完成的操作，而自动调查列出了警报和状态。 在改进的Microsoft 365 Defender中，操作中心将跨电子邮件、设备和用户的修正操作和调查汇集在一个位置。  |
| [威胁分析](threat-analytics.md) |  移动到导航栏顶部，以便更轻松地发现和使用。 现在包括终结点、电子邮件和协作的威胁信息。    |

### <a name="endpoints"></a>终结点

| 领域 | 更改说明 |
|---------|---------|
|搜索   |  搜索栏位于页面顶部。 键入时会提供建议。 可以在 Defender for Endpoint 和 Defender for Identity 中搜索以下实体： <br><br> - **设备** - Defender for Endpoint 和 Defender for Identity 都支持。 甚至可以使用搜索运算符，例如，可以使用"contains"搜索主机名的一部分。 <br><br> - **用户** - Defender for Endpoint 和 Defender for Identity 都支持。 <br><br> - **文件、IP 和 URL** - 与 Defender for Endpoint 中的功能相同。 <br> 注意：*IP 和 URL 搜索完全匹配，不会显示在搜索结果页中 - 它们直接指向实体页。  <br><br> - **TVM** - 与 Defender for Endpoint 中的功能相同 (漏洞、软件和建议) 。 <br><br>  增强的搜索结果页集中了来自所有实体的结果。  |
|[仪表板](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  这是安全操作仪表板。 请参阅有关触发了多少个活动警报、哪些设备存在风险、哪些用户处于危险之中以及警报、设备和用户的严重性级别的概述。 还可以查看是否有任何设备出现传感器问题、整体服务运行状况以及检测到任何未解决的警报的方式。 |
|设备清单 | 无更改。 |
|[漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    名称已缩短以适应导航窗格。 它与危险和漏洞管理部分相同，下面包含所有页面。     |
| 合作伙伴和 API | 无更改。 |
| 评估&教程    |     新的测试和学习功能。     |
| 配置管理   |  无更改。  |

> [!NOTE]
> **自动调查和修正** 现在是事件的一部分。 可以在 **"事件>调查** "选项卡中看到自动调查和修正事件。

> [!TIP]
> 设备搜索是从终结点>搜索完成的。

### <a name="access-and-reporting"></a>访问和报告

| 领域 | 更改说明 |
|---------|---------|
| 报告  | 请参阅有关终结点和电子邮件&协作的报告，包括威胁防护、设备运行状况和符合性以及易受攻击的设备。 |
| 运行状况  |  当前链接到Microsoft 365 管理中心中的"服务运行状况"[页。](https://admin.microsoft.com/) |
| 设置 |  管理Microsoft 365 Defender、终结点、电子邮件&协作、标识和设备发现设置。   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365安全导航和功能

左侧导航栏或快速启动栏将看起来熟悉。 但是，Microsoft 365 Defender门户中有一些新的和更新的元素。 

### <a name="incidents-and-alerts"></a>事件和警报

将跨电子邮件、设备和标识的事件和警报管理结合起来。 警报页通过组合攻击信号来构造详细信息，为警报提供完整的上下文。 全新的统一体验现在汇集了跨工作负荷的一致警报视图。 您可以快速分案、调查，以及采取有效措施。

- [详细了解事件](incidents-overview.md)
- [深入了解如何管理警报](investigate-alerts.md)

:::image type="content" source="../../media/converge-1-alerts-and-actions.png" alt-text="Microsoft 365 Defender门户中的&quot;警报和操作&quot;快速启动栏" lightbox="../../media/converge-1-alerts-and-actions.png":::

### <a name="hunting"></a>搜寻

通过使用 [高级搜索查询来在终结点、Office 365 邮箱等位置主动搜索威胁、恶意软件和恶意](advanced-hunting-overview.md)。 这些强大的查询可用于查找和查看已知和潜在威胁的威胁指标和实体。

可以从高级搜寻查询生成[自定义检测规则](custom-detection-rules.md)，以帮助你主动监视可能表明存在违规活动和配置错误的设备的事件。


### <a name="action-center"></a>操作中心

操作中心显示自动调查和响应功能创建调查。 Microsoft 365 Defender 中的自动自恢复功能可自动响应特定事件，帮助团队实现安全。

[详细了解操作中心](m365d-action-center.md)。

### <a name="threat-analytics"></a>威胁分析

从 Microsoft 安全研究人员获取威胁智能。 威胁分析可帮助安全团队在面对新兴威胁时更有效率。 威胁分析包括：

- Microsoft Defender for Office 365 的与电子邮件相关的检测和缓解措施。 除了从 Microsoft Defender for Endpoint 中可用的终结点数据外，还有一个终结点数据。
- 与威胁相关的事件视图。
- 增强的体验，可快速识别和使用报告中的可操作信息。

可以从Microsoft 365 Defender中的左上角导航栏或显示组织最主要威胁的专用仪表板卡访问威胁分析。

详细了解如何 [使用威胁分析跟踪和响应新出现的威胁](./threat-analytics.md)。

### <a name="endpoints-section"></a>"终结点"部分

查看和管理组织中终结点的安全性。 如果已使用Microsoft Defender 安全中心，它将看起来很熟悉。

:::image type="content" source="../../media/converge-2-endpoints.png" alt-text="Microsoft 365 Defender门户中的&quot;终结点&quot;快速启动栏" lightbox="../../media/converge-2-endpoints.png":::

### <a name="access-and-reports"></a>访问和报表

查看报表、更改设置和修改用户角色。

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Microsoft 365 Defender门户中的&quot;访问和报告&quot;快速启动栏" lightbox="../../media/converge-4-access-and-reporting-new.png":::

### <a name="siem-api-connections"></a>SIEM API 连接

如果使用 [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md)，则可以继续执行此操作。 我们在 API 有效负载上添加了指向警报页或Microsoft 365安全门户中的事件页的新链接。 新的 API 字段包括 LinkToMTP 和 IncidentLinkToMTP。 有关详细信息，请参阅[将帐户从Microsoft Defender for Endpoint重定向到Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md)。

### <a name="email-alerts"></a>电子邮件警报

可以继续使用 Defender for Endpoint 的电子邮件警报。 我们在指向Microsoft 365 Defender中的警报页或事件页面的电子邮件中添加了新链接。 有关详细信息，请参阅[将帐户从Microsoft Defender for Endpoint重定向到Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md)。

### <a name="managed-security-service-providers-mssp"></a>托管安全服务提供商 (MSSP) 

统一门户目前不支持在同一浏览会话中同时登录到多个租户。 可以通过[还原到前Microsoft Defender for Endpoint门户](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)来选择退出自动重定向，以保持此功能，直到问题得到解决。

## <a name="related-information"></a>相关信息

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft 365 Defender中的Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [将帐户从Microsoft Defender for Endpoint重定向到Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)
