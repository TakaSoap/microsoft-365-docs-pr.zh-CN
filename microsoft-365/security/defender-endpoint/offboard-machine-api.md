---
title: 载出计算机 API
description: 了解如何使用 API 从 Microsoft Defender for Endpoint 中将设备从设备上载出。
keywords: api， 图形 api， 受支持的 api， 收集调查包
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
ms.technology: mde
ms.openlocfilehash: 03a1ef11224021703a6f33f82fa2c4f135a317a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934173"
---
# <a name="offboard-machine-api"></a>载出计算机 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 说明
从 Defender for Endpoint 载出设备。


## <a name="limitations"></a>限制
 - 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> 此 API 在 Windows 10 版本 1703 及更高版本或 Windows Server 2019 及更高版本上受支持。 此 API 在 MacOS 或 Linux 设备上不受支持。

## <a name="permissions"></a>权限
若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   Machine.Offboard |  "载出计算机"
委派（工作或学校帐户） |    Machine.Offboard |  "载出计算机"

>[!Note]
> 使用用户凭据获取令牌时：
>- 用户需要"全局管理员"AD 角色
>- 用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | String | Bearer {token}。 **必需**。
Content-Type | string | application/json. **必需**。

## <a name="request-body"></a>请求正文
在请求正文中，提供具有以下参数的 JSON 对象：

参数 | 类型    | 说明
:---|:---|:---
评论 |   字符串 |    要与操作关联的注释。 **必需**。

## <a name="response"></a>响应
如果成功，此方法在响应正文中返回 201 - 已创建响应 [代码和计算机](machineaction.md) 操作。


## <a name="example"></a>示例

**请求**

下面是一个请求示例。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
