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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 627791e9dc3d4bf18047a05734a4e275152d19da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845028"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中主动查找具有高级搜寻的威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。 您可以主动检查网络中的事件以查找威胁指示器和实体。 灵活的数据访问可实现已知和潜在威胁的无约束搜寻。
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

你可以使用相同的威胁搜寻查询来构建自定义检测规则。 这些规则会自动运行以检查并响应可疑的违规活动、错误配置的计算机以及其他发现。

此功能类似于 [Microsoft Defender For Endpoint 中的高级搜寻](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。 在 Microsoft 365 安全中心中提供，此功能支持通过以下查询检查更广泛的数据集：

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Cloud App Security
- Microsoft Defender for Identity

若要使用高级搜寻，请 [打开 Microsoft 365 Defender](mtp-enable.md)。

## <a name="get-started-with-advanced-hunting"></a>高级搜寻入门

我们建议您通过几个步骤快速开始执行高级搜寻。

| 学习目标 | 说明 | 资源 |
|--|--|--|
| **了解语言** | 高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)，支持相同的语法和运算符。 通过运行第一个查询开始学习查询语言。 | [查询语言概述](advanced-hunting-query-language.md) |
| **了解如何使用查询结果** | 了解您可以查看或导出结果的各种图表和各种方式。 了解如何快速调整查询、向下钻取以获取更丰富的信息，并采取响应操作。 | - [处理查询结果](advanced-hunting-query-results.md)<br>- [对查询结果执行操作](advanced-hunting-take-action.md) |
| **了解架构** | 更好地大致了解架构及其列中的表。 了解在构造查询时查找数据的位置。 | - [架构参考](advanced-hunting-schema-tables.md)<br>- [从 Microsoft Defender for Endpoint 转换](advanced-hunting-migrate-from-mdatp.md) |
| **获取专家提示和示例** | 从 Microsoft 专家处获取免费培训指南。 浏览涵盖不同威胁搜寻方案的预定义查询集合。 | - [获取专家培训](advanced-hunting-expert-training.md)<br>- [使用共享查询](advanced-hunting-shared-queries.md)<br>- [开始智能寻线](advanced-hunting-go-hunt.md)<br>- [在设备、电子邮件、应用和标识之间寻找威胁](advanced-hunting-query-emails-devices.md) |
| **优化查询和处理错误** | 了解如何创建高效和无错误的查询。 | - [查询最佳实践](advanced-hunting-best-practices.md)<br>- [处理错误](advanced-hunting-errors.md) |
| **创建自定义检测规则** | 了解如何使用高级搜寻查询来触发通知并自动采取响应操作。 | - [自定义检测概述](custom-detections-overview.md)<br>- [自定义检测规则](custom-detection-rules.md) |

## <a name="get-access"></a>获取访问权限
若要使用高级搜寻或其他 [Microsoft 365 Defender](microsoft-threat-protection.md) 功能，您需要在 Azure Active Directory 中使用适当的角色。 此外，您对终结点数据的访问权限由基于角色的访问控制在 Microsoft Defender for Endpoint 中 (RBAC) 设置决定。 [阅读有关管理对 Microsoft 365 Defender 的访问权限的信息](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>数据刷新和更新频率
高级的搜寻数据可分为两种不同的类型，每种方式都有不同的合并。

- **事件或活动数据** —填充有关警报、安全事件、系统事件和常规评估的表。 高级搜寻几乎会在收集这些数据的传感器成功传输到相应的云服务后立即收到。 例如，您可以在工作站或域控制器上的正常传感器中立即查询事件数据，这些数据在 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 中可用后几乎会立即查询。
- **实体数据** —使用有关用户和设备的信息填充表。 这些数据来自相对静态数据源和动态源，如 Active Directory 条目和事件日志。 为了提供新数据，每15分钟更新一次表中的所有新信息，添加可能未完全填充的行。 每隔24小时，合并数据以插入包含有关每个实体的最新、最全面的数据集的记录。

## <a name="time-zone"></a>时区
高级搜寻中的时间信息位于 UTC 时区中。

## <a name="related-topics"></a>相关主题
- [了解查询语言](advanced-hunting-query-language.md)
- [获取专家培训](advanced-hunting-expert-training.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](custom-detections-overview.md)

