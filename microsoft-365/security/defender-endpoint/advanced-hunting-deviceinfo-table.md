---
title: 高级搜寻架构中的 DeviceInfo 表
description: 了解高级搜寻架构的 DeviceInfo 表中的操作系统、计算机名称和其他设备信息
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， deviceinfo， 设备， 操作系统， 平台， 用户， DeviceInfo
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
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056159"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高级 `DeviceInfo` 搜寻 [架构中的](advanced-hunting-overview.md) 表包含有关组织中设备的信息，包括其操作系统版本、活动用户和计算机名称。 使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅 [高级搜寻架构参考](advanced-hunting-schema-reference.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 记录事件的日期和时间 |
| `DeviceId` | string | 服务中设备的唯一标识符 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `ClientVersion` | string | 在设备上运行的终结点代理或传感器的版本 |
| `PublicIP` | string | 已载入设备用于连接到 Defender for Endpoint 服务的公共 IP 地址。 这可能是设备本身、NAT 设备或代理的 IP 地址 |
| `OSArchitecture` | string | 在设备上运行的操作系统的体系结构 |
| `OSPlatform` | string | 在设备上运行的操作系统的平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7 |
| `OSBuild` | string | 在设备上运行的操作系统的生成版本 |
| `IsAzureADJoined` | boolean | 指示设备是否已加入 Azure Active Directory 的布尔值指示器 |
| `LoggedOnUsers` | string | 事件时以 JSON 数组格式登录设备的所有用户列表 |
| `RegistryDeviceTag` | string | 通过注册表添加的设备标记 |
| `ReportId` | long | 基于重复计数器的事件标识符。 若要标识唯一事件，此列必须与 DeviceName 和 Timestamp 列一起使用 |
| `OSVersion` | string | 在设备上运行的操作系统的版本 |
| `MachineGroup` | string | 计算机的机器组。 基于角色的访问控制使用该组来确定对计算机的访问权限 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
