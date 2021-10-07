---
title: 从事件 API 创建警报
description: 了解如何使用创建警报 API 在 Microsoft Defender for Endpoint 中的事件顶部创建新的警报。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 信息， id
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
ms.openlocfilehash: fb30a5dbc2d5a6859343a1b382cdbd0106819cd2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191943"
---
# <a name="create-alert-api"></a>创建警报 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 说明

在事件 [顶部](alerts.md) 创建新的 **警报**。

- **创建警报需要 Microsoft Defender for Endpoint** 事件。
- 你将需要提供请求中的事件中的 3 个参数：**事件** 时间、计算机 **ID** 和 **报告 ID。** 请参阅下面的示例。
- 可以使用高级搜寻 API 或门户中的事件。
- 如果同一设备上存在具有相同标题的打开警报，则新创建的警报将合并到该警报中。
- 自动调查将在通过 API 创建的警报上自动启动。

## <a name="limitations"></a>限制

1. 此 API 的速率限制是每分钟 15 次调用。

## <a name="permissions"></a>权限

若要调用此 API，需要以下权限之一。 若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)

权限类型 | 权限 | 权限显示名称
:---|:---|:---
Application | Alert.ReadWrite.All | "读取和写入所有警报"
委派（工作或学校帐户） | Alert.ReadWrite | "读取和写入警报"

> [!NOTE]
> 使用用户凭据获取令牌时：
>
> - 用户至少需要具有以下角色权限："警报调查" (请参阅创建和管理角色，了解) [](user-roles.md)
> - 用户需要具有与警报关联的设备的访问权限，根据设备组设置 (创建和管理设备组，了解) [](machine-groups.md)

## <a name="http-request"></a>HTTP 请求

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>请求标头

名称|类型|说明
:---|:---|:---
Authorization | String | Bearer {token}。 必需。
Content-Type | String | application/json. **必需**。

## <a name="request-body"></a>请求正文

在请求正文中，提供以下值 (所有请求) ：

属性 | 类型 | 说明
:---|:---|:---
eventTime | DateTime (UTC)  | 事件作为字符串的精确时间，从高级搜寻获取。 例如， ```2018-08-03T16:45:21.7115183Z``` **必需**。
reportId | 字符串 | 事件的 reportId，从高级搜寻获取。 必需。
machineId | 字符串 | 标识事件的设备 ID。 **必需**。
severity | 字符串 | 警报的严重性。 属性值为："Low"、Medium 和"High"。 **必需**。
title | String | 警报的标题。 必需。
说明 | 字符串 | 警报的说明。 **必需**。
recommendedAction| String | 建议安全人员在分析警报时采取的操作。 必需。
“类别”| 字符串 | 警报的类别。 属性值包括："General"、"CommandAndControl"、"Collection"、"CredentialAccess"、"DefenseEvasion"、"Discovery"、"Exfiltration"、"Exploit"、"Execution"、"InitialAccess"、"LateralMovement"、"Malware"、"Persistence"、"PrivilegeEscalation"、"Ransomware"、"SuspiciousActivity"（ **必需**）。

## <a name="response"></a>响应

如果成功，此方法在响应正文中返回 200 OK 和一个新的 [alert](alerts.md) 对象。 如果具有指定属性的事件 (_reportId_ _、eventTime_ 和 _machineId_) 未找到 - 404 未找到。

## <a name="example"></a>示例

### <a name="request"></a>请求

下面是一个请求示例。

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
