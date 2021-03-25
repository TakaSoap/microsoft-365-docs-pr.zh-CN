---
title: 获取 RBAC 计算机组集合 API
description: 了解如何使用获取 KB 集合 API 在 Microsoft Defender 高级威胁防护中检索 RBAC 设备组的集合。
keywords: api， 图形 api， 受支持的 api， 获取， RBAC， 组
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166427"
---
# <a name="get-kb-collection-api"></a>获取 KB 集合 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


检索 RBAC 设备组的集合。

## <a name="permissions"></a>权限
用户需要读取权限。

## <a name="http-request"></a>HTTP 请求
```
GET /testwdatppreview/machinegroups
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
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

**响应**

下面是一个响应示例。
字段 ID 包含设备组 **ID，** 并且等于设备信息中的字段 **rbacGroupId。** 只有 **对于尚未** 分配到任何组的所有设备的一个组，取消分组的字段才为 true。 像往常一样，此组的名称为"UnassignedGroup"。

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
