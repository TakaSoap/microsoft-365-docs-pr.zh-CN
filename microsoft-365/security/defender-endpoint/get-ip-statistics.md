---
title: 获取 IP 统计信息 API
description: 使用 Microsoft Defender for Endpoint 获取 IP 的最新统计信息。
keywords: api， 图形 api， 受支持的 api， 获取， ip， 统计信息， 普遍程度
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
ms.openlocfilehash: a98b78e85956d49c3b7d7e389882e017dcede3a4
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283244"
---
# <a name="get-ip-statistics-api"></a>获取 IP 统计信息 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明
检索给定 IP 的统计信息。

## <a name="limitations"></a>限制
1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。
2. Lookbackhours 的最大值是 720 小时 (30 天) 。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Ip.Read.All|"读取 IP 地址配置文件"
委派（工作或学校帐户）|Ip.Read.All|"读取 IP 地址配置文件"

> [!NOTE]
> 使用用户凭据获取令牌时：
> - 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)

## <a name="http-request"></a>HTTP 请求

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 必需。

## <a name="request-uri-parameters"></a>请求 URI 参数

名称|类型|说明
:---|:---|:---
lookBackHours|Int32|定义我们重新搜索以获取统计信息的小时数。 默认为 30 天。 **可选**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且 ip 存在 - 200 正常，正文中提供统计数据。 IP 有效但不存在 - organizationPrevalence 0，IP 无效 - HTTP 400。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```

|名称|说明|
|---|---|
|组织普遍程度|打开到此 IP 的网络连接的设备数。|
|首次看到组织|组织中此 IP 的第一个连接。|
|上次查看组织|组织中此 IP 的最后一个连接。|

> [!NOTE]
> 此统计信息基于过去 30 天的数据。
