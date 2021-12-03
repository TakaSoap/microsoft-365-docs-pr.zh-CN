---
title: 获取计算机相关警报 API
description: 了解如何使用获取计算机相关警报 API。 此 API 允许你检索与 Microsoft Defender for Endpoint 中的特定设备相关的所有警报。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 相关， 警报
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
ms.openlocfilehash: 49cc0fca3ae7617b86ab079daace92eb3790db94
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283505"
---
# <a name="get-machine-related-alerts--api"></a>获取计算机相关警报 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：** 
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

检索 [与特定](alerts.md) 设备相关的所有警报。

## <a name="limitations"></a>限制

1. 你可以根据配置的保留期查询上次更新的设备。
2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Alert.Read.All|"读取所有警报"
应用程序|Alert.ReadWrite.All|"读取和写入所有警报"
委派（工作或学校帐户） | Alert.Read | "读取警报"
委派（工作或学校帐户） | Alert.ReadWrite | "读取和写入警报"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："查看数据"。 有关权限详细信息，请参阅创建 [和管理角色](user-roles.md)。
> - 用户需要基于设备组设置访问设备。 有关设备组设置详细信息，请参阅 [创建和管理设备组](machine-groups.md)。

## <a name="http-request"></a>HTTP 请求

```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization | String | Bearer {token}。 必需。

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且设备存在：200 正常，正文[](alerts.md)中具有警报实体列表。 如果未找到设备：404 未找到。
