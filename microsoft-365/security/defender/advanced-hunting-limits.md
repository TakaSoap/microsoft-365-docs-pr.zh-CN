---
title: 搜索中的高级搜寻配额和使用Microsoft 365 Defender
description: 了解各种配额和使用参数 (服务) 使高级搜寻服务保持响应
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构， kusto， CPU 限制， 查询限制， 资源， 最大结果， 配额， 参数， 分配
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
ms.openlocfilehash: fe0ad42ac0ebfc7f6816e412ab6ffb0ac9291b44
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60643155"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高级搜寻配额和使用参数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

为保持服务性能高且响应迅速，高级搜寻设置各种配额和使用 (也称为"服务限制") 。 这些配额和参数分别应用于手动运行的查询和使用自定义检测规则 [运行的查询](custom-detection-rules.md)。 定期运行多个查询的客户应注意这些限制，并 [应用](advanced-hunting-best-practices.md) 优化最佳做法以最大限度地减少中断。

请参阅下表以了解现有配额和使用参数。

| Quota 或参数 | Size | 刷新周期 | 说明 |
|--|--|--|--|
| 日期范围 | 30 天 | 每个查询 | 每个查询可以查找过去 30 天内的数据。 |
| 结果集 | 10,000 行 | 每个查询 | 每个查询最多可以返回 10,000 条记录。 |
| Timeout | 10 分钟 | 每个查询 | 每个查询最多可以运行 10 分钟。 如果未在 10 分钟内完成，则服务将显示一个错误。
| CPU 资源 | 基于租户大小 | 每 15 分钟 | 只要 [查询运行且租户已占用](advanced-hunting-errors.md) 已分配资源的 10% 以上，门户就会显示错误。 如果租户已达到 100%，查询将受到阻止，直到下一个 15 分钟周期。 |

>[!NOTE] 
>一组单独的配额和参数适用于通过 API 执行的高级搜寻查询。 [阅读有关高级搜寻 API](./api-advanced-hunting.md)

## <a name="related-topics"></a>相关主题

- [高级搜寻最佳做法](advanced-hunting-best-practices.md)
- [处理高级搜寻错误](advanced-hunting-errors.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [自定义检测概述](custom-detections-overview.md)