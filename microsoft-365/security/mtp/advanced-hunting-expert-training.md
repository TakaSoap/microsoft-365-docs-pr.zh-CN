---
title: 获取高级搜寻方面的专家培训
description: 来自高级搜寻专家的免费培训和指导
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、语言、培训、方案、基本到高级、视频、分步
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
ms.openlocfilehash: 4e63badee2ca031bdd3ea7682396353d1658981b
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430405"
---
# <a name="get-expert-training-on-advanced-hunting"></a>获取高级搜寻方面的专家培训

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

通过 _跟踪入侵_者、新安全分析员和经验丰富的威胁 hunters 的网络广播系列，快速提高您对高级搜寻的掌握程度。 该系列将指导您完成创建自己的复杂查询的基本方法。 先从第一个视频开始，再跳转到符合你的体验级别的更高级视频。


| 标题 | 说明 | Watch | Queries | 
|--|--|--|--|
| 剧集1： KQL 基础知识 | 这一部分涵盖了 Microsoft 威胁防护中的高级求职的基础知识。 了解可用的高级搜寻数据和基本 KQL 语法和运算符。 | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14)  | [CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| 剧集2：联接 | 继续了解高级搜寻中的数据以及如何将表格联接在一起。 了解 `inner` 、 `outer` 、 `unique` 和 `semi` 联接，并了解默认 Kusto 联接的细微差别 `innerunique` 。 | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33)  | [CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| 剧集3：汇总、透视和可视化数据 | 现在，您已经了解了如何筛选、处理和联接数据，现在可以汇总、量化、透视和可视化。 此集中讨论了 `summarize` 运算符和各种计算，同时还介绍了架构中的其他表。 您还将了解如何将数据集转换为可帮助您提取洞察力的图表。 | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52)  | [CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| 剧集4：让我们来寻找！ 将 KQL 应用于事件跟踪 | 在此部分中，你将了解到跟踪某些攻击者的活动。 我们利用我们对 Kusto 和高级搜寻的改进了解来跟踪攻击。 了解字段中使用的实际窍门，包括 cybersecurity 的 ABCs 以及如何将其应用到事件响应。 | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36)  | [CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>如何使用 CSL 文件
在开始剧集之前，请访问 [GitHub 上相应的 KUSTO CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) ，并将其内容复制到高级搜寻查询编辑器。 在观看剧集时，可以使用复制的内容遵循演讲者和运行查询。 

以下来自 CSL 文件的摘要显示了一组标记为注释的综合指南 `//` 。

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

同一个 CSL 文件包含注释之前和之后的查询，如下所示。 若要 [在编辑器中运行包含多个查询](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)的特定查询，请将光标移动到该查询，然后选择 " **运行查询**"。   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解高级搜寻查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
