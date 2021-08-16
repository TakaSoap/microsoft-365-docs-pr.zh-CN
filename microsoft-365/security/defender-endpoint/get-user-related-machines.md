---
title: 获取与用户相关的计算机 API
description: 了解如何使用获取与用户相关的计算机 API 检索与 Microsoft Defender for Endpoint 中的用户 ID 相关的设备集合。
keywords: api， 图形 api， 受支持的 api， 获取， 用户， 用户相关警报
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
ms.openlocfilehash: c0337c83419e2584c779abdd1bc88b75e6c1a63a5c7cc38fe1a719a6d6908029
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53894379"
---
# <a name="get-user-related-machines-api"></a>获取与用户相关的计算机 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明
检索与给定用户 ID 相关的设备的集合。

## <a name="limitations"></a>限制

此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序 |Machine.Read.All|"读取所有计算机配置文件"
应用程序 |Machine.ReadWrite.All |"读取和写入所有计算机信息"
委派（工作或学校帐户） | Machine.Read | "读取计算机信息"
委派（工作或学校帐户） | Machine.ReadWrite | "读取和写入计算机信息"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："查看数据"。 有关详细信息，请参阅创建 [和管理角色](user-roles.md)) 
> - 响应将仅包括用户可以基于设备组设置访问的设备。 有关详细信息，请参阅创建 [和管理设备组](machine-groups.md)。

## <a name="http-request"></a>HTTP 请求

```http
GET /api/users/{id}/machines
```

**ID 不是完整的 UPN，而只是用户名。 (，若要检索供用户 user1@contoso.com /api/users/user1/machines)**

## <a name="request-headers"></a>请求头

名称|类型|说明
:---|:---|:---
Authorization | String | Bearer {token}。 **必需**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且用户存在 - 200 正常[](machine.md)，正文中包含计算机实体列表。 如果用户不存在 - 404 未找到。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
