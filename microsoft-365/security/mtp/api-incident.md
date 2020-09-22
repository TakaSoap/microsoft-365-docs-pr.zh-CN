---
title: Microsoft 威胁防护 API 中的事件资源类型
description: 了解 Microsoft 威胁防护中事件资源类型的方法和属性
keywords: 事件、事件、api
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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201299"
---
# <a name="incident-resource-type"></a>事件资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

>[!IMPORTANT] 
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>Methods

方法 |返回类型 |说明
:---|:---|:---
[列出事件](api-list-incidents.md) | [事件](api-incident.md) 列表 | 获取事件列表。
[更新事件](api-update-incidents.md) | [事例](api-incident.md) | 更新特定事件。


## <a name="properties"></a>属性

属性 |    类型    |    说明
:---|:---|:---
incidentId | long | 事件唯一 ID。
redirectIncidentId | nullable 长 | 当前事件合并到的事件 ID。
incidentName | string | 事件的名称。
createdTime | DateTimeOffset | 创建事件) 的日期和时间，以 UTC (。
lastUpdateTime | DateTimeOffset | 上次更新事件) UTC (的日期和时间。
assignedTo | string | 事件的所有者。
severity | 枚举 | 事件的严重性。 可能的值是 ```UnSpecified``` ： ```Informational``` 、 ```Low``` 、 ```Medium``` 和 ```High``` 。
status | 枚举 | 指定事件的当前状态。 可能的值为 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。
classification | 枚举 | 事件的规范。 可取值为：```Unknown```、```FalsePositive```、```TruePositive```。
可用性 | 枚举 | 指定事件的确定。 可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。
tags | 字符串列表 | 事件标记列表。
警报 | 通知列表 | 相关警报的列表。 请参阅 [List 事件](api-list-incidents.md) API 文档中的示例。
