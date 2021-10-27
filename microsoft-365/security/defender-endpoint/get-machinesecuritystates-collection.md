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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: api
ms.openlocfilehash: af3881a5215871b0405f2f6b42b73c248af0c00c
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586869"
---
# <a name="get-machines-security-states-collection-api"></a>获取计算机安全状态集合 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

检索设备安全状态的集合。

## <a name="permissions"></a>权限

用户需要读取权限。

## <a name="http-request"></a>HTTP 请求

```http
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a>请求标头

标头|值
:---|:---
Authorization|Bearer {token}。 必需。
内容类型|application/json

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功 - 200 正常。

## <a name="example"></a>示例

### <a name="request-example"></a>请求示例

下面是一个请求示例。

```http
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

### <a name="response-example"></a>响应示例

以下是响应示例。

字段 *ID* 包含设备 ID，并且等于设备信息中的字段 *ID**。

```json
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
        ...
    ]
}
```
