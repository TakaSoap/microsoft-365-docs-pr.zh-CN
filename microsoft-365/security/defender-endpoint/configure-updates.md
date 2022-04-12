---
title: 为 Microsoft Defender 更新创建自定义逐步推出过程
description: 了解如何使用受支持的工具为更新创建自定义逐步推出过程
keywords: 更新工具、gpo、intune、mdm、Microsoft 终结点管理器、策略、powershell
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
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4a963172e69b61a7cb33486132630e0d56d0420b
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788537"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>为 Microsoft Defender 更新创建自定义逐步推出过程

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

> [!NOTE]
> 此功能需要Microsoft Defender 防病毒版本 4.18.2106.X 或更高版本。

若要为 Defender 更新创建自己的自定义逐步推出过程，可以使用 组策略、Microsoft Endpoint Manager 和 PowerShell。

下表列出了用于配置更新通道的可用组策略设置：

<br>

****

|设置标题|说明|Location|
|---|---|---|
|选择逐步的 Microsoft Defender 每月平台更新推出通道|启用此策略以指定设备在每月逐步推出期间接收 Microsoft Defender 平台更新的时间。 <p> Beta 通道：设置为此通道的设备将是第一个接收新更新的设备。 选择 Beta Channel 以参与识别和向 Microsoft 报告问题。 默认情况下，Windows预览体验计划中的设备订阅此频道。 若要在 (手动) 测试环境和数量有限的设备中使用。 <p> 当前频道 (预览版) ：设置为此频道的设备将在每月逐步发布周期内最早提供更新。 建议用于预生产/验证环境。 <p> 当前频道 (分阶段) ：设备将在每月逐步发布周期后提供更新。 建议应用于生产人口中具有代表性的一小部分 (约 10%) 。 <p> 当前频道 (广泛) ：只有在逐步发布周期完成后，才会提供设备更新。 建议应用于生产人口中广泛的设备集 (~10-100%) 。 <p> 关键时间延迟：设备将提供 48 小时延迟的更新。 仅针对关键环境建议。 <p>如果禁用或未配置此策略，设备将在逐步发布周期中自动保持最新状态。 适用于大多数设备。|Windows组件\Microsoft Defender 防病毒|
|选择逐步的 Microsoft Defender 月度引擎更新推出通道|启用此策略以指定设备在每月逐步推出期间接收 Microsoft Defender 引擎更新的时间。 <p> Beta 通道：设置为此通道的设备将是第一个接收新更新的设备。 选择 Beta Channel 以参与识别和向 Microsoft 报告问题。 默认情况下，Windows预览体验计划中的设备订阅此频道。 若要在 (手动) 测试环境和数量有限的设备中使用。 <p> 当前频道 (预览版) ：设置为此频道的设备将在每月逐步发布周期内最早提供更新。 建议用于预生产/验证环境。 <p> 当前频道 (分阶段) ：设备将在每月逐步发布周期后提供更新。 建议应用于生产人口中具有代表性的一小部分 (约 10%) 。 <p> 当前频道 (广泛) ：只有在逐步发布周期完成后，才会提供设备更新。 建议应用于生产人口中广泛的设备集 (~10-100%) 。 <p> 关键时间延迟：设备将提供 48 小时延迟的更新。 仅针对关键环境建议。<p> 如果禁用或未配置此策略，设备将在逐步发布周期中自动保持最新状态。 适用于大多数设备。|Windows组件\Microsoft Defender 防病毒|
|选择逐步的 Microsoft Defender 每日安全智能更新推出通道|启用此策略以指定设备在每日逐步推出期间何时接收 Microsoft Defender 安全智能更新。 <p> 当前频道 (分阶段) ：发布周期后将提供设备更新。 建议应用于生产人口中具有代表性的一小部分 (约 10%) 。 <p> 当前频道 (广泛) ：只有在逐步发布周期完成后，才会提供设备更新。 建议应用于生产人口中广泛的设备集 (~10-100%) 。 <p>  如果禁用或未配置此策略，设备将在每日发布周期中自动保持最新状态。 适用于大多数设备。|Windows组件\Microsoft Defender 防病毒|
|禁用 Microsoft Defender 更新的逐步推出|启用此策略可禁用 Defender 更新的逐步推出。 <p> 当前频道 (广泛) ：设置为此通道的设备将在逐步发布周期中持续提供更新。 最适合仅接收有限更新的数据中心计算机。 <p> 注意：此设置适用于每月和每日 Defender 更新，并将覆盖以前为平台和引擎更新配置的任何通道选择。 <p> 如果禁用或未配置此策略，则设备将保留在当前通道 (默认) 中，除非在平台和引擎更新的特定通道中另有指定。 在逐步发布周期中自动保持最新状态。 适用于大多数设备。|Windows组件\Microsoft Defender 防病毒|
|

## <a name="group-policy"></a>组策略

> [!NOTE]
> 更新后的 Defender ADMX 模板将与 21H2 版本的 Windows 10 一起发布。 非本地化版本可供下载 https://github.com/microsoft/defender-updatecontrols。

可以使用[组策略](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)在终结点上配置和管理Microsoft Defender 防病毒。

通常，可以使用以下过程来配置或更改Microsoft Defender 防病毒组策略设置：

1. 在组策略管理计算机上，打开 **组策略管理控制台**，右键单击要配置 **的组策略对象** (GPO) ，然后单击 **“编辑**”。

2. 使用组策略管理编辑器转到 **计算机配置**。

3. 单击 **“管理模板**”。

4. 展开树以 **> Microsoft Defender 防病毒Windows组件**。

5. 展开本主题中表中称为 **“位置** ”的部分 () 其中包含要配置的设置，双击设置以将其打开，然后进行配置更改。

6. [像平时一样部署更新后的 GPO](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)。

## <a name="intune"></a>Intune

按照以下链接中的说明在Intune中创建自定义策略：

[在 Microsoft Intune 中添加Windows 10设备的自定义设置 - Azure \|Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

有关用于逐步推出过程的 Defender CSP 的详细信息，请参阅 [Defender CSP](/windows/client-management/mdm/defender-csp)。

## <a name="powershell"></a>PowerShell

`Set-MpPreference`使用 cmdlet 配置逐步更新的推出。

使用以下参数：

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

示例：

用于 `Set-MpPreference -PlatformUpdatesChannel Beta` 配置从 Beta 通道到达的平台更新。

有关参数以及如何配置参数的详细信息，请参阅 [Set-MpPreference (Microsoft Defender 防病毒) |Microsoft Docs](/powershell/module/defender/set-mppreference)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)