---
title: Microsoft 威胁防护中的高级搜寻限制
description: 了解保持高级搜寻服务响应性的各种服务限制
keywords: 高级搜索、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构、kusto、CPU 限制、查询限制、资源和最大结果
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
ms.openlocfilehash: aaba01f5970c9abf55f5fae760d1ba1fed8ba914
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199873"
---
# <a name="advanced-hunting-service-limits"></a>高级搜寻服务限制

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

为保持服务的性能和响应能力，高级搜寻设置了对查询手动运行和 [自定义检测规则](custom-detection-rules.md)的各种限制。 若要了解这些限制，请参阅下表。

| 限制 | Size | 刷新周期 | 说明 |
|--|--|--|--|
| 数据区域 | 30 天 | 每个查询 | 每个查询最长可查找过去30天的数据。 |
| 结果集 | 10000行 | 每个查询 | 每个查询最长可返回10000条记录。 |
| Timeout | 10 分钟 | 每个查询 | 每个查询最长可运行10分钟。 如果未在10分钟内完成，则服务将显示一个错误。
| CPU 资源 | 基于租户大小 | -在每小时，然后每15分钟<br>-每日午夜12点 | 该服务分别强制实施每日和15分钟的限制。 对于每个限制，无论何时运行查询以及租户使用了10% 以上的已分配资源， [门户都会显示错误](advanced-hunting-errors.md) 。 如果租户在下一天或15分钟周期中已达到100%，则会阻止查询。 |

>[!NOTE] 
>一组单独的限制适用于通过 API 执行的高级搜索查询。 [阅读有关高级搜寻 Api 的信息](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

定期运行多个查询的客户应跟踪消耗量并 [应用优化最佳实践](advanced-hunting-best-practices.md) ，以最大限度地减少超出这些限制导致的中断。

## <a name="related-topics"></a>相关主题

- [高级的求职最佳实践](advanced-hunting-best-practices.md)
- [处理高级搜寻错误](advanced-hunting-errors.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [自定义检测概述](custom-detections-overview.md)
