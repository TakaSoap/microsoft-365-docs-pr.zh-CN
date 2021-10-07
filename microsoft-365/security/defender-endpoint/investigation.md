---
title: 调查资源类型
description: Microsoft Defender for Endpoint Investigation 实体。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 调查
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 069e74b8ad0aef33caab411b92c24c4d0b72f022
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194149"
---
# <a name="investigation-resource-type"></a>调查资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

代表 Defender for Endpoint 中的自动调查实体。

有关详细信息 [，请参阅自动](automated-investigations.md) 调查概述。

## <a name="methods"></a>方法

方法|返回类型|说明
:---|:---|:---
[列表调查](get-investigation-collection.md)|调查集合|获取调查集合
[获取单个调查](get-investigation-object.md)|调查实体|获取单个 Investigation 实体。
[启动调查](initiate-autoir-investigation.md)|调查实体|在设备上启动调查。

## <a name="properties"></a>属性

属性|类型|说明
:---|:---|:---
id|String|调查实体的标识。 
startTime|DateTime Nullable|创建调查的日期和时间。
endTime|DateTime Nullable|调查完成的日期和时间。
cancelledBy|字符串|取消调查的用户/应用程序的 ID。
state|枚举|调查的当前状态。 可能的值包括："Unknown"、"Terminated"、 "SuccessfullyRemediated"、"Benign"、"Failed"、"PartiallyRemediated"、"Running"、"PendingApproval"、"PendingResource"、"PartiallyInvestigated"、"TerminatedByUser"、"TerminatedBySystem"、"Queued"、"InnerFailure"、"PreexistingAlert"、"UnsupportedOs"、"UnsupportedAlertType"和"SuppressedAlert"。
statusDetails|String|有关调查状态的其他信息。
machineId|String|执行调查的设备 ID。
computerDnsName|String|执行调查的设备的名称。
triggeringAlertId|String|触发调查的警报的 ID。

## <a name="json-representation"></a>Json 表示形式

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
