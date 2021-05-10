---
title: 阻止模式下的终结点检测和响应
description: 了解阻止模式下的终结点检测和响应
keywords: Microsoft Defender for Endpoint， mde， EDR处于阻止模式， 被动模式阻止
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
ms.date: 05/08/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 86bb27005365b625ee07feaa067c0ac488c3bb4b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302036"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>终结点检测和响应 (EDR) 阻止模式

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>阻止EDR什么？

[在阻止模式下 (EDR) ](overview-endpoint-detection-response.md)终结点检测和响应功能可提供对恶意项目的保护，即使 Microsoft Defender 防病毒处于被动模式时。 打开后，EDR模式阻止在设备上检测到的恶意项目或行为。 EDR阻止模式在后台工作，以修正在泄露后检测到的恶意项目。 

EDR模式中的用户还集成了[威胁](next-gen-threat-and-vuln-mgt.md)& 漏洞管理。 如果组织的安全团队尚未启用，EDR启用[](tvm-security-recommendation.md)阻止模式的安全建议。 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="建议在阻止EDR启用此模式":::

> [!NOTE]
> 若要获取最佳保护，请确保为终结点基线 **[部署 Microsoft Defender。](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>检测到某些内容时会发生什么情况？

当EDR模式启用后检测到恶意项目时，适用于终结点的 Microsoft Defender 将阻止并修正这些项目。 安全操作团队将在操作中心中将检测状态视为"已阻止"或[](respond-machine-alerts.md#check-activity-details-in-action-center)"已阻止"，列为已完成操作。 

下图显示了一个不需要的软件的实例，这些软件在阻止模式下通过EDR阻止：

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR阻止模式下检测到某些内容":::


## <a name="enable-edr-in-block-mode"></a>启用EDR阻止模式

> [!IMPORTANT]
> 在以[阻止模式](#requirements-for-edr-in-block-mode)打开应用前，EDR满足要求。

1. 转到 [https://securitycenter.windows.com](https://securitycenter.windows.com) "Microsoft Defender 安全中心 () 并登录。 

2. 选择 **设置**  >  **高级功能"。**

3. 在阻止 **EDR启用" "。**

> [!NOTE]
> EDR在阻止模式下只能打开Microsoft Defender 安全中心。 不能使用注册表项、Intune 或组策略启用或禁用EDR阻止模式。

## <a name="requirements-for-edr-in-block-mode"></a>阻止模式下EDR应用的要求

|要求  |详细信息  |
|---------|---------|
|权限 |全局管理员或安全管理员角色在 Azure Active Directory 中[分配](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。 请参阅 [基本权限](basic-permissions.md)。 |
|操作系统     |以下版本之一： <br/>- Windows 10 (所有)  <br/>- Windows Server 版本 1803 或更高版本 <br/>- Windows Server 2019 <br/>- Windows Server 2016 (仅在Microsoft Defender 防病毒处于活动状态时)      |
|WindowsE5 注册     |WindowsE5 包含在以下订阅中： <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 Identity &威胁防护产品一起 <br/><br/>请参阅[每个](/microsoft-365/enterprise/microsoft-365-overview#components)[计划的组件和功能](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。       |
|Microsoft Defender 防病毒  |Microsoft Defender 防病毒在主动模式或被动模式下安装和运行。  (可以一Microsoft Defender 防病毒 Microsoft 防病毒解决方案一起使用。) [确认Microsoft Defender 防病毒处于主动或被动模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。 |
|云端保护 |请确保Microsoft Defender 防病毒配置云保护，以[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。 |
|Microsoft Defender 防病毒反恶意软件客户端 |确保你的客户端是最新的。 使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMProductVersion** 行中，应该会看到 **4.18.2001.10** 或更上方。 |
|Microsoft Defender 防病毒引擎 |确保你的引擎是最新的。 使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMEngineVersion** 行中，应该会看到 **1.1.16700.2** 或更上方。 |

> [!IMPORTANT]
> 若要获取最佳保护值，请确保防病毒解决方案配置为接收定期更新和基本功能，并且已配置排除 [项](configure-exclusions-microsoft-defender-antivirus.md)。 EDR模式中的策略将遵守为阻止模式定义的Microsoft Defender 防病毒。

## <a name="frequently-asked-questions"></a>常见问题解答 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>我是否需要在阻止EDR打开状态，即使我在设备上Microsoft Defender 防病毒运行？

我们建议保持EDR模式处于打开状态，Microsoft Defender 防病毒被动模式还是主动模式运行。 EDR模式使用 Microsoft Defender for Endpoint 提供另一层防御。 它允许 Defender for Endpoint 根据攻破后的行为和检测EDR操作。 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>EDR模式是否对用户的防病毒保护有任何影响？ 

EDR模式运行不会影响在用户设备上运行的第三方防病毒保护。 EDR如果主防病毒解决方案遗漏了某些内容，或者存在泄露后检测，则以阻止模式运行。 EDR模式运行方式与被动Microsoft Defender 防病毒中的阻止操作类似，但它也会阻止和修正检测到的恶意项目或行为。

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>为什么我需要使Microsoft Defender 防病毒保持最新？ 

由于Microsoft Defender 防病毒检测并修正恶意项目，因此保持最新很重要。 为了EDR模式运行，它使用最新的设备学习模型、行为检测和启发。 [Defender for Endpoint](microsoft-defender-endpoint.md)功能堆栈以集成方式工作。 若要获得最佳保护值，Microsoft Defender 防病毒保持最新状态。 请参阅[管理Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。 

### <a name="why-do-we-need-cloud-protection-on"></a>为什么需要云保护？ 

需要云保护才能在设备上启用该功能。 云保护 [允许 Defender for Endpoint](microsoft-defender-endpoint.md) 基于安全智能的广度和深度以及行为和设备学习模型提供最新且最丰富的保护。

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>如何将用户Microsoft Defender 防病毒被动模式？

根据操作系统，当运行非 Microsoft 防病毒/反恶意软件解决方案的设备载入 Defender for Endpoint 时，Microsoft Defender 防病毒自动进入被动模式。 有关详细信息，请参阅如何Microsoft Defender 防病毒[Defender for Endpoint 功能](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality)。 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>如何确认Microsoft Defender 防病毒处于主动或被动模式？

若要确认Microsoft Defender 防病毒处于主动或被动模式，可以在运行命令提示符或 PowerShell 的设备上Windows。


|方法  |Procedure  |
|---------|---------|
| PowerShell     | 1. 选择"开始"菜单，开始键入 `PowerShell` ，然后在Windows PowerShell中打开" 开始"菜单。 <p>2. 键入 `Get-MpComputerStatus` 。 <p>3. 在结果列表中，在 **AMRunningMode** 行中查找下列值之一： <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。        |
|命令提示符     | 1. 选择"开始"菜单，开始键入 ，然后在Windows `Command Prompt` 打开命令提示符。 <p>2. 键入 `sc query windefend` 。 <p>3. 在结果列表中的 **"状态** "行中，确认服务正在运行。         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>在阻止模式下禁用EDR需要的时间？

如果选择在阻止EDR禁用此功能，则系统最多可能需要 30 分钟才能禁用此功能。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>EDR上是否支持阻止Windows Server 2016？

如果Microsoft Defender 防病毒模式或被动模式下运行，EDR支持以下版本的 Windows：

- Windows 10 (所有版本) 
- Windows服务器版本 1803 或更高版本 
- Windows Server 2019 

如果Windows Server 2016在Microsoft Defender 防病毒模式下运行，并且终结点已载入到 Defender for Endpoint，则EDR支持以阻止模式运行。 但是，EDR阻止模式旨在当终结点上不是Microsoft Defender 防病毒防病毒解决方案时提供额外保护。 在这种情况下，Microsoft Defender 防病毒被动模式下运行。 目前，Microsoft Defender 防病毒在被动模式下运行 Windows Server 2016。 若要了解更多信息，请参阅[Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)。

## <a name="see-also"></a>另请参阅

- [Tech Community博客：在EDR模式下进行介绍：停止跟踪攻击](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [行为阻止和控制](behavioral-blocking-containment.md)

