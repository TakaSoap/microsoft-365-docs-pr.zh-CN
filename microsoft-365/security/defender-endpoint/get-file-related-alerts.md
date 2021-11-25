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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 04a10bc02800cbd9d0b3bfb8ddc1920b368052a2
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168974"
---
# <a name="get-file-related-alerts-api"></a>获取与文件相关的警报 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

检索与给定文件哈希相关的警报集合。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。
2. 只有 SHA-1 哈希函数 (MD5 或 SHA-256) 。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅对 [终结点 API 使用 Defender](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
Application|Alert.Read.All|"读取所有警报"
Application|Alert.ReadWrite.All|"读取和写入所有警报"
委派（工作或学校帐户）|Alert.Read|"读取警报"
委派（工作或学校帐户）|Alert.ReadWrite|"读取和写入警报"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)
> - 响应将仅包含与设备关联的警报，根据设备组设置 (请参阅创建和管理设备组，了解) [](machine-groups.md)

## <a name="http-request"></a>HTTP 请求

```http
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 必需。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且文件存在 - 200 正常，正文中 [具有](alerts.md) 警报实体列表。 如果文件不存在 - 200 确定，但为空集。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```
