---
title: Microsoft 365 Defender 高级搜寻 API
description: 了解如何使用 Microsoft 365 Defender 的高级搜寻 API 运行高级搜寻查询
keywords: 高级搜寻， API， api， MTP， M365 Defender， Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719376"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a>Microsoft 365 Defender 高级搜寻 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 威胁防护

> [!IMPORTANT]
> 某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

[高级搜寻](advanced-hunting-overview.md)是威胁搜寻工具，它使用专门[](advanced-hunting-query-language.md)构造的查询来检查 Microsoft 365 Defender 中过去 30 天的事件数据。 可以使用高级搜寻查询来检查异常活动、检测可能的威胁，甚至响应攻击。 高级搜寻 API 允许你以编程方式查询事件数据。

## <a name="quotas-and-resource-allocation"></a>配额和资源分配

下列条件与所有查询相关。

1. 查询将浏览并返回过去 30 天的数据。
2. 结果可返回最多 100，000 行。
3. 每个租户每分钟最多可以拨打 10 个呼叫。
4. 每个租户每小时有 10 分钟的运行时间。
5. 每个租户的运行时间总小时数为四小时。
6. 如果单个请求运行超过 10 分钟，它将退出并返回错误。
7. HTTP 响应代码指示你已按发送的请求数或分配的运行时间达到 `429` 配额。 响应正文将包括重置达到的配额之前的时间。

## <a name="permissions"></a>权限

调用高级搜寻 API 需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅 [Access the Microsoft 365 Defender Protection API](api-access.md)

权限类型 | 权限 | 权限显示名称
-|-|-
应用程序 | AdvancedHunting.Read.All | 运行高级查询
委派（工作或学校帐户） | AdvancedHunting.Read | 运行高级查询

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

参数 | 类型 | 说明
-|-|-
查询 | 文本 | 要运行的查询。 **注意：必需**

## <a name="response"></a>响应

如果成功，此方法将在响应正文中返回 `200 OK` 和 _QueryResponse_ 对象。

响应对象包含三个顶级属性：

1. Stats - 查询性能统计信息的字典。
2. Schema - 响应的架构，即每个Name-Type对的列表。
3. 结果 - 高级搜寻事件列表。

## <a name="example"></a>示例

在下面的示例中，用户发送下面的查询，并接收包含 、和 的 API 响应 `Stats` `Schema` 对象 `Results` 。

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

- [访问 Microsoft 365 Defender API](api-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
- [高级搜寻概述](advanced-hunting-overview.md)
