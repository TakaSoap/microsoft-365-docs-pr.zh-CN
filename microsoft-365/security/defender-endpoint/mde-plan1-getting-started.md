---
title: 开始Microsoft Defender for Endpoint计划 1
description: 开始使用 Defender for Endpoint Plan 1。 了解如何使用Defender for Cloud、管理警报和设备以及查看报表。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/03/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.custom: intro-get-started
ms.openlocfilehash: 68315c6cf7947c2d42e58e34b4496e0ef790c8b0
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665483"
---
# <a name="get-started-with-microsoft-defender-for-endpoint-plan-1"></a>开始Microsoft Defender for Endpoint计划 1

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) 使你能够查看有关检测到的威胁的信息、管理警报和事件、对检测到的威胁采取任何所需的操作，以及管理设备。 Microsoft 365 Defender门户是开始与 Defender for Endpoint Plan 1 交互的威胁防护功能的地方。 以下部分介绍如何开始使用：

- [Microsoft 365 Defender 门户](#the-microsoft-365-defender-portal)
- [查看和管理事件&警报](#view-and-manage-incidents--alerts)
- [管理设备](#manage-devices)
- [查看报表](#view-reports)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户

Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) 可以查看警报、管理设备和查看报表。 登录Microsoft 365 Defender门户时，将开始使用主页，如下图所示：

:::image type="content" source="../../media/mde-p1/m365-defender-portal.png" alt-text="Microsoft 365 Defender的门户" lightbox="../../media/mde-p1/m365-defender-portal.png":::

主页为安全团队提供了警报、设备状态和检测到的威胁的快照聚合视图。 设置了Defender for Cloud，以便安全运营团队可以快速轻松地找到他们要查找的信息。

> [!NOTE]
> 本文中所示的示例可能不同于你在Microsoft 365 Defender门户中看到的内容。 在门户中看到的内容取决于许可证和权限。 此外，安全团队还可以通过添加、删除和重新排列卡来自定义组织的门户。

### <a name="cards-highlight-key-information-and-include-recommendations"></a>卡片突出显示关键信息并包含建议

主页包含卡片，如下图中显示的活动事件卡片：

:::image type="content" source="../../media/mde-p1/active-incidents-card.png" alt-text="活动事件卡" lightbox="../../media/mde-p1/active-incidents-card.png":::

该卡片提供一目了然的信息，以及一个链接或按钮，你可以选择该链接或按钮来查看更详细的信息。 引用示例"活动事件"卡片，可以选择 **"查看所有事件** "以导航到事件列表。

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="事件列表" lightbox="../../media/mde-p1/incidents.png":::

### <a name="navigation-bar-makes-it-easy-to-find-alerts-the-action-center-and-more"></a>导航栏可轻松查找警报、操作中心等

屏幕左侧的导航栏使你可以在事件、警报、操作中心、报表和设置之间轻松移动。 下表描述了导航栏。<br/><br/>

| 导航栏项 | 说明 |
|:---|:---|
| **主页** | 导航到[Microsoft 365 Defender门户](../defender/microsoft-365-security-center-mde.md)的主页。 |
| **事件&警报** | 展开以显示 **事件** 和 **警报**。 |
| **事件&警报** > **事件** | 导航到 **"事件"** 列表。 触发警报和/或检测到威胁时会创建事件。 默认情况下，" **事件** "列表显示过去 30 天的数据，其中首先列出了最新的事件。 <br/><br/> 若要了解详细信息，请参阅 ["事件](view-incidents-queue.md)"。 |
| **事件&警报** > **警报** | 导航到 **警报** 列表 (也称为 **警报队列**) 。 检测到可疑或恶意文件、进程或行为时，将触发警报。 默认情况下，" **警报** "列表显示过去 30 天的数据，其中首先列出了最新的警报。 <br/><br/> 若要了解详细信息，请参阅 [警报](alerts-queue.md)。 |
| **操作中心** | 导航到操作中心，该中心跟踪修正和手动响应操作。 操作中心跟踪如下活动： <br/>- Microsoft Defender 防病毒遇到恶意文件，然后阻止/删除该文件。 <br/>- 安全团队隔离设备。<br/>- Defender for Endpoint 检测并隔离文件。 <br/><br/> 若要了解详细信息，请参阅 [操作中心](auto-investigation-action-center.md)。 |
| **安全分数** | 显示组织的安全状况的表示形式以及改进操作和指标列表。 <br/><br/> 若要了解详细信息，请参阅 [Microsoft 安全分数](../defender/microsoft-secure-score.md)。 |
| **Learning中心** | 导航到可以访问的学习路径列表，了解有关Microsoft 365安全功能的详细信息。  |
| **端点** > **搜索** | 导航到可在其中按设备名称搜索特定设备的页面。 在结果列表中，可以一目了然地看到详细信息，例如风险级别和运行状况状态。 |
|  **端点** > **设备清单** | 导航到载入到 Defender for Endpoint 的设备列表。 提供有关设备的信息，例如其暴露和风险级别。 <br/><br/> 若要了解详细信息，请参阅 [设备清单](machines-view-overview.md)。 |
|  **端点** > **配置&基线** | 展开以显示 **安全基线** 和 **配置管理**。 |
|  **端点** > **配置&基线** > **安全基线** | 安全基线是预配置的策略和设置组，可帮助你高效有效地应用建议的安全设置。 基线包括基于行业最佳做法的设置。 可以保留默认设置，也可以根据组织的需求自定义基线。 <br/><br/> 若要了解详细信息，请参阅[使用安全基线在Intune中配置Windows 10设备](/mem/intune/protect/security-baselines)。 |
|  **端点** > **配置&基线** > **配置管理** | 导航到 **"设备配置管理** "页，可在其中查看有关载入设备的信息，并采取措施载入更多设备。 |
| **报表** | 导航到报表，例如 [威胁防护报告](threat-protection-reports.md)、 [设备运行状况和符合性报告](machine-reports.md)以及 [Web 保护报告](web-protection-overview.md)。 |
| **运行状况** | 包括指向 **服务运行状况** 和 **消息中心的** 链接。  |
| **健康** > **服务运行状况** | 导航到Microsoft 365 管理中心中的服务运行状况页。 通过此页，可以查看组织订阅中所有可用服务的运行状况。   |
| **健康** > **消息中心** | 导航到Microsoft 365 管理中心中的消息中心。 消息中心提供有关计划内更改的信息。 每条消息都描述即将出现的内容、它对用户的影响以及如何管理更改。 |  
| **&角色的权限** | 允许你授予使用Microsoft 365 Defender门户的权限。 权限通过Azure Active Directory (Azure AD) 中的角色授予。 选择一个角色，并显示浮出窗格。 浮出控件包含指向Azure AD的链接，可在其中添加或删除角色组中的成员。 <br/><br/> 若要了解详细信息，请参阅 [使用基于角色的访问控制管理门户访问](rbac.md)。  |
| **设置** | 导航到Microsoft 365 Defender门户的常规设置 (列为 **安全中心**) 和 Defender for Endpoint (列为 **终结点**) 。 <br/><br/> 若要了解详细信息，请[参阅设置](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)。 |
| **更多资源** | 显示更多门户和中心的列表，例如Azure Active Directory和Microsoft 365 合规中心。 <br/><br/> 若要了解详细信息，请参阅 [Microsoft 安全门户和管理中心](../defender/portals.md)。 |

> [!TIP]
> 若要了解详细信息，请参阅[Microsoft 365 Defender门户概述](../defender/microsoft-365-security-center-mde.md)。

## <a name="view-and-manage-incidents--alerts"></a>查看和管理事件&警报

登录Microsoft 365 Defender门户时，请务必查看和管理事件和警报。 从 **事件** 列表开始。 下图显示了事件的列表，包括一个严重性很高的事件，另一个事件严重性中等。

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="事件列表":::

选择事件以查看有关事件的详细信息。 详细信息包括触发了哪些警报、受影响的设备和用户数量以及其他详细信息。 下图显示了事件详细信息的示例。

:::image type="content" source="../../media/mde-p1/single-incident.png" alt-text="事件的详细信息" lightbox="../../media/mde-p1/single-incident.png":::

使用 **"警报**"、" **设备**"和 **"用户** "选项卡查看详细信息，例如触发的警报、受影响的设备和受影响的用户帐户。 可以从那里执行手动响应操作，例如隔离设备、停止和隔离文件等。

> [!TIP]
> 若要了解有关使用 **事件** 视图的详细信息，请参阅 ["管理事件](manage-incidents.md)"。

## <a name="manage-devices"></a>管理设备

若要查看和管理组织的设备，请在导航栏的 **"终结点**"下选择 **"设备清单**"。 你将看到设备列表，如下图所示：

:::image type="content" source="../../media/mde-p1/device-inventory.png" alt-text="设备清单" lightbox="../../media/mde-p1/device-inventory.png":::

该列表包括为其生成警报的设备。 默认情况下，显示的数据是过去 30 天的数据，其中首先列出了最新的项目。 选择设备以查看有关它的详细信息。 随即打开浮出窗格，如下图所示：

:::image type="content" source="../../media/mde-p1/device-inventory-selecteddevice.png" alt-text="所选设备详细信息" lightbox="../../media/mde-p1/device-inventory-selecteddevice.png":::

浮出窗格显示详细信息，例如设备的任何活动警报，并包含要采取措施的链接，例如隔离设备。

如果设备上存在活动警报，可以在浮出窗格中查看它们。 选择单个警报以查看有关该警报的更多详细信息。 或者，执行隔离 **设备** 等操作，以便可以进一步调查设备，同时最大限度地降低感染其他设备的风险。

> [!TIP]
> 若要了解详细信息，请参阅 [Defender for Endpoint 设备列表中的"调查设备](investigate-machines.md)"。

## <a name="view-reports"></a>查看报告

在 Defender for Endpoint Plan 1 中，Microsoft 365 Defender门户中提供了多个报表。 若要访问报表，请执行以下步骤：

1. 转到Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航栏中，选择 **"报表**"。

3. 在列表中选择一个报表。 你将看到以下三个报告：

   - 威胁防护报告
   - 设备运行状况报告
   - Web 保护报告

> [!TIP]
> 有关详细信息，请参阅 [威胁防护报告](threat-protection-reports.md)。

### <a name="threat-protection-report"></a>威胁防护报告

若要访问威胁防护报告，请在Microsoft 365 Defender门户中选择 **"报** 表"，然后选择 **"威胁防护**"。 威胁防护报告显示警报趋势、状态、类别等。 视图按两列排列： **警报趋势** 和 **警报状态**，如下图所示：

:::image type="content" source="../../media/mde-p1/threat-protection-report.png" alt-text="威胁防护报告" lightbox="../../media/mde-p1/threat-protection-report.png":::

向下滚动以查看每个列表中的所有视图。

- 默认情况下，" **警报趋势"** 列中的视图显示过去 30 天的数据，但你可以设置一个视图来显示过去 3 个月、过去 6 个月或自定义时间范围 (长达 180 天) 。
- **警报状态** 列中的视图是前一个工作日的快照。

> [!TIP]
> 若要了解详细信息，请 [参阅 Defender for Endpoint 中的威胁防护报告](threat-protection-reports.md)。

### <a name="device-health-report"></a>设备运行状况报告

若要访问设备运行状况报告，请在Microsoft 365 Defender门户中选择 **"报** 表"，然后选择 **"设备运行状况**"。 设备运行状况报告显示组织中设备的运行状况状态和防病毒。 与 [威胁防护报告](#threat-protection-report)类似，视图按两列排列： **设备趋势** 和 **设备摘要**，如下图所示：

:::image type="content" source="../../media/mde-p1/device-health-report.png" alt-text="设备运行状况报告" lightbox="../../media/mde-p1/device-health-report.png":::

向下滚动以查看每个列表中的所有视图。 默认情况下，" **设备趋势** "列中的视图显示过去 30 天的数据，但您可以更改视图以显示过去三个月、过去六个月或自定义时间范围 (最多 180 天) 。 **设备摘要** 视图是前一个工作日的快照。

> [!TIP]
> 若要了解详细信息，请参阅 [设备运行状况](machine-reports.md)。

### <a name="web-protection-report"></a>Web 保护报告

若要访问设备运行状况报告，请在Microsoft 365 Defender门户中选择 **"报** 表"，然后选择 **Web 保护**。 Web 保护报告显示一段时间内的检测，例如恶意 URL 和尝试访问被阻止的 URL，如下图所示：

:::image type="content" source="../../media/mde-p1/web-protection-report.png" alt-text="Web 保护报告" lightbox="../../media/mde-p1/web-protection-report.png":::

向下滚动以查看 Web 保护报告中的所有视图。 某些视图包括可查看更多详细信息、配置威胁防护功能甚至管理在 Defender for Endpoint 中充当异常的指示器的链接。

> [!TIP]
> 若要了解详细信息，请参阅 [Web 保护](web-protection-overview.md)。

## <a name="next-steps"></a>后续步骤

- [管理Microsoft Defender for Endpoint计划 1](mde-p1-maintenance-operations.md)
- [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)
