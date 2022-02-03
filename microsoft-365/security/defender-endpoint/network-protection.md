---
title: 使用网络保护来帮助防止连接到错误站点
description: 通过阻止用户访问已知的恶意和可疑网络地址来保护网络
keywords: 网络保护， 攻击， 恶意网站， ip， 域， 域
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
ms.collection: m365initiative-m365-defender
ms.date: ''
ms.openlocfilehash: dfa84cf167dfdb366ad4a7c636a85a30b6de24a4
ms.sourcegitcommit: 726a72f135358603c2fde3f4067d834536e6deb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "62326928"
---
# <a name="protect-your-network"></a>保护你的网络

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="overview-of-network-protection"></a>网络保护概述

网络保护有助于保护设备免受基于 Internet 的事件的影响。 网络保护是攻击面减少功能。 它有助于防止员工通过应用程序访问危险域。 在 Internet 上托管欺诈邮件、攻击和其他恶意内容的域被视为危险。 网络保护扩展[了 Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 的范围，以阻止尝试基于域或主机名 (低信誉源 (的所有出站 HTTP) ) 。

网络保护将 [Web 保护中的保护扩展到](web-protection-overview.md) 操作系统级别。 它为其他受支持的浏览器和非浏览器应用程序提供 Edge 中的 Web 保护功能。 此外，网络保护在终结点检测和响应 (ICS) 可见性和阻止泄露 [指示器](overview-endpoint-detection-response.md)。 例如，网络保护 [适用于可用于阻止](manage-indicators.md) 特定域或主机名的自定义指示器。

> [!TIP]
> 有关网络保护的工作原理，demo.wd.microsoft.com Microsoft Defender for Endpoint [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 测试站点。

## <a name="requirements-for-network-protection"></a>网络保护要求

网络保护Windows 10 专业版或Enterprise，Microsoft Defender 防病毒实时保护。

<br>

****

|Windows 版本|Microsoft Defender 防病毒|
|---|---|
|Windows 10版本 1709 或更高版本 <p> Windows 11 <p> Windows Server 1803 或更高版本|[Microsoft Defender 防病毒必须启用](configure-real-time-protection-microsoft-defender-antivirus.md)实时保护和[云提供的保护](enable-cloud-protection-microsoft-defender-antivirus.md)|
|

启用服务后，可能需要配置网络或防火墙，以允许服务和设备（也称为 (设备）) 。

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="configuring-network-protection"></a>配置网络保护

若要详细了解如何启用网络保护，请参阅 **[启用网络保护](enable-network-protection.md)**。 使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。

## <a name="viewing-network-protection-events"></a>查看网络保护事件

网络保护最适合 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，它为你提供有关 Exploit Protection 事件的详细报告，并作为警报调查方案的一部分 [进行阻止](investigate-alerts.md)。

当网络保护阻止连接时，将显示来自操作中心的通知。 安全运营团队 [可以使用](attack-surface-reduction-rules-deployment-implement.md#customize-attack-surface-reduction-rules) 组织的详细信息和联系信息自定义通知。 此外，可以启用和自定义各个攻击面减少规则，以适合要监视的某些技术。

您还可以使用 [审核模式评估](audit-windows-defender.md) 网络保护在启用后将对组织产生怎样的影响。

## <a name="review-network-protection-events-in-the-microsoft-365-defender-portal"></a>查看网络保护门户中的Microsoft 365 Defender事件

Microsoft Defender for Endpoint 提供事件的详细报告和阻止，作为警报调查方案的 [一部分](investigate-alerts.md)。 可以在警报队列中的 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) 或通过使用高级搜寻查看[这些详细信息](advanced-hunting-overview.md)。[](review-alerts.md) 如果你使用的是审核 [模式，](audit-windows-defender.md)可以使用高级搜寻来查看网络保护设置在启用后将如何影响你的环境。

下面是高级搜寻的示例查询：

```kusto
DeviceNetworkEvents
|where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked', 'ConnectionSuccess')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>在事件查看器中查看Windows保护事件

你可以查看 Windows 事件日志，以查看网络保护阻止访问恶意 IP 或 (或审核) IP 或域时创建的事件：

1. [直接复制 XML](event-views.md)。

2. 选择“确定”。

此过程将创建一个自定义视图，该视图筛选为只显示与网络保护相关的以下事件：

<br>

****

|事件 ID|描述|
|---|---|
|5007|更改设置时的事件|
|1125|在审核模式下触发网络保护时的事件|
|1126|在阻止模式下触发网络保护时的事件|
|

## <a name="network-protection-and-the-tcp-three-way-handshake"></a>网络保护和 TCP 三向握手

使用网络保护，确定是允许还是阻止对站点的访问是在通过 [TCP/IP](/troubleshoot/windows-server/networking/three-way-handshake-via-tcpip) 完成三向握手之后。 因此，当网站被`ConnectionSuccess``NetworkConnectionEvents`网络保护阻止时，你可能会在 Microsoft 365 Defender 门户中看到 操作类型，即使网站已被实际阻止。 `NetworkConnectionEvents` 从 TCP 层而不是从网络保护报告。 三向握手完成后，网络保护将允许或阻止对站点的访问。

下面是工作原理的示例：

1. 假设用户尝试访问其设备上的网站。 该站点恰好托管在一个危险域中，应该受到网络保护阻止。  

2. 通过 TCP/IP 开始三向握手。 在操作完成之前，将 `NetworkConnectionEvents` 记录操作，其列为 `ActionType` `ConnectionSuccess`。 但是，一旦完成三向握手过程，网络保护就会阻止对站点的访问。 所有这些操作都非常快。 类似的过程Microsoft Defender SmartScreen;当三[](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)向握手完成时，即已做出确定，并阻止或允许对网站的访问。

3. 在Microsoft 365 Defender门户中，警报队列中[会列出警报](alerts-queue.md)。 该警报的详细信息包括 和 `NetworkConnectionEvents` `AlertEvents`。 可以看到网站被阻止 `NetworkConnectionEvents` ，即使你还有 ActionType 为 的项目 `ConnectionSuccess`。

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>在多Windows中运行Windows 10 企业版桌面的注意事项

由于应用程序具有多用户Windows 10 企业版，请记住以下几点：

1. 网络保护是设备范围内的一项功能，不能面向特定的用户会话。

2. Web 内容筛选策略也是设备范围的。

3. 如果需要区分用户组，请考虑创建单独的虚拟Windows池和分配。

4. 在审核模式下测试网络保护，以在推出之前评估其行为。

5. 如果您具有大量用户或大量多用户会话，请考虑调整部署大小。

### <a name="alternative-option-for-network-protection"></a>网络保护的备用选项

对于Windows 10 企业版会话 1909 及以下时间（在 Azure 上的 Windows 虚拟桌面中使用）中，可以使用以下方法启用 Microsoft Edge 的网络保护：

1. 使用 ["打开网络保护](enable-network-protection.md) "并按照说明应用策略。

2. 执行以下 PowerShell 命令： `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>网络保护疑难解答

由于网络保护运行的环境，Microsoft 可能无法检测操作系统代理设置。 在某些情况下，网络保护客户端无法访问云服务。 若要解决连接问题，具有 E5 许可证的客户应配置以下注册表项之一：

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="see-also"></a>另请参阅

- [评估网络保护](evaluate-network-protection.md) |执行一个快速方案，演示功能的工作方式以及通常会创建哪些事件。
- [启用网络保护](enable-network-protection.md) |使用组策略、PowerShell 或 MDM CSP 在网络中启用和管理网络保护。
- [在攻击中配置攻击面减少Microsoft Intune](/mem/intune/protect/endpoint-security-asr-policy)
