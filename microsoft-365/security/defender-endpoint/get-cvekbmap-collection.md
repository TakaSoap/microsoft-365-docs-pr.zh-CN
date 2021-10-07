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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 3921f79172bbbcc32b8510809b54bec477e44b85
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192839"
---
# <a name="get-cve-kb-map-api"></a>获取 CVE-KB 地图 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

检索 CVE 到 KB 和 CVE 详细信息的地图。

## <a name="permissions"></a>权限

用户需要读取权限。

## <a name="http-request"></a>HTTP 请求

```http
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a>请求标头

标头|值
:---|:---
Authorization|Bearer {token}。 **必需**。
内容类型|application/json

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且存在映射 - 200 正常。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

### <a name="response-example"></a>响应示例

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
    ...
}
```
