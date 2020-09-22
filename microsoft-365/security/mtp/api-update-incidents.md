---
title: 更新事件 API
description: 了解如何使用 Microsoft 威胁防护 API 更新事件
keywords: 更新、api、事件
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
ms.openlocfilehash: 8ad47453c7163bfac99c17f42986b818cdca603f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203615"
---
# <a name="update-incidents-api"></a>更新事件 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

>[!IMPORTANT] 
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="api-description"></a>API 说明
更新现有事件的属性。
<br>可更新属性包括 ```status``` ： ```determination``` 、 ```classification``` 、 ```assignedTo``` 和 ```tags``` 。


## <a name="limitations"></a>限制
1. 此 API 的速率限制为每分钟50个呼叫和每小时的1500个呼叫。
2. 如果将分类设置为 TruePositive，则可以设置 " ```determination``` 仅限"。


## <a name="permissions"></a>权限
若要调用此 API，必须有以下权限之一。 若要了解详细信息，包括如何选择权限，请参阅 [访问 Microsoft 威胁防护 api](api-access.md)。

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   事件 ReadWrite。 All |    ' 读取和写入所有事件 '
委派（工作或学校帐户） | 事件读写 | "读取和写入事件"

>[!NOTE]
> 使用用户凭据获取令牌时：
>- 用户需要具有更新门户中的事件的权限。


## <a name="http-request"></a>HTTP 请求

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | String | 持有者 {令牌}。 **** 必需。
Content-Type | String | application/json. **** 必需。


## <a name="request-body"></a>请求正文
在请求正文中，提供应更新的相关字段的值。
<br>请求正文中不包括的现有属性将保留其以前的值，或根据对其他属性值的更改重新计算。 
<br>为了获得最佳性能，不应包括尚未更改的现有值。

属性 | 类型 | 说明
:---|:---|:---
状态 | 枚举 | 指定警报的当前状态。 可能的值为 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。
assignedTo | string | 事件的所有者。
classification | 枚举 | 通知的规范。 可取值为：```Unknown```、```FalsePositive```、```TruePositive```。
可用性 | 枚举 | 指定通知的确定。 可取值为：```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware``` 或 ```Other```。
tags | 字符串列表 | 事件标记列表。



## <a name="response"></a>响应
如果成功，此方法将在响应正文中返回 200 OK 和 incident 实体，其中包含更新的属性。 如果找不到具有指定 id 的事件-找不到404。


## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>相关主题
- [事件 API](api-incident.md)
- [列出事件](api-list-incidents.md)
