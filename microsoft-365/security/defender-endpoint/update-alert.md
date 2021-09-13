---
title: 更新警报实体 API
description: 了解如何使用此 API 更新 Microsoft Defender for Endpoint 警报。 可以更新状态、确定、分类和 assignedTo 属性。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 信息， id
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
ms.openlocfilehash: 00c02bad3f95d2bd8def69d5dd6ad8e1c2e857df
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59196276"
---
# <a name="update-alert"></a>更新警报

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 说明
更新现有警报 [的属性](alerts.md)。

提供 **或不** 更新属性的注释提交。

可更新的属性包括 `status` ：、 `determination` 和 `classification` `assignedTo` 。

## <a name="limitations"></a>限制

1. 你可以更新 API 中可用的警报。 有关详细信息 [，请参阅列出](get-alerts.md) 警报。
2. 此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型|权限|权限显示名称
:---|:---|:---
应用程序|Alerts.ReadWrite.All|"读取和写入所有警报"
委派（工作或学校帐户）|Alert.ReadWrite|"读取和写入警报"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："警报调查" (请参阅创建和管理角色，了解) [](user-roles.md)
> - 用户需要具有与警报关联的设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) 

## <a name="http-request"></a>HTTP 请求

```http
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization|String|Bearer {token}。 **必需**。
Content-Type|String|application/json. **必需**。

## <a name="request-body"></a>请求正文

在请求正文中，提供应更新的相关字段的值。

请求正文中不包括的现有属性将保留其以前的值，或根据对其他属性值的更改重新计算。

为获得最佳性能，不应包含尚未更改的现有值。

属性|类型|说明
:---|:---|:---
status|String|指定警报的当前状态。 属性值为："New"、InProgress 和"Resolved"。
assignedTo|String|警报的所有者
classification|字符串|指定警报的规范。 属性值为："Unknown"、"FalsePositive"和"TruePositive"。
确定|String|指定警报的确定。 属性值包括："NotAvailable"、"Apt"、"Malware"、SecurityPersonnel、"SecurityTesting"、"UnwantedSoftware"和"Other"
注释|String|要添加到警报的注释。

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 200 OK 和 [alert](alerts.md) 实体以及更新的属性。 如果未找到具有指定 ID 的警报 - 404 未找到。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
