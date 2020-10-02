---
title: 'Microsoft 威胁防护中的 AssignedIPAddresses ( # A1 函数在高级搜寻中'
description: '了解如何使用 AssignedIPAddresses ( # A1 函数来获取分配给设备的最新 IP 地址'
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、FileProfile、文件配置文件、函数、扩充
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ea6b65e5e6d676c5efb2622193197bae5b9ba1b2
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338541"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

使用 `AssignedIPAddresses()` [高级搜寻](advanced-hunting-overview.md) 查询中的功能快速获取已分配给设备的最新 IP 地址。 如果指定时间戳参数，此函数将获取指定时间的最新 IP 地址。 

此函数返回具有以下列的表：

| 列 | 数据类型 | 说明 |
|------------|-------------|-------------|
| `Timestamp` | datetime | 使用 IP 地址观察到设备的最晚时间 |
| `IPAddress` | string | 设备使用的 IP 地址 |
| `IPType` | string | 指示 IP 地址是否为公用地址或专用地址 |
| `NetworkAdapterType` | int | 已为其分配 IP 地址的设备使用的网络适配器类型。 有关可能的值，请参阅 [this 枚举](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | 与分配的 IP 地址的适配器连接的网络。 每个 JSON 数组包含网络名称、类别 (公用、专用或域) 、说明以及指示是否已将其公开连接到 internet 的标志 |

## <a name="syntax"></a>语法

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>参数

- **x**— `DeviceId` 或 `DeviceName` 标识设备的值
- **y**— `Timestamp` (datetime) 值指示函数获取特定时间的最近分配的 IP 地址。 如果未指定，则该函数将返回最新的 IP 地址。

## <a name="examples"></a>示例

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>获取设备24小时前使用的 IP 地址的列表

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>获取设备使用的 IP 地址并查找与之通信的设备
此查询使用 `AssignedIPAddresses()` 函数来获取设备 (`example-device-name`) 在特定日期 () 之前或之前的已分配 IP 地址 `example-date` 。 然后，它使用 IP 地址查找与其他设备启动的设备的连接。 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-tables.md)
