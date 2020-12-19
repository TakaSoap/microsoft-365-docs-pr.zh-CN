---
title: Microsoft 365 Defender 事件 API 和事件资源类型
description: 了解 Microsoft 365 Defender 中事件资源类型的方法和属性
keywords: 事件， 事件， api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719330"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender 事件 API 和事件资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

[事件](incidents-overview.md)是有助于描述攻击的相关警报的集合。 来自组织中不同实体的事件由 Microsoft 365 Defender 自动聚合。 可以使用事件 API 以编程方式访问组织的事件和相关警报。

## <a name="quotas-and-resource-allocation"></a>配额和资源分配

每分钟最多可以请求 50 个呼叫或每小时 1500 个呼叫。 每个方法也有其自己的配额。 有关特定于方法的配额详细信息，请参阅要使用的方法各自的文章。

HTTP 响应代码指示你已按发送的请求数或分配的运行时间达到 `429` 配额。 响应正文将包括重置达到的配额之前的时间。

## <a name="permissions"></a>权限

事件 API 需要针对其每个方法的不同类型的权限。 有关所需权限详细信息，请参阅相应方法的文章。

## <a name="methods"></a>方法

方法 | 返回类型 | 说明
-|-|-
[列出事件](api-list-incidents.md) | [事件](api-incident.md) 列表 | 获取事件列表。
[更新事件](api-update-incidents.md) | [事件](api-incident.md) | 更新特定事件。

## <a name="request-body-response-and-examples"></a>请求正文、响应和示例

请参阅各自的方法文章，了解有关如何构造请求或分析响应的更多详细信息，以及实际示例。

## <a name="common-properties"></a>通用属性

属性 | 类型 | 说明
-|-|-
incidentId | long | 事件唯一 ID。
redirectIncidentId | nullable long | 当前事件合并到的事件 ID。
incidentName | string | 事件的名称。
createdTime | DateTimeOffset | 创建事件 (的日期和时间) UTC 格式。
lastUpdateTime | DateTimeOffset | 上次更新事件 (的日期和时间) UTC 格式。
assignedTo | string | 事件的所有者。
severity | 枚举 | 事件的严重性。 可能的值是： ```UnSpecified``` ```Informational``` 、 、 和 ```Low``` ```Medium``` ```High``` 。
status | 枚举 | 指定事件的当前状态。 可能的值是： ```Active``` 和 ```Resolved``` ```Redirected``` 。
classification | 枚举 | 事件规范。 可取值为：```Unknown```、```FalsePositive```、```TruePositive```。
确定 | 枚举 | 指定事件确定。 可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。
tags | string List | 事件标记列表。
警报 | 警报列表 | 相关警报列表。 请参阅列表事件 API [文档](api-list-incidents.md) 的示例。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [事件概述](incidents-overview.md)
- [列出事件 API](api-list-incidents.md)
- [更新事件 API](api-update-incidents.md)
