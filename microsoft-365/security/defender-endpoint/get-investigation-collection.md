---
title: 列表调查 API
description: 使用此 API 创建与获取调查集合相关的调用
keywords: api， 图形 api， 受支持的 api， 调查集合
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
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770141"
---
# <a name="list-investigations-api"></a>列表调查 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 说明
检索调查 [的集合](investigation.md)。
<br>支持 [OData V4 查询](https://www.odata.org/documentation/)。
<br>OData 的 ```$filter``` 查询在： 、 ```startTime``` 和 ```state``` ```machineId``` 属性上 ```triggeringAlertId``` 受支持。
<br>请参阅 Microsoft [Defender for Endpoint 的 OData 查询示例](exposed-apis-odata-samples.md)


## <a name="limitations"></a>限制
1. 最大页面大小为 10，000。
2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。 


## <a name="permissions"></a>权限
若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   Alert.Read.All |    "读取所有警报"
应用程序 |   Alert.ReadWrite.All |   "读取和写入所有警报"
委派（工作或学校帐户） | Alert.Read | "读取警报"
委派（工作或学校帐户） | Alert.ReadWrite | "读取和写入警报"

>[!Note]
> 使用用户凭据获取令牌时：
>- 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)

## <a name="http-request"></a>HTTP 请求
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | String | Bearer {token}。 **必需**。


## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功，此方法将返回包含调查实体集合的 200 正常 [响应](investigation.md) 代码。


## <a name="example"></a>示例

**请求**

下面是请求获取所有调查的示例： 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

**响应**

下面是一个响应示例：

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
