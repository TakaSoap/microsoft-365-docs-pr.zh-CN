---
title: 获取 KB 集合 API
description: 使用 Microsoft Defender for Endpoint 检索知识库 (KB) 和 KB 详细信息。
keywords: api， 图形 api， 受支持的 api， 获取， kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 22faf080245598957a90122a3ea6b4c5cf3faca4
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622096"
---
# <a name="get-kb-collection-api"></a>获取 KB 集合 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

检索 KB 和 KB 详细信息的集合。

## <a name="permissions"></a>权限

用户需要读取权限。

## <a name="http-request"></a>HTTP 请求

```http
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a>请求标头

标头|值 
:---|:---
Authorization|Bearer {token}。 **必需**。
内容类型|application/json

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功 - 200 正常。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        ...
}
```
