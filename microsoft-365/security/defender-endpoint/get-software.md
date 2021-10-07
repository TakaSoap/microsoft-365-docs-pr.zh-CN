---
title: 列出软件
description: 检索软件清单列表
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 软件清单， 威胁& 漏洞管理 api， Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ada4ebd15d9a84241ca68b6e2664475f97ab7d6f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191823"
---
# <a name="list-software-inventory-api"></a>列出软件清单 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

检索组织软件清单。
<br>支持 [OData V4 查询](https://www.odata.org/documentation/)。
<br>OData 支持的运算符：
<br>```$filter``` on：  ```id``` ```name``` 、 和 ```vendor``` 属性。
<br>```$top``` 最大值为 10，000。
<br>```$skip```.
<br>请参阅 Microsoft [Defender for Endpoint 的 OData 查询示例](exposed-apis-odata-samples.md)。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。

权限类型|权限|权限显示名称
:---|:---|:---
Application|Software.Read.All|"读取威胁和漏洞管理软件信息"
委派（工作或学校帐户）|Software.Read|"读取威胁和漏洞管理软件信息"

## <a name="http-request"></a>HTTP 请求

```http
GET /api/Software
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|字符串|Bearer {token}。 必需。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功，此方法在正文中返回软件清单为 200 OK。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/Software
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a>相关主题

- [基于风险的威胁&漏洞管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威胁&漏洞软件清单](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
