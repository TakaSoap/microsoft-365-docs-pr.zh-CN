---
title: 处理高级搜寻 for Microsoft 威胁防护中的错误
description: 了解使用高级搜寻时显示的错误
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构、kusto、超时、资源、错误、未知错误
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 20133e0f5dda3abc583adf66cc20a1d8fde190cf
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197997"
---
# <a name="handle-advanced-hunting-errors"></a>处理高级搜寻错误

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


高级搜索显示错误，以通知有语法错误，并在查询命中 [预定义限制](advanced-hunting-limits.md)时发出通知。 有关如何解决或避免错误的提示，请参阅下表。 

| 错误类型 | 原因 | 解决方案 | 错误消息示例 |
|--|--|--|--|
| 语法错误 | 查询包含不可识别的名称，包括对不存在的运算符、列、函数或表的引用。 | 确保对 [Kusto 运算符和函数](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 的引用正确无误。 检查 [架构](advanced-hunting-schema-tables.md) 中是否有正确的高级搜寻列、函数和表。 将变量字符串括在引号中，以供识别。 编写查询时，请使用 IntelliSense 中的 "自动完成" 建议。 | `A recognition error occurred.` |
| 语义错误 | 虽然查询使用有效的运算符、列、函数或表名称，但在其结构和生成的逻辑中存在错误。 在某些情况下，高级搜寻会识别导致错误的特定运算符。 | 检查查询结构中是否存在错误。 有关指南，请参阅 [Kusto 文档](https://docs.microsoft.com/azure/data-explorer/kusto/query/) 。 编写查询时，请使用 IntelliSense 中的 "自动完成" 建议。 |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| 时时 | 查询只能在 [有限的时间段](advanced-hunting-limits.md)内运行，然后超时。在运行复杂查询时，可能会更频繁地发生此错误。 | [优化查询](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 限制 | 同一个租户中的查询已超过根据租户大小分配的 [CPU 资源](advanced-hunting-limits.md) 。 | 该服务每隔15分钟检查一次 CPU 资源使用情况，并在使用率超过分配的限制的10% 时显示警告。 如果达到100% 的使用率，服务将在下一天或15分钟周期结束之前阻止查询。 [优化查询以避免命中 CPU 限制](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 超出结果大小限制  | 查询的结果集的聚合大小已超出最大限制。 如果结果集太大而导致在 10000-记录限制处截断不能将其减小到可接受的大小，则会发生此错误。 具有可调内容的多个列的结果更有可能受到此错误的影响。 | [优化查询](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| 资源消耗过多 | 查询消耗了过多的资源，并且已停止完成。 在某些情况下，高级搜寻会识别未优化的特定操作员。 | [优化查询](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 未知错误 | 由于未知原因，查询失败。 | 请尝试再次运行查询。 如果查询继续返回未知错误，请与 Microsoft 通过门户联系。 | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>相关主题
- [高级的求职最佳实践](advanced-hunting-best-practices.md)
- [服务限制](advanced-hunting-limits.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [Kusto 查询语言概述](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
