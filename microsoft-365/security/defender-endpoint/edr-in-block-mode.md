---
title: 阻止模式下的终结点检测和响应
description: 了解在块模式下终结点检测和响应
keywords: Microsoft Defender for Endpoint、mde、EDR在阻止模式下，被动模式阻止
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
ms.openlocfilehash: 5a9441a41db2dfbe53bfb280152c038e9dbc383e
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789835"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>阻止模式下的终结点检测和响应 (EDR)。

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="what-is-edr-in-block-mode"></a>阻止模式下EDR是什么？

当Microsoft Defender 防病毒不是主要防病毒产品且处于被动模式下运行时，阻止模式下的[终结点检测和响应](overview-endpoint-detection-response.md) (EDR) 可为恶意项目提供额外的保护。 阻止模式下的EDR可在后台工作，以修正EDR功能检测到的恶意项目。 主要的非 Microsoft 防病毒产品可能遗漏了此类项目。 对于运行Microsoft Defender 防病毒作为主要防病毒软件的设备，在阻止模式下EDR允许Microsoft Defender 防病毒对违规后的行为EDR检测采取自动操作，从而提供额外的防御层。

> [!IMPORTANT]
> EDR在阻止模式下不提供启用Microsoft Defender 防病毒实时保护时可用的所有保护。 依赖于Microsoft Defender 防病毒为活动防病毒解决方案的所有功能将不起作用，包括以下关键示例：
>
> - 当Microsoft Defender 防病毒处于被动模式时，实时保护（包括访问扫描）不可用。 若要详细了解实时保护策略设置，请参阅 **[启用和配置Microsoft Defender 防病毒始终可用的保护](configure-real-time-protection-microsoft-defender-antivirus.md)**。
>
> - 仅当Microsoft Defender 防病毒处于活动模式下运行时，才能使用 **[网络保护](network-protection.md)** 和 **[攻击面减少规则](attack-surface-reduction.md)** 等功能。
>
> 预计非 Microsoft 防病毒解决方案会提供这些功能。

阻止模式下的EDR与[威胁& 漏洞管理](next-gen-threat-and-vuln-mgt.md)集成。 如果尚未启用阻止模式，组织的安全团队将收到[一项安全建议](tvm-security-recommendation.md)，以便在阻止模式下启用EDR。

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="在阻止模式下打开EDR的建议" lightbox="images/edrblockmode-TVMrecommendation.png":::

> [!TIP]
> 若要获得最佳保护，请确保 **[部署Microsoft Defender for Endpoint基线](configure-machines-security-baseline.md)**。

## <a name="what-happens-when-something-is-detected"></a>检测到某个内容时会发生什么情况？

启用EDR模式下的EDR并检测到恶意项目时，Microsoft Defender for Endpoint块并修正该项目。 安全操作团队会在 [操作中心](respond-machine-alerts.md#check-activity-details-in-action-center)将检测状态视为 **“已阻止**”或 **“阻止**”，并列出为已完成的操作。

下图显示了在阻止模式下通过EDR检测和阻止的不需要软件的实例：

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="在块模式下EDR检测" lightbox="images/edr-in-block-mode-detection.png":::


## <a name="enable-edr-in-block-mode"></a>在块模式下启用EDR

> [!IMPORTANT]
> 从平台版本 4.18.2202.X 开始，现在可以在块模式下将EDR设置为使用 Intune CSP 面向特定设备组。 可以在Microsoft 365 Defender门户中继续在块模式租户范围内设置<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">EDR</a>。  (非 Microsoft 防病毒解决方案安装并在设备) 上处于活动状态，则主要建议在阻止模式下运行Microsoft Defender 防病毒的设备使用阻止模式EDR。 

> [!TIP]
> 在阻止模式下打开EDR之前，请确保满足[这些要求](#requirements-for-edr-in-block-mode)。

### <a name="security-portal"></a>安全门户 

1. 转到Microsoft 365 Defender门户 () [https://security.microsoft.com/](https://security.microsoft.com/) 并登录。

2. 选择 **设置** \> **终结点** \> **常规** \> **高级功能**。

3. 向下滚动，然后在 **块模式下启用EDR**。

### <a name="intune"></a>Intune

若要在Intune中创建自定义策略，请参阅[“部署OMA-URIs通过Intune面向 CSP，以及与本地的比较](/troubleshoot/mem/intune/deploy-oma-uris-to-target-csp-via-intune)。

有关用于在块模式下EDR的 Defender CSP 的详细信息，请参阅 [Defender CSP](/windows/client-management/mdm/defender-csp) 下的“配置/被动修正”。


## <a name="requirements-for-edr-in-block-mode"></a>块模式下EDR的要求

下表列出了在块模式下EDR的要求：

|要求|详细信息|
|---|---|
|权限|必须在[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)中分配全局管理员或安全管理员角色。 有关详细信息，请参阅 [基本权限](basic-permissions.md)。|
|操作系统|设备必须运行以下Windows版本之一： <br/>- Windows 11 <br/>- Windows 10 (所有版本) <br/>- Windows服务器 2022 <br/>- Windows服务器 2019<br/>- Windows服务器版本 1803 或更高版本<br/>- 使用[新的统一客户端解决方案](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)) <sup>[[1](#fn1)]</sup> Windows Server 2016和Windows Server 2012 R2 (  |
|Microsoft Defender for Endpoint|设备必须载入 Defender for Endpoint。 另请参阅以下文章： <br/>- [Microsoft Defender for Endpoint的最低要求](minimum-requirements.md)<br/>- [载入设备并配置Microsoft Defender for Endpoint功能](onboard-configure.md)<br/>- [将Windows服务器载入 Defender for Endpoint 服务](configure-server-endpoints.md)<br/>- [新Windows Server 2012统一解决方案中的 R2 和 2016 功能 (预览版) ](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) |
|Microsoft Defender 防病毒|设备必须安装Microsoft Defender 防病毒并在主动模式或被动模式下运行。 [确认Microsoft Defender 防病毒处于主动或被动模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。|
|云端保护|必须配置Microsoft Defender 防病毒才能[启用云传递的保护](enable-cloud-protection-microsoft-defender-antivirus.md)。|
|Microsoft Defender 防病毒平台|设备必须是最新的。 若要确认使用 PowerShell，请以管理员身份运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMProductVersion** 行中，应会看到 **4.18.2001.10** 或更高版本。 <p> 要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。|
|Microsoft Defender 防病毒引擎|设备必须是最新的。 若要确认使用 PowerShell，请以管理员身份运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMEngineVersion** 行中，应会看到 **1.1.16700.2** 或更高版本。 <p> 要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。|

 (<a id="fn1">1</a>) 请参阅 [Windows Server 2016 和 Windows Server 2012 R2 是否支持EDR阻止模式？](#is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2)

> [!IMPORTANT]
> 若要获得最佳保护值，请确保将防病毒解决方案配置为接收常规更新和基本功能，并 [配置排除](configure-exclusions-microsoft-defender-antivirus.md)项。 在块模式下EDR遵循为Microsoft Defender 防病毒定义的排除，但不遵循为Microsoft Defender for Endpoint定义的[指示器](manage-indicators.md)。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="can-i-specify-exclusions-for-edr-in-block-mode"></a>是否可以在阻止模式下为EDR指定排除项？

在获取误报后，可以在[提交网站Microsoft 安全智能](https://www.microsoft.com/en-us/wdsi/filesubmission)提交文件进行分析。

还可以为Microsoft Defender 防病毒定义排除项。 请参阅[配置和验证Microsoft Defender 防病毒扫描的排除项](configure-exclusions-microsoft-defender-antivirus.md)。

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>如果我在设备上运行Microsoft Defender 防病毒，是否需要在阻止模式下启用EDR？

在阻止模式下EDR的主要目的是修正非 Microsoft 防病毒产品遗漏的违规后检测。 当Microsoft Defender 防病毒处于活动模式时，在阻止模式下启用EDR的好处微乎其微，因为实时保护应首先捕获和修正检测。 建议在 Microsoft Defender for Antivirus 处于被动模式下运行的终结点上启用阻止模式下的EDR。 EDR检测可以通过 [PUA 保护](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)或在阻止模式[下自动调查&修正功能](automated-investigations.md)自动修正。

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>在阻止模式下EDR是否会影响用户的防病毒保护？

在阻止模式下EDR不会影响在用户设备上运行的第三方防病毒保护。 如果主要防病毒解决方案缺少某些内容，或者存在违规后检测，则阻止模式下的EDR有效。 在阻止模式下EDR的工作方式与被动模式下Microsoft Defender 防病毒一样，只不过在阻止模式下EDR也会阻止和修正检测到的恶意项目或行为。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>为什么我需要保持Microsoft Defender 防病毒最新？

由于Microsoft Defender 防病毒检测和修正恶意项目，因此请务必保持最新状态。 为了使阻止模式下的EDR有效，它使用最新的设备学习模型、行为检测和启发式。 [Defender for Endpoint](microsoft-defender-endpoint.md) 功能堆栈以集成方式工作。 若要获得最佳保护值，应保持Microsoft Defender 防病毒最新。 请参阅[“管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

### <a name="why-do-we-need-cloud-protection-maps-on"></a>为什么我们需要云保护 (MAPS) ？

需要云保护才能在设备上启用该功能。 云保护使 [Defender for Endpoint](microsoft-defender-endpoint.md) 能够根据我们的安全智能的广度和深度，以及行为和设备学习模型提供最新和最大的保护。

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>主动模式和被动模式之间的区别是什么？

对于运行Windows 10、Windows 11、Windows服务器、版本 1803 或更高版本、Windows Server 2019 或 Windows服务器 2022（当Microsoft Defender 防病毒处于活动模式时）的终结点，它将用作设备上的主要防病毒软件。 在被动模式下运行时，Microsoft Defender 防病毒不是主要防病毒产品。 在这种情况下，Microsoft Defender 防病毒不会实时修正威胁。

> [!NOTE]
> 仅当设备载入到Microsoft Defender for Endpoint时，Microsoft Defender 防病毒才能在被动模式下运行。

有关详细信息，请参阅[Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)。

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>如何实现确认Microsoft Defender 防病毒处于主动或被动模式？

若要确认Microsoft Defender 防病毒是在主动模式还是被动模式下运行，可以在运行Windows的设备上使用命令提示符或 PowerShell。

|方法|Procedure|
|---|---|
|PowerShell|1. 选择"开始"菜单，开始键入`PowerShell`，然后在结果中打开Windows PowerShell。<br/><br/>2. 类型 `Get-MpComputerStatus`。<br/><br/>3. 在结果列表的 **AMRunningMode** 行中，查找以下值之一：<br/>- `Normal`<br/>- `Passive Mode`<br/><br/>若要了解详细信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。|
|命令提示符|1. 选择"开始"菜单，开始键入`Command Prompt`，然后在结果中打开Windows命令提示符。<br/><br/>2. 类型 `sc query windefend`。<br/><br/>3. 在结果列表中的 **STATE** 行中，确认服务正在运行。 |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>如何实现确认处于阻止模式的EDR已在被动模式下打开Microsoft Defender 防病毒？

可以使用 PowerShell 来确认阻止模式下的EDR已打开，Microsoft Defender 防病毒在被动模式下运行。

1. 选择"开始"菜单，开始键入`PowerShell`，然后在结果中打开Windows PowerShell。

2. 类型 `Get-MPComputerStatus|select AMRunningMode`。

3. 确认是否显示结果 `EDR Block Mode`。

   > [!TIP]
   > 如果Microsoft Defender 防病毒处于活动模式，你将看到而不是`EDR Block Mode`。`Normal` 若要了解详细信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016-and-windows-server-2012-r2"></a>EDR在 Windows Server 2016 和 Windows Server 2012 R2 上是否支持阻止模式？

如果Microsoft Defender 防病毒在主动模式或被动模式下运行，则支持在块模式下EDR以下版本的Windows：

- Windows 11
- Windows 10 (所有版本) 
- Windows服务器版本 1803 或更高版本 
- Windows Server 2022
- Windows Server 2019 
- 使用[新的统一客户端解决方案](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)Windows Server 2016和Windows Server 2012 R2 () 

使用适用于 Windows Server 2016 和 Windows Server 2012 R2 [的新统一客户端解决方案](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)，可以在被动模式或主动模式下在块模式下运行EDR。

> [!NOTE]
> Windows Server 2016和Windows Server 2012 R2 必须使用载[入Windows服务器](configure-server-endpoints.md)中的说明载入，才能使此功能正常工作。 

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>禁用阻止模式下的EDR需要多长时间？

如果选择在阻止模式下禁用EDR，系统最多可能需要 30 分钟才能禁用此功能。

## <a name="see-also"></a>另请参阅

- [技术Community博客：在阻止模式下引入EDR：在跟踪中停止攻击](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)

- [行为阻止和控制](behavioral-blocking-containment.md)
