---
title: Microsoft 365 Defender 中的高级搜寻配额和使用参数
description: 了解用于保持高级搜寻 (响应) 服务限制的各种配额和使用参数
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构， kusto， CPU 限制， 查询限制， 资源， 最大结果， 配额， 参数， 分配
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929786"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高级搜寻配额和使用参数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

为保持服务性能高且响应迅速，高级搜寻设置各种配额和使用 (也称为"服务限制") 。 这些配额和参数适用于手动运行的查询和自定义 [检测规则](custom-detection-rules.md)。 定期运行多个查询的客户应跟踪使用情况，并 [应用优化](advanced-hunting-best-practices.md) 最佳实践以最大限度地减少中断。

请参阅下表以了解现有配额和使用参数。

| 配额或参数 | Size | 刷新周期 | 说明 |
|--|--|--|--|
| 数据区域 | 30 天 | 每个查询 | 每个查询都可以查找过去 30 天内的数据。 |
| 结果集 | 10，000 行 | 每个查询 | 每个查询最多可返回 10，000 条记录。 |
| Timeout | 10 分钟 | 每个查询 | 每个查询最多可以运行 10 分钟。 如果在 10 分钟内未完成，则服务将显示一个错误。
| CPU 资源 | 基于租户大小 | - 每小时，然后每 15 分钟<br>- 每日午夜 12 点 | 该服务单独强制执行每日和 15 分钟配额。 对于每个配额，只要查询 [运行](advanced-hunting-errors.md) 且租户已占用已分配资源的 10% 以上，门户就会显示一个错误。 如果租户达到 100%，直到下一个每日或 15 分钟周期之后，查询将被阻止。 |

>[!NOTE] 
>一组单独的配额和参数适用于通过 API 执行的高级搜寻查询。 [阅读有关高级搜寻 API](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>相关主题

- [高级搜寻最佳做法](advanced-hunting-best-practices.md)
- [处理高级搜寻错误](advanced-hunting-errors.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [自定义检测概述](custom-detections-overview.md)