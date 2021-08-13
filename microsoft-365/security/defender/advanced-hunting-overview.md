---
title: 概述 - 高级搜寻
description: 了解 Microsoft 365 中的高级搜寻查询以及如何使用它们来主动查找网络中的威胁和弱点
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 564afed2c10d232076bf6875e035bcf03ea7712ada2b430729f4a936a675b8bb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53833191"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>通过高级搜寻主动搜寻Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

> 希望体验 Microsoft 365 Defender？ 你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。
>

高级搜寻是基于查询的威胁搜寻工具，允许你浏览最多 30 天的原始数据。 你可以主动检查网络中事件，以查找威胁指示器和实体。 通过灵活的数据访问，可以不受限制地搜寻已知威胁和潜在威胁。
<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

你可以使用相同的威胁搜寻查询来构建自定义检测规则。 这些规则将自动运行，以检查并响应可疑的泄露活动、错误配置的计算机和其他发现。

此功能类似于 Microsoft [Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) 中的高级搜寻，并支持从以下位置检查更广泛的数据集的查询：

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft 云应用安全
- Microsoft Defender for Identity

若要使用高级搜寻，[请打开Microsoft 365 Defender。](m365d-enable.md)

有关数据中高级搜寻Microsoft Cloud App Security，请参阅[视频](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)。 

## <a name="get-started-with-advanced-hunting"></a>高级搜寻入门

我们建议执行几个步骤以快速开始使用高级搜寻。

| 学习目标 | 说明 | 资源 |
|--|--|--|
| **了解语言** | 高级搜寻基于 [Kusto 查询语言](/azure/kusto/query/)，支持相同的语法和运算符。 通过运行第一个查询开始学习查询语言。 | [查询语言概述](advanced-hunting-query-language.md) |
| **了解如何使用查询结果** | 了解图表以及查看或导出结果的各种方法。 了解如何快速调整查询、向下钻取以获取更丰富的信息以及执行响应操作。 | - [使用查询结果](advanced-hunting-query-results.md)<br /> - [对查询结果采取措施](advanced-hunting-take-action.md) |
| **了解架构** | 更好地大致了解架构及其列中的表。 了解在构造查询时在何处查找数据。 | - [架构参考](advanced-hunting-schema-tables.md) <br />- [从 Microsoft Defender for Endpoint 转换](advanced-hunting-migrate-from-mde.md) |
| **获取专家提示和示例** | 通过 Microsoft 专家的指南免费培训。 浏览涵盖不同威胁搜寻方案的预定义查询集合。 | - [获取专家培训](advanced-hunting-expert-training.md) <br />- [使用共享查询](advanced-hunting-shared-queries.md) <br />- [去寻线](advanced-hunting-go-hunt.md) <br />- [跨设备、电子邮件、应用和标识搜寻威胁](advanced-hunting-query-emails-devices.md) |
| **优化查询和处理错误** | 了解如何创建高效且无错误的查询。 | - [查询最佳做法](advanced-hunting-best-practices.md)<br />- [处理错误](advanced-hunting-errors.md) |
| **创建自定义检测规则** | 了解如何使用高级搜寻查询来触发警报并自动执行响应操作。 | - [自定义检测概述](custom-detections-overview.md) <br />- [自定义检测规则](custom-detection-rules.md) |

## <a name="get-access"></a>获取访问权限
若要使用高级搜寻或其他[Microsoft 365 Defender](microsoft-365-defender.md)功能，你需要一个合适的角色Azure Active Directory。 [阅读高级搜寻所需的角色和权限](custom-roles.md)。

此外，对终结点数据的访问由基于角色的访问控制 (Microsoft Defender for Endpoint) RBAC 设置确定。 [阅读有关管理对 Microsoft 365 Defender 的访问权限](m365d-permissions.md)。


## <a name="data-freshness-and-update-frequency"></a>数据新鲜度和更新频率
高级搜寻数据可以分为两种不同的类型，每种类型合并的方式不同。

- **事件或活动数据**- 填充有关警报、安全事件、系统事件和例程评估的表。 高级搜寻在收集它们传感器将其成功传输到相应的云服务后，几乎会立即收到此数据。 例如，在 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 上提供事件数据后，你几乎可以在工作站或域控制器上立即查询来自正常传感器的事件数据。
- **实体** 数据 - 使用有关用户和设备的信息填充表。 此数据来自相对静态数据源和动态源，如 Active Directory 条目和事件日志。 为了提供最新数据，表格每 15 分钟更新一次任何新信息，并添加可能未完全填充的行。 每 24 小时合并一次数据，以插入包含有关每个实体的最新、最全面的数据集的记录。

## <a name="time-zone"></a>时区
高级搜寻中的时间信息采用 UTC 时区。

## <a name="related-topics"></a>相关主题
- [了解查询语言](advanced-hunting-query-language.md)
- [获取专家培训](advanced-hunting-expert-training.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](custom-detections-overview.md)
