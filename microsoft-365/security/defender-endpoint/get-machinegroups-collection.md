---
title: 获取 RBAC 计算机组集合 API
description: 了解如何使用获取 KB 集合 API 在 Microsoft Defender for Endpoint 中检索 RBAC 设备组的集合。
keywords: api， 图形 api， 受支持的 api， 获取， RBAC， 组
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
ms.date: 10/07/2018
ms.openlocfilehash: 7ce84e35f2a5ece81b1cb70436c6c75a940c99b9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207015"
---
# <a name="get-kb-collection-api"></a>获取 KB 集合 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

检索 RBAC 设备组的集合。

## <a name="permissions"></a>权限

用户需要读取权限。

## <a name="http-request"></a>HTTP 请求

```http
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a>请求标头

标头|值
:---|:---
Authorization | Bearer {token}。 **必需**。
内容类型 | application/json

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功 - 200 正常。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

### <a name="response-example"></a>响应示例

下面是一个响应示例。
字段 ID 包含设备组 **ID，** 并且等于设备信息中的字段 **rbacGroupId。**
只有 **对于尚未** 分配到任何组的所有设备的一个组，取消分组的字段才为 true。 像往常一样，此组的名称为"UnassignedGroup"。

```http
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
        ...
}
```
