---
title: Microsoft 365 Defender高级搜寻 API
description: 了解如何使用 Microsoft 365 Defender 高级搜寻 API 运行高级搜寻查询
keywords: 高级搜寻， API， api， M365 Defender， Microsoft 365 Defender
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
ms.openlocfilehash: 05957fcf7cf2b3b03fbc757fc8b21e67156b285a
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500818"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender高级搜寻 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

[高级搜寻](advanced-hunting-overview.md)是一种威胁搜寻工具，它[](advanced-hunting-query-language.md)使用专门构造的查询来检查过去 30 天内Microsoft 365 Defender。 可以使用高级搜寻查询来检查异常活动、检测可能的威胁，甚至响应攻击。 高级搜寻 API 允许你以编程方式查询事件数据。

## <a name="quotas-and-resource-allocation"></a>配额和资源分配

下列条件与所有查询相关。

1. 查询将浏览并返回过去 30 天的数据。
2. 结果最多返回 100，000 行。
3. 每个租户每分钟最多可以拨打 45 个呼叫。
4. 如果租户已达到 100%，查询将受到阻止，直到下一个 15 分钟周期。
5. 如果单个请求运行的时间超过 10 分钟，它将退出并返回错误。
6. HTTP `429` 响应代码指示你已按发送的请求数或按分配的运行时间达到配额。 阅读响应正文，了解已达到的限制。 

> [!NOTE]
> 上面列出的所有配额 (例如，每个租户大小每) 15 个呼叫。 这些配额是最小值。

## <a name="permissions"></a>Permissions

调用高级搜寻 API 需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅[访问 Microsoft 365 Defender 保护 API](api-access.md)

权限类型 | 权限 | 权限显示名称
-|-|-
应用程序 | AdvancedQuery.Read.All| 运行高级查询
委派（工作或学校帐户） | AdvancedQuery.Read | 运行高级查询

>[!Note]
> 使用用户凭据获取令牌时：
>
>- 用户需要具有"查看数据"AD 角色
>- 用户需要基于设备组设置访问设备。

## <a name="http-request"></a>HTTP 请求

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>请求标头

标头 | 值
-|-
Authorization | Bearer {token} **注意：必需**
Content-Type | application/json

## <a name="request-body"></a>请求正文

在请求正文中，提供具有以下参数的 JSON 对象：

参数 | 类型 | Description
-|-|-
查询 | 文本 | 要运行的查询。 **注意：必需**

## <a name="response"></a>响应

如果成功，此方法将在响应正文 `200 OK`中返回 和 _QueryResponse_ 对象。

response 对象包含三个顶级属性：

1. Stats - 查询性能统计信息的字典。
2. Schema - 响应的架构，每个列Name-Type对的列表。
3. 结果 - 高级搜寻事件列表。

## <a name="example"></a>示例

在下面的示例中，用户发送下面的查询并接收包含 、 和 的 API `Stats``Schema`响应对象`Results`。

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
