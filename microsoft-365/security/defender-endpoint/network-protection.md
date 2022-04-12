---
title: 使用网络保护来帮助防止与不良站点的连接
description: 通过阻止用户访问已知的恶意和可疑网络地址来保护网络
keywords: 网络保护、攻击、恶意网站、ip、域、域
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: overview
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: ''
ms.openlocfilehash: f58c7afe9c6f532f7f6420d58bcd681778483680
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789329"
---
# <a name="protect-your-network"></a>保护你的网络

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="overview-of-network-protection"></a>网络保护概述

网络保护有助于保护设备免受基于 Internet 的事件的影响。 网络保护是攻击面减少功能。 它有助于防止员工通过应用程序访问危险域。 在 Internet 上托管网络钓鱼诈骗、攻击和其他恶意内容的域被视为危险。 网络保护扩展[了Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)的范围，以阻止所有尝试连接到基于域或主机名)  (低信誉源的出站 HTTP () 流量。

网络保护将 [Web 保护中的保护](web-protection-overview.md) 扩展到操作系统级别。 它为其他受支持的浏览器和非浏览器应用程序提供 Edge 中的 Web 保护功能。 此外，当与 [终结点检测和响应](overview-endpoint-detection-response.md)一起使用时，网络保护还提供入侵指标 (IOC) 的可见性和阻塞性。 例如，网络保护适用于可用于阻止特定域或主机名的 [自定义指示](manage-indicators.md) 器。

> [!TIP]
> 请参阅 demo.wd.microsoft.com 的[Microsoft Defender for Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)测试场站点，了解网络保护的工作原理。

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

## <a name="requirements-for-network-protection"></a>网络保护要求

网络保护需要Windows 10 专业版或Enterprise，并Microsoft Defender 防病毒实时保护。

<br>

****

|Windows 版本|Microsoft Defender 防病毒|
|---|---|
|Windows 10版本 1709 或更高版本 <p> Windows 11 <p> Windows服务器 1803 或更高版本|必须启用[Microsoft Defender 防病毒实时保护](configure-real-time-protection-microsoft-defender-antivirus.md)和[云提供的保护](enable-cloud-protection-microsoft-defender-antivirus.md)|
|

启用服务后，可能需要配置网络或防火墙，以允许服务与设备之间的连接 (也称为终结点) 。

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="configuring-network-protection"></a>配置网络保护

有关如何启用网络保护的详细信息，请参阅 **[“启用网络保护](enable-network-protection.md)**”。 使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。

## <a name="viewing-network-protection-events"></a>查看网络保护事件

网络保护最适用于[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，这为你提供了有关攻击保护事件和阻止的详细报告，作为[警报调查方案](investigate-alerts.md)的一部分。

当网络保护阻止连接时，会从操作中心显示通知。 安全运营团队可以使用组织的详细信息和联系信息 [自定义通知](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) 。 此外，可以启用和自定义单个攻击面减少规则，以适应某些要监视的技术。

还可以使用 [审核模式](audit-windows-defender.md) 来评估网络保护在启用后对组织的影响。

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中查看网络保护事件

Microsoft Defender for Endpoint提供有关事件和块的详细报告，作为[警报调查方案的一](investigate-alerts.md)部分。 可以在Microsoft 365 Defender门户中查看这些详细信息， ([https://security.microsoft.com](https://security.microsoft.com) [警报队列](review-alerts.md)中的) 或使用[高级搜寻](advanced-hunting-overview.md)。 如果使用的是 [审核模式](audit-windows-defender.md)，则可以使用高级搜寻来查看网络保护设置在启用后会对环境产生怎样的影响。

下面是高级搜寻的示例查询：

```kusto
DeviceNetworkEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked', 'ConnectionSuccess')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>查看Windows 事件查看器中的网络保护事件

可以查看Windows事件日志，查看网络保护阻止 (或审核) 访问恶意 IP 或域时创建的事件：

1. [直接复制 XML](event-views.md)。

2. 选择“确定”。

此过程创建一个自定义视图，该视图筛选为仅显示与网络保护相关的以下事件：

<br>

****

|事件 ID|描述|
|---|---|
|5007|更改设置时的事件|
|1125|在审核模式下触发网络保护时的事件|
|1126|网络保护在阻止模式下触发时的事件|
|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>网络保护和 TCP 三向握手

通过网络保护，通过 [TCP/IP 完成三向握手](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip)后，确定是允许还是阻止对站点的访问。 因此，当网站被网络保护阻止时，你可能会在Microsoft 365 Defender门户中看到以下操作类型`ConnectionSuccess``NetworkConnectionEvents`，即使站点实际上已被阻止。 `NetworkConnectionEvents` 从 TCP 层报告，而不是从网络保护报告。 三向握手完成后，网络保护允许或阻止对站点的访问。

下面是工作原理的示例：

1. 假设用户尝试访问其设备上的网站。 站点恰好托管在危险域上，应由网络保护阻止。  

2. 通过 TCP/IP 开始的三向握手。 完成之前，将记录一个 `NetworkConnectionEvents` 操作，并将其 `ActionType` 列为 `ConnectionSuccess`。 但是，三向握手过程一完成，网络保护就会阻止对站点的访问。 这一切发生得非常快。 [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)也发生了类似的过程;三向握手完成后，就会做出确定，并且会阻止或允许访问站点。

3. 在Microsoft 365 Defender门户中，[警报队列中列出了警报](alerts-queue.md)。 该警报的详细信息包括和 `NetworkConnectionEvents` `AlertEvents`。 你可以看到网站已被阻止，即使你也有一个 `NetworkConnectionEvents` 项与 ActionType 的 `ConnectionSuccess`。

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>多会话Windows 10 企业版运行Windows虚拟桌面的注意事项

由于Windows 10 企业版的多用户性质，请记住以下几点：

1. 网络保护是设备范围的一项功能，不能针对特定用户会话。

2. Web 内容筛选策略也是设备范围。

3. 如果需要区分用户组，请考虑创建单独的Windows虚拟桌面主机池和分配。

4. 在审核模式下测试网络保护，以在推出之前评估其行为。

5. 如果有大量用户或大量多用户会话，请考虑调整部署的大小。

### <a name="alternative-option-for-network-protection"></a>网络保护的替代选项

对于在 Azure 上Windows虚拟桌面中使用的Windows 10 企业版多会话 1909 及更高版本，可以使用以下方法启用Microsoft Edge的网络保护：

1. 使用 [启用网络保护](enable-network-protection.md) 并按照说明应用策略。

2. 执行以下 PowerShell 命令：
  - `Set-MpPreference -EnableNetworkProtection Enabled`
  - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
  - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
  - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>网络保护故障排除

由于运行网络保护的环境，Microsoft 可能无法检测操作系统代理设置。 在某些情况下，网络保护客户端无法访问云服务。 若要解决连接问题，具有 E5 许可证的客户应配置以下注册表项之一：

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="see-also"></a>另请参阅

- [评估网络保护](evaluate-network-protection.md) |执行一个快速方案，演示功能的工作原理，以及通常会创建哪些事件。
- [启用网络保护](enable-network-protection.md)|使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。
- [在Microsoft Intune中配置攻击面减少功能](/mem/intune/protect/endpoint-security-asr-policy)
