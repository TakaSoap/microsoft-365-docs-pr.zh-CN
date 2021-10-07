---
title: 通过计算机和软件获取所有漏洞
description: 检索计算机和软件影响组织的所有漏洞的列表
keywords: api， 图形 api， 受支持的 api， 获取， 漏洞信息， Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 75194ec1c0d549ba5bb8727db31e182a381187f8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162634"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a>按计算机和软件列出漏洞

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

检索每台计算机和软件影响组织的所有[漏洞](machine.md)[的列表](software.md)。

- 如果漏洞具有修复 KB，它将出现在响应中。
- 支持 [OData V4 查询](https://www.odata.org/documentation/)。
- OData 的 `$filter` 查询受以下项支持：、、、、、 `id` `cveId` `machineId` `fixingKbId` `productName` `productVersion` `severity` 和 `productVendor` 属性。
<br>```$stop``` 最大值为 10，000
<br>```$skip```

> [!TIP]
> 这是适用于集成Power BI [API。](api-power-bi.md)

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。

权限类型|权限|权限显示名称
:---|:---|:---
Application|Vulnerability.Read.All|"读取威胁和漏洞管理漏洞信息"
委派（工作或学校帐户）|Vulnerability.Read|"读取威胁和漏洞管理漏洞信息"

## <a name="http-request"></a>HTTP 请求

```http
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 **必需**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功，此方法在正文中返回 200 OK 和漏洞列表。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a>另请参阅

- [基于风险危险和漏洞管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [组织中漏洞](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
