---
title: 获取 CVE-KB 地图 API
description: 了解如何使用获取 CVE-KB 映射 API 在 Microsoft Defender for Endpoint 中检索 CVE 到 KB 的映射和 CVE 详细信息。
keywords: api， 图形 api， 受支持的 api， get， cve， kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166328"
---
# <a name="get-cve-kb-map-api"></a>获取 CVE-KB 地图 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

检索 CVE 到 KB 和 CVE 详细信息的地图。

## <a name="permissions"></a>Permissions
用户需要读取权限。

## <a name="http-request"></a>HTTP 请求
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>请求标头

标头 | 值 
:---|:---
Authorization | Bearer {token}。 **必需**。
内容类型 | application/json

## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功且存在映射 - 200 正常。

## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

**响应**

下面是一个响应示例。

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
