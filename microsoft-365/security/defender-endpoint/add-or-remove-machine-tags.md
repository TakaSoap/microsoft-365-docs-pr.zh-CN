---
title: 添加或删除计算机标记 API
description: 了解如何使用添加或删除计算机标记 API 在 Microsoft Defender for Endpoint 中添加或删除计算机标记。
keywords: api， 图形 api， 受支持的 api， 标记， 计算机标记
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2ec34011d00e77c5e32f58567a0b705cf7c0dc1c
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301121"
---
# <a name="add-or-remove-machine-tags-api"></a>添加或删除计算机标记 API

**适用于：**

- [Microsoft Defender for Endpoint 计划 1 ](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2 ](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

向特定计算机添加或删除 [标记](machine.md)。

## <a name="limitations"></a>限制

1. 你可以根据配置的保留期在上次看到的计算机上发布。

2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Machine.ReadWrite.All|"读取和写入所有计算机信息"
委派（工作或学校帐户）|Machine.ReadWrite|"读取和写入计算机信息"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："管理安全性设置"。 有关详细信息 (请参阅 [创建和管理角色，](user-roles.md) 了解) 
> - 用户需要具有计算机访问权限，根据计算机组设置 [ (创建和管理](machine-groups.md) 计算机组，了解详细信息) 

## <a name="http-request"></a>HTTP 请求

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 必需。
Content-Type|string|application/json. 必需。

## <a name="request-body"></a>请求正文

在请求正文中，提供具有以下参数的 JSON 对象：

参数|类型|说明
:---|:---|:---
值|String|标记名称。 必需。
操作|枚举|添加或删除。 允许的值包括："Add"或"Remove"。 必需。

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 200 - 正常响应代码和更新的 Machine。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是添加计算机标记的请求示例。

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- 若要删除计算机标记，在请求正文中将 Action 设置为"Remove"而不是"Add"。
