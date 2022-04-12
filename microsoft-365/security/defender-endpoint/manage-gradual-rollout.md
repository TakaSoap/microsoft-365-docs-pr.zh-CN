---
title: 管理 Microsoft Defender 更新的逐步推出过程
description: 了解逐步更新过程和控件
keywords: 更新、更新过程、控件、发布
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
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d8a500babf581cd70b92a39b32a3be0bb5d4acd3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789373"
---
# <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>管理 Microsoft Defender 更新的逐步推出过程

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

请务必确保客户端组件是最新的，以提供关键保护功能并防止攻击。

功能通过多个组件提供：

- [终结点检测&响应](overview-endpoint-detection-response.md)
- 使用[云提供保护的](cloud-protection-microsoft-defender-antivirus.md)[下一代保护](microsoft-defender-antivirus-windows.md)
- [攻击面减少](overview-attack-surface-reduction.md)

更新使用逐步发布过程按月发布。 此过程有助于使早期故障检测在发生时捕获影响，并在更大规模的推出之前快速解决它。

> [!NOTE]
> 有关如何控制每日安全智能更新的详细信息，请[参阅计划Microsoft Defender 防病毒保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)。 更新可确保下一代保护能够抵御新威胁，即使云提供的保护对终结点不可用。

## <a name="microsoft-gradual-rollout-model"></a>Microsoft 逐步推出模型

每月 Defender 更新遵循以下逐步推出模型：

1. 第一个版本将发布到 Beta 频道订阅者。
2. 经过验证、反馈和修复后，我们将以限制的方式开始逐步推出过程，并首先预览频道订阅者。
3. 然后，我们继续向全球其余人口发布更新，从 10-100% 纵向扩展。

我们的工程师持续监视影响并升级任何问题，以便根据需要创建修补程序。

## <a name="how-to-customize-your-internal-deployment-process"></a>如何自定义内部部署过程

如果计算机从 Windows 更新 接收 Defender 更新，则逐步推出过程可能会导致某些计算机比其他计算机更快地接收 Defender 更新。 以下部分介绍如何定义一个策略，该策略允许自动更新通过利用更新通道配置以不同的方式流向特定的设备组。

> [!NOTE]
> 规划自己的逐步发布时，请确保始终有一系列设备订阅预览版和暂存频道。 这将为组织和 Microsoft 提供防止或查找和修复特定于环境的问题的机会。

对于通过 Windows Server Update Services (WSUS) 或 Microsoft Endpoint Configuration Manager (MECM) 接收更新的计算机，可为所有Windows更新提供更多选项，包括选项Microsoft Defender for Endpoint。

- 详细了解如何使用 WSUS、MECM 等解决方案在[管理Microsoft Defender 防病毒更新和应用基线时管理更新的分发和应用 - Windows安全性](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates)。

## <a name="update-channels-for-monthly-updates"></a>每月更新的更新频道

可以将计算机分配到更新通道，以定义计算机接收每月引擎和平台更新的节奏。

有关如何配置更新的详细信息，请参阅 [为 Microsoft Defender 更新创建自定义逐步推出过程](configure-updates.md)。

以下更新通道可用：

<br>

****

|频道名称|说明|应用程序|
|---|---|---|
|Beta 频道 - 预发行版|在其他人之前测试更新|设置为此通道的设备将是第一个接收新的每月更新的设备。 选择 Beta Channel 以参与识别和向 Microsoft 报告问题。 默认情况下，Windows预览体验计划中的设备订阅此频道。 仅用于测试环境。|
|当前频道（预览）|在逐步发布期间 **提前** 获取当前频道更新|设置为此通道的设备将在逐步发布周期内尽早提供更新。 建议用于预生产/验证环境。|
|当前频道 (暂存) |在逐步发布期间稍后获取当前频道更新|设备将在逐步发布周期的后面提供更新。 建议应用于设备总体中具有代表性的一小部分 (约 10%) 。|
|当前频道 (广泛) |在逐步发布结束时获取更新|只有在逐步发布周期完成后，才会提供设备更新。 建议应用于生产人口中广泛的设备集 (~10-100%) 。|
|关键：时间延迟|延迟 Defender 更新|设备将提供 48 小时延迟的更新。 最适合仅接收有限更新的数据中心计算机。 仅针对关键环境建议。|
| (默认) ||如果禁用或未配置此策略，设备将保留在当前频道 (默认) ：在逐步发布周期内自动保持最新状态。 适用于大多数设备。|
|

### <a name="update-channels-for-daily-updates"></a>更新每日更新的频道

还可以将计算机分配给通道，以定义它每天接收更新的节奏。 请注意，与每月过程不同，没有 Beta 通道，此渐进式发布周期每天发生多次。

<br>

****

|频道名称|说明|应用程序|
|---|---|---|
|当前频道 (暂存) |在逐步发布期间稍后获取当前频道更新|设备将在逐步发布周期的后面提供更新。 建议应用于设备总体中具有代表性的一小部分 (约 10%) 。|
|当前频道 (广泛) |在逐步发布结束时获取更新|设备将在逐步发布周期后提供更新。 最适合仅接收有限更新的数据中心计算机。 注意：此设置适用于所有 Defender 更新。|
| (默认) ||如果禁用或未配置此策略，设备将保留在当前频道 (默认) ：在逐步发布周期内自动保持最新状态。 适用于大多数设备|
|

> [!NOTE]
> 如果希望强制更新到最新的签名，而不是利用时间延迟，则需要先删除此策略。

## <a name="update-guidance"></a>更新指南

在大多数情况下，使用Windows 更新时建议的配置是允许终结点在到达时接收和应用每月 Defender 更新。 这可在保护与可以引入的更改相关联的可能影响之间提供最佳平衡。

对于需要更受控制的自动 Defender 更新逐步推出的环境，请考虑使用部署组的方法：

1. 参与Windows预览体验计划，或将一组设备分配到 Beta 频道。
2. 指定选择加入预览频道（通常是验证环境）以提前接收新更新的试点组。
3. 指定在分阶段频道逐步推出期间稍后接收更新的一组计算机。 通常情况下，这会代表大约 10% 的人口。
4. 指定在逐步发布周期完成后接收更新的一组计算机。 这些通常是重要的生产系统。

对于其余设备，默认设置是在 Microsoft 逐步推出过程中到达时接收新更新，无需进一步配置。

采用此模型：

- 允许在早期版本到达生产环境之前对其进行测试
- 确保生产环境仍收到定期更新，并确保防范严重威胁。

## <a name="management-tools"></a>管理工具

若要为每月更新创建自己的自定义逐步推出过程，可以使用以下工具：

- 组策略
- Microsoft Endpoint Manager
- PowerShell

有关如何使用这些工具的详细信息，请参阅 [为 Microsoft Defender 更新创建自定义逐步推出过程](configure-updates.md)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)