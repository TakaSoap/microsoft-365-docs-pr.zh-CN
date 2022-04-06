---
title: 设备发现概述
description: 了解如何利用Microsoft 365 Defender中的终结点发现在网络中查找非托管设备
keywords: 设备发现， 发现， 被动， 主动， 网络， 可见性， 服务器， 工作站， 载入， 非托管设备
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: siosulli
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365-initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f6046576fcea2fe961e73e88168c6254a2d95a40
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665043"
---
# <a name="device-discovery-overview"></a>设备发现概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

保护环境需要清点网络中的设备。 但是，网络中的映射设备通常成本高昂、具有挑战性和耗时。

Microsoft Defender for Endpoint提供设备发现功能，可帮助你查找连接到公司网络的非托管设备，而无需额外的设备或繁琐的进程更改。 设备发现使用网络中的载入终结点来收集、探测或扫描网络，以发现非托管设备。 使用设备发现功能可以发现：

- Enterprise终结点 (工作站、服务器和移动设备) 尚未载入到Microsoft Defender for Endpoint
- 路由器和交换机等网络设备
- 打印机和照相机等 IoT 设备

未知和非托管设备会给网络带来重大风险 - 无论是未修补的打印机、安全配置较弱的网络设备，还是没有安全控制的服务器。 发现设备后，可以：

- 将非托管终结点载入到服务，提高其安全可见性。
- 通过识别和评估漏洞并检测配置缺口来减少攻击面。

观看此视频，快速了解设备发现方式：

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWORdQ]

结合此功能，现有危险和漏洞管理体验中提供了载入设备以Microsoft Defender for Endpoint的安全建议。

## <a name="discovery-methods"></a>发现方法

可以选择载入设备要使用的发现模式。 该模式控制企业网络中非托管设备的可见性级别。

有两种可用的发现模式：

- **基本发现**：在此模式下，终结点将被动地收集网络中的事件，并从中提取设备信息。 基本发现使用SenseNDR.exe二进制文件进行被动网络数据收集，不会启动网络流量。 终结点只需从载入设备看到的每个网络流量中提取数据。 通过基本发现，你只能获得网络中非托管终结点的有限可见性。

- **标准发现** (建议) ：此模式允许终结点主动在网络中查找设备，以丰富收集的数据并发现更多设备- 帮助你构建可靠且一致的设备清单。 除了使用被动方法观察到的设备外，标准模式还利用使用网络中的多播查询查找更多设备的常见发现协议。 标准模式使用智能、主动探测来发现有关观察到的设备的其他信息，以丰富现有设备信息。 启用标准模式后，组织中的网络监视工具可能会观察到发现传感器生成的最小且可以忽略不清的网络活动。

可以更改和自定义发现设置，有关详细信息，请参阅" [配置设备发现](configure-device-discovery.md)"。

> [!IMPORTANT]
> 标准发现是从 2021 年 7 月 19 日开始的所有客户的默认模式。 可以通过"设置"页选择将此配置更改为基本配置。 如果选择基本模式，则只会在网络中获得非托管终结点的有限可见性。

> [!NOTE]
> 发现引擎区分在公司网络中接收的网络事件与公司网络外部的网络事件。 不会在设备清单中发现或列出未连接到公司网络的设备。

## <a name="device-inventory"></a>设备清单

已发现但尚未加入并受Microsoft Defender for Endpoint保护的设备将在"计算机和移动"选项卡的设备清单中列出。

若要评估这些设备，可以在设备清单列表中使用名为"载入状态"的筛选器，该筛选器可以具有以下任何值：

- 载入：终结点载入到Microsoft Defender for Endpoint。
- 可以载入：在网络中发现了终结点，操作系统被标识为受Microsoft Defender for Endpoint支持的终结点，但目前尚未载入。 强烈建议载入这些设备。
- 不支持：终结点是在网络中发现的，但Microsoft Defender for Endpoint不支持。
- 信息不足：系统无法确定设备的可支持性。 在网络中的更多设备上启用标准发现可以丰富发现的属性。

:::image type="content" source="images/2b62255cd3a9dd42f3219e437b956fb9.png" alt-text="设备清单仪表板" lightbox="images/2b62255cd3a9dd42f3219e437b956fb9.png":::

> [!TIP]
> 始终可以应用筛选器从设备清单列表中排除非托管设备。 还可以使用 API 查询上的载入状态列筛选出非托管设备。

有关详细信息，请参阅 [设备清单](machines-view-overview.md)。

## <a name="network-device-discovery"></a>网络设备发现

组织中部署的大量非托管网络设备会造成大量外围攻击，对整个企业构成重大风险。 Microsoft Defender for Endpoint网络发现功能有助于确保发现、准确分类网络设备并将其添加到资产清单中。

网络设备不会作为标准终结点进行管理，因为 Defender for Endpoint 本身没有内置的传感器。 这些类型的设备需要无代理方法，远程扫描将从设备获取必要的信息。 为此，将在每个网络段上使用指定的Microsoft Defender for Endpoint设备对预配置的网络设备执行定期身份验证扫描。 发现后，Defender for Endpoint 的危险和漏洞管理功能提供集成工作流，以保护发现的交换机、路由器、WLAN 控制器、防火墙和 VPN 网关。

有关详细信息，请参阅 [网络设备](network-devices.md)。

## <a name="device-discovery-integrations"></a>设备发现集成

若要解决获得足够的可见性来查找、识别和保护完整的 OT/IOT 资产清单这一难题，Microsoft Defender for Endpoint现在支持以下集成：

- **Corelight**：Microsoft 已与 Corelight 合作，从 Corelight 网络设备接收数据。 这Microsoft 365 Defender提高了对非托管设备网络活动的可见性，包括与其他非托管设备或外部网络的通信。 有关详细信息，请参阅 ["启用 Corelight 数据集成](corelight-integration.md)"。

- **Microsoft Defender for IoT**：此集成将Microsoft Defender for Endpoint的设备发现功能与 Microsoft Defender for IoT 的无代理监视功能相结合，以保护连接到 IT 网络 (的企业 IoT 设备，例如，通过 Internet 语音协议 (VoIP) 、打印机和智能电视) 。 有关详细信息，请参阅 [启用 Microsoft Defender for IoT 集成](enable-microsoft-defender-for-iot-integration.md)。

## <a name="vulnerability-assessment-on-discovered-devices"></a>发现设备上的漏洞评估

设备上的漏洞和风险以及网络中发现的其他非托管设备是当前 TVM 流的一部分，在"安全推荐"下，在门户的实体页中表示。
搜索"SSH"相关安全建议，查找与非托管和托管设备相关的 SSH 漏洞。

:::image type="content" source="images/1156c82ffadd356ce329d1cf551e806c.png" alt-text="安全建议仪表板" lightbox="images/1156c82ffadd356ce329d1cf551e806c.png":::


## <a name="use-advanced-hunting-on-discovered-devices"></a>在发现的设备上使用高级搜寻

可以使用高级搜寻查询在发现的设备上获得可见性。
在 DeviceInfo 表中查找有关发现的终结点的详细信息，或与 DeviceNetworkInfo 表中的这些设备相关的网络相关信息。

:::image type="content" source="images/f48ba1779eddee9872f167453c24e5c9.png" alt-text="可在其中使用查询的高级搜寻页" lightbox="images/f48ba1779eddee9872f167453c24e5c9.png":::

设备发现利用Microsoft Defender for Endpoint载入设备作为网络数据源，将活动属性为非载入设备。 这意味着，如果Microsoft Defender for Endpoint载入设备与非载入设备通信，则可以在时间线和高级搜寻 DeviceNetworkEvents 表中查看非载入设备上的活动。

新事件是基于连接 (TCP 的传输控制协议) ，适合当前的 DeviceNetworkEvents 方案。 TCP 从未启用的Microsoft Defender for Endpoint流入已启用Microsoft Defender for Endpoint设备。

还添加了以下操作类型：

- ConnectionAttempt - 尝试建立 TCP 连接 (同步) 
- ConnectionAcknowleded - 确认已接受 TCP 连接 (syn\ack) 

可以尝试此示例查询：

```text
DeviceNetworkEvents
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"
| take 10
```

## <a name="next-steps"></a>后续步骤

- [配置设备发现](configure-device-discovery.md)
- [设备发现常见问题解答](device-discovery-faq.md)
