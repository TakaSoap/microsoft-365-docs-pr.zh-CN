---
title: 获取与域相关的警报 API
description: 了解如何使用获取域相关警报 API 检索与 Microsoft Defender for Endpoint 中的给定域地址相关的警报。
keywords: api， 图形 api， 受支持的 api， 获取， 域， 相关， 警报
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
ms.openlocfilehash: 176daff75e39f8ed4dda2854d3448cb9fbaa5dad
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211135"
---
# <a name="get-domain-related-alerts-api"></a>获取与域相关的警报 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明

检索与给定 [域](alerts.md) 地址相关的警报集合。

## <a name="limitations"></a>限制

1. 你可以根据配置的保留期查询上次更新的警报。
2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

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
> - 响应将仅包含与设备关联的警报，根据设备组设置 (请参阅创建和管理设备组，了解详细信息) [](machine-groups.md)

## <a name="http-request"></a>HTTP 请求

```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a>请求标头

|标头|值|
|---|---|
|Authorization|String|

## <a name="request-body"></a>请求正文

Empty

## <a name="response"></a>响应

如果成功且域存在 - 200 正常，警报 [实体](alerts.md) 列表可用。 如果域不存在 - 200 确定，但具有空集。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
