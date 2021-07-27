---
title: 启动调查 API
description: 使用此 API 在设备上开始调查。
keywords: api， 图形 api， 受支持的 api， 调查
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
ms.openlocfilehash: f02542b7ec7cae91d36420b03b245195b500248d
ms.sourcegitcommit: bef7bd019531317d083c1125f7d339750c450b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587653"
---
# <a name="start-investigation-api"></a>启动调查 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

在设备上启动自动调查。

有关详细信息 [，请参阅自动](automated-investigations.md) 调查概述。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每小时 50 次调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Alert.ReadWrite.All|"读取和写入所有警报"
委派（工作或学校帐户）|Alert.ReadWrite|"读取和写入警报"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："活动修正操作" (有关详细信息，请参阅创建和管理) [](user-roles.md)
> - 用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求

```http
POST https://api.security.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|字符串|Bearer {token}。 **必需**。
Content-Type|string|application/json. **必需**。

## <a name="request-body"></a>请求正文

在请求正文中，提供具有以下参数的 JSON 对象：

参数|类型|说明
:---|:---|:---
评论|字符串|要与操作关联的注释。 **必需**。

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 201 - [已创建响应](investigation.md) 代码和调查。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```https
POST https://api.security.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
