---
title: 按标记 API 查找设备
description: 查找包含指定标记的所有设备
keywords: api， 受支持的 api， 获取， 设备， 查找， 查找设备， 按标记， 标记
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
ms.openlocfilehash: 93363ba9cb6252a32406c0c29dfb7d757d2f411d
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302190"
---
# <a name="find-devices-by-tag-api"></a>按标记 API 查找设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：** 
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

按[标记 查找](machine.md)[计算机](machine-tags.md)。

`startswith` 支持 查询。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Machine.Read.All|"读取所有计算机配置文件"
应用程序|Machine.ReadWrite.All|"读取和写入所有计算机信息"
委派（工作或学校帐户）|Machine.Read|"读取计算机信息"
委派（工作或学校帐户）|Machine.ReadWrite|"读取和写入计算机信息"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 响应将仅包括用户基于设备组设置有权访问的设备 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 
> - 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)
> - 响应将仅包括用户基于设备组设置有权访问的设备 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求

```http
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 必需。

## <a name="request-uri-parameters"></a>请求 URI 参数

名称|类型|说明
:---|:---|:---
tag|String|标记名称。 必需。
useStartsWithFilter|Boolean|设置为 true 时，搜索将查找标记名称以查询中的给定标记开头的所有设备。 默认值为 false。 **可选**。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功 - 200 正常，响应正文中提供计算机列表。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```
