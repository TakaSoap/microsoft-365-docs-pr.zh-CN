---
title: Microsoft 365 Defender高级搜寻 API
description: 了解如何使用Microsoft 365 Defender的高级搜寻 API 运行高级搜寻查询
keywords: 高级搜寻，API，api，M365 Defender，Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: d01cdacc40b58eb940b2773606221b4fdbe18728
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823181"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender高级搜寻 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

[高级搜寻](advanced-hunting-overview.md)是一种威胁搜寻工具，它使用[专门构造的查询](advanced-hunting-query-language.md)来检查Microsoft 365 Defender中过去 30 天的事件数据。 可以使用高级搜寻查询来检查异常活动、检测可能的威胁，甚至响应攻击。 高级搜寻 API 允许以编程方式查询事件数据。

## <a name="quotas-and-resource-allocation"></a>配额和资源分配

以下条件与所有查询相关。

1. 查询会浏览并返回过去 30 天内的数据。
2. 结果最多可以返回 100，000 行。
3. 每个租户每分钟最多可以拨打 45 个电话。
4. 如果租户已达到 100%，查询将受到阻止，直到下一个 15 分钟周期。
5. 如果单个请求运行超过 10 分钟，则会超时并返回错误。
6. `429` HTTP 响应代码指示已按发送的请求数或分配的运行时间达到配额。 读取响应正文以了解已达到的限制。 

> [!NOTE]
> 上面列出的所有配额 (例如，每分钟 15 次调用) 为每个租户大小。 这些配额是最低的。

## <a name="permissions"></a>权限

调用高级搜寻 API 需要以下权限之一。 若要了解详细信息，包括如何选择权限，请[参阅“访问Microsoft 365 Defender保护 API](api-access.md)

权限类型 | 权限 | 权限显示名称
-|-|-
应用程序 | AdvancedHunting.Read.All| 运行高级查询
委派（工作或学校帐户） | AdvancedHunting.Read | 运行高级查询

>[!Note]
> 使用用户凭据获取令牌时：
>
>- 用户需要具有“查看数据”AD 角色
>- 用户需要根据设备组设置访问设备。

## <a name="http-request"></a>HTTP 请求

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>请求标头

标头 | 值
-|-
Authorization | 持有者 {token} **注意：必需**
Content-Type | application/json

## <a name="request-body"></a>请求正文

在请求正文中，提供具有以下参数的 JSON 对象：

参数 | 类型 | 说明
-|-|-
查询 | 文本 | 要运行的查询。 **注意：必需**

## <a name="response"></a>响应

如果成功，此方法将返回，并在响应正文中返回 `200 OK`一个 _QueryResponse_ 对象。

响应对象包含三个顶级属性：

1. 统计信息 - 查询性能统计信息的字典。
2. 架构 - 响应的架构，每个列的Name-Type对列表。
3. 结果 - 高级搜寻事件的列表。

## <a name="example"></a>示例

在下面的示例中，用户发送以下查询并接收包含`Stats``Schema``Results`和接收的 API 响应对象。

### <a name="query"></a>查询

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a>Response 对象

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a>相关文章

- [访问Microsoft 365 Defender API](api-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [高级搜寻概述](advanced-hunting-overview.md)
