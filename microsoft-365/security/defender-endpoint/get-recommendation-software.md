---
title: 获取软件建议
description: 检索与特定软件相关的安全建议。
keywords: api， 图形 api， 受支持的 api， 获取， 安全建议， 软件的安全建议， 威胁和漏洞管理， 威胁和漏洞管理 api
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
ms.openlocfilehash: 82479b0248ceee95321d269e3f48a4eeea3ad193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199497"
---
# <a name="get-recommendation-by-software"></a>获取软件建议

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

检索与特定软件相关的安全建议。

## <a name="permissions"></a>权限
若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   SecurityRecommendation.Read.All |   "读取威胁和漏洞管理安全建议信息"
委派（工作或学校帐户） | SecurityRecommendation.Read |  "读取威胁和漏洞管理安全建议信息"

## <a name="http-request"></a>HTTP 请求
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | 字符串 | Bearer {token}。 **必需**。


## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功，此方法返回 200 OK，并返回与正文中的安全建议关联的软件。


## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

**响应**

下面是一个响应示例。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a>相关主题
- [基于风险的威胁&漏洞管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威胁&漏洞安全建议](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
