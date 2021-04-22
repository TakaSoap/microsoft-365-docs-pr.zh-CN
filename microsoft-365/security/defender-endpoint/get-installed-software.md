---
title: 获取已安装的软件
description: 检索与给定设备 ID 相关的已安装软件的集合。
keywords: api， 图形 api， 受支持的 api， 获取， 列表， 文件， 信息， 软件清单， 每个设备安装的软件， 威胁 & 漏洞管理 api， Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: ebd689fd53dd804f857c6bec7a412c27988835d0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935097"
---
# <a name="get-installed-software"></a>获取已安装的软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

检索与给定设备 ID 相关的已安装软件的集合。

## <a name="permissions"></a>权限
若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |Software.Read.All |    "读取威胁和漏洞管理软件信息"
委派（工作或学校帐户） | Software.Read |    "读取威胁和漏洞管理软件信息"

## <a name="http-request"></a>HTTP 请求
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | String | Bearer {token}。 **必需**。


## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功，此方法在正文中返回包含已安装软件信息的 200 OK。


## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

**响应**

下面是一个响应示例。


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a>另请参阅

- [基于风险的威胁&漏洞管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [威胁&漏洞软件清单](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
