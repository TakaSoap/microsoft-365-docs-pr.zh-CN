---
title: Microsoft 365 Defender 高级搜寻架构中的命名更改
description: 跟踪和查看高级搜寻架构中的命名更改表和列
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 数据， 命名更改， 重命名， Microsoft 威胁防护
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
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780771"
---
# <a name="advanced-hunting-schema---naming-changes"></a>高级搜寻架构 - 命名更改

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高级 [搜寻架构](advanced-hunting-schema-tables.md) 会定期更新，以添加新表和列。 在某些情况下，重命名或替换现有列名称以改进用户体验。 请参阅本文，查看可能会影响查询的命名更改。

命名更改将自动应用于保存在安全中心的查询，包括自定义检测规则使用的查询。 无需手动更新这些查询。 但是，您需要更新以下查询：
- 使用 API 运行的查询
- 保存在安全中心外部的其他地方的查询

## <a name="december-2020"></a>2020 年 12 月

| 表名 | 原始列名称 | 新列名称 | 更改原因
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | 客户反馈 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | 客户反馈 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | 客户反馈 |

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)