---
title: 列出软件版本分发
description: 检索组织的软件版本分布列表
keywords: api， 图形 api， 受支持的 api， 获取， 软件版本分发， Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845002"
---
# <a name="list-software-version-distribution"></a>列出软件版本分发 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

检索组织的软件版本分布列表。 

## <a name="permissions"></a>权限
若要调用此 API，需要以下权限之一。 若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 | Software.Read.All | "读取威胁和漏洞管理软件信息"
委派（工作或学校帐户） | Software.Read | "读取威胁和漏洞管理软件信息"

## <a name="http-request"></a>HTTP 请求
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a>请求标头

| 名称        | 类型 | 说明
|:--------------|:-------|:--------------|
| Authorization | String | Bearer {token}。**必需**。

## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功，此方法返回 200 OK，并返回正文中的软件分发数据列表。 


## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

**响应**

下面是一个响应示例。

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a>相关主题
- [基于风险的威胁&漏洞管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威胁&漏洞软件清单](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
