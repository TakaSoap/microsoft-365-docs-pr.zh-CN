---
title: 获取通知相关 IP 信息
description: 使用 Microsoft Defender for Endpoint 检索与特定警报相关的所有 IP。
keywords: api， 图形 api， 受支持的 api， 获取警报信息， 警报信息， 相关 ip
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
ms.openlocfilehash: a317e197c425750c8db0592f1e2f1e4d6d90a142
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59170071"
---
# <a name="get-alert-related-ips-information-api"></a>获取与警报相关的 IP 信息 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

检索与特定警报相关的所有 IP。

## <a name="limitations"></a>限制

1. 你可以根据配置的保留期查询上次更新的警报。
2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Ip.Read.All|"读取 IP 地址配置文件"
委派（工作或学校帐户）|Ip.Read.All|"读取 IP 地址配置文件"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)
> - 用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理设备组，了解) [](machine-groups.md)

## <a name="http-request"></a>HTTP 请求

```http
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 **必需**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且警报和 IP 存在 - 200 正常。 如果未找到警报 - 404 未找到。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228
                }
                ...
    ]
}
```
