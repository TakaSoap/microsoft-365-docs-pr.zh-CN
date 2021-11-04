---
title: 为 Microsoft Defender 更新创建自定义逐步推出过程
description: 了解如何使用受支持的工具为更新创建自定义逐步推出过程
keywords: 更新工具， gpo， intune， mdm， microsoft 终结点管理器， 策略， powershell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 9023a6fe8f95f086ad90f2a6276733bd4a4213a2
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747188"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>为 Microsoft Defender 更新创建自定义逐步推出过程

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> 此功能需要Microsoft Defender 防病毒 4.18.2106.X 或更高版本。

若要为 Defender 更新创建自己的自定义逐步推出过程，可以使用组策略、Microsoft Endpoint Manager和 PowerShell。

下表列出了用于配置更新通道的可用组策略设置：

<br>

****

|设置标题|说明|Location|
|---|---|---|
|选择逐步 Microsoft Defender 每月平台更新推出通道|启用此策略可指定设备在每月逐步推出期间何时接收 Microsoft Defender 平台更新。 <p> Beta 渠道：设置为此频道的设备将是第一个接收新更新的设备。 选择 Beta 渠道以参与识别问题并报告给 Microsoft。 默认情况下，Windows预览体验计划中的设备订阅到此频道。 用于 (手动) 测试环境以及有限数量的设备。 <p> Current Channel (Preview) ：设置为此频道的设备将在每月逐步发布周期内最早提供更新。 建议用于预生产/验证环境。 <p> Current Channel (Staged) ： Devices will be offered updates after the monthly gradual release cycle. 建议应用于生产总体中具有代表性的较小部分 (大约 10%) 。 <p> Current Channel (Broad) ： Devices will be offered updates only after the gradual release cycle completes. 建议应用于生产总体中的一组广泛的设备 (约 10-100%) 。 <p> Critical- Time Delay：将为设备提供延迟为 48 小时的更新。 仅针对关键环境建议。 <p>如果禁用或不配置此策略，设备将在逐步发布周期中自动保持最新状态。 适用于大多数设备。|WindowsComponents\Microsoft Defender 防病毒|
|选择逐步 Microsoft Defender 每月引擎更新推出频道|启用此策略可指定设备在每月逐步推出期间何时接收 Microsoft Defender 引擎更新。 <p> Beta 渠道：设置为此频道的设备将是第一个接收新更新的设备。 选择 Beta 渠道以参与识别问题并报告给 Microsoft。 默认情况下，Windows预览体验计划中的设备订阅到此频道。 用于 (手动) 测试环境以及有限数量的设备。 <p> Current Channel (Preview) ：设置为此频道的设备将在每月逐步发布周期内最早提供更新。 建议用于预生产/验证环境。 <p> Current Channel (Staged) ： Devices will be offered updates after the monthly gradual release cycle. 建议应用于生产总体中具有代表性的较小部分 (大约 10%) 。 <p> Current Channel (Broad) ： Devices will be offered updates only after the gradual release cycle completes. 建议应用于生产总体中的一组广泛的设备 (约 10-100%) 。 <p> Critical- Time Delay：将为设备提供延迟为 48 小时的更新。 仅针对关键环境建议。<p> 如果禁用或不配置此策略，设备将在逐步发布周期中自动保持最新状态。 适用于大多数设备。|WindowsComponents\Microsoft Defender 防病毒|
|选择逐步 Microsoft Defender 每日安全智能更新推出通道|启用此策略可指定设备在每日逐步推出期间何时接收 Microsoft Defender 安全智能更新。 <p> Current Channel (Staged) ： Devices will be offered updates after the release cycle. 建议应用于生产总体中具有代表性的较小 (约 10%) 。 <p> Current Channel (Broad) ： Devices will be offered updates only after the gradual release cycle completes. 建议应用于生产总体中的一组广泛的设备 (约 10-100%) 。 <p>  如果禁用或不配置此策略，设备将在每日发布周期内自动保持最新状态。 适用于大多数设备。|WindowsComponents\Microsoft Defender 防病毒|
|禁用 Microsoft Defender 更新的逐步推出|启用此策略可禁用 Defender 更新的逐步推出。 <p> Current Channel (Broad) ： Devices set to this channel will be offered updates last during the gradual release cycle. 最适合仅接收有限更新的数据中心计算机。 <p> 注意：此设置适用于每月和每日 Defender 更新，将覆盖之前为平台和引擎更新配置的任何频道选择。 <p> 如果禁用或不配置此策略，设备将保留在当前频道 (默认) 除非在平台和引擎更新的特定频道中另行指定。 在逐步发布周期中自动保持最新。 适用于大多数设备。|WindowsComponents\Microsoft Defender 防病毒|
|

## <a name="group-policy"></a>组策略

> [!NOTE]
> 更新后的 Defender ADMX 模板将随 21H2 版本发布Windows 10。 可在 下载非本地化版本 https://github.com/microsoft/defender-updatecontrols 。

可以使用组[策略](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)在终结点上配置Microsoft Defender 防病毒管理策略。

通常，可以使用以下过程配置或更改Microsoft Defender 防病毒策略设置：

1. 在组策略管理计算机上，打开组策略管理控制台，右键单击要配置的组策略对象 **(** GPO) 然后单击 **编辑。**

2. 使用组策略管理编辑器转到计算机 **配置**。

3. 单击 **"管理模板"。**

4. 展开树以Windows **组件> Microsoft Defender 防病毒。**

5. 展开本主题 (表中称为"位置"的部分) 其中包含要配置的设置，双击该设置将其打开，然后进行配置更改。

6. [像平常一样部署更新的 GPO。](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)

## <a name="intune"></a>Intune

按照以下链接中的说明在 Intune 中创建自定义策略：

[在 Windows 10 中添加 Microsoft Intune 设备的自定义设置 - Azure \| Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

有关用于逐步推出过程的 Defender CSP 详细信息，请参阅 [Defender CSP](/windows/client-management/mdm/defender-csp)。

## <a name="powershell"></a>PowerShell

使用 `Set-MpPreference` cmdlet 配置逐步更新的推出。

使用以下参数：

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

示例：

用于 `Set-MpPreference -PlatformUpdatesChannel Beta` 配置平台更新以从 Beta 渠道到达。

有关参数以及如何配置参数的信息，请参阅 [Set-MpPreference (Defender) |Microsoft Docs](/powershell/module/defender/set-mppreference)。
