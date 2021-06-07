---
title: 按 Id 获取建议
description: 按 ID 检索安全建议。
keywords: api， 图形 api， 受支持的 api， 获取， 安全建议， 按 ID 的安全建议， 危险和漏洞管理， 危险和漏洞管理 api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4ec4758453f43cb211143918ed5fe8fe83e91c3f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771797"
---
# <a name="get-recommendation-by-id"></a>按 ID 获取建议

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

按 ID 检索安全建议。

## <a name="permissions"></a>权限
若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   SecurityRecommendation.Read.All |   "读取威胁和漏洞管理安全建议信息"
委派（工作或学校帐户） | SecurityRecommendation.Read |  "读取威胁和漏洞管理安全建议信息"

## <a name="http-request"></a>HTTP 请求
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | String | Bearer {token}。 **必需**。


## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功，此方法在正文中返回 200 OK 以及安全建议。


## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

**响应**

下面是一个响应示例。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a>相关主题
- [基于风险的威胁&漏洞管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威胁&漏洞安全建议](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
