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
ms.openlocfilehash: 3dc075caccc5724ed3ea76e5d3c06f3a5b6f7f2e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59162255"
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
indicatorType|枚举|指示器的类型。 可能的值是："FileSha1"、"FileSha256"、"FileMd5"、"CertificateThumbprint"、"IpAddress"、"DomainName"和"Url"。
应用程序|String|与指示器关联的应用程序。
action|枚举|如果在组织中发现指示器，将采取的操作。 可能的值包括："Warn"、"Block"、"Audit"、"Alert"、"AlertAndBlock"、"BlockAndRemediate"和"Allowed"。
|externalID|String|客户可以在自定义关联请求中提交的 ID。|
sourceType|枚举|"用户"（如果由用户创建的指示器 (例如从门户) 创建的指示器，例如"AadApp"（如果通过 API 使用自动应用程序提交）。
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
## <a name="public-preview-indicator-types"></a>公共预览版：指示器类型

> [!IMPORTANT]
> 本节中的信息 (公共预览版自动调查和修正 **引擎) 预** 发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

API 支持的指示器操作类型为：

- 允许
- 通知
- AlertAndBlock
- Audit
- 阻止
- BlockAndRemediate
- Warn

操作类型的 API 列表包含新的响应操作以及 AlertAndBlock 和 Alert (之前的) 。 有关响应操作类型的说明详细信息，请参阅创建 [指示器](manage-indicators.md)。

允许、警告、阻止和 BlockAndRemediate IoC 响应操作在公共预览版中。 有关公共预览版的详细信息，请参阅公共预览版：自定义文件 IoC 增强功能和[API 架构更新 - Microsoft 技术Community。](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/public-preview-custom-file-ioc-enhancements-and-api-schema/ba-p/2676997)




> [!Note]
>
> AlertAndBlock (响应操作，当功能) GAed 时，将删除 Alert) 。 估计的 GA 日期（宽限期）为 2021 年 10 月。  我们建议尽快更新任何现有模板或脚本。

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
