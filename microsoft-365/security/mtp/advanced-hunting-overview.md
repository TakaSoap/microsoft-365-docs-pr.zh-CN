---
title: 概述-高级搜寻
description: 了解 Microsoft 365 中的高级搜寻查询以及如何使用它们来主动查找网络中的威胁和弱点
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、架构、kusto、microsoft 365、Microsoft 威胁防护
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7bda309dbb1b601c77b6fb34ff9b8be14d5638d
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138274"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>通过 Microsoft 威胁防护中的高级搜寻主动搜寻威胁

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。 你可以主动检查网络中的事件来找到感兴趣的指示器和实体。 灵活访问数据有助于无约束搜寻已知威胁和潜在威胁。

您可以使用相同的威胁搜寻查询来生成自定义检测规则。 这些规则会自动运行以检查和响应各种事件和系统状态，包括可疑的入侵活动和误配置的计算机。

在 Microsoft 365 安全中心中，高级搜索支持从各种工作区查看数据的查询，其中包括有关设备、电子邮件、应用程序和 Microsoft Defender ATP、Office 365 ATP、Microsoft 云应用安全性和 Azure ATP 等标识的数据。 若要使用高级搜寻，请[打开 Microsoft 威胁防护](mtp-enable.md)。

## <a name="get-started-with-advanced-hunting"></a>高级搜寻入门

我们建议执行几个步骤来通过高级搜寻快速启动并运行。

| 学习目标 | 说明 | 资源 |
|--|--|--|
| **了解语言** | 高级搜寻基于[Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)，支持相同的语法和运算符。 通过运行第一个查询开始学习查询语言。 | [查询语言概述](advanced-hunting-query-language.md) |
| **了解如何使用查询结果** | 了解您可以查看或导出结果的各种图表和各种方式。 了解如何快速调整查询和向下钻取以获取更丰富的信息。 | [处理查询结果](advanced-hunting-query-results.md) |
| **了解架构** | 更好地大致了解架构及其列中的表。 这将帮助你确定在何处查找数据以及如何构建查询。 | [架构参考](advanced-hunting-schema-tables.md) |
| **利用预定义查询** | 浏览涵盖不同威胁搜寻方案的预定义查询集合。 | - [使用共享查询](advanced-hunting-shared-queries.md)<br>- [开始智能寻线](advanced-hunting-go-hunt.md) |
| **优化查询** | 了解如何创建高效查询以及组合电子邮件和设备中的数据的查询。 | - [查询最佳实践](advanced-hunting-shared-queries.md) <br>- [跨设备和电子邮件的智能寻线](advanced-hunting-best-practices.md) |
| **创建自定义检测规则** | 了解如何使用高级搜寻查询来触发通知并自动应用响应操作。 | - [自定义检测概述](custom-detections-overview.md)<br>- [自定义检测规则](custom-detection-rules.md) |

## <a name="get-access"></a>获取访问权限
若要使用高级搜寻或其他[Microsoft 威胁防护](microsoft-threat-protection.md)功能，您需要在 Azure AD 中为其分配一个适当的角色。 请注意，对终结点数据的访问受 Microsoft Defender ATP 中基于角色的访问控制设置的影响。 [阅读有关管理 Microsoft 威胁防护的访问权限](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>数据刷新和更新频率
高级的搜寻数据可分为两种不同的类型，每种方式都有不同的合并。

- **事件或活动数据**—填充有关警报、安全事件、系统事件和常规评估的表。 高级搜寻几乎会在收集这些数据的传感器成功传输到相应的云服务后立即收到。 例如，您可以开始在工作站或域控制器上的正常传感器中查询事件数据，这些数据在 Microsoft Defender ATP 和 Azure ATP 上可用后几乎可以立即开始。
- **实体数据**—使用有关用户和设备的统一信息填充表。 此类数据来自相对静态数据源（如 Active Directory 条目）和动态源（如事件日志）。 为了提供最新数据，每15分钟更新一次表格，以添加任何新信息，添加可能未完全填充的行。 每隔24小时，合并数据以插入包含有关每个实体的最新、最全面的数据集的记录。

## <a name="related-topics"></a>相关主题
- [了解查询语言](advanced-hunting-query-language.md)
- [处理查询结果](advanced-hunting-query-results.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](custom-detections-overview.md)
