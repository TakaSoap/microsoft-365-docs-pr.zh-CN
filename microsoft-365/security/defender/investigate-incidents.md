---
title: 调查 Microsoft 365 Defender 中的事件
description: 分析与设备、用户和邮箱相关的事件。
keywords: 事件, 多个事件, 计算机, 设备, 用户, 标识, 邮件, 电子邮件, 邮箱, 调查, 图表, 证据
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592092"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>调查 Microsoft 365 Defender 中的事件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**

- Microsoft 365 Defender

Microsoft 365 Defender 聚合来自你的设备、用户和邮箱的所有用户的相关警报、资产、调查和证据，以便全面了解整个攻击范围。

调查影响网络的警报，了解其含义，整理与事件相关的证据，以便可以制定出有效的补救计划。

## <a name="investigate-an-incident"></a>调查事件

1. 从事件队列中选择一个事件。 <BR> 侧面板将打开，并预览重要信息，如状态、严重性、类别和影响的实体。

    ![事件侧面板的图像](../../media/incident-side-panel.png)

2. 选择“**打开事件页面**”。 <BR> 这将打开事件页面，您可以在其中找到事件详细信息、注释和操作、选项卡 (概述、警报、设备、用户、调查、证据) 。

3. 查看警报、设备、用户、其它涉及事件的实体。

## <a name="incident-overview"></a>事件概述

"概述" 页面提供有关事件的最需要注意事项的概览信息。

!["事件概述" 页面图像](../../media/incidents-overview.png)

攻击类别可直观和数字地了解攻击对击杀链的进度。 与其他 Microsoft 安全产品一样，Microsoft 365 Defender 与[MITRE ATT&&trade; CK](https://attack.mitre.org/)框架一致。

“范围” 部分提供了属于此事件的最受影响的资产列表。 如果存在有关此资产的具体信息（例如风险级别、调查优先级以及资产上的任何标记），也将在本节中显示。

“警报”时间线能够提前了解警报发生的时间顺序以及警报与此事件关联的原因。

最后“证据部分”汇总了事件中包含的项目数量和修正状态，因此能够立即确定是否需要采取措施。

此概述可通过深入了解事件的首要特征，有助于了解事件的初始会审。

## <a name="alerts"></a>警报

你可以查看与事件相关的所有警报及其其他信息，例如严重性、警报中涉及的实体、警报的来源 (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365) 以及它们链接在一起的原因。

![事件警报页面图像](../../media/incident-alerts.png)

警报默认按时间顺序排序，可以首先查看攻击如何随时间推移。 单击每个警报将引导你进入相关警报页面，你可以在这里对此警报进行深入调查。 在调查警报中了解如何使用警报页面和 [统一警报队列](investigate-alerts.md)

## <a name="devices"></a>设备

"设备" 选项卡列出了出现与事件相关警报的所有设备。

单击执行攻击的计算机的名称，导航至计算机页面，可在其中查看触发的警报和有助于调查的相关事件。

![事件“计算机”选项卡图像](../../media/incident-machines.png)

选择 "时间线" 选项卡，将能够在计算机时间线之间滚动，并按时间顺序查看计算机上观察到的所有事件和行为，并与引发的警报交错。

> [!TIP]
> 可以在设备页面上执行按需扫描。 在 Microsoft 365 安全中心中，选择 **"设备清单"。** 选择具有警报的设备，然后运行防病毒扫描。 防病毒扫描等操作会进行跟踪，并且显示在"设备清单 **"页上。** 若要了解更多信息，请参阅 [在设备上运行 Microsoft Defender 防病毒扫描](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。


## <a name="users"></a>用户

查看标记为属于事件或与事件相关的邮箱。

单击用户名，将导航至用户的 Cloud App Security 页面，可在此进行进一步调查。

![事件“用户”选项卡图像](../../media/incident-users.png)

## <a name="mailboxes"></a>邮箱

调查标记为属于事件或与事件相关的邮箱。 若要执行进一步的调查工作，选择与邮件相关的警报将打开 Microsoft Defender for Office 365，可在其中执行修正操作。

![事件“邮箱”选项卡图像](../../media/incident-mailboxes.png)

## <a name="investigations"></a>调查

选择 **"** 调查"以查看此事件中的警报触发的所有自动调查。 调查将执行修正操作或等待分析员批准操作，具体取决于如何将自动调查配置为在 Microsoft Defender for Endpoint 和 Defender for Office 365 中运行。

![事件“调查”选项卡图像](../../media/incident-investigations.png)

选择“调查”，以导航到调查详细信息页面，获取有关调查和修复状态的完整信息。 如果有作为调查的一部分等待审批的任何操作，它们将显示在"挂起的操作"选项卡中。采取操作作为事件修正的一部分。

## <a name="evidence"></a>证据

Microsoft 365 Defender 自动调查警报中所有事件支持的事件和可疑实体，从而自动响应和有关重要文件、流程、服务、电子邮件等的信息。 这有助于快速检测并阻止事件中的潜在威胁。

![事件“证据”选项卡图像](../../media/incident-evidence.png)

每一被分析的实体都将标记有裁定（恶意、可疑和清除）以及修正状态。 这可有助于解整个事件的修正状态，以及执行进一步补救的后续步骤。

## <a name="related-topics"></a>相关主题

- [事件概述](incidents-overview.md)
- [确定事件优先级](incident-queue.md)
- [管理事件](manage-incidents.md)

