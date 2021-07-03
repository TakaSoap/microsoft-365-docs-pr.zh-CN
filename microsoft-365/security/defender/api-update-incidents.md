---
title: 更新事件 API
description: 了解如何使用 Microsoft 365 Defender API 更新事件
keywords: 更新， api， 事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 60f1209331862eb21d3b1949265f0873dcf2e5a7
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287815"
---
# <a name="update-incidents-api"></a>更新事件 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

## <a name="api-description"></a>API 说明

更新现有事件的属性。 可更新的属性包括 ```status``` ```determination``` ```classification``` ：、、、、 ```assignedTo``` ```tags``` 和 ```comments``` 。

### <a name="quotas-resource-allocation-and-other-constraints"></a>配额、资源分配和其他约束

1. 在达到限制阈值之前，每分钟最多可以拨打 50 个呼叫或每小时 1500 个呼叫。
2. 只有在设置为 `determination` `classification` TruePositive 时，才能设置该属性。

如果请求受到限制，它将返回 响应 `429` 代码。 响应正文将指示开始进行新呼叫的时间。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息，包括如何选择权限，请参阅访问Microsoft 365 Defender [API。](api-access.md)

权限类型 | 权限 | 权限显示名称
-|-|-
Application | Incident.ReadWrite.All | 读取和写入所有事件
委派（工作或学校帐户） | Incident.ReadWrite | 读取和写入事件

> [!NOTE]
> 使用用户凭据获取令牌时，用户需要具有在门户中更新事件的权限。

## <a name="http-request"></a>HTTP 请求

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
-|-|-
Authorization | 字符串 | Bearer {token}。 **必需**。
Content-Type | String | application/json. **必需**。

## <a name="request-body"></a>请求正文

在请求正文中，提供应更新的字段的值。 请求正文中未包含的现有属性将保留其值，除非由于相关值更改而必须重新计算它们。 为获得最佳性能，应省略尚未更改的现有值。

属性 | 类型 | 说明
-|-|-
状态 | 枚举 | 指定事件的当前状态。 可能的值是 ```Active``` ：、 ```Resolved``` 和 ```Redirected``` 。
assignedTo | string | 事件的所有者。
classification | 枚举 | 事件的规范。 可取值为：```Unknown```、```FalsePositive```、```TruePositive```。
确定 | 枚举 | 指定事件的确定。 可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。
标记 | 字符串列表 | 事件标记列表。
comment | string | 要添加到事件的注释。

## <a name="response"></a>响应

如果成功，此方法返回 `200 OK` 。 响应正文将包含具有更新属性的事件实体。 如果未找到具有指定 ID 的事件，该方法将返回 `404 Not Found` 。

## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

**响应**

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a>相关文章

- [访问Microsoft 365 Defender API](api-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [事件 API](api-incident.md)
- [列出事件](api-list-incidents.md)
- [事件概述](incidents-overview.md)
