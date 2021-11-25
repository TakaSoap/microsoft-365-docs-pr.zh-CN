---
title: 按内部 IP API 查找设备
description: 查找在给定时间戳之前和之后 15 分钟的时间范围内使用请求的内部 IP 查看的设备
keywords: api， 图形 api， 受支持的 api， 获取， 设备， IP， 查找， 查找设备， 按 ip， ip
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
ms.openlocfilehash: 6f8040ce207faef8ec802ddb637b97917c822801
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168686"
---
# <a name="find-devices-by-internal-ip-api"></a>按内部 IP API 查找设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：** 
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

查找 [在](machine.md) 给定时间戳之前和之后 15 分钟的时间范围内使用请求的内部 IP 看到的计算机。

## <a name="limitations"></a>限制

1. 给定的时间戳必须过去 30 天。
2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
Application|Machine.Read.All|"读取所有计算机配置文件"
Application|Machine.ReadWrite.All|"读取和写入所有计算机信息"
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
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 必需。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功 - 200 正常，响应正文中提供计算机列表。
如果时间戳不是过去 30 天 - 400 错误请求。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
