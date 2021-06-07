---
title: 高级搜寻 API
ms.reviewer: ''
description: 了解如何使用高级搜寻 API 在 Microsoft Defender for Endpoint 上运行高级查询。 了解限制并查看示例。
keywords: api， 受支持的 api， 高级搜寻， 查询
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
ms.openlocfilehash: 0173e271967a1b5b18d69713e9e6540e9cd11a87
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772397"
---
# <a name="advanced-hunting-api"></a>高级搜寻 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a>限制

1. 只能对过去 30 天的数据运行查询。

2. 结果最多包含 100，000 行。

3. 每个租户的执行次数受到限制：
   - API 调用：每分钟最多 45 个调用，每小时最多 1500 个调用。
   - 执行时间：每小时运行 10 分钟，一天运行 3 小时。

4. 单个请求的最大执行时间为 10 分钟。

5. 429 响应表示达到请求数或 CPU 的配额限制。 读取响应正文，了解已达到的限制。 

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   AdvancedQuery.Read.All |    "运行高级查询"
委派（工作或学校帐户） | AdvancedQuery.Read | "运行高级查询"

>[!Note]
> 使用用户凭据获取令牌时：
>- 用户需要具有"查看数据"AD 角色
>- 用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a>请求标头

标头 | 值 
:---|:---
Authorization | Bearer {token}。 **必需**。
Content-Type    | application/json

## <a name="request-body"></a>请求正文

在请求正文中，提供具有以下参数的 JSON 对象：

参数 | 类型    | 说明
:---|:---|:---
查询 | 文本 |  要运行的查询。 **必需**。

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 200 OK 和 _QueryResponse_ 对象。


## <a name="example"></a>示例

##### <a name="request"></a>请求

下面是一个请求示例。

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a>响应

下面是一个响应示例。

>[!NOTE]
>为简洁起见，可能会截断此处所示的响应对象。 所有属性都将通过实际调用返回。

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a>相关主题

- [Microsoft Defender for Endpoint API 简介](apis-intro.md)
- [门户中的高级搜寻](advanced-hunting-query-language.md)
- [通过 PowerShell 高级搜寻](run-advanced-query-sample-powershell.md)
