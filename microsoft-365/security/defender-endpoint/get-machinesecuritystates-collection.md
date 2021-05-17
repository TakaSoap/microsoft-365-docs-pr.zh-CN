---
title: 获取计算机安全状态集合 API
description: 使用 Microsoft Defender for Endpoint 检索设备安全状态的集合。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 安全性， 状态
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200361"
---
# <a name="get-machines-security-states-collection-api"></a>获取计算机安全状态集合 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

检索设备安全状态的集合。

## <a name="permissions"></a>Permissions
用户需要读取权限。

## <a name="http-request"></a>HTTP 请求
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a>请求标头

标头 | 值 
:---|:---
Authorization | Bearer {token}。 **必需**。
内容类型 | application/json

## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功 - 200 正常。

## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

**响应**

下面是一个响应示例。
字段 *ID* 包含设备 ID，并且等于设备信息中的字段 *ID**。 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
