---
title: 高级搜寻中的 DeviceFromIP () Microsoft 365 Defender
description: 了解如何使用 DeviceFromIP () 函数获取已分配特定 IP 地址的设备
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 设备， devicefromIP， 函数， 扩充
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
ms.openlocfilehash: c2482c83eef315c390e2748e371ddf26dcb3c012
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60705347"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


使用高级搜寻查询中的 函数可快速获取给定时间点已分配给特定 IP 地址 `DeviceFromIP()` 的设备列表。 [](advanced-hunting-overview.md) 

此函数返回具有以下列的表：

| 列 | 数据类型 | 说明 |
|------------|-------------|-------------|
| `IP` | string | IP 地址  |
| `DeviceId` | string | 服务中设备的唯一标识符 |


## <a name="syntax"></a>语法

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>参数

此函数作为查询的一部分调用。

- **x**— 第一个参数通常已是查询中的一列。 在这种情况下，它是名为 的列 ，您希望查看已分配给它的设备列表的 `IP` IP 地址。 它应该是本地 IP 地址。 不支持外部 IP 地址。
- **y**— 第二个可选参数是 ，它指示函数从特定时间获取最新 `Timestamp` 分配的设备。 如果未指定，函数将返回最新可用记录。

## <a name="example"></a>示例


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>获取已分配特定 IP 地址的最新设备

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-tables.md)
