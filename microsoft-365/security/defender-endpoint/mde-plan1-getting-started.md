---
title: Microsoft Defender 终结点计划 1 入门
description: 开始使用 Defender for Endpoint Plan 1。 了解如何使用 Defender for Cloud、管理警报和设备以及查看报告。
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
ms.openlocfilehash: d4e585a7714bddc8c89de75ae49464da7bfe0305
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62245323"
---
# <a name="get-started-with-microsoft-defender-for-endpoint-plan-1"></a>Microsoft Defender 终结点计划 1 入门

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

通过Microsoft 365 Defender门户 () 查看有关检测到的威胁的信息、管理警报和事件、对检测到的威胁采取任何所需操作以及 [https://security.microsoft.com](https://security.microsoft.com) 管理设备。 在Microsoft 365 Defender门户中，你可以开始与使用 Defender for Endpoint Plan 1 获取的威胁防护功能交互。 以下各节介绍如何开始：

- [Microsoft 365 Defender 门户](#the-microsoft-365-defender-portal)
- [查看和管理事件&警报](#view-and-manage-incidents--alerts)
- [管理设备](#manage-devices)
- [查看报告](#view-reports)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户

Microsoft 365 Defender门户 () ，你可以在这里查看警报、管理设备和 [https://security.microsoft.com](https://security.microsoft.com) 查看报告。 当你登录到 Microsoft 365 Defender门户时，你将从主页开始，如下图所示：

:::image type="content" source="../../media/mde-p1/m365-defender-portal.png" alt-text="Microsoft 365 Defender 门户":::

主页为安全团队提供了警报、设备状态和检测到的威胁的快照聚合视图。 已设置 Defender for Cloud，以便你的安全运营团队可以快速轻松地找到他们正在寻找的信息。

> [!NOTE]
> 本文中所示的示例可能与你在应用程序门户中Microsoft 365 Defender不同。 在门户中看到的内容取决于许可证和权限。 此外，安全团队可以通过添加、删除和重新设置卡片来自定义组织的门户。

### <a name="cards-highlight-key-information-and-include-recommendations"></a>卡片突出显示关键信息并包括建议

主页包含卡片，如下图中所示的活动事件卡片：

:::image type="content" source="../../media/mde-p1/active-incidents-card.png" alt-text="活动事件卡片":::

卡片提供了一览信息，以及一个链接或按钮，您可以选择该链接或按钮查看更多详细信息。 引用我们的示例"活动事件"卡片，我们可以选择"查看 **所有** 事件"以导航到事件列表。

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="事件列表":::

### <a name="navigation-bar-makes-it-easy-to-find-alerts-the-action-center-and-more"></a>导航栏便于查找警报、操作中心等

利用屏幕左侧的导航栏，您可以在事件、警报、操作中心、报告和设置之间轻松移动。 下表介绍了导航栏。<br/><br/>

| 导航栏项 | 说明 |
|:---|:---|
| **主页** | 导航到 Microsoft 365 Defender[主页](../defender/microsoft-365-security-center-mde.md)。 |
| **事件&警报** | 展开以显示 **事件** 和 **警报**。 |
| **事件&警报**  > **事件** | 导航到 **"事件"** 列表。 当触发警报和/或检测到威胁时，将创建事件。 默认情况下，" **事件** "列表显示最近 30 天的数据，首先列出最近事件。 <br/><br/> 若要了解更多信息，请参阅 [事件](view-incidents-queue.md)。 |
| **事件&警报**  > **警报** | 导航到 **警报列表** (也称为警报 **队列**) 。 当检测到可疑或恶意文件、进程或行为时，将触发警报。 默认情况下，警报 **列表** 显示最近 30 天的数据，首先列出最新警报。 <br/><br/> 若要了解更多信息，请参阅 [警报](alerts-queue.md)。 |
| **操作中心** | 导航到操作中心，该中心跟踪修正和手动响应操作。 操作中心将跟踪类似以下的活动： <br/>- Microsoft Defender 防病毒遇到恶意文件，然后阻止/删除该文件。 <br/>- 安全团队隔离设备。<br/>- Defender for Endpoint 检测并隔离文件。 <br/><br/> 若要了解更多信息，请参阅 [操作中心](auto-investigation-action-center.md)。 |
| **安全分数** | 显示组织安全状况的表示形式以及改进措施和指标列表。 <br/><br/> 若要了解更多信息，请参阅 [Microsoft 安全分数](../defender/microsoft-secure-score.md)。 |
| **Learning中心** | 导航到可以访问的学习路径列表，以了解有关Microsoft 365功能。  |
| **终结点**  > **搜索** | 导航到可以按设备名称搜索特定设备的页面。 在结果列表中，您可以一目了然地查看详细信息，如风险级别和运行状况。 |
|  **终结点**  > **设备清单** | 导航到已载入到 Defender for Endpoint 的设备列表。 提供有关设备的信息，例如设备的曝光和风险级别。 <br/><br/> 若要了解更多信息，请参阅 [设备清单](machines-view-overview.md)。 |
|  **终结点**  > **配置&基线** | 展开以显示 **安全基线和****配置管理**。 |
|  **终结点**  > **配置&基线**  > **安全基线** | 安全基线是预配置的策略和设置组，可帮助你有效应用建议的安全设置。 基线包括基于行业最佳做法的设置。 您可以保留默认设置，或自定义基线以满足组织的需求。 <br/><br/> 若要了解更多信息，请参阅[使用安全基线在 Intune Windows 10配置设备](/mem/intune/protect/security-baselines)。 |
|  **终结点**  > **配置&基线**  > **配置管理** | 导航到 **"设备配置管理** "页，可在其中查看有关已载入设备的信息，并采取措施载入更多设备。 |
| **报表** | 导航到报告， [如威胁防护](threat-protection-reports.md)报告、设备运行状况和合规性 [报告](machine-reports.md)以及 [Web 保护报告](web-protection-overview.md)。 |
| **运行状况** | 包括指向服务 **运行状况和消息****中心的链接**。  |
| **运行状况**  > **服务运行状况** | 导航到"服务运行状况"页Microsoft 365 管理中心。 通过此页面，您可以查看组织订阅提供的所有服务的运行状况状态。   |
| **运行状况**  > **消息中心** | 导航到邮件消息中心Microsoft 365 管理中心。 消息中心提供有关计划更改的信息。 每条消息都描述即将发生的变化、它可能会如何影响用户以及如何管理更改。 |  
| **角色&权限** | 使您可以授予使用 Microsoft 365 Defender 门户的权限。 权限通过角色或角色Azure Active Directory (Azure AD) 。 选择一个角色，将出现一个飞出窗格。 该飞出包含一个Azure AD链接，可在其中添加或删除角色组的成员。 <br/><br/> 若要了解更多信息，请参阅 [使用基于角色的访问控制管理门户访问](rbac.md)。  |
| **设置** | 导航到你的 Microsoft 365 Defender 门户的常规 (列为安全中心) 和Defender for Endpoint (列为 **终结点) 。** <br/><br/> 若要了解更多信息[，请参阅](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)设置。 |
| **更多资源** | 显示更多门户和中心的列表，如Azure Active Directory和Microsoft 365 合规中心。 <br/><br/> 若要了解更多信息，请参阅 [Microsoft 安全门户和管理中心](../defender/portals.md)。 |

> [!TIP]
> 若要了解更多信息，请参阅Microsoft 365 Defender[门户概述](../defender/microsoft-365-security-center-mde.md)。

## <a name="view-and-manage-incidents--alerts"></a>查看和管理事件&警报

登录 Microsoft 365 Defender门户时，请确保查看和管理事件和警报。 从事件 **列表** 开始。 下图显示了事件列表，包括高严重性事件和中等严重性事件。

:::image type="content" source="../../media/mde-p1/incidents.png" alt-text="事件列表":::

选择事件以查看有关事件的详细信息。 详细信息包括触发了哪些警报、受影响的设备和用户数以及其他详细信息。 下图显示了事件详细信息的示例。

:::image type="content" source="../../media/mde-p1/single-incident.png" alt-text="事件详细信息":::

使用 **警报**、**设备和** 用户选项卡查看详细信息，例如触发的警报、受影响的设备和受影响的用户帐户。 你可以从该位置执行手动响应操作，例如隔离设备、停止和隔离文件等。

> [!TIP]
> 若要了解有关使用事件视图 **的更多** 信息，请参阅 [管理事件](manage-incidents.md)。

## <a name="manage-devices"></a>管理设备

若要查看和管理组织的设备，请在导航栏中的"终结点"下，选择"**设备清单"。**  你将看到设备列表，如下图所示：

:::image type="content" source="../../media/mde-p1/device-inventory.png" alt-text="设备清单":::

该列表包括生成警报的设备。 默认情况下，显示的数据是过去 30 天，首先列出最新项目。 选择设备以查看有关它的信息。 将打开一个飞出窗格，如下图所示：

:::image type="content" source="../../media/mde-p1/device-inventory-selecteddevice.png" alt-text="所选设备详细信息":::

飞出窗格显示详细信息（例如设备的任何活动警报）并包括要采取措施的链接，例如隔离设备。

如果设备上存在活动警报，可以在飞出窗格中查看它们。 选择单个警报以查看有关它的更多详细信息。 或者，采取隔离设备等操作，以便你可以进一步调查设备，同时将感染其他设备的风险最小化。

> [!TIP]
> 若要了解更多信息，请参阅 [调查 Defender for Endpoint 设备列表中的设备](investigate-machines.md)。

## <a name="view-reports"></a>查看报告

在 Defender for Endpoint Plan 1 中，多个报告在 Microsoft 365 Defender 门户中提供。 若要访问报告，请按照以下步骤操作：

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. 在导航栏中，选择"报告 **"。**

3. 在列表中选择一个报表。 你将看到以下三个报告：

   - 威胁防护报告
   - 设备运行状况报告
   - Web 保护报告

> [!TIP]
> 有关详细信息，请参阅 [威胁防护报告](threat-protection-reports.md)。

### <a name="threat-protection-report"></a>威胁防护报告

若要访问威胁防护报告，在 Microsoft 365 Defender门户中，选择"报告"，然后选择"**威胁防护"。** 威胁防护报告显示警报趋势、状态、类别等。 视图按两列排列： **警报趋势** 和 **警报状态**，如下图所示：

:::image type="content" source="../../media/mde-p1/threat-protection-report.png" alt-text="威胁防护报告":::

向下滚动以查看每个列表中的所有视图。

- 默认情况下，"警报趋势"列中的视图显示过去 30 天的数据，但您可以设置视图以显示最近三个月、过去六个月或自定义时间范围 (最多为) 年的数据。
- 警报状态 **列中的** 视图是前一个工作天的快照。

> [!TIP]
> 若要了解更多信息，请参阅 Defender [for Endpoint 中的威胁防护报告](threat-protection-reports.md)。

### <a name="device-health-report"></a>设备运行状况报告

若要访问设备运行状况报告，在Microsoft 365 Defender门户中，选择"报告"，然后选择"设备 **运行状况"。** 设备运行状况报告显示组织中各设备的运行状况状态和防病毒。 与威胁[防护报告类似](#threat-protection-report)，视图按两列排列：设备趋势和设备摘要，如下图所示：

:::image type="content" source="../../media/mde-p1/device-health-report.png" alt-text="设备运行状况报告":::

向下滚动以查看每个列表中的所有视图。 默认情况下，"设备趋势"列中的视图显示过去 30 天的数据，但你可以更改视图以显示最近三个月、过去六个月或自定义时间范围 (最多为) 年 180 天的数据。 设备 **摘要视图** 是上一个工作天的快照。

> [!TIP]
> 若要了解更多信息，请参阅 [设备运行状况](machine-reports.md)。

### <a name="web-protection-report"></a>Web 保护报告

若要访问设备运行状况报告，在Microsoft 365 Defender门户中，选择"报告"，然后选择 **"Web 保护"。**  Web 保护报告显示一段时间的检测，如恶意 URL 和尝试访问阻止的 URL，如下图所示：

:::image type="content" source="../../media/mde-p1/web-protection-report.png" alt-text="Web 保护报告":::

向下滚动以查看 Web 保护报告中的所有视图。 某些视图包括链接，通过这些链接可以查看更多详细信息、配置威胁防护功能，甚至管理在 Defender for Endpoint 中充当例外的指示器。

> [!TIP]
> 若要了解更多信息，请参阅 [Web 保护](web-protection-overview.md)。

## <a name="next-steps"></a>后续步骤

- [管理 Microsoft Defender 终结点计划 1](mde-p1-maintenance-operations.md)
- [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)
