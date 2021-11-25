---
title: Microsoft Defender for Endpoint 中的高级搜寻概述
description: 使用 Microsoft Defender for Endpoint 中的威胁搜寻功能生成查找网络中的威胁和弱点的查询
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， 适用于终结点的 microsoft defender， wdatp， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， 时区， UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2e1b6a5bb77dc757861a5d7f56d8a4380c6fc6c1
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168830"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>使用高级搜寻主动搜寻威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhunting-abovefoldlink)。

高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。 你可以主动检查网络中的事件来找到威胁指示器和实体。 通过灵活的数据访问，可以不受限制地搜寻已知威胁和潜在威胁。

观看此视频，快速概览高级搜寻，以及快速入门的简短教程。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqo]

你可以使用相同的威胁搜寻查询来构建自定义检测规则。 这些规则将自动运行，以检查并响应可疑的泄露活动、错误配置的计算机和其他发现。

> [!TIP]
> 使用[Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview)中的高级搜寻，使用 Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps 和 Microsoft Defender for Identity 数据搜寻威胁。 [打开"Microsoft 365 Defender"。](/microsoft-365/security/defender/m365d-enable)

若要详细了解如何将高级搜寻工作流从 Microsoft Defender for Endpoint 移动到 Microsoft 365 Defender从 Microsoft Defender for Endpoint 迁移高级[搜寻查询](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)。

## <a name="get-started-with-advanced-hunting"></a>高级搜寻入门

执行以下步骤以提升高级搜寻知识。

我们建议执行几个步骤来通过高级搜寻快速启动并运行。

<br>

****

|学习目标|说明|资源|
|---|---|---|
|**了解语言**|高级搜寻基于 [Kusto 查询语言](/azure/kusto/query/)，支持相同的语法和运算符。 通过运行第一个查询开始学习查询语言。|[查询语言概述](advanced-hunting-query-language.md)|
|**了解如何使用查询结果**|了解图表以及查看或导出结果的各种方法。 了解如何快速调整查询并向下钻取以获取更丰富的信息。|[处理查询结果](advanced-hunting-query-results.md)|
|**了解架构**|更好地大致了解架构及其列中的表。 了解在构造查询时在何处查找数据。|[架构参考](advanced-hunting-schema-reference.md)|
|**使用预定义查询**|浏览涵盖不同威胁搜寻方案的预定义查询集合。|[共享查询](advanced-hunting-shared-queries.md)|
|**优化查询和处理错误**|了解如何创建高效且无错误的查询。|[查询最佳做法](advanced-hunting-best-practices.md) <p> [处理错误](advanced-hunting-errors.md)|
|**获得最完整的覆盖范围**|使用审核设置为组织提供更好的数据覆盖范围。|[扩展高级搜寻范围](advanced-hunting-extend-data.md)|
|**运行快速调查**|快速运行高级搜寻查询以调查可疑活动。|[使用 go hunt 快速搜寻实体或 *事件信息*](advanced-hunting-go-hunt.md)|
|**包含威胁和地址泄露**|通过隔离文件、限制应用执行和其他操作来响应攻击|[对高级搜寻查询结果采取措施](advanced-hunting-take-action.md)|
|**创建自定义检测规则**|了解如何使用高级搜寻查询来触发警报并自动执行响应操作。|[自定义检测概述](overview-custom-detections.md) <p> [自定义检测规则](custom-detection-rules.md)|
|

## <a name="data-freshness-and-update-frequency"></a>数据新鲜度和更新频率

可以将高级搜寻数据分类为两种不同的类型，每种类型以不同的方式合并。

- **事件或活动数据**：填充有关警报、安全事件、系统事件和常规评估的表。 高级搜寻在收集它们传感器将其成功传输到 Defender for Endpoint 后，几乎会立即收到此数据。
- **实体数据**：使用有关用户和设备的综合信息填充表。 此数据来自相对静态的数据源和动态源，例如 Active Directory 条目和事件日志。 为了提供最新数据，表格每 15 分钟更新一次任何新信息，并添加可能未完全填充的行。 每 24 小时合并一次数据，以插入包含有关每个实体的最新、最全面的数据集的记录。

## <a name="time-zone"></a>时区

高级搜寻中的时间信息当前处于 UTC 时区。

## <a name="related-topics"></a>相关主题

- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [了解架构](advanced-hunting-schema-reference.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](overview-custom-detections.md)
- [存储帐户概述](/azure/storage/common/storage-account-overview)
- [Azure 事件中心 — 大数据流式处理平台和事件获取服务](/azure/event-hubs/event-hubs-about)
