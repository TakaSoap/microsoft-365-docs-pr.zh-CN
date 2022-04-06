---
title: 设备发现常见问题解答
description: '查找有关设备发现常见问题解答 (常见问题解答) '
keywords: 设备发现， 发现， 被动， 主动， 网络， 可见性， 服务器， 工作站， 载入， 非托管设备
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
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 54a1b816f3d1322cab5558e5bd09d5d9b4285ae8
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664999"
---
# <a name="device-discovery-frequently-asked-questions"></a>设备发现常见问题解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- - [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

查找有关设备发现常见问题解答 (常见问题解答) 。

## <a name="what-is-basic-discovery-mode"></a>什么是基本发现模式？

此模式允许每个Microsoft Defender for Endpoint载入设备收集网络数据并发现相邻设备。 载入终结点被动地收集网络中的事件，并从中提取设备信息。 不会启动网络流量。 载入终结点只需从载入设备看到的每个网络流量中提取数据。 用于在网络中列出非托管设备的此数据。

## <a name="can-i-disable-basic-discovery"></a>是否可以禁用基本发现？

可以选择通过 ["高级功能](advanced-features.md) "页关闭设备发现。 但是，你将失去网络中非托管设备的可见性。 请注意，无论发现被关闭，SenseNDR.exe仍将在载入设备上运行。 

## <a name="what-is-standard-discovery-mode"></a>什么是标准发现模式？

在此模式下，载入到Microsoft Defender for Endpoint的终结点可以主动探测网络中观察到的设备，以使用可忽略不计的网络流量) 丰富收集的数据 (。 只有基本发现模式观察到的设备才会在标准模式下主动探测。 强烈建议使用此模式生成可靠且一致的设备清单。 如果选择禁用此模式并选择"基本发现"模式，则可能只会在网络中获得非托管终结点的有限可见性。

 标准模式还利用使用网络中的多播查询查找更多设备的常见发现协议，以及使用被动方法观察到的设备。

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>是否可以控制哪些设备执行标准发现？

可以自定义用于执行标准发现的设备列表。 可以在当前 (Windows 10或更高版本支持此功能的所有载入设备上启用标准发现，Windows服务器 2019 或更高版本设备仅) ，也可以通过指定设备标记来选择设备的子集或子集。 在这种情况下，所有其他设备将配置为仅运行基本发现。 该配置在"设备发现设置"页中可用。

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>是否可以从设备清单列表中排除非托管设备？

是的，可以应用筛选器从设备清单列表中排除非托管设备。 还可以使用 API 查询上的载入状态列筛选出非托管设备。

## <a name="which-onboarded-devices-can-perform-discovery"></a>哪些载入设备可以执行发现？

Windows 10版本 1809 或更高版本、Windows 11、Windows Server 2019 或 Windows Server 2022 上运行的载入设备可以执行发现。

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>如果我的载入设备连接到我的主网络或公共访问点，会发生什么情况？

发现引擎区分在公司网络中接收的网络事件与公司网络外部的网络事件。 通过关联所有租户客户端的网络标识符，事件将区分从专用网络和公司网络接收的事件。 例如，如果组织中的大多数设备报告它们已连接到同一网络名称，并且具有相同的默认网关和 DHCP 服务器地址，则可以假定此网络可能是公司网络。 专用网络设备不会列在清单中，也不会主动探测。

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>捕获和分析哪些协议？

默认情况下，所有在 Windows 10 版本 1809 或更高版本上运行的载入设备Windows 11，Windows服务器 2019， 或Windows服务器 2022 捕获和分析以下协议：ARP、CDP、DHCP、DHCPv6、IP (标头) 、LLDP、LLMNR、mDNS、MNDP、NBNS、SSDP、TCP (SYN 标头) 、UDP (标头) 、WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>在标准发现中使用哪些协议进行主动探测？
当设备配置为运行标准发现时，将使用以下协议探测公开的服务：ARP、 FTP、HTTP、HTTPS、ICMP、LLMNR、NBNS、RDP、SIP、SMTP、SNMP、SSH、Telnet、UPNP、WSD、SMB、NBSS、IPP、PJL、RPC、mDNS、DHCP、AFP、CrestonCIP、IphoneSync、WinRM、VNC、SLP、LDAP


## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>如何排除使用标准发现探测的目标？

如果网络上存在不应主动探测的设备，还可以定义排除项列表，以防止扫描它们。 该配置在"设备发现设置"页中可用。

> [!NOTE]
> 设备仍可能回复网络中的多播发现尝试。 这些设备将被发现，但不会主动探测。 

## <a name="can-i-exclude-devices-from-being-discovered"></a>是否可以排除设备被发现？

由于设备发现使用被动方法来发现网络中的设备，因此可以在企业网络中发现和列出与公司网络中载入设备通信的任何设备。 只能从活动探测中排除设备。

## <a name="how-frequent-is-the-active-probing"></a>活动探测的频率有多高？

当观察到设备特征的变化以确保现有信息是最新的 (通常情况下，设备在三周内探测的次数不超过一次时，将主动探测设备) 

## <a name="my-security-tool-raised-alert-on-unicastscannerps1--psscript_guidps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>我的安全工具对UnicastScanner.ps1/PSScript_{GUID}.ps1或由它发起的端口扫描活动发出了警报，我该怎么办？

活动探测脚本由 Microsoft 签名，并且是安全的。 可以将以下路径添加到排除列表： `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps1`

## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>标准发现活动探测生成的流量是多少？

主动探测可在载入设备和探测设备之间生成最多 50Kb 的流量，每次探测尝试

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>为什么设备清单中的"可以载入"设备与仪表板磁贴中的"要载入的设备"数量之间存在差异？

你可能会注意到设备清单中"可以载入"下列出的设备数、"载入到Microsoft Defender for Endpoint"安全建议和"要加入的设备"仪表板小组件之间的差异。

 安全建议和仪表板小组件适用于网络中稳定的设备;不包括临时设备、来宾设备和其他设备。 其理念是在持久设备上进行推荐，这也意味着组织的总体安全分数。

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>是否可以载入已找到的非托管设备？

是。 可以手动载入非托管设备。 网络中的非托管终结点会为网络带来漏洞和风险。 将它们载入到服务可以提高其安全可见性。

## <a name="ive-noticed-that-unmanaged-device-health-state-is-always-active-why-is-that"></a>我注意到非托管设备运行状况状态始终为"活动"，为什么会这样？

暂时，非托管设备运行状况状态将在设备清单的标准保留期内"处于活动状态"，而不考虑其实际状态。

## <a name="does-standard-discovery-look-like-malicious-network-activity"></a>标准发现是否类似于恶意网络活动？

考虑标准发现时，你可能想知道探测的影响，特别是安全工具是否可能怀疑此类活动是恶意的。 以下小节将解释为什么组织在几乎所有情况下都不应担心启用标准发现。  

### <a name="probing-is-distributed-across-all-windows-devices-on-the-network"></a>探测分布在网络上的所有Windows设备上

与恶意活动（通常会从少量遭到入侵的设备扫描整个网络）相反，Microsoft Defender for Endpoint的标准发现探测是从所有载入Windows设备启动的，使活动变得良性和非异常。 探测由云集中管理，以平衡网络中所有受支持的载入设备之间的探测尝试。  

### <a name="active-probing-generates-negligible-amount-of-extra-traffic"></a>活动探测生成可忽略不计的额外流量

非托管设备通常会在三周内进行多次探测，并生成不到 50KB 的流量。 恶意活动通常包括高重复性探测尝试，在某些情况下，数据外泄会生成大量网络流量，这些流量可以通过网络监视工具识别为异常。

### <a name="your-windows-device-already-runs-active-discovery"></a>Windows设备已运行活动发现

活动发现功能始终嵌入到Windows操作系统中，以查找附近的设备、终结点和打印机，以便更轻松地在网络中的终结点之间进行"即插即用"体验和文件共享。 类似的功能在移动设备、网络设备和清单应用程序中实现，仅举几例。  

标准发现使用相同的发现方法来标识设备，并为网络中Microsoft 365 Defender设备清单中的所有设备具有统一可见性。 例如 - 标准发现标识网络中附近的终结点的方式与Windows在网络中列出可用打印机的方式相同。 

网络安全和监视工具对网络上设备执行的此类活动漠不关心。 

### <a name="only-unmanaged-devices-are-being-probed"></a>仅探测非托管设备

已构建设备发现功能，仅用于发现和识别网络上的非托管设备。 这意味着不会探测以前发现的已载入Microsoft Defender for Endpoint设备。

### <a name="you-can-exclude-network-lures-from-active-probing"></a>可以从活动探测中排除网络诱惑

标准发现支持将设备或范围排除 (子网) 从活动探测中排除。 如果已部署网络诱惑，则可以使用设备发现设置基于 IP 地址或子网定义排除项， (一系列 IP 地址) 。 定义这些排除项将确保不会主动探测这些设备，也不会发出警报。 这些设备将仅使用被动方法发现， (类似于基本发现模式) 。
