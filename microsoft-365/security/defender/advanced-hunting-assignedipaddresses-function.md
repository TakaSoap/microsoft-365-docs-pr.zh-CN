---
title: 高级搜寻中的 AssignedIPAddresses () 函数Microsoft 365 Defender
description: 了解如何使用 AssignedIPAddresses () 函数获取分配给设备的最新 IP 地址
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， FileProfile， 文件配置文件， 函数， 扩充
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c60f9ff0b302948d5fd2d8c450e33a12768e8db0
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60665523"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

使用 `AssignedIPAddresses()` 高级搜寻 [查询中的](advanced-hunting-overview.md) 函数可快速获取已分配给设备的最新 IP 地址。 如果指定时间戳参数，此函数将获取指定时间的最新 IP 地址。 

此函数返回具有以下列的表：

| 列 | 数据类型 | 说明 |
|------------|-------------|-------------|
| `Timestamp` | datetime | 使用 IP 地址观测到设备的最新时间 |
| `IPAddress` | string | 设备使用的 IP 地址 |
| `IPType` | string | 指示 IP 地址是公用地址还是专用地址 |
| `NetworkAdapterType` | int | 已分配 IP 地址的设备使用的网络适配器类型。 有关可能的值，请参阅 [此枚举](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | 具有分配 IP 地址的适配器所连接至的网络。 每个 JSON 数组都包含网络名称、类别 (公共、专用或域) 、说明以及指示其是否公开连接到 Internet 的标志 |

## <a name="syntax"></a>语法

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>参数

- **x** `DeviceId` — `DeviceName` 或用于标识设备的值
- **y**— (datetime) 指示函数从特定时间获取最新分配的 `Timestamp` IP 地址的值。 如果未指定，函数将返回最新的 IP 地址。

## <a name="examples"></a>示例

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>获取设备 24 小时之前使用的 IP 地址列表

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>获取设备使用的 IP 地址并查找与设备通信的设备
此查询使用 函数获取特定日期或 () 或之前为设备分配的 `AssignedIPAddresses()` IP `example-device-name` `example-date` () 。 然后，它使用 IP 地址查找与其他设备启动的设备的连接。 

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