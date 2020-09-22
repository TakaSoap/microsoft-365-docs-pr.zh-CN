---
title: 高级搜寻 Api
description: 了解如何使用 Microsoft 威胁防护 API 运行高级搜寻查询
keywords: 高级搜寻、Api、api、MTP
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
ms.openlocfilehash: dd7b02200e370588bbb9470a3d7e897b30234ead
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197805"
---
# <a name="advanced-hunting-apis"></a>高级搜寻 Api

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

>[!IMPORTANT] 
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="limitations"></a>限制
1. 只能对最近30天的数据运行查询。
2. 结果将包含最多100000行。
3. 对每个租户执行的次数限制为：每分钟最多10个呼叫、每小时运行时间为10分钟，每小时运行一次，运行时间为4小时。
4. 单个请求的最大执行时间为10分钟。
5. 429响应将表示通过请求数或 CPU 达到配额限制。 429响应正文也会指示续订配额前的时间。 


## <a name="permissions"></a>权限
若要调用此 API，必须有以下权限之一。 若要了解详细信息，包括如何选择权限，请参阅 [访问 Microsoft 威胁防护 api](api-access.md)

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   AdvancedHunting |  "运行高级查询"
委派（工作或学校帐户） | AdvancedHunting。请阅读 | "运行高级查询"

>[!Note]
> 使用用户凭据获取令牌时：
>- 用户需要具有 "查看数据" AD 角色
>- 用户需要具有基于设备组设置的设备的访问权限。

## <a name="http-request"></a>HTTP 请求
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>请求标头

标头 | 值 
:---|:---
Authorization | 持有者 {令牌}。 **** 必需。
Content-Type    | application/json

## <a name="request-body"></a>请求正文
在请求正文中，提供具有以下参数的 JSON 对象：

参数 | 类型    | 说明
:---|:---|:---
查询 | 文本 |  要运行的查询。 **** 必需。

## <a name="response"></a>响应
如果成功，此方法在响应正文中返回 200 OK 和 _类_ 对象。 <br><br>

Response 对象分为3个部分 (属性) ：<br>
1) ```Stats``` -查询性能统计信息。<br>
2) ```Schema``` -响应的架构，每个列的名称类型对的列表。 <br>
3) ```Results``` -高级搜寻事件的列表。

## <a name="example"></a>示例

请求

下面是一个请求示例。


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

响应

下面是一个响应示例。


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

## <a name="related-topic"></a>相关主题
- [访问 Microsoft 威胁防护 Api](api-access.md)
