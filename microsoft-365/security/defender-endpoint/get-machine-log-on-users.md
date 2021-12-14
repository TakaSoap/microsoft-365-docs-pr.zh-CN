---
title: 获取计算机登录用户 API
description: 了解如何使用获取计算机登录用户 API 在 Microsoft Defender for Endpoint 中检索设备上已登录用户的集合。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 登录， 用户
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
ms.openlocfilehash: 1c8635e7037f72830584d09d229891822a2e1f52
ms.sourcegitcommit: 2716cb48cc6127f6b851d177af23f276fb07bfc9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61426419"
---
# <a name="get-machine-logon-users-api"></a>获取计算机登录用户 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：** 
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 说明
检索特定设备上已登录用户的集合。

## <a name="limitations"></a>限制
1. 你可以根据配置的保留期查询上次更新的警报。
2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
Application |User.Read.All |"读取用户配置文件"
委派（工作或学校帐户） | User.Read.All | "读取用户配置文件"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："查看数据"。 有关详细信息，请参阅创建 [和管理角色](user-roles.md)。
> - 响应将仅在设备对用户可见时包含用户，基于设备组设置。 有关详细信息，请参阅创建 [和管理设备组](machine-groups.md)。

## <a name="http-request"></a>HTTP 请求

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization | 字符串 | Bearer {token}。 **必需**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且设备存在 - 200 正常[](user.md)，正文中具有用户实体列表。 如果未找到设备 - 404 未找到。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a>响应

下面是一个响应示例。

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
