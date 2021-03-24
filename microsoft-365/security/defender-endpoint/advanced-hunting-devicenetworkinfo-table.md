---
title: 高级搜寻架构中的 DeviceNetworkInfo 表
description: 了解高级搜寻架构的 DeviceNetworkInfo 表中的网络配置信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， devicenetworkinfo， 设备， 设备， mac， ip， 适配器， dns， dhcp， 网关， 隧道， DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056156"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高级 `DeviceNetworkInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关设备网络配置的信息，包括网络适配器、IP 和 MAC 地址以及连接的网络或域。 使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中设备的唯一标识符 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 和 `DeviceName` `Timestamp` 列一起使用 |
| `NetworkAdapterName` | string | 网络适配器的名称 |
| `MacAddress` | string | 网络适配器的 MAC 地址 |
| `NetworkAdapterType` | string | 网络适配器类型。 有关可能的值，请参阅 [此枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true) |
| `NetworkAdapterStatus` | string | 网络适配器的运行状态。 有关可能的值，请参阅 [此枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true) |
| `TunnelType` | string | 隧道协议（如果接口用于此目的，例如 6to4、Teredo、ISATAP、PPTP、SSTP 和 SSH） |
| `ConnectedNetworks` | string | 适配器连接到的网络。 每个 JSON 数组都包含网络名称、类别 (公共、专用或域) 、说明以及指示其是否公开连接到 Internet 的标志 |
| `DnsAddresses` | string | JSON 数组格式的 DNS 服务器地址 |
| `IPv4Dhcp` | string | DHCP 服务器的 IPv4 地址 |
| `IPv6Dhcp` | string | DHCP 服务器的 IPv6 地址 |
| `DefaultGateways` | string | JSON 数组格式的默认网关地址 |
| `IPAddresses` | string | 包含分配给适配器的所有 IP 地址及其各自的子网前缀和 IP 地址空间（如公共、专用或链接本地）的 JSON 数组 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
