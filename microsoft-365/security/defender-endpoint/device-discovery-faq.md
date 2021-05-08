---
title: 设备发现常见问题
description: 查找有关设备发现的常见问题 (常见问题) 常见问题解答
keywords: 设备发现， 发现， 被动， 主动， 网络， 可见性， 服务器， 工作站， 载入， 非托管设备
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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c61e69b5c8d414ab229fa8bf64eb657a6e40304
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245956"
---
# <a name="device-discovery-frequently-asked-questions"></a>设备发现常见问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

查找有关设备发现的常见问题 (常见问题) 常见问题解答。

## <a name="what-is-basic-discovery-mode"></a>什么是基本发现模式？
此模式允许每个 Microsoft Defender for Endpoint 载入设备收集网络数据并发现相邻设备。 已载入的终结点被动收集网络中事件并从中提取设备信息。 不会启动任何网络流量。 载入的终结点只需从已载入设备看到的每一个网络流量中提取数据。 此数据用于列出网络中非托管设备。

## <a name="can-i-disable-basic-discovery"></a>能否禁用基本发现？
可以选择通过"高级功能"页关闭 [设备](advanced-features.md) 发现。 但是，你将丢失网络中非托管设备的可见性。 

## <a name="what-is-standard-discovery-mode"></a>什么是标准发现模式？
 在此模式下，载入到 Microsoft Defender for Endpoint 的终结点可以主动探测网络中观察到的设备，以丰富收集的数据 (网络流量可以忽略不计) 。 强烈建议使用此模式生成可靠且一致的设备清单。 如果选择禁用此模式，并选择"基本发现模式"，可能只会获得网络中非托管终结点的有限可见性。

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>我能否控制哪些设备执行标准发现？
 你可以自定义用于执行标准发现的设备列表。 你可以在所有也支持此功能的已载入设备上启用标准发现 (当前仅 Windows 10 设备) 或者通过指定设备的设备标记选择一部分或部分设备。 在这种情况下，所有其他设备将配置为仅运行基本发现。 配置在设备发现设置页中提供。

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>能否从设备清单列表中排除非托管设备？
是，你可以应用筛选器，从设备清单列表中排除非托管设备。 您还可以使用 API 查询上的载入状态列筛选出非托管设备。 


## <a name="which-onboarded-devices-can-perform-discovery"></a>哪些载入的设备可以执行发现？
 在版本 1809 或Windows 10上运行的已载入设备可以执行发现。

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>如果我的已载入设备连接到我的家庭网络或公共访问点，会发生什么情况？
 发现引擎区分在企业网络中接收的网络事件与企业网络外部的网络事件。 通过在所有租户的客户端之间关联网络标识符，可以区分从专用网络和企业网络接收的事件。 例如，如果网络中的大多数设备报告它们连接到了相同的网络名称，并且具有相同的默认网关和 DHCP 服务器地址，则假定此网络可能是企业网络。 专用网络设备不会在清单中列出，并且不会主动探测器。

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>要捕获和分析哪些协议？
 默认情况下， 在 Windows 10 版本 1809 或更高版本上运行的所有已载入设备正在捕获和分析以下协议：ARP、CDP、DHCP、DHCPv6、IP (标头) 、LLDP、LLMNR、mDNS、MNDP、NBNS、SSDP、TCP (标头) 、UDP (标头) 、WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>在标准发现中，使用哪些协议进行主动探测？
 当设备配置为运行标准发现时，会使用下列协议对公开的服务进行探测：ARP、FTP、HTTP、ICMP、LLMNR、NBNS、RDP、SIP、SMTP、SNMP、SSH、Telnet、UPNP、WSD、SMB、NBSS、IPP、PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>如何排除使用标准发现对目标进行探测？
 如果网络上有些设备不应主动探测器，则还可以定义排除项列表以防止它们被扫描。 配置在设备发现设置页中提供。

## <a name="can-i-exclude-devices-from-being-discovered"></a>能否排除发现的设备？
 由于设备发现使用被动方法发现网络中设备，因此可以发现与企业网络中已载入设备通信的任何设备，并列在清单中。 只能将设备排除在活动探测中。

## <a name="how-frequent-is-the-active-probing"></a>活动探测频率如何？
 当每 1 到 3 周 (观察设备特征更改时) 将主动探测设备，以确保现有信息是最新的。

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>我的安全工具引发了UnicastScanner.ps1启动的扫描活动或端口扫描活动的警报，我应该做什么？
 活动的探测脚本由 Microsoft 签名，并且是安全的。 你可以将以下路径添加到排除列表： `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>标准发现活动探测器生成的流量量是什么？
 每次探测尝试，活动探测在已载入设备和探测器设备之间可生成多达 5K 的流量

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>为什么设备清单中的"可载入"设备与仪表板磁贴中的"可载入"设备数存在差异？
你可能会注意到，在设备清单、"载入到 Microsoft Defender for Endpoint"安全建议和"载入设备"仪表板小组件中"可以载入"下列出的设备数量之间存在差异。

 安全建议和仪表板小部件适用于网络中稳定的设备;不包括临时设备、来宾设备和其他。 该想法是在持久性设备上推荐，这也意味着组织的总体安全分数。

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>我能否载入找到的非托管设备？
 对。 网络中非托管终结点会为网络带来漏洞和风险。 将它们载入服务可提升对它们的安全可见性。 


