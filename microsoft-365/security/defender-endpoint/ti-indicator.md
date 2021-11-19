---
title: 指示器资源类型
description: 使用 Microsoft Defender for Endpoint 指定实体详细信息并定义指示器的过期时间。
keywords: api， 受支持的 api， 获取， TiIndicator， 指示器， 最近
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
ms.openlocfilehash: 4d31bce9aa3cc6c64771e0931c22849aa1d92eec
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110075"
---
# <a name="indicator-resource-type"></a>指示器资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

- 请参阅门户 [中的相应](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) "指示器"页。

方法|返回类型|Description
:---|:---|:---
[列出指示器](get-ti-indicators-collection.md)|[指示器](ti-indicator.md) 集合|列表 [指示器](ti-indicator.md) 实体。
[提交指示器](post-ti-indicator.md)|[指示器](ti-indicator.md)|提交或更新 [指示器](ti-indicator.md) 实体。
[导入指示器](import-ti-indicators.md)|[指示器](ti-indicator.md) 集合|提交或 [更新指示器](ti-indicator.md) 实体。
[删除指示器](delete-ti-indicator-by-id.md)|无内容|删除 [指示器](ti-indicator.md) 实体。

## <a name="properties"></a>属性

属性|类型|说明
:---|:---|:---
id|String|Indicator [实体的](ti-indicator.md) 标识。
indicatorValue|String|指示器 [的值](ti-indicator.md)。
indicatorType|枚举|指示器的类型。 可能的值是："FileSha1"、"FileSha256"、"FileMd5"、"CertificateThumbprint"、"IpAddress"、"DomainName"和"Url"。
应用程序|String|与指示器关联的应用程序。
action|枚举|如果在组织中发现指示器，将采取的操作。 可能的值包括："Warn"、"Block"、"Audit"、"Alert"、"AlertAndBlock"、"BlockAndRemediate"和"Allowed"。
|externalID|String|客户可以在自定义关联请求中提交的 ID。|
sourceType|枚举|"用户"，如果由用户创建的指示器 (例如，从门户) ，"AadApp"，以防它通过 API 使用自动应用程序提交。
createdBySource|string|提交指示器的用户/应用程序的名称。
createdBy|String|提交指示器的用户/应用程序的唯一标识。
lastUpdatedBy|String|上次更新指示器的用户/应用程序的标识。
creationTimeDateTimeUtc|DateTimeOffset|创建指示器的日期和时间。
expirationTime|DateTimeOffset|指示器的过期时间。
lastUpdateTime|DateTimeOffset|上次更新指示器的时间。
severity|枚举|指示器的严重性。 可能的值包括："Informational"、"Low"、"Medium"和"High"。
title|String|指示器标题。
说明|String|指示器的说明。
recommendedActions|String|指示器的建议操作。
rbacGroupNames|字符串列表|RBAC 设备组名称，其中指示器已公开且处于活动状态。 空列表，以防它向所有设备公开。
rbacGroupIds|字符串列表|RBAC 设备组 ID，其中指示器已公开且处于活动状态。 空列表，以防它向所有设备公开。
generateAlert|枚举|**如果** 警报生成是必需的，则其为 **True;** 如果此指示器不应生成警报，则其为 False。

## <a name="indicator-types"></a>指示器类型

API 支持的指示器操作类型为：

- Allowed
- Audit
- 阻止
- BlockAndRemediate
- 仅 (适用于云应用的 Defender) 

有关响应操作类型的说明详细信息，请参阅创建 [指示器](manage-indicators.md)。

> [!Note]
>
> AlertAndBlock (和 Alert) 2022 年 1 月前受支持。 在此日期之后，所有客户都必须使用上面列出的操作类型之一。

## <a name="json-representation"></a>Json 表示形式

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
