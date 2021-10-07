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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4bc2afa433cba0ce5ae8fd82dab1e278d29f57e4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211132"
---
# <a name="get-domain-statistics-api"></a>获取域统计信息 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

检索给定域上的统计信息。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。
2. 最大值为 `lookbackhours` 720 小时 (30 天) 。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
Application|URL。Read.All|"读取 URL"
委派（工作或学校帐户）|URL。Read.All|"读取 URL"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)

## <a name="http-request"></a>HTTP 请求

```http
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a>请求标头

标头|值
:---|:---
Authorization|Bearer {token}。 **必需**。

## <a name="request-uri-parameters"></a>请求 URI 参数

名称|类型|说明
:---|:---|:---
lookBackHours|Int32|定义我们重新搜索以获取统计信息的小时数。 默认为 30 天。 **可选**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且域存在 - 200 正常，响应正文中具有 statistics 对象。 如果域不存在 - 200 正常，普遍程度设置为 0。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "organizationPrevalence": 4070,
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
