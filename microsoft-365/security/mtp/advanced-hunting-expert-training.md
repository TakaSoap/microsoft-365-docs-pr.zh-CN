---
title: 获取高级搜寻方面的专家培训
description: 高级搜寻专家的免费培训和指导
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 语言， 培训， 方案， 基本到高级， 视频， 分步执行
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
ms.openlocfilehash: aba0a6ab2c82c038eda8e66890c0c95303dea947
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053831"
---
# <a name="get-expert-training-on-advanced-hunting"></a>获取高级搜寻方面的专家培训

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

通过跟踪攻击者（针对新安全分析师和经验丰富的威胁情报人员的网络广播系列）快速提升你的高级搜寻知识。 本系列将指导你完成基本信息，以创建您自己的复杂查询。 从关于基础功能的第一个视频开始，或跳转到适合你的体验级别的更高级视频。


| 标题 | 说明 | Watch | 查询 | 
|--|--|--|--|
| 第 1 集：KQL 基础知识 | 此部分介绍 Microsoft 365 Defender 中高级搜寻的基础知识。 了解可用的高级搜寻数据和基本 KQL 语法和运算符。 | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54：14)  | [CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| 第 2 集：加入 | 继续了解高级搜寻中的数据以及如何将表联接在一起。 了解 `inner` 、 `outer` `unique` 和联接，并了解默认 `semi` Kusto 联接的 `innerunique` 细微差别。 | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53：33)  | [CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| 第 3 部分：汇总、透视和可视化数据 | 现在，你已经了解了筛选、操作和联接数据，是时候汇总、量化、透视和可视化了。 此部分讨论了 `summarize` 运算符和各种计算，同时在架构中引入了其他表。 你还将学习如何将数据集转换为图表，以帮助你提取见解。 | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48：52)  | [CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| 第 4 集：让我们进行搜寻！ 将 KQL 应用于事件跟踪 | 在此集中，你将了解如何跟踪一些攻击者活动。 我们使用改进的 Kusto 和高级搜寻功能跟踪攻击。 了解现场使用的实际技巧，包括网络安全的 APC 以及如何将它们应用于事件响应。 | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59：36)  | [CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


通过 *L33TSP3AK 获取更多专家培训：Microsoft 365 Defender* 中的高级搜寻，这是一个 Web 广播系列，供希望扩展他们在 Microsoft 365 Defender 中使用高级搜寻执行安全调查的技术知识和实践技能的分析师。 

| 标题 | 说明 | Watch | 查询 | 
|--|--|--|--|
| 第 1 集  | 在此集中，你将了解运行高级搜寻查询的不同最佳做法。 涵盖的主题包括：如何优化查询、对勒索软件使用高级搜寻、将 JSON 作为动态类型处理，以及如何使用外部数据运算符。 | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56：34)  | [CSL 文件](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>如何使用 CSL 文件
在启动剧集之前，访问 GitHub 上的相应 [Kusto CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) 文件，将其内容复制到高级搜寻查询编辑器。 在观看剧集时，可以使用复制的内容关注扬声器并运行查询。 

下面摘自 CSL 文件，其中显示了一组标记为注释的综合指南 `//` 。

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

同一 CSL 文件在注释之前和之后包括查询，如下所示。 若要在编辑器中使用多个查询 [](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)运行特定查询，请移动光标到该查询，然后选择"**运行查询"。**   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
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
