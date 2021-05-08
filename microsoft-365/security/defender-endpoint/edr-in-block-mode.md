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
ms.date: 05/06/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 78201fd20d689a6774eb5395aa787a2b15147972
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274480"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>在阻止模式下， (EDR) 终结点检测和响应

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>什么是阻止模式下的 EDR？

[在阻止模式下](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) 终结点检测和响应功能可提供对恶意项目的保护，即使 Microsoft Defender 防病毒在被动模式下运行。 打开后，阻止模式下的 EDR 将阻止在设备上检测到的恶意项目或行为。 阻止模式下的 EDR 在后台工作，可修正在泄露后检测到的恶意项目。 

阻止模式下的 EDR 也与威胁和漏洞& [集成](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)。 如果尚未启用 EDR，组织[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)的安全团队会获得一条安全建议，以在阻止模式下打开它。 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="建议在阻止模式下打开 EDR":::

> [!NOTE]
> 若要获取最佳保护，请确保为终结点基线 **[部署 Microsoft Defender。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>检测到某些内容时会发生什么情况？

当在阻止模式下打开 EDR 并检测到恶意项目时，适用于终结点的 Microsoft Defender 将阻止并修正这些项目。 安全操作团队将在操作中心中将检测状态视为"已阻止"或[](respond-machine-alerts.md#check-activity-details-in-action-center)"已阻止"，列为已完成操作。 

下图显示了在阻止模式下通过 EDR 检测并阻止的不需要软件的实例：

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="阻止模式下的 EDR 检测到某些内容":::


## <a name="enable-edr-in-block-mode"></a>在阻止模式下启用 EDR

> [!IMPORTANT]
> 在阻止 [模式下打开](#requirements-for-edr-in-block-mode) EDR 之前，请确保满足要求。

1. 转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 并登录。 

2. 选择 **"设置**  >  **""高级功能"。**

3. 在阻止 **模式下打开 EDR。**

> [!NOTE]
> 阻止模式下的 EDR 只能在 Microsoft Defender 安全中心中打开。 不能使用注册表项、Intune 或组策略在阻止模式下启用或禁用 EDR。

## <a name="requirements-for-edr-in-block-mode"></a>阻止模式下的 EDR 要求

|要求  |详细信息  |
|---------|---------|
|权限 |在 Azure Active Directory 中分配的全局管理员或 [安全管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。 请参阅 [基本权限](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions)。 |
|操作系统     |以下版本之一： <br/>- Windows 10 (所有版本)  <br/>- Windows Server 版本 1803 或更高版本 <br/>- Windows Server 2019 <br/>- Windows Server 2016 (仅在 Microsoft Defender 防病毒在活动模式下运行)      |
|Windows E5 注册     |Windows E5 包含在以下订阅中： <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 以及 Identity &威胁防护产品 <br/><br/>请参阅[每个](/microsoft-365/enterprise/microsoft-365-overview#components)[计划的组件和功能](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。       |
|Microsoft Defender 防病毒  |必须在主动模式或被动模式下安装并运行 Microsoft Defender 防病毒。  (可以将 Microsoft Defender 防病毒与非 Microsoft 防病毒解决方案一同使用。) 确认 Microsoft Defender 防病毒 [处于主动或被动模式](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode)。 |
|云端保护 |确保配置了 Microsoft Defender 防病毒，以启用 [云保护](enable-cloud-protection-microsoft-defender-antivirus.md)。 |
|Microsoft Defender 防病毒反恶意软件客户端 |确保你的客户端是最新的。 使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMProductVersion** 行中，应该会看到 **4.18.2001.10** 或更上方。 |
|Microsoft Defender 防病毒引擎 |确保你的引擎是最新的。 使用 PowerShell 以管理员角色运行 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet。 在 **AMEngineVersion** 行中，应该会看到 **1.1.16700.2** 或更上方。 |

> [!IMPORTANT]
> 若要获取最佳保护值，请确保防病毒解决方案配置为接收定期更新和基本功能，并且已配置排除 [项](configure-exclusions-microsoft-defender-antivirus.md)。 阻止模式下的 EDR 遵守为 Microsoft Defender 防病毒定义的排除项。

## <a name="frequently-asked-questions"></a>常见问题解答 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>我是否需要在阻止模式下打开 EDR，即使我在设备上运行 Microsoft Defender 防病毒？

我们建议在阻止模式下保持 EDR 处于打开状态，无论 Microsoft Defender 防病毒是在被动模式下运行还是处于活动模式。 块模式下的 EDR 通过 Microsoft Defender for Endpoint 提供另一层防御。 它允许 Defender for Endpoint 根据攻破后的行为 EDR 检测采取操作。 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>阻止模式下的 EDR 是否将影响用户的防病毒保护？ 

阻止模式下的 EDR 不会影响在用户设备上运行的第三方防病毒保护。 如果主防病毒解决方案遗漏了某些内容，或者存在泄露后检测，则阻止模式下的 EDR 可以正常工作。 阻止模式下的 EDR 的工作方式与被动模式下 [的 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)的工作方式类似，但它也会阻止和修正检测到的恶意项目或行为。 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>为什么需要使 Microsoft Defender 防病毒保持最新状态？ 

由于 Microsoft Defender 防病毒会检测并修正恶意项目，因此保持其最新状态非常重要。 为了在块模式中实现 EDR 有效，它使用最新的设备学习模型、行为检测和启发。 [Defender for Endpoint](microsoft-defender-endpoint.md)功能堆栈以集成方式工作。 若要获得最佳保护价值，应使 Microsoft Defender 防病毒保持最新。 请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。 

### <a name="why-do-we-need-cloud-protection-on"></a>为什么需要云保护？ 

需要云保护才能在设备上启用该功能。 云保护 [允许 Defender for Endpoint](microsoft-defender-endpoint.md) 基于安全智能的广度和深度以及行为和设备学习模型提供最新且最丰富的保护。

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>如何将 Microsoft Defender 防病毒设置为被动模式？

根据操作系统，当运行非 Microsoft 防病毒/反恶意软件解决方案的设备载入 Defender for Endpoint 时，Microsoft Defender 防病毒可以自动进入被动模式。 有关详细信息，请参阅[防病毒和 Microsoft Defender for Endpoint。](microsoft-defender-antivirus-compatibility.md#antivirus-and-microsoft-defender-for-endpoint) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>如何确认 Microsoft Defender 防病毒处于主动或被动模式？

若要确认 Microsoft Defender 防病毒是在主动模式还是被动模式下运行，可以在运行 Windows 的设备上使用命令提示符或 PowerShell。


|方法  |Procedure  |
|---------|---------|
| PowerShell     | 1. 选择"开始"菜单，开始键入 `PowerShell` ，然后Windows PowerShell结果中的"开始"菜单。 <p>2. 键入 `Get-MpComputerStatus` 。 <p>3. 在结果列表中，在 **AMRunningMode** 行中查找下列值之一： <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>若要了解更多信息，请参阅 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。        |
|命令提示符     | 1. 选择"开始"菜单，开始键入 `Command Prompt` ，然后在结果中打开 Windows 命令提示符。 <p>2. 键入 `sc query windefend` 。 <p>3. 在结果列表中的 **"状态** "行中，确认服务正在运行。         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>在阻止模式下禁用 EDR 需要的时间？

如果选择在阻止模式下禁用 EDR，则系统最多可能需要 30 分钟才能禁用此功能。

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Windows Server 2016 是否支持 EDR 阻止模式？

如果 Microsoft Defender 防病毒在主动模式或被动模式下运行，则以下版本的 Windows 支持阻止模式下的 EDR：

- Windows 10 (所有版本) 
- Windows Server 版本 1803 或更高版本 
- Windows Server 2019 

如果 Windows Server 2016 在活动模式下运行 Microsoft Defender 防病毒，并且终结点已载入到适用于终结点的 Defender，则支持阻止模式下的 EDR。 但是，当 Microsoft Defender 防病毒不是终结点上的主要防病毒解决方案时，阻止模式下的 EDR 旨在提供额外的保护。 

## <a name="see-also"></a>另请参阅

- [技术社区博客：在阻止模式下引入 EDR：停止其跟踪中的攻击](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [行为阻止和控制](behavioral-blocking-containment.md)
- [更好地结合：Microsoft Defender 防病毒软件和 Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

