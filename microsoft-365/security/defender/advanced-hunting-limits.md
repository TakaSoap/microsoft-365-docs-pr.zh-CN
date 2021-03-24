---
title: Microsoft 365 Defender 中的高级搜寻配额和使用参数
description: 了解使高级搜寻服务保持响应 (服务) 的各种配额和使用参数
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 19606b06ff1a1369614bab533a949bc383c90ad3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055576"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高级搜寻配额和使用参数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

为保持服务性能高且响应迅速，高级搜寻设置各种配额和使用 (也称为"服务限制") 。 这些配额和参数适用于手动和自定义检测规则 [运行的查询](custom-detection-rules.md)。 定期运行多个查询的客户应跟踪使用情况， [并应用](advanced-hunting-best-practices.md) 优化最佳做法以最大限度地减少中断。

请参阅下表以了解现有配额和使用参数。

| 配额或参数 | Size | 刷新周期 | 说明 |
|--|--|--|--|
| 数据区域 | 30 天 | 每个查询 | 每个查询都可以查找过去 30 天的数据。 |
| 结果集 | 10，000 行 | 每个查询 | 每个查询最多可返回 10，000 条记录。 |
| Timeout | 10 分钟 | 每个查询 | 每个查询最多可以运行 10 分钟。 如果未在 10 分钟内完成，则服务将显示一个错误。
| CPU 资源 | 基于租户大小 | - 每小时，然后每 15 分钟<br>- 每天午夜 12 点 | 该服务单独强制执行每日和 15 分钟配额。 对于每个配额，只要 [查询运行](advanced-hunting-errors.md) 且租户已占用已分配资源的 10% 以上，门户就会显示一个错误。 如果直到下一个每日或 15 分钟周期之后租户一直达到 100%，将阻止查询。 |

>[!NOTE] 
>一组单独的配额和参数适用于通过 API 执行的高级搜寻查询。 [阅读有关高级搜寻 API](./api-advanced-hunting.md)

## <a name="related-topics"></a>相关主题

- [高级搜寻最佳做法](advanced-hunting-best-practices.md)
- [处理高级搜寻错误](advanced-hunting-errors.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [自定义检测概述](custom-detections-overview.md)