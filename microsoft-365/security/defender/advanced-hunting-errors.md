---
title: 处理高级搜寻中用于搜索Microsoft 365 Defender
description: 了解使用高级搜寻时显示的错误
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构， kusto， 超时， 资源， 错误， 未知错误， 限制， 配额， 参数， 分配
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f3b87dc127a1cf5d19d1e310ac4b31b60f690499
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154564"
---
# <a name="handle-advanced-hunting-errors"></a>处理高级搜寻错误

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint


高级搜寻显示错误，以通知语法错误以及查询命中预定义 [配额和使用参数时](advanced-hunting-limits.md)。 有关如何解决或避免错误的提示，请参阅下表。

| 错误类型 | 原因 | 解决方案 | 错误消息示例 |
|--|--|--|--|
| 语法错误 | 查询包含无法识别的名称，包括对不存在的运算符、列、函数或表的引用。 | 确保对 [Kusto 运算符和函数的引用](/azure/data-explorer/kusto/query/) 正确无误。 检查 [架构，](advanced-hunting-schema-tables.md) 了解正确的高级搜寻列、函数和表。 将变量字符串括在引号中，以便识别它们。 编写查询时，请使用 IntelliSense 中的自动完成建议。 | `A recognition error occurred.` |
| 语义错误 | 尽管查询使用有效的运算符、列、函数或表名称，但其结构和生成的逻辑中存在错误。 在某些情况下，高级搜寻可以标识导致错误的具体运算符。 | 检查查询结构中的错误。 有关指南 [，请参阅 Kusto](/azure/data-explorer/kusto/query/) 文档。 编写查询时，请使用 IntelliSense 中的自动完成建议。 |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| 超时 | 查询只能在超时前的 [有限时段内运行](advanced-hunting-limits.md)。运行复杂查询时，此错误可能更频繁地发生。 | [优化查询](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 节流 | 同一租户中的查询已超出基于租户大小分配的 [CPU](advanced-hunting-limits.md) 资源。 | 该服务每隔 15 分钟和每天检查一次 CPU 资源使用情况，并在使用量超过分配配额的 10% 后显示警告。 如果达到了 100% 的利用率，服务会阻止查询，直到下一个每日或 15 分钟周期。 [优化查询以避免达到 CPU 配额](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 超出结果大小限制  | 查询结果集的聚合尺寸已超过最大尺寸。 如果结果集太大，以达到在 10,000 条记录的限制下截断无法将其缩减到可接受的大小时，则会发生此错误。 具有多个列且具有可缩放内容的结果更有可能受到此错误的影响。 | [优化查询](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| 资源消耗过多 | 查询消耗了过多的资源，已停止完成。 在某些情况下，高级搜寻可以识别出未优化的特定运算符。 | [优化查询](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 未知错误 | 由于未知原因，查询失败。 | 请尝试再次运行查询。 如果查询继续返回未知错误，请通过门户联系 Microsoft。 | `An unexpected error occurred during query execution. Please try again in a few minutes.`



## <a name="related-topics"></a>相关主题
- [高级搜寻最佳做法](advanced-hunting-best-practices.md)
- [配额和使用参数](advanced-hunting-limits.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [Kusto 查询语言概述](/azure/data-explorer/kusto/query/)