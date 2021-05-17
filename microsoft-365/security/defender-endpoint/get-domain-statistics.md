---
title: 获取域统计信息 API
description: 了解如何使用获取域统计信息 API 检索 Microsoft Defender for Endpoint 中给定域的统计信息。
keywords: api， 图形 api， 受支持的 api， 获取， 域， 域相关设备
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
ms.technology: mde
ms.openlocfilehash: eef06657d7f691a89e5985640431c2cc706557b4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166464"
---
# <a name="get-domain-statistics-api"></a>获取域统计信息 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 说明
检索给定域上的统计信息。


## <a name="limitations"></a>限制
1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。


## <a name="permissions"></a>权限
若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   URL。Read.All |  "读取 URL"
委派（工作或学校帐户） | URL。Read.All | "读取 URL"

>[!Note]
> 使用用户凭据获取令牌时：
>- 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)

## <a name="http-request"></a>HTTP 请求
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>请求标头

标头 | 值 
:---|:---
Authorization | Bearer {token}。 **必需**。

## <a name="request-uri-parameters"></a>请求 URI 参数

名称 | 类型 | 说明
:---|:---|:---
lookBackHours | Int32 | 定义我们重新搜索以获取统计信息的小时数。 默认为 30 天。 **可选。**

## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功且域存在 - 200 正常，响应正文中具有 statistics 对象。 如果域不存在 - 404 未找到。


## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

**响应**

下面是一个响应示例。


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
