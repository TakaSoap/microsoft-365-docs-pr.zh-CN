---
title: Microsoft Defender ATP 中的高级搜寻限制
description: 了解使高级搜寻服务保持响应的各种服务限制
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp， 搜索， 查询， 遥测， 架构， kusto， CPU 限制， 查询限制， 资源， 最大结果
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499525"
---
# <a name="advanced-hunting-service-limits"></a>高级搜寻服务限制

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

为保持服务的可执行性和响应性，高级搜寻为手动和自定义检测规则运行的查询 [设置各种限制](custom-detection-rules.md)。 请参阅下表以了解这些限制。

| 限制 | Size | 刷新周期 | 说明 |
|--|--|--|--|
| 数据区域 | 30 天 | 每个查询 | 每个查询都可以查找过去 30 天的数据。 |
| 结果集 | 10，000 行 | 每个查询 | 每个查询最多可返回 10，000 条记录。 |
| Timeout | 10 分钟 | 每个查询 | 每个查询最多可以运行 10 分钟。 如果未在 10 分钟内完成，则服务将显示一个错误。
| CPU 资源 | 基于租户大小 | - 每小时，然后每 15 分钟<br>- 每天午夜 12 点 | 该服务单独强制执行每日和 15 分钟的限制。 对于每个限制，只要 [查询运行](advanced-hunting-errors.md) 且租户已占用已分配资源的 10% 以上，门户就会显示一个错误。 如果直到下一个每日或 15 分钟周期之后租户一直达到 100%，将阻止查询。 |

>[!NOTE] 
>一组单独的限制适用于通过 API 执行的高级搜寻查询。 [阅读有关高级搜寻 API](run-advanced-query-api.md)

定期运行多个查询的客户应跟踪消耗情况，并应用[](advanced-hunting-best-practices.md)优化最佳做法，以最大限度地减少超出这些限制造成的中断。

## <a name="related-topics"></a>相关主题

- [高级搜寻最佳做法](advanced-hunting-best-practices.md)
- [处理高级搜寻错误](advanced-hunting-errors.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [自定义检测规则](custom-detection-rules.md)
