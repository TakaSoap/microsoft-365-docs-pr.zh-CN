---
title: 阻止模式下的终结点检测和响应
description: 了解阻止模式下的终结点检测和响应
keywords: Microsoft Defender for Endpoint， mde， EDR in block mode， passive mode blocking
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 08/31/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: c590812ccc975206c6c278794f943f7e16c8bdd1
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "59357677"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>阻止模式下的终结点检测和响应 (EDR)。

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="what-is-edr-in-block-mode"></a>阻止EDR什么？

[当终结点检测和响应](overview-endpoint-detection-response.md) (EDR) 在非主要防病毒产品且在被动模式下运行时，Microsoft Defender 防病毒保护，防止恶意项目。 EDR阻止模式在后台工作，以修正由功能检测到的EDR项目。 此类项目可能已被主要的非 Microsoft 防病毒产品错过。 对于运行 Microsoft Defender 防病毒 作为主防病毒的设备，EDR在阻止模式下运行，通过允许 Microsoft Defender 防病毒 对泄露后的行为检测自动采取EDR防护。

> [!IMPORTANT]
> EDR阻止模式时，不会提供启用实时Microsoft Defender 防病毒时可用的所有保护。 依赖于要成为Microsoft Defender 防病毒防病毒解决方案的所有功能将不起作用，包括以下关键示例：
>
> - 实时保护（包括访问时扫描）在处于被动Microsoft Defender 防病毒时不可用。 若要了解有关实时保护策略设置的信息，请参阅启用 **[和配置Microsoft Defender 防病毒始终启用保护](configure-real-time-protection-microsoft-defender-antivirus.md)**。
> - 网络 **[保护和](network-protection.md)** 攻击面减少 **[规则](attack-surface-reduction.md)** 等功能仅在网络Microsoft Defender 防病毒模式运行时可用。
>
> 预计非 Microsoft 防病毒解决方案会提供这些功能。

EDR模式中的应用已与威胁& 漏洞管理[集成](next-gen-threat-and-vuln-mgt.md)。 如果组织的安全团队尚未启用EDR启用阻止[](tvm-security-recommendation.md)模式，则安全团队将获取安全建议。

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="建议在阻止EDR打开该模式。":::

> [!TIP]
> 若要获取最佳保护，请确保为终结点基线 **[部署 Microsoft Defender。](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>检测到某些内容时会发生什么情况？

当EDR模式启用后检测到恶意项目时，适用于终结点的 Microsoft Defender 将阻止并修正这些项目。 安全操作团队将在操作中心中将检测状态视为"已阻止"或[](respond-machine-alerts.md#check-activity-details-in-action-center)"已阻止"，列为已完成操作。 

下图显示了一个不需要的软件的实例，这些软件在阻止模式下通过EDR阻止：

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR阻止模式时检测到某些内容。":::


## <a name="enable-edr-in-block-mode"></a>启用EDR阻止模式

> [!TIP]
> 在以[阻止模式](#requirements-for-edr-in-block-mode)打开应用前，EDR满足要求。

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com/](https://security.microsoft.com/) () 并登录。
2. Choose **设置** \> **Endpoints** \> **General** \> **Advanced features**.
3. 向下滚动，然后在块模式下EDR **启用"**

> [!NOTE]
> EDR在阻止模式下只能打开Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 或之前 [https://securitycenter.windows.com](https://securitycenter.windows.com) Microsoft Defender 安全中心 () 。 不能使用注册表项、Microsoft Intune或组策略来启用或禁用EDR阻止模式。

## <a name="requirements-for-edr-in-block-mode"></a>阻止模式下EDR要求

|要求|详细信息|
|---|---|
|权限|必须在 "全局管理员"或"安全管理员"角色中分配[Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) 有关详细信息，请参阅 [基本权限](basic-permissions.md)。|
|操作系统|设备必须运行以下版本之一Windows： <ul><li>Windows 10 (所有) </li><li>Windows服务器版本 1803 或更高版本</li><li>Windows Server 2019</li><li>Windows Server 2016 (仅在Microsoft Defender 防病毒处于活动状态时) </li></ul>|
|Microsoft Defender for Endpoint|设备必须载入到适用于终结点的 Defender。 请参阅 [Microsoft Defender for Endpoint 的最低要求](minimum-requirements.md)。|
|Microsoft Defender 防病毒|设备必须已安装Microsoft Defender 防病毒在主动模式或被动模式下运行。 [确认Microsoft Defender 防病毒处于主动或被动模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。|
|云端保护|Microsoft Defender 防病毒配置云保护，以[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。|
|Microsoft Defender 防病毒平台|设备必须是最新的。 若要确认，使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMProductVersion** 行中，应该会看到 **4.18.2001.10** 或更上方。 <p> 要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。|
|Microsoft Defender 防病毒引擎|设备必须是最新的。 若要确认，使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMEngineVersion** 行中，应该会看到 **1.1.16700.2** 或更上方。 <p> 要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。|

> [!IMPORTANT]
> 若要获取最佳保护值，请确保防病毒解决方案配置为接收定期更新和基本功能，并且已配置排除 [项](configure-exclusions-microsoft-defender-antivirus.md)。 EDR模式配置遵守为 Microsoft Defender 防病毒 定义的排除项，但不包括为 Microsoft Defender for [](manage-indicators.md) Endpoint 定义的指示器。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>如果我在设备上运行EDR，是否需要在阻止Microsoft Defender 防病毒打开？

在阻止模式下EDR主要目的是修正非 Microsoft 防病毒产品错过的泄露后检测。 但是，我们建议保持EDR模式处于打开状态，Microsoft Defender 防病毒被动模式还是主动模式运行。

- 当Microsoft Defender 防病毒处于被动模式时，EDR模式中的用户与 Microsoft Defender for Endpoint 一起提供另一层防御。
- 当Microsoft Defender 防病毒模式时，EDR阻止模式不会提供额外的扫描，但它允许 Microsoft Defender 防病毒 对泄露后的行为或行为EDR自动操作。

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>EDR阻止模式是否会影响用户的防病毒保护？

EDR模式访问不会影响在用户设备上运行的第三方防病毒保护。 EDR如果主防病毒解决方案遗漏了某些内容，或者存在泄露后检测，则以阻止模式运行。 EDR模式运行方式与被动模式下Microsoft Defender 防病毒一样，只不过EDR模式下的阻止模式也会阻止和修正检测到的恶意项目或行为。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>为什么我需要使Microsoft Defender 防病毒保持最新状态？

由于Microsoft Defender 防病毒检测并修正恶意项目，因此必须使项目保持最新状态。 为了EDR模式运行，它使用最新的设备学习模型、行为检测和启发。 [Defender for Endpoint](microsoft-defender-endpoint.md)功能堆栈以集成方式工作。 若要获取最佳保护值，Microsoft Defender 防病毒保持最新状态。 请参阅[管理Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

### <a name="why-do-we-need-cloud-protection-maps-on"></a>为什么需要云保护 (MAPS) 打开？

需要云保护才能在设备上启用该功能。 云保护 [允许 Defender for Endpoint](microsoft-defender-endpoint.md) 基于安全智能的广度和深度以及行为和设备学习模型提供最新且最丰富的保护。

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>主动模式和被动模式之间有什么区别？

对于运行 Windows 10、Windows Server 版本 1803 或更高版本或 Windows Server 2019 的终结点，当 Microsoft Defender 防病毒 处于活动状态时，它将用作设备上的主要防病毒。 在被动模式下运行时，Microsoft Defender 防病毒不是主要的防病毒产品。 在这种情况下，威胁不会由Microsoft Defender 防病毒进行修正。

> [!NOTE]
> Microsoft Defender 防病毒设备载入到 Microsoft Defender for Endpoint 时，才能在被动模式下运行。

有关详细信息，请参阅兼容性[Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>如何确认Microsoft Defender 防病毒处于主动或被动模式？

若要确认Microsoft Defender 防病毒模式还是被动模式运行，可以在运行命令提示符的设备上使用 Windows。

<br/><br/>

|方法|Procedure|
|---|---|
|PowerShell|<ol><li>选择"开始"菜单，开始键入 `PowerShell` ，然后在Windows PowerShell中打开" "。</li><li>类型 `Get-MpComputerStatus`。</li><li>在结果列表中，在 **AMRunningMode** 行中查找下列值之一：<ul><li>`Normal`</li><li>`Passive Mode`</li></ul></li></ol> <p> 若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。|
|命令提示符|<ol><li>选择"开始"菜单，开始键入 `Command Prompt` ，然后在Windows打开命令提示符。</li><li>类型 `sc query windefend`。</li><li>在结果列表中的 **"状态** "行中，确认服务正在运行。</li></ol>|

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>如何确认在EDR模式下已打开阻止模式，Microsoft Defender 防病毒处于被动模式？

可以使用 PowerShell 确认阻止EDR处于阻止模式时处于打开状态，Microsoft Defender 防病毒被动模式下运行。

1. 选择"开始"菜单，开始键入 `PowerShell` ，然后在Windows PowerShell中打开" "。

2. 类型 `Get-MPComputerStatus|select AMRunningMode`。

3. 确认显示结果 `EDR Block Mode` 。

   > [!TIP]
   > 如果Microsoft Defender 防病毒处于活动状态，你将看到 `Normal` 而不是 `EDR Block Mode` 。 若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>在EDR上是否支持阻止Windows Server 2016？

如果Microsoft Defender 防病毒模式或被动EDR运行，则以下版本的 Windows 支持以阻止模式Windows：

- Windows 10 (所有) 
- Windows服务器版本 1803 或更高版本
- Windows Server 2019

#### <a name="what-about-windows-server-2016"></a>如何Windows Server 2016？

如果Windows Server 2016在Microsoft Defender 防病毒模式下运行，并且终结点已载入到 Defender for Endpoint，则EDR支持以阻止模式运行。 但是，EDR模式模式旨在当终结点上不是Microsoft Defender 防病毒防病毒解决方案时提供额外保护。 在这种情况下，Microsoft Defender 防病毒被动模式下运行。

目前，Microsoft Defender 防病毒在被动模式下运行 Windows Server 2016。 若要了解更多信息，请参阅被动[模式和Windows服务器](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server)Microsoft Defender 防病毒[兼容性](microsoft-defender-antivirus-compatibility.md)。

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>在阻止模式下禁用EDR需要的时间？

如果选择在阻止EDR禁用此功能，则系统最多可能需要 30 分钟才能禁用此功能。

## <a name="see-also"></a>另请参阅

- [Tech Community博客：在阻止EDR中介绍内容：停止其跟踪中的攻击](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [行为阻止和控制](behavioral-blocking-containment.md)
