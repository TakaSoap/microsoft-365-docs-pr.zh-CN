---
title: 在 Microsoft 365 Defender 中调查事件
description: 调查与设备、用户和邮箱相关的事件。
keywords: 事件， 事件， 分析， 响应， 计算机， 设备， 用户， 标识， 邮件， 电子邮件， 邮箱， 调查， 图形， 证据
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 8138c07ab871ab1a6a8d89df980c914983bbb58e
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666935"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中调查事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

Microsoft 365 Defender将设备、用户和邮箱中的所有相关警报、资产、调查和证据聚合到事件中，以便全面了解攻击的整个广度。

在某个事件中，你将分析影响网络的警报，了解它们的含义，并整理证据，以便可以制定有效的修正计划。

## <a name="initial-investigation"></a>初步调查

在深入了解详细信息之前，请查看事件的属性和摘要。

首先，可以从复选标记列中选择事件。 下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="在Microsoft 365 Defender门户中选择事件" lightbox="../../media/investigate-incidents/incidents-ss-incident-select.png":::

执行此操作时，将打开一个摘要窗格，其中包含有关事件的关键信息，例如向其分配事件的严重性，以及 [事件的 MITRE ATT&CK&trade;](https://attack.mitre.org/) 类别。 下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="在Microsoft 365 Defender门户中显示事件摘要详细信息的窗格。" lightbox="../../media/investigate-incidents/incidents-ss-incident-side-panel.png":::

在此处，可以选择 **"打开事件"页**。 这将打开事件的主页，你将在其中找到警报、设备、用户、调查和证据的更多摘要信息和选项卡。

还可以通过从事件队列中选择事件名称来打开事件的主页。

## <a name="summary"></a>摘要

" **摘要** "页提供有关事件的要注意事项的快照概览。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 Defender门户中事件的摘要信息" lightbox="../../media/incidents-overview/incidents-ss-incident-summary.png":::

这些部分中会组织信息。

| 节 | 说明 |
|:-------|:-----|
| 警报和类别 | 一个视觉和数字视图，了解攻击对杀伤链的推进程度。 与其他 Microsoft 安全产品一样，Microsoft 365 Defender与 [MITRE ATT&CK&trade;](https://attack.mitre.org/) 框架保持一致。 警报时间线显示警报发生的时间顺序以及每个警报的状态和名称。 |
| 范围 |  显示受影响的设备、用户和邮箱的数量，并按风险级别和调查优先级的顺序列出实体。 |
| 证据 | 显示受事件影响的实体数。 |
| 事件信息 | 显示事件的属性，例如标记、状态和严重性。 |
|||

使用 **"摘要"** 页评估事件的相对重要性，并快速访问关联的警报和受影响的实体。

## <a name="alerts"></a>警报

在 **"警报"** 选项卡上，可以查看与事件相关的警报的警报队列及其相关的其他信息，例如：

- 严重性。
- 警报中涉及的实体。
- 警报源 (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Defender for Cloud应用和应用治理加载项) 。
- 他们联系在一起的原因。

下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Microsoft 365 Defender门户中事件的&quot;警报&quot;窗格" lightbox="../../media/investigate-incidents/incident-alerts.png":::

默认情况下，警报按时间顺序排序，以便查看攻击在一段时间内的表现。 在事件中选择警报时，Microsoft 365 Defender显示特定于整个事件上下文的警报信息。 

可以看到警报的事件，其他触发的警报导致了当前警报，以及攻击中涉及的所有受影响实体和活动，包括设备、文件、用户和邮箱。

下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Microsoft 365 Defender门户中事件内警报的详细信息。" lightbox="../../media/investigate-incidents/incident-alert-example.png":::

事件警报页包含以下部分：

- 警报故事，其中包括：

   - 发生了什么事

   - Mailbox01 会使用新的数据库重新联机。

   - 相关事件

- 右窗格中的警报属性 (状态、详细信息、说明和其他) 

并非每个警报都有" **警报"故事** 部分中列出的所有子节。

了解如何在 [调查警报](investigate-alerts.md)时使用警报队列和警报页。

## <a name="devices"></a>设备

" **设备"** 选项卡列出了与事件相关的所有设备。 下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Microsoft 365 Defender门户中事件的&quot;设备&quot;页" lightbox="../../media/investigate-incidents/incident-devices.png":::

可以选择设备的复选标记，查看设备的详细信息、目录数据、活动警报和登录用户。 选择设备的名称，查看 Defender for Endpoint 设备清单中的设备详细信息。 下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender for Endpoint中的设备清单选项相关页面。" lightbox="../../media/investigate-incidents/incident-devices-details.png":::

在设备页中，可以收集有关设备的其他信息，例如其所有警报、时间线和安全建议。 例如，在 **"时间线"** 选项卡中，可以滚动浏览计算机时间线，并按时间顺序查看在计算机上观察到的所有事件和行为，这些事件和行为与引发的警报相穿插。

> [!TIP]
> 可以在设备页面上执行按需扫描。 在Microsoft 365 Defender门户中，选择"**终结点">设备清单**。 选择具有警报的设备，然后运行防病毒扫描。 将跟踪防病毒扫描等操作，并在 **"设备清单** "页上显示。 若要了解详细信息，请参阅 [设备上的 Run Defender 防病毒扫描](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。

## <a name="users"></a>用户

" **用户** "选项卡列出了已确定为事件一部分或与事件相关的所有用户。 下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Microsoft 365 Defender门户中的&quot;用户&quot;页。" lightbox="../../media/investigate-incidents/incident-users.png":::

可以选择用户的复选标记，查看用户帐户威胁、曝光和联系信息的详细信息。 选择用户名以查看其他用户帐户详细信息。

了解如何在调查用户时查看其他用户信息和管理事件 [的用户](investigate-users.md)。


## <a name="mailboxes"></a>邮箱

" **邮箱** "选项卡列出了已确定为事件一部分或与事件相关的所有邮箱。 下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Microsoft 365 Defender门户中事件的&quot;邮箱&quot;页。" lightbox="../../media/investigate-incidents/incident-mailboxes.png":::

可以选择邮箱的复选标记以查看活动警报列表。 选择邮箱名称，查看资源管理器页面上用于Defender for Office 365的其他邮箱详细信息。

## <a name="investigations"></a>调查

" **调查** "选项卡列出了此事件中警报触发的所有 [自动调查](m365d-autoir.md) 。 自动调查将执行修正操作或等待分析师批准操作，具体取决于你如何将自动调查配置为在 Defender for Endpoint 和 Defender for Office 365 中运行。

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Microsoft 365 Defender门户中事件的调查页" lightbox="../../media/investigate-incidents/incident-investigations.png":::

选择调查以导航到其详细信息页，以获取有关调查和修正状态的完整信息。 如果在调查过程中有任何待批准的操作，它们将显示在 **"挂起操作历史记录** "选项卡中。作为事件修正的一部分采取行动。

还有一个 **"调查图** "选项卡，显示：

- 警报与组织中受影响的资产的连接。
- 哪些实体与哪些警报以及它们如何成为攻击事件的一部分相关。
- 事件的警报。

调查图通过将属于攻击的不同可疑实体与其相关资产（如用户、设备和邮箱）连接起来，帮助你快速了解攻击的全部范围。 

有关详细信息，请参阅[Microsoft 365 Defender中的自动调查和响应](m365d-autoir.md)。

## <a name="evidence-and-response"></a>证据和响应

" **证据和响应** "选项卡显示事件中警报中所有受支持的事件和可疑实体。 下面是一个示例。

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Microsoft 365 Defender门户中事件的证据和响应页" lightbox="../../media/investigate-incidents/incident-evidence.png":::

Microsoft 365 Defender自动调查警报中所有事件支持的事件和可疑实体，为你提供有关重要电子邮件、文件、流程、服务、IP 地址等的信息。 这有助于快速检测和阻止事件中的潜在威胁。

每个分析实体都标有 (恶意、可疑、清理) 和修正状态的判断。 这有助于了解整个事件的修正状态，以及可以采取哪些后续步骤。

## <a name="graph-preview"></a>Graph (预览) 

**"Graph**"选项卡显示攻击的完整范围、攻击如何随着时间推移通过网络传播、攻击开始的位置以及攻击者走了多远。 它将参与攻击的不同可疑实体与其相关资产（如用户、设备和邮箱）连接起来。 

在 **"Graph**"选项卡中，可以：

1. 在图中播放警报和节点，因为它们随时间推移而发生，以了解攻击的年表。


   :::image type="content" source="../../media/investigate-incidents/incident-graph-play.gif" alt-text="在Graph页上播放警报和节点":::
 

2. 打开实体窗格，以便查看实体详细信息并执行修正操作，例如删除文件或隔离设备。
 
   :::image type="content" source="../../media/investigate-incidents/incident-graph-entity-pane.png" alt-text="Microsoft 365 Defender门户中Graph页上的实体窗格" lightbox="../../media/investigate-incidents/incident-graph-entity-pane.png":::

3. 根据与警报相关的实体突出显示警报。
 
   :::image type="content" source="../../media/investigate-incidents/incident-graph-alert.png" alt-text="Graph页上的警报突出显示" lightbox="../../media/investigate-incidents/incident-graph-alert.png":::

## <a name="next-steps"></a>后续步骤

根据需要：

- [调查事件的警报](investigate-alerts.md)
- [调查事件的用户](investigate-users.md)

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [确定事件优先级](incident-queue.md)
- [管理事件](manage-incidents.md)
