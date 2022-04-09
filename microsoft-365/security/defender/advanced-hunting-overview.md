---
title: 概述 - 高级搜寻
description: 了解 Microsoft 365 中的高级搜寻查询以及如何使用它们来主动查找网络中的威胁和弱点
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、Microsoft 365 Defender、microsoft 365、m365、搜索、查询、遥测、自定义检测、架构、kusto
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 1ee8d8fbd3b1a56f83106ffaf6be937fa984c272
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731430"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>使用 Microsoft 365 Defender 中的高级搜寻主动搜寻威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级搜寻是一种基于查询的威胁搜寻工具，可让你浏览最多 30 天的原始数据。 你可以主动检查网络中的事件来找到威胁指示器和实体。 灵活访问数据可以不受约束地搜寻已知威胁和潜在威胁。
<br><br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4G6DO]

可以使用相同的威胁搜寻查询来生成自定义检测规则。 这些规则自动运行以检查，然后响应可疑的违规活动、配置错误的计算机和其他发现。

此功能类似于[Microsoft Defender for Endpoint中的高级搜寻](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)功能，并支持检查更广泛的数据集的查询：

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

若要使用高级搜寻，[请打开Microsoft 365 Defender](m365d-enable.md)。

有关Microsoft Defender for Cloud Apps数据中的高级搜寻的详细信息，请参[阅视频](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)。 

## <a name="get-started-with-advanced-hunting"></a>高级搜寻入门

我们建议执行几个步骤，快速开始高级搜寻。

| 学习目标 | 说明 | 资源 |
|--|--|--|
| **了解语言** | 高级搜寻基于[Kusto查询语言](/azure/kusto/query/)，支持相同的语法和运算符。 通过运行第一个查询开始学习查询语言。 | [查询语言概述](advanced-hunting-query-language.md) |
| **了解如何使用查询结果** | 了解图表以及查看或导出结果的各种方式。 了解如何快速调整查询、向下钻取以获取更丰富的信息，以及如何执行响应操作。 | - [处理查询结果](advanced-hunting-query-results.md)<br /> - [对查询结果采取措施](advanced-hunting-take-action.md) |
| **了解架构** | 更好地大致了解架构及其列中的表。 了解在构造查询时在何处查找数据。 | - [架构参考](advanced-hunting-schema-tables.md) <br />- [从Microsoft Defender for Endpoint过渡](advanced-hunting-migrate-from-mde.md) |
| **获取专家提示和示例** | 在 Microsoft 专家的指导下免费训练。 浏览涵盖不同威胁搜寻方案的预定义查询集合。 | - [获取专家培训](advanced-hunting-expert-training.md) <br />- [使用共享查询](advanced-hunting-shared-queries.md) <br />- [去打猎](advanced-hunting-go-hunt.md) <br />- [跨设备、电子邮件、应用和标识搜寻威胁](advanced-hunting-query-emails-devices.md) |
| **优化查询并处理错误** | 了解如何创建高效且无错误的查询。 | - [查询最佳做法](advanced-hunting-best-practices.md)<br />- [处理错误](advanced-hunting-errors.md) |
| **创建自定义检测规则** | 了解如何使用高级搜寻查询触发警报并自动执行响应操作。 | - [自定义检测概述](custom-detections-overview.md) <br />- [自定义检测规则](custom-detection-rules.md) |

## <a name="get-access"></a>获取访问权限
若要使用高级搜寻或其他[Microsoft 365 Defender](microsoft-365-defender.md)功能，需要在Azure Active Directory中发挥适当的作用。 [了解高级搜寻所需的角色和权限](custom-roles.md)。

此外，对终结点数据的访问权限由基于角色的访问控制 (RBAC) Microsoft Defender for Endpoint中的设置决定。 [了解如何管理对Microsoft 365 Defender的访问权限](m365d-permissions.md)。


## <a name="data-freshness-and-update-frequency"></a>数据新鲜度和更新频率
可以将高级搜寻数据分类为两种不同的类型，每种类型以不同的方式合并。

- **事件或活动数据** - 填充有关警报、安全事件、系统事件和例行评估的表。 高级搜寻几乎会在成功收集这些数据的传感器之后立刻将这些数据传输到相应的云服务。 例如，几乎可以在工作站或域控制器上从运行状况良好的传感器查询事件数据，这些数据在Microsoft Defender for Endpoint和Microsoft Defender for Identity上可用之后。
- **实体数据** - 使用有关用户和设备的信息填充表。 此数据来自相对静态的数据源和动态源，例如 Active Directory 条目和事件日志。 若要提供新数据，表每 15 分钟更新一次，并添加可能未完全填充的行。 每 24 小时合并一次数据，以插入包含有关每个实体的最新、最全面的数据集的记录。

## <a name="time-zone"></a>时区
高级搜寻中的时间信息位于 UTC 时区中。

## <a name="related-topics"></a>相关主题
- [了解查询语言](advanced-hunting-query-language.md)
- [获取专家培训](advanced-hunting-expert-training.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](custom-detections-overview.md)
