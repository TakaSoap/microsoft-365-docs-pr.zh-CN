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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7cfb066ec2eaf486a3cb3e708720436098bb01d0
ms.sourcegitcommit: 9469d16c6bbd29442a6787beaf7d84fb7699c5e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "58400231"
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

方法|返回类型|说明
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
indicatorType|枚举|指示器的类型。 可能的值是："FileSha1"、"FileSha256"、"IpAddress"、"DomainName"和"Url"。
应用程序|String|与指示器关联的应用程序。
action|枚举|如果在组织中发现指示器，将采取的操作。 可能的值包括："Alert"、"AlertAndBlock"和"Allowed"。
sourceType|枚举|"用户"，如果由用户创建的指示器 (例如，从门户) ，"AadApp"，以防它通过 API 自动应用提交。
source|string|提交指示器的用户/应用程序的名称。
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

## <a name="public-preview-indicator-types"></a>公共预览版：指示器类型

> [!IMPORTANT]
> 本节中 (公共预览版自动调查和修正 **引擎) 预** 发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

API 支持的指示器操作类型为：

- AlertAndBlock
- 允许
- Audit
- 通知
- Warn
- BlockExecution
- BlockRemdiation

操作类型的 API 列表包含新的响应操作以及 AlertAndBlock 和 Alert (之前的) 。

> [!Note]
>
> 当功能达到 GAed (将删除 AlertAndBlock 和 Alert) 响应操作。 估计的 GA 日期（宽限期）为 2021 年 10 月。  我们建议尽快更新任何现有模板或脚本。

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
