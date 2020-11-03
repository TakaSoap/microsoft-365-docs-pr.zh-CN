---
title: 高级搜寻架构中的 DeviceInfo 表
description: 了解高级搜寻架构的 DeviceInfo 表中的操作系统、计算机名称和其他计算机信息
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、machineinfo、DeviceInfo、设备、计算机、OS、平台、用户
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 1bb48b4332bc9d60de15bb513f04a503d6a6913b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842710"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender



`DeviceInfo`[高级搜寻](advanced-hunting-overview.md)架构中的表包含有关组织中的计算机的信息，包括 OS 版本、活动用户和计算机名称。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `ClientVersion` | string | 在计算机上运行的终结点代理或传感器的版本 |
| `PublicIP` | string | 载入计算机用于连接到 Microsoft Defender for Endpoint service 的公共 IP 地址。 这可以是计算机本身、NAT 设备或代理的 IP 地址 |
| `OSArchitecture` | string | 计算机上运行的操作系统的体系结构 |
| `OSPlatform` | string | 计算机上运行的操作系统平台。 这表示特定操作系统，包括同一系列内的变体，如 Windows 10 和 Windows 7 |
| `OSBuild` | string | 计算机上运行的操作系统的内部版本版本 |
| `IsAzureADJoined` | boolean | 指示是否已将计算机加入 Azure Active Directory 的布尔指示符 |
| `LoggedOnUsers` | string | 在事件采用 JSON 数组格式时，在计算机上登录的所有用户的列表 |
| `RegistryDeviceTag` | string | 通过注册表添加的计算机标记 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和时间戳列结合使用 |
| `OSVersion` | string | 计算机上运行的操作系统版本 |
| `MachineGroup` | string | 计算机的计算机组。 此组由基于角色的访问控制用于确定对计算机的访问权限 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
