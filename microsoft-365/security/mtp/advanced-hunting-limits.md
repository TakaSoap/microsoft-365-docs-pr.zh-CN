---
title: Microsoft 365 Defender 中的高级搜寻配额和使用参数
description: '了解 (服务限制的各种配额和使用参数，以确保高级搜寻服务响应速度) '
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构、kusto、CPU 限制、查询限制、资源、最大结果、配额、参数、分配
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
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847364"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高级搜寻配额和使用参数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

为了保持服务的性能和响应能力，高级搜寻设置各种配额和使用参数 (也称为 "服务限制" ) 。 这些配额和参数适用于手动运行的查询和 [自定义检测规则](custom-detection-rules.md)。 定期运行多个查询的客户应跟踪消耗量并 [应用优化最佳实践](advanced-hunting-best-practices.md) 以最大限度地减少中断。

请参阅下表，了解现有的配额和使用参数。

| 配额或参数 | Size | 刷新周期 | 说明 |
|--|--|--|--|
| 数据区域 | 30 天 | 每个查询 | 每个查询最长可查找过去30天的数据。 |
| 结果集 | 10000行 | 每个查询 | 每个查询最长可返回10000条记录。 |
| Timeout | 10 分钟 | 每个查询 | 每个查询最长可运行10分钟。 如果未在10分钟内完成，则服务将显示一个错误。
| CPU 资源 | 基于租户大小 | -在每小时，然后每15分钟<br>-每日午夜12点 | 该服务分别强制实施每日和15分钟的配额。 对于每个配额，只要查询运行且租户已消耗10% 以上的已分配资源，门户就会 [显示错误](advanced-hunting-errors.md) 。 如果租户在下一天或15分钟周期中已达到100%，则会阻止查询。 |

>[!NOTE] 
>一组单独的配额和参数适用于通过 API 执行的高级搜寻查询。 [阅读有关高级搜寻 Api 的信息](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>相关主题

- [高级的求职最佳实践](advanced-hunting-best-practices.md)
- [处理高级搜寻错误](advanced-hunting-errors.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [自定义检测概述](custom-detections-overview.md)