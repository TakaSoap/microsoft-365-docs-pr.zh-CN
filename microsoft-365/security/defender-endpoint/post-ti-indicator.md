---
title: 提交或更新指示器 API
description: 了解如何使用提交或更新指示器 API 在 Microsoft Defender for Endpoint 中提交或更新新的指示器实体。
keywords: api， 图形 api， 受支持的 api， 提交， ti， 指示器， 更新
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 03235435028b9e30adc6ffd39fa512af05fd3ee3
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622792"
---
# <a name="submit-or-update-indicator-api"></a>提交或更新指示器 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

提交或更新新的 [指示器](ti-indicator.md) 实体。

不支持 IP 的 CIDR 表示法。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。
2. 每个租户 15，000 个活动指示器的限制。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅 [入门](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Ti.ReadWrite|"读取和写入指示器"
应用程序|Ti.ReadWrite.All|"读取和写入所有指示器"
委派（工作或学校帐户）|Ti.ReadWrite|"读取和写入指示器"

## <a name="http-request"></a>HTTP 请求

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|字符串|Bearer {token}。 **必需**。
Content-Type|string|application/json. **必需**。

## <a name="request-body"></a>请求正文

在请求正文中，提供具有以下参数的 JSON 对象：

参数|类型|说明
:---|:---|:---
indicatorValue|字符串|Indicator [实体的](ti-indicator.md) 标识。 **必需**
indicatorType|枚举|指示器的类型。 可能的值是："FileSha1"、"FileSha256"、"IpAddress"、"DomainName"和"Url"。 **必需**
action|枚举|如果在组织中发现指示器，将采取的操作。 可能的值是："Alert"、"AlertAndBlock"和"Allowed"。 **必需**
应用程序|字符串|与指示器关联的应用程序。 **可选**
title|String|指示器警报标题。 **必需**
说明|字符串|指示器的说明。 **必需**
expirationTime|DateTimeOffset|指示器的过期时间。 **可选**
severity|枚举|指示器的严重性。 可能的值包括："Informational"、"Low"、"Medium"和"High"。 **可选**
recommendedActions|字符串|TI 指示器警报建议操作。 **可选**
rbacGroupNames|字符串|将应用指示器的 RBAC 组名称的逗号分隔列表。 **可选**

## <a name="response"></a>响应

- 如果成功，此方法在响应正文中返回 200 - OK 响应代码和已创建/已更新 [的 Indicator](ti-indicator.md) 实体。
- 如果未成功：此方法返回 400 - 错误请求。 错误的请求通常指示正文不正确。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a>相关主题

- [管理指示器](manage-indicators.md)
