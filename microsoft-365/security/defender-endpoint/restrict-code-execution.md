---
title: 限制应用执行 API
description: 使用此 API 创建与限制应用程序执行相关的调用。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7195e91a3a9b7aef6977c925f2c8689d3e461815
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771569"
---
# <a name="restrict-app-execution-api"></a>限制应用执行 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 说明
限制设备上除预定义集之外的所有应用程序的执行。


## <a name="limitations"></a>限制
1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>权限
若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   Machine.RestrictExecution | "限制代码执行"
委派（工作或学校帐户） | Machine.RestrictExecution | "限制代码执行"

>[!Note]
> 使用用户凭据获取令牌时：
>- 用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)
>- 用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
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
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- 若要从设备中删除代码执行限制，请参阅删除 [应用限制](unrestrict-code-execution.md)。
