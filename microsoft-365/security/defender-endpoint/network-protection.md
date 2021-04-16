---
title: 使用网络保护来帮助防止连接到错误站点
description: 通过阻止用户访问已知的恶意和可疑网络地址来保护网络
keywords: 网络保护， 攻击， 恶意网站， ip， 域， 域
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: a22cab9185b2ece2e8e30c00ea747cca823f4920
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861141"
---
# <a name="protect-your-network"></a>保护你的网络

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

网络保护有助于减少基于 Internet 的事件对设备的攻击面。 它防止员工使用任何应用程序访问可能承载网络钓鱼欺诈、攻击和 Internet 上的其他恶意内容危险域。 网络保护扩展了 Microsoft [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 的范围，以阻止所有基于域或主机名 (尝试连接到低信誉源 (的出站 HTTP) ) 。

从 Windows 10 版本 1709 开始，Windows 支持网络保护。 网络保护在其他操作系统上尚不受支持，但使用基于 Chromium 的新 Microsoft Edge 支持 Web 保护。 若要了解更多信息，请参阅 [Web 保护](web-protection-overview.md)。

网络保护将 Web 保护 [中的保护扩展到](web-protection-overview.md) 操作系统级别。 它在 Edge 中为其他受支持的浏览器和非浏览器应用程序提供 Web 保护功能。 此外，当与终结点检测和响应一 (ICS 时，网络保护) 和阻止泄露[指示器。](overview-endpoint-detection-response.md) 例如，网络保护适用于你的 [自定义指示器](manage-indicators.md)。

若要详细了解如何启用网络保护，请参阅 [启用网络保护](enable-network-protection.md)。 使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。

> [!TIP]
> 有关网络保护的工作原理，demo.wd.microsoft.com Microsoft Defender [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) for Endpoint 测试站点。

网络保护最适合 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，它为你提供有关 Exploit Protection 事件的详细报告，并作为警报调查方案的一部分 [进行阻止](investigate-alerts.md)。

当网络保护阻止连接时，将显示来自操作中心的通知。 安全运营团队 [可以使用](customize-attack-surface-reduction.md#customize-the-notification) 组织的详细信息和联系信息自定义通知。 此外，可以启用和自定义各个攻击面减少规则，以适合要监视的某些技术。

您还可以使用 [审核模式评估](audit-windows-defender.md) 网络保护在启用后对组织的影响。

## <a name="requirements"></a>要求

网络保护需要 Windows 10 专业版或企业版以及 Microsoft Defender 防病毒实时保护。

| Windows 版本 | Microsoft Defender 防病毒 |
|:---|:---|
| Windows 10 版本 1709 或更高版本 <p>Windows Server 1803 或更高版本 | [必须启用 Microsoft Defender 防病毒实时](configure-real-time-protection-microsoft-defender-antivirus.md)[保护和云保护](enable-cloud-protection-microsoft-defender-antivirus.md) |

启用服务后，可能需要配置网络或防火墙，以允许服务和设备之间的连接 (也称为终结点) 。  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>查看 Microsoft Defender 终结点安全中心中的网络保护事件

Microsoft Defender for Endpoint 提供事件的详细报告和阻止，作为警报调查方案的 [一部分](investigate-alerts.md)。

可以使用高级搜寻查询 Microsoft Defender 的终结点 [数据](advanced-hunting-overview.md)。 如果你使用的是审核 [模式](audit-windows-defender.md)，可以使用高级搜寻来查看网络保护设置在启用后将如何影响你的环境。

下面是一个示例查询

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>在 Windows 事件查看器中查看网络保护事件

你可以查看 Windows 事件日志以查看网络保护阻止访问恶意 IP 或域 (或审核) IP 或域时创建的事件：

1. [直接复制 XML。](event-views.md)

2. 选择“确定”。

此过程将创建一个自定义视图，该视图筛选为只显示与网络保护相关的以下事件：

| 事件 ID | 说明 |
|:---|:---|
| 5007 | 更改设置时的事件 |
| 1125 | 在审核模式下触发网络保护时的事件 |
| 1126 | 在阻止模式下触发网络保护时的事件 |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>运行 Windows 10 企业版多会话的 Windows 虚拟桌面的注意事项

由于 Windows 10 企业版具有多用户特性，请注意以下几点：

1. 网络保护是设备范围内的一项功能，不能面向特定的用户会话。

2. Web 内容筛选策略也是设备范围的。

3. 如果需要区分用户组，请考虑创建单独的 Windows 虚拟桌面主机池和分配。

4. 在审核模式下测试网络保护，以在推出之前评估其行为。 

5. 如果您具有大量用户或大量多用户会话，请考虑调整部署大小。

### <a name="alternative-option-for-network-protection"></a>网络保护的备用选项

对于在 Azure 上的 Windows 虚拟桌面中使用的 Windows 10 企业版多会话 1909 及更新，可以使用以下方法启用 Microsoft Edge 的网络保护：

1. 使用 ["打开网络保护](enable-network-protection.md) "并按照说明应用策略。

2. 执行以下 PowerShell 命令： `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>网络保护疑难解答

由于网络保护运行的环境，Microsoft 可能无法检测操作系统代理设置。 在某些情况下，网络保护客户端无法访问云服务。 若要解决连接问题，具有 E5 许可证的客户应配置以下 Defender 注册表项之一：

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>相关文章

- [评估网络保护](evaluate-network-protection.md) |执行一个快速方案，演示功能的工作方式以及通常会创建哪些事件。

- [启用网络保护](enable-network-protection.md) |使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。
