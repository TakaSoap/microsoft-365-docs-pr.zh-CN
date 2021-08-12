---
title: 获取与文件相关的警报 API
description: 了解如何使用获取与文件相关的警报 API 获取与 Microsoft Defender for Endpoint 中的给定文件哈希相关的警报集合。
keywords: api， 图形 api， 受支持的 api， 获取， 文件， 哈希
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
ms.openlocfilehash: f342a4a104fb908bc8b8c05d2d53d190de8d64c9a826fb87be641e63921bb456
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53793810"
---
# <a name="get-file-related-alerts-api"></a>获取与文件相关的警报 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

检索与给定文件哈希相关的警报集合。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Alert.Read.All|"读取所有警报"
应用程序|Alert.ReadWrite.All|"读取和写入所有警报"
委派（工作或学校帐户）|Alert.Read|"读取警报"
委派（工作或学校帐户）|Alert.ReadWrite|"读取和写入警报"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)
> - 根据设备组设置，响应将仅包含与设备关联的警报 (有关详细信息，请参阅创建和管理设备) [](machine-groups.md)

## <a name="http-request"></a>HTTP 请求

```http
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 **必需**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且文件存在 - 200 正常，正文中 [具有警报](alerts.md) 实体列表。 如果文件不存在 - 404 未找到。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```
