---
title: 阻止模式下的终结点检测和响应
description: 了解终结点检测和响应阻止模式
keywords: Microsoft Defender for Endpoint，mde，EDR块模式，被动模式阻止
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
- admindeeplinkDEFENDER
ms.date: 04/04/2022
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: eb40eaee9043e81331eca98c85f1467111cc37e4
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64638347"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>阻止模式下的终结点检测和响应 (EDR)。

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="what-is-edr-in-block-mode"></a>阻止EDR什么？

[当终结点检测和响应](overview-endpoint-detection-response.md) (EDR) 在阻止模式下运行时，当终结点Microsoft Defender 防病毒主要防病毒产品并且正在被动模式下运行时，可针对恶意项目提供额外的保护。 EDR阻止模式在后台工作，以修正由功能检测到的EDR项目。 此类项目可能已被主要的非 Microsoft 防病毒产品错过。 对于运行 Microsoft Defender 防病毒 作为其主要防病毒的设备，EDR在阻止模式下运行，通过允许 Microsoft Defender 防病毒 对攻破后的行为和检测自动采取EDR防护。

> [!IMPORTANT]
> EDR阻止模式时，不会提供启用实时Microsoft Defender 防病毒时可用的所有保护。 依赖于要成为Microsoft Defender 防病毒防病毒解决方案的所有功能将不起作用，包括以下关键示例：
>
> - 实时保护（包括访问时扫描）在处于被动Microsoft Defender 防病毒时不可用。 若要详细了解实时保护策略设置，请参阅启用 **[和配置Microsoft Defender 防病毒始终启用保护](configure-real-time-protection-microsoft-defender-antivirus.md)**。
>
> - 网络 **[保护和](network-protection.md)** 攻击面减少 **[规则](attack-surface-reduction.md)** 等功能仅在网络Microsoft Defender 防病毒模式运行时可用。
>
> 预计非 Microsoft 防病毒解决方案会提供这些功能。

EDR模式中的应用与威胁威胁[& 漏洞管理](next-gen-threat-and-vuln-mgt.md)。 如果组织的安全团队尚未启用EDR，你[](tvm-security-recommendation.md)组织的安全团队将获取一个安全建议，以在阻止模式下启用它。

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="在阻止模式下打开EDR的建议" lightbox="images/edrblockmode-TVMrecommendation.png":::

> [!TIP]
> 若要获得最佳保护，请确保部署 **[Microsoft Defender for Endpoint基线](configure-machines-security-baseline.md)**。

## <a name="what-happens-when-something-is-detected"></a>检测到某些内容时会发生什么情况？

当EDR模式打开并检测到恶意项目时，Microsoft Defender for Endpoint阻止并修复这些项目。 安全操作团队将在操作中心看到检测状态为"已阻止"或"[](respond-machine-alerts.md#check-activity-details-in-action-center)已阻止"，列为已完成操作。

下图显示了一个不需要的软件的实例，这些软件在阻止模式下EDR阻止：

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="在阻止模式下EDR进行检测" lightbox="images/edr-in-block-mode-detection.png":::


## <a name="enable-edr-in-block-mode"></a>启用EDR阻止模式

> [!IMPORTANT]
> 从平台版本 4.18.2202.X 开始，你现在可以在阻止模式下将 EDR 设置为使用 CSP 面向Intune组。 你可以继续在 EDR 门户的阻止模式租户范围内设置<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender设置。</a> EDR在被动模式下运行 Microsoft Defender 防病毒 的设备主要推荐使用 (在设备上安装并激活非 Microsoft 防病毒解决方案) 。 

> [!TIP]
> 在以[阻止模式](#requirements-for-edr-in-block-mode)打开应用前，EDR满足要求。

### <a name="security-portal"></a>安全门户 

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com/](https://security.microsoft.com/) 并登录。

2. 选择 **设置** \> **终结点常规** \>  \> **高级功能"**。

3. 向下滚动，然后在块模式下EDR **启用。**

### <a name="intune"></a>Intune

若要在云解决方案Intune策略，OMA-URIs部署策略以通过 Intune 面向云解决方案提供商，并参阅[与本地的比较](/troubleshoot/mem/intune/deploy-oma-uris-to-target-csp-via-intune)。

有关在阻止模式下EDR的 Defender CSP 详细信息，请参阅 Defender CSP 下的"Configuration/PassiveRemediation["](/windows/client-management/mdm/defender-csp)。


## <a name="requirements-for-edr-in-block-mode"></a>阻止模式下EDR要求

下表列出了在阻止模式下EDR要求：

|要求|详细信息|
|---|---|
|权限|您必须在服务器中分配全局管理员或安全[管理员Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) 有关详细信息，请参阅 [基本权限](basic-permissions.md)。|
|操作系统|设备必须运行以下版本之一Windows： <br/>- Windows 11 <br/>- Windows 10 (所有) <br/>- Windows Server 2022 <br/>- Windows Server 2019<br/>- Windows Server 版本 1803 或更高版本<br/>- Windows Server 2016 Windows Server 2012统一 (解决方案部署 R2) <sup>[[1](#fn1)]</sup> [](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview)  |
|Microsoft Defender for Endpoint|设备必须载入到适用于终结点的 Defender。 另请参阅以下文章： <br/>- [最低要求Microsoft Defender for Endpoint](minimum-requirements.md)<br/>- [载入设备和配置Microsoft Defender for Endpoint功能](onboard-configure.md)<br/>- [将Windows载入 Defender for Endpoint 服务](configure-server-endpoints.md)<br/>- [新式Windows Server 2012预览版中新增了 R2 和 2016 (R2 和 2016) ](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) |
|Microsoft Defender 防病毒|设备必须已安装Microsoft Defender 防病毒在主动模式或被动模式下运行。 [确认Microsoft Defender 防病毒处于主动或被动模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。|
|云端保护|Microsoft Defender 防病毒配置云保护，以启用[云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。|
|Microsoft Defender 防病毒平台|设备必须是最新的。 若要确认，使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMProductVersion** 行中，应该会看到 **4.18.2001.10** 或更上方。 <p> 要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。|
|Microsoft Defender 防病毒引擎|设备必须是最新的。 若要确认，使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMEngineVersion** 行中，应该会看到 **1.1.16700.2** 或更上方。 <p> 要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。|

 (<a id="fn1">1</a>) 请参阅 [R2 EDR R2](#is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2) 上是否支持阻止Windows Server 2016 Windows Server 2012模式？

> [!IMPORTANT]
> 若要获取最佳保护值，请确保防病毒解决方案配置为接收定期更新和基本功能，并且已配置 [排除项](configure-exclusions-microsoft-defender-antivirus.md)。 EDR阻止模式时，将遵守为Microsoft Defender 防病毒定义的排除项，但不包括为阻止模式定义的Microsoft Defender for Endpoint[](manage-indicators.md)。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="can-i-specify-exclusions-for-edr-in-block-mode"></a>能否在阻止模式下为EDR排除项？

在获得误报后，可以在提交文件提交Microsoft 安全智能[分析](https://www.microsoft.com/en-us/wdsi/filesubmission)。

还可以为自定义项定义Microsoft Defender 防病毒。 请参阅[配置并验证扫描的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)。

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>如果我在设备上运行EDR，是否需要在阻止Microsoft Defender 防病毒打开？

在阻止模式下EDR主要目的是修正非 Microsoft 防病毒产品错过的泄露后检测。 在阻止模式下启用EDR在阻止模式下Microsoft Defender 防病毒最小好处，因为实时保护应首先捕获和修正检测。 我们建议在处于EDR运行 Microsoft Defender 防病毒的终结点上启用阻止模式。 EDR [PUA](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) 保护或自动调查和阻止模式下的修正&[自动](automated-investigations.md)修正检测。

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>EDR模式是否会影响用户的防病毒保护？

EDR模式访问不会影响在用户设备上运行的第三方防病毒保护。 EDR如果主防病毒解决方案遗漏了某些内容，或者存在攻破后检测，则阻止模式下的防病毒功能有效。 EDR模式配置的工作方式与被动模式下Microsoft Defender 防病毒一样，只不过EDR模式下的阻止模式也会阻止和修正检测到的恶意项目或行为。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>为什么我需要使Microsoft Defender 防病毒保持最新状态？

由于Microsoft Defender 防病毒检测并修正恶意项目，因此保持其最新状态非常重要。 为了EDR模式运行，它使用最新的设备学习模型、行为检测和启发。 [Defender for Endpoint](microsoft-defender-endpoint.md) 功能堆栈以集成方式工作。 若要获得最佳保护值，Microsoft Defender 防病毒保持最新状态。 请参阅[管理Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

### <a name="why-do-we-need-cloud-protection-maps-on"></a>为什么需要云保护 (MAPS) 上？

需要云保护才能在设备上启用该功能。 云保护 [允许 Defender for Endpoint](microsoft-defender-endpoint.md) 基于安全智能的广度和深度以及行为和设备学习模型提供最新且最丰富的保护。

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>主动模式和被动模式之间有什么区别？

对于运行 Windows 10、Windows 11、Windows Server 版本 1803 或更高版本、Windows Server 2019 或 Windows Server 2022（当 Microsoft Defender 防病毒 处于活动状态）的终结点，它将用作设备上的主要防病毒。 在被动模式下运行时，Microsoft Defender 防病毒不是主要的防病毒产品。 在这种情况下，威胁不会由Microsoft Defender 防病毒进行修正。

> [!NOTE]
> Microsoft Defender 防病毒设备载入到设备后，才能在被动模式下Microsoft Defender for Endpoint。

有关详细信息，请参阅Microsoft Defender 防病毒[兼容性](microsoft-defender-antivirus-compatibility.md)。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>如何实现确认Microsoft Defender 防病毒处于主动或被动模式？

若要确认Microsoft Defender 防病毒处于主动或被动模式，可以在运行命令提示符或 PowerShell 的设备上Windows。

|Method|Procedure|
|---|---|
|PowerShell|1. 选择"开始"菜单，开始键入 `PowerShell`，然后在Windows PowerShell中打开" "。<br/><br/>2. 键入 `Get-MpComputerStatus`。<br/><br/>3. 在结果列表中，在 **AMRunningMode** 行中查找下列值之一：<br/>- `Normal`<br/>- `Passive Mode`<br/><br/>若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。|
|命令提示符|1. 选择"开始"菜单，开始键入 `Command Prompt`，然后在Windows打开命令提示符。<br/><br/>2. 键入 `sc query windefend`。<br/><br/>3. 在结果列表中的 **"状态** "行中，确认服务正在运行。 |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>如何实现确认EDR模式是否处于打开状态，Microsoft Defender 防病毒处于被动模式？

可以使用 PowerShell 确认在EDR模式下打开处于阻止模式Microsoft Defender 防病毒处于被动模式。

1. 选择"开始"菜单，开始键入 `PowerShell`，然后在Windows PowerShell中打开" "。

2. 类型 `Get-MPComputerStatus|select AMRunningMode`。

3. 确认显示结果 `EDR Block Mode`。

   > [!TIP]
   > 如果Microsoft Defender 防病毒处于活动状态，你将看到 而不是 `Normal` `EDR Block Mode`。 若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2"></a>R2 EDR R2 上是否支持Windows Server 2016 Windows Server 2012模式？

如果Microsoft Defender 防病毒模式或被动模式EDR，则以下版本的 Windows 支持阻止模式下的Windows：

- Windows 11
- Windows 10 (所有) 
- Windows Server 版本 1803 或更高版本 
- Windows Server 2022
- Windows Server 2019 
- Windows Server 2016 Windows Server 2012统一 ([解决方案来部署](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) R2) 

使用适用于 [R2](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview) 和 Windows Server 2016 Windows Server 2012 的新统一客户端解决方案，EDR被动模式或主动模式下运行客户端。

> [!NOTE]
> Windows Server 2016 Windows Server 2012 R2 必须按照[载入 Windows 服务器中的](configure-server-endpoints.md)说明载入 R2，此功能将正常工作。 

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>在阻止模式下禁用EDR需要的时间？

如果选择在阻止EDR禁用此功能，则系统最多可能需要 30 分钟才能禁用此功能。

## <a name="see-also"></a>另请参阅

- [Tech Community博客：在EDR模式下进行介绍：停止其跟踪中的攻击](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)

- [行为阻止和控制](behavioral-blocking-containment.md)
