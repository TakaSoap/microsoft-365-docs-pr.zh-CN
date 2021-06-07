---
title: 获取计算机相关警报 API
description: 了解如何使用获取计算机相关警报 API 检索与 Microsoft Defender for Endpoint 中的特定设备相关的所有警报。
keywords: api， 图形 api， 受支持的 api， 获取， 设备， 相关， 警报
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: bf445332fed7b8661c510bf60f36088b79e2d8df
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770021"
---
# <a name="get-machine-related-alerts--api"></a>获取计算机相关警报 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明
检索 [与特定](alerts.md) 设备相关的所有警报。


## <a name="limitations"></a>限制
1. 你可以根据配置的保留期查询上次更新的设备。
2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。


权限类型 |   权限  |   权限显示名称
:---|:---|:---
应用程序 |   Alert.Read.All |    "读取所有警报"
应用程序 |   Alert.ReadWrite.All |   "读取和写入所有警报"
委派（工作或学校帐户） | Alert.Read | "读取警报"
委派（工作或学校帐户） | Alert.ReadWrite | "读取和写入警报"

>[!Note]
> 使用用户凭据获取令牌时：
>- 用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)
>- 用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>请求标头

名称 | 类型 | 说明
:---|:---|:---
Authorization | String | Bearer {token}。 **必需**。


## <a name="request-body"></a>请求正文
Empty

## <a name="response"></a>响应
如果成功且设备存在 - 200 正常[](alerts.md)，正文中具有警报实体列表。 如果未找到设备 - 404 未找到。
