---
title: 分数方法和属性
description: 按设备组检索组织的曝光分数、设备安全分数和曝光分数
keywords: api， 图形 api， 受支持的 api， 分数， 曝光分数， 设备安全分数， 按设备组的曝光分数
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: fe69b42c2d8bf80089b749cd41e59664cc2921e3
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300978"
---
# <a name="score-resource-type"></a>分数资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methods

方法|返回类型|说明
:---|:---|:---
[获取曝光分数](get-exposure-score.md)|[分数](score.md)|获取组织曝光分数。
[获取设备安全分数](get-device-secure-score.md)|[分数](score.md)|获取组织设备安全分数。
[按设备组列出曝光分数](get-machine-group-exposure-score.md)|[分数](score.md)|按设备组列出分数。

## <a name="properties"></a>属性

属性|类型|说明
:---|:---|:---
得分|双精度|当前分数。
时间|日期时间|调用此 API 的日期和时间。
RbacGroupName|String|设备组名称。
RbacGroupId|String|设备组 ID。
