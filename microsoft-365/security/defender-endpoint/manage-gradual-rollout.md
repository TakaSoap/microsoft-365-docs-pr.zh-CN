---
title: 管理 Microsoft Defender 更新的逐步推出过程
description: 了解逐步更新过程和控件
keywords: 更新， 更新过程， 控件， 发布
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ceeae633c85912d4c344ed8a74fe66def168efd5
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882581"
---
# <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>管理 Microsoft Defender 更新的逐步推出过程

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

确保客户端组件是最新的，以提供关键保护功能和防止攻击，这一点非常重要。

功能通过多个组件提供：

- [终结点检测&响应](overview-endpoint-detection-response.md)
- [具有云保护](microsoft-defender-antivirus-windows.md)[的下一代保护](cloud-protection-microsoft-defender-antivirus.md)
- [攻击面减少](overview-attack-surface-reduction.md)

使用逐步发布过程每月发布一次更新。 此过程有助于启用早期故障检测，以在影响发生时捕获影响，并快速在更大推出前解决它。

> [!NOTE]
> 若要详细了解如何控制日常安全智能更新，请参阅计划Microsoft Defender 防病毒[更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)。 更新可确保下一代保护可以抵御新威胁，即使云提供的保护对终结点不可用。

## <a name="microsoft-gradual-rollout-model"></a>Microsoft 逐步推出模型

每月 Defender 更新遵循以下逐步推出模型：

1. 第一版向 Beta 渠道订阅者发布。
2. 在验证、反馈和修复后，我们以限制方式开始逐步推出过程，并首先预览频道订阅者。
3. 然后，我们向全球其余总体发布更新，从 10% 到 100% 向外扩展。

我们的工程师持续监视影响并上报任何问题，以根据需要创建修补程序。

## <a name="how-to-customize-your-internal-deployment-process"></a>如何自定义内部部署过程

如果你的计算机从 Windows 更新接收 Defender 更新，逐步推出过程可能会导致你的某些计算机接收 Defender 更新早于其他计算机。 以下部分介绍如何定义一种策略，该策略允许自动更新通过利用更新通道配置以不同方式流向特定设备组。

> [!NOTE]
> 在规划自己的逐步发布时，请确保始终有一些设备订阅到预览频道和分步频道。 这将为组织和 Microsoft 提供防止或查找并修复特定于你的环境的问题的机会。

例如，对于通过 WSUS) Windows Server Update Services (或 MICROSOFT ENDPOINT CONFIGURATION MANAGER (MECM) 接收更新的计算机，可供所有 Windows 更新使用更多选项，包括适用于终结点的 Microsoft Defender 选项。

- 若要详细了解如何使用 WSUS、MECM 等解决方案管理更新的分发和应用程序，请参阅管理 Microsoft Defender 防病毒[更新](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates)和应用基线 - Windows安全 。

## <a name="update-channels-for-monthly-updates"></a>每月更新的更新频道

你可以将计算机分配给更新频道，以定义计算机接收每月引擎和平台更新的节奏。

若要详细了解如何配置更新，请参阅为 Microsoft Defender 更新创建自定义 [逐步推出过程](configure-updates.md)。

以下更新频道可用：

<br>

****

|频道名称|说明|Application|
|---|---|---|
|Beta 渠道 - 预发布|在其他人之前测试更新|设置为此频道的设备将是第一个接收新每月更新的设备。 选择 Beta 渠道以参与识别问题并报告给 Microsoft。 默认情况下，Windows预览体验计划中的设备订阅此频道。 仅在测试环境中使用。|
|当前频道（预览）|在逐步发布 **期间提前获取** 当前频道更新|在逐步发布周期中，将最早向设置为此频道的设备提供更新。 建议用于预生产/验证环境。|
|当前频道 (阶段) |在逐步发布期间获取当前频道更新|设备将在逐步发布周期的稍后阶段提供更新。 建议应用于设备总体中具有代表性的较小部分 (大约 10%) 。|
|当前频道 (广泛) |在逐步发布结束时获取更新|仅在逐步发布周期完成后，才向设备提供更新。 建议应用于生产总体中的一组广泛的设备 (约 10-100%) 。|
|关键：时间延迟|延迟 Defender 更新|为设备提供延迟为 48 小时的更新。 最适合仅接收有限更新的数据中心计算机。 仅针对关键环境建议。|
| (默认) ||如果禁用或不配置此策略，设备将保留在当前频道 (默认) ：在逐步发布周期中自动保持最新。 适用于大多数设备。|
|

### <a name="update-channels-for-daily-updates"></a>每日更新的更新频道

还可以将计算机分配给频道，以定义接收每日更新的节奏。 请注意，与每月进程不同，没有 Beta 渠道，并且此逐步发布周期每天发生多次。

<br>

****

|频道名称|说明|Application|
|---|---|---|
|当前频道 (阶段) |在逐步发布期间获取当前频道更新|设备将在逐步发布周期的稍后阶段提供更新。 建议应用于设备总体中具有代表性的较小部分 (大约 10%) 。|
|当前频道 (广泛) |在逐步发布结束时获取更新|设备将在逐步发布周期后提供更新。 最适合仅接收有限更新的数据中心计算机。 注意：此设置适用于所有 Defender 更新。|
| (默认) ||如果禁用或不配置此策略，设备将保留在当前频道 (默认) ：在逐步发布周期中自动保持最新。 适用于大多数设备|
|

> [!NOTE]
> 如果你希望强制更新最新的签名，而不是利用时间延迟，你将需要首先删除此策略。

## <a name="update-guidance"></a>更新指南

在大多数情况下，使用 Windows 更新时的建议配置是允许终结点在到达时接收和应用每月 Defender 更新。 这可在保护与与它们可以引入的更改相关联的可能影响之间提供最佳平衡。

对于需要更受控逐步推出自动 Defender 更新的环境，请考虑使用部署组的方法：

1. 参加预览Windows计划，或将一组设备分配到 Beta 渠道。
2. 指定选择加入预览频道（通常是验证环境）的试点组，以尽早接收新更新。
3. 指定一组计算机，这些计算机稍后在逐步推出期间从 Staged 频道接收更新。 通常，这代表大约占总体的 10%。
4. 指定一组在逐步发布周期完成后接收更新的计算机。 这些通常是重要的生产系统。

对于其余设备，默认设置是在 Microsoft 逐步推出过程中收到新更新，无需进一步配置。

采用此模型：

- 允许你在早期版本到达生产环境之前测试它们
- 确保生产环境仍收到定期更新，并确保防范关键威胁。

## <a name="management-tools"></a>管理工具

若要为每月更新创建自己的自定义逐步推出过程，可以使用以下工具：

- 组策略
- Microsoft Endpoint Manager
- PowerShell

有关如何使用这些工具的详细信息，请参阅为 Microsoft [Defender 更新创建自定义逐步推出过程](configure-updates.md)。
