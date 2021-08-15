---
title: 获取事件 API
description: 了解如何使用"获取事件"API 在事件Microsoft 365 Defender。
keywords: api， 图形 api， 受支持的 api， 获取， 文件， 哈希
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
ms.openlocfilehash: 1e50e997dd6a64ac20b06c4a2717f10716642607c815dc12a9732dd64a419c93
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53888819"
---
# <a name="get-incident-information-api"></a>获取事件信息 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

按 ID 检索特定事件

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。

权限类型|权限|权限显示名称
---|---|---
应用程序|Incident.Read.All|"读取所有事件"
应用程序|Incident.ReadWrite.All|"读取和写入所有事件"
委派（工作或学校帐户）|Incident.Read|"读取事件"
委派（工作或学校帐户）|Incident.ReadWrite|"读取和写入事件"

> [!NOTE]
>
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："查看数据"
> - 响应将仅包括用户向其中公开的事件

## <a name="http-request"></a>HTTP 请求

```console
GET .../api/incidents/{id}
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
---|---|---
Authorization|String|Bearer {token}。 **必需**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 200 OK 和事件实体。
如果未找到具有指定 ID 的事件 - 404 未找到。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
