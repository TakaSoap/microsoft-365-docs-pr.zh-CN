---
title: 设备发现概述
description: 了解如何利用终结点发现Microsoft 365 Defender在网络中查找非托管设备
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e32880b46b04ce9ee755c09b6cbff2e3e484f4ff
ms.sourcegitcommit: 6b24f65c987e5ca06e6d5f4fc10804cdbe68b034
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2021
ms.locfileid: "61320847"
---
# <a name="device-discovery-overview"></a>设备发现概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

保护环境需要清点网络中设备。 但是，网络中映射设备的成本通常很高、具有挑战性且耗时。

Microsoft Defender for Endpoint 提供设备发现功能，可帮助你查找连接到公司网络的非托管设备，而无需额外的设备或繁琐的过程更改。 设备发现使用网络中载入的终结点收集、探测或扫描网络以发现非托管设备。 设备发现功能允许你发现：

- Enterprise尚未 (Microsoft Defender for Endpoint) 、工作站、服务器和移动设备的终结点
- 路由器和交换机等网络设备
- IoT 设备，如打印机和相机

未知和未托管的设备会为网络带来重大风险 -无论是未修补的打印机、安全配置较弱的网络设备，还是没有安全控制的服务器。 发现设备后，你可以：

- 将非托管终结点载入到服务，从而提升这些终结点的安全可见性。
- 通过识别和评估漏洞以及检测配置差距来减少攻击面。

观看此视频，快速概览设备发现方法：

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWORdQ]

结合此功能，将设备载入 Microsoft Defender for Endpoint 的安全建议作为现有威胁和漏洞管理体验的一部分提供。

## <a name="discovery-methods"></a>发现方法

你可以选择由载入的设备使用的发现模式。 该模式控制你可以为企业网络中非托管设备获取的可见性级别。

有两种可用的发现模式：

- **基本发现**：在此模式下，终结点将被动收集网络中事件并从中提取设备信息。 基本发现使用SenseNDR.exe二进制进行被动网络数据收集，并且不会启动任何网络流量。 终结点只需从载入的设备看到的每一个网络流量中提取数据。 通过基本发现，你只能有限地查看网络中非托管终结点。

- 标准发现 (推荐) ：此模式允许终结点主动查找网络中设备，以丰富收集的数据并发现更多设备 - 帮助你构建可靠且一致的设备清单。 除了使用被动方法观察到的设备之外，标准模式还利用使用网络中多播查询的常见发现协议来查找更多设备。 标准模式使用智能的活动探测来发现有关观测到的设备的其他信息，以丰富现有设备信息。 启用标准模式时，组织中网络监视工具可能会观察到由发现传感器生成的最小且可以忽略不计的网络活动。

你可以更改和自定义发现设置，有关详细信息，请参阅配置 [设备发现](configure-device-discovery.md)。

> [!IMPORTANT]
> 标准发现是自 2021 年 7 月 19 日起所有客户的默认模式。 你可以选择通过设置页将此配置更改为基本配置。 如果选择基本模式，将仅获取网络中非托管终结点的有限可见性。

> [!NOTE]
> 发现引擎区分在企业网络中接收的网络事件与企业网络外部的网络事件。 未连接到公司网络的设备不会在设备清单中发现或列出。

## <a name="device-inventory"></a>设备清点

已发现但尚未由 Microsoft Defender for Endpoint 载入并保护的设备将在"终结点"选项卡内的"设备清单"中列出。

可以在设备清单列表中使用名为"载入状态"的筛选器，该筛选器可以具有以下任何值：

- 已载入：终结点已载入到 Microsoft Defender for Endpoint。
- 可以载入：已发现网络中终结点，操作系统被标识为 Microsoft Defender for Endpoint 支持的操作系统，但当前尚未载入。 我们强烈建议载入这些设备。
- 不支持：终结点已发现在网络中，但不受 Microsoft Defender for Endpoint 支持。
- 信息不足：系统无法确定设备的可支持性。 在网络中更多设备上启用标准发现可以丰富发现的属性。

![设备清单仪表板的图像。](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> 你始终可以应用筛选器以从设备清单列表中排除非托管设备。 您还可以使用 API 查询上的载入状态列筛选出非托管设备。

## <a name="network-device-discovery"></a>网络设备发现

组织中部署大量非托管网络设备会创建较大的攻击面，并给整个企业带来重大风险。 Microsoft Defender for Endpoint 网络发现功能可帮助你确保发现网络设备、准确分类网络设备并添加到资产清单。

网络设备不作为标准终结点进行管理，因为 Defender for Endpoint 本身没有内置于网络设备中的传感器。 这些类型的设备需要无代理方法，远程扫描将获取设备的必要信息。 为此，将在每个网段上使用指定的 Microsoft Defender for Endpoint 设备，以定期对预配置的网络设备执行经过身份验证的扫描。 一旦发现，适用于终结点的 defender 危险和漏洞管理 功能将提供集成的工作流，用于保护发现的交换机、路由器、WLAN 控制器、防火墙和 VPN 网关。

有关详细信息，请参阅 [网络设备](network-devices.md)。

## <a name="device-discovery-integrations"></a>设备发现集成

为了应对获得足够的可见性以查找、标识并保护完整的 OT/IOT 资产清单这一难题，Microsoft Defender for Endpoint 现在支持以下集成：

- **Corelight：Microsoft** 已与 Corelight 合作接收来自 Corelight 网络设备的数据。 这样Microsoft 365 Defender可进一步查看非托管设备的网络活动，包括与其他非托管设备或外部网络的通信。 有关详细信息，请参阅启用 [Corelight 数据集成](corelight-integration.md)。

- **Microsoft Defender for IoT：** 此集成将适用于终结点的 Microsoft Defender 设备发现功能与 Microsoft Defender for IoT 的无代理监视功能相结合，用于保护连接到 IT 网络 (例如，Internet 语音 (VoIP) 、打印机和智能电视) 的企业 IoT 设备。 有关详细信息，请参阅启用 [Microsoft Defender for IoT 集成](enable-microsoft-defender-for-iot-integration.md)。

## <a name="vulnerability-assessment-on-discovered-devices"></a>已发现设备的漏洞评估

你的设备以及网络中发现的其他非托管设备的漏洞和风险是"安全 推荐"下当前 TVM 流的一部分，在门户的实体页面中表示。
搜索与"SSH"相关的安全建议，以查找与非托管和托管设备相关的 SSH 漏洞。

![安全建议仪表板的图像。](images/1156c82ffadd356ce329d1cf551e806c.png)

## <a name="use-advanced-hunting-on-discovered-devices"></a>在发现的设备上使用高级搜寻

可以使用高级搜寻查询了解发现的设备的可见性。
在 DeviceInfo 表中查找有关发现的终结点的详细信息，或在 DeviceNetworkInfo 表中查找有关这些设备的网络相关信息。

![高级搜寻使用的图像。](images/f48ba1779eddee9872f167453c24e5c9.png)

设备发现将适用于终结点载入设备的 Microsoft Defender 用作网络数据源，将活动属性化为未载入的设备。 这意味着，如果 Microsoft Defender for Endpoint 已载入设备与非载入设备通信，则未载入的设备上的活动可以在时间线上和通过高级搜寻 DeviceNetworkEvents 表看到。

新事件是基于连接的传输控制 (TCP) ，并且适合当前的 DeviceNetworkEvents 方案。 从启用了非 Microsoft Defender for Endpoint 的设备进入启用终结点的 Microsoft Defender 设备的 TCP。

还添加了以下操作类型：

- ConnectionAttempt - 尝试建立 TCP 连接 (同步) 
- ConnectionAcknowledged - 确认已接受 syn\ack (TCP) 

您可以尝试此示例查询：

```text
DeviceNetworkEvents
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"
| take 10
```

## <a name="changed-behavior"></a>已更改行为

以下部分列出了在启用此功能后，你将在 Microsoft Defender for <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"></a> Endpoint 和 Microsoft 365 Defender门户中观察到的更改。

1. 未载入到 Microsoft Defender for Endpoint 的设备应显示在设备清单、高级搜寻和 API 查询中。 这可能会显著增加查询结果的大小。
    1. 高级搜寻中的"DeviceInfo"和"DeviceNetworkInfo"表现在将保留发现的设备。 可以使用"OnboardingStatus"属性筛选出这些设备。
    2. 已发现的设备应显示在流式 API 查询结果中。 可以使用查询中的筛选器筛选出 `OnboardingStatus` 这些设备。
2. 非托管设备将基于定义的条件分配到现有设备组。
3. 在极少数情况下，标准发现可能会触发网络监视器或安全工具上的警报。 如果遇到此类事件，请提供反馈以帮助防止这些问题定期发生。 你可以明确排除特定目标或整个子网，不由标准发现主动探测。

## <a name="next-steps"></a>后续步骤

- [配置设备发现](configure-device-discovery.md)
- [设备发现常见问题解答](device-discovery-faq.md)
