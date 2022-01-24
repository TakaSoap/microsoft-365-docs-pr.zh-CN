---
title: Microsoft 365 Defender事件 API 和事件资源类型
description: 了解事件资源类型的方法和属性Microsoft 365 Defender
keywords: 事件， 事件， api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: a1a3f119e0aafe75b58df9c2330a950d5ab31ead
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172303"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 Defender事件 API 和事件资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

[事件](incidents-overview.md)是帮助描述攻击的相关警报的集合。 来自组织中不同实体的事件会自动由Microsoft 365 Defender。 可以使用事件 API 以编程方式访问组织的事件和相关警报。

## <a name="quotas-and-resource-allocation"></a>配额和资源分配

每分钟最多可以请求 50 个呼叫或每小时 1500 个呼叫。 每个方法也有其自己的配额。 有关特定于方法的配额的信息，请参阅想要使用的方法各自的文章。

HTTP 响应代码指示你已按发送的请求数或按分配的运行时间 `429` 达到配额。 响应正文将包括重置达到的配额之前的时间。

## <a name="permissions"></a>权限

事件 API 需要针对其每个方法的不同类型的权限。 有关所需权限详细信息，请参阅相应方法的文章。

## <a name="methods"></a>方法

方法 | 返回类型 | 说明
-|-|-
[列出事件](api-list-incidents.md) | [事件](api-incident.md) 列表 | 获取事件列表。
[更新事件](api-update-incidents.md) | [事件](api-incident.md) | 更新特定事件。
[获取事件](api-get-incident.md) | [事件](api-incident.md) | 获取单个事件。

## <a name="request-body-response-and-examples"></a>请求正文、响应和示例

请参阅各自的方法文章，了解有关如何构造请求或分析响应的更多详细信息，以及实际示例。

## <a name="common-properties"></a>通用属性

属性 | 类型 | 说明
-|-|-
incidentId | long | 事件唯一 ID。
redirectIncidentId | nullable long | 当前事件合并到的事件 ID。
incidentName | string | 事件的名称。
createdTime | DateTimeOffset | 创建事件时 (UTC) 日期和时间。
lastUpdateTime | DateTimeOffset | 上次更新事件 (UTC) 日期和时间。
assignedTo | string | 事件的所有者。
severity | 枚举 | 事件的严重性。 可能的值是 ```UnSpecified``` ```Informational``` ```Low``` ：、、、 ```Medium``` 和 ```High``` 。
状态 | 枚举 | 指定事件的当前状态。 可能的值为： ```Active```、 ```InProgress```、 ```Resolved```和 ```Redirected```。
classification | 枚举 | 事件的规范。 可取值为：```Unknown```、```FalsePositive```、```TruePositive```。
确定 | 枚举 | 指定事件的确定。 可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。
标记 | 字符串列表 | 事件标记列表。
comments | 事件注释列表 | 事件注释对象包含：注释字符串、createdBy 字符串和 createTime 日期时间。
警报 | 警报列表 | 相关警报列表。 请参阅列表事件 API [文档](api-list-incidents.md) 的示例。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [事件概述](incidents-overview.md)
- [列出事件 API](api-list-incidents.md)
- [更新事件 API](api-update-incidents.md)
