---
title: 列出计算机 API
description: 了解如何使用列出计算机 API 检索已与 Microsoft Defender for Endpoint 云通信的计算机集合。
keywords: api， 图形 api， 受支持的 api， 获取， 设备
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f06973bc45ecac05c15d48afe5f0e2e9e7788f78
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770741"
---
# <a name="list-machines-api"></a>列出计算机 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明
检索 [已与](machine.md) Microsoft Defender for Endpoint 云通信的计算机集合。
<br>支持 [OData V4 查询](https://www.odata.org/documentation/)。
<br>OData 的 `$filter` 查询在 上受支持 `computerDnsName` `lastSeen` ：、、、、 `healthStatus` `osPlatform` 和 `riskScore` `rbacGroupId` 。
<br>有关示例， [请参阅使用 Defender for Endpoint 的 OData 查询](exposed-apis-odata-samples.md)


## <a name="limitations"></a>限制
1. 你可以根据配置的保留期获取最后一次看到的设备。
2. 最大页面大小为 10，000。
3. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。 


## <a name="permissions"></a>权限

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   Machine.Read.All |  "读取所有计算机配置文件"
应用程序 |   Machine.ReadWrite.All | "读取和写入所有计算机信息"
委派（工作或学校帐户） | Machine.Read | "读取计算机信息"
委派（工作或学校帐户） | Machine.ReadWrite | "读取和写入计算机信息"

>[!Note]
> 使用用户凭据获取令牌时：
>- 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)
>- 响应将仅包括用户有权访问的设备，根据设备组设置 (请参阅创建和管理设备组，了解) [](machine-groups.md)

## <a name="http-request"></a>HTTP 请求

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | String | Bearer {token}。 **必需**。


## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功且计算机存在 - 200 正常，正文中 [包含](machine.md) 计算机实体列表。 如果没有最近的计算机 - 404 未找到。


## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

**响应**

下面是一个响应示例。

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2018-08-02T14:55:03.7791856Z",
            "osPlatform": "Windows10",
            "version": "1709",
            "osProcessor": "x64",
            "lastIpAddress": "172.17.230.209",
            "lastExternalIpAddress": "167.220.196.71",
            "osBuild": 18209,
            "healthStatus": "Active",
            "rbacGroupId": 140,
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Medium",
            "isAadJoined": true,
            "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
            "machineTags": [ "test tag 1", "test tag 2" ]
        }
        ...
    ]
}
```

## <a name="related-topics"></a>相关主题
- [使用 Microsoft Defender for Endpoint 的 OData 查询](exposed-apis-odata-samples.md)
