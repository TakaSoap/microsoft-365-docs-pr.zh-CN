---
title: 分数方法和属性
description: 按设备组检索组织的曝光分数、设备安全分数和曝光分数
keywords: api， 图形 api， 受支持的 api， 分数， 曝光分数， 设备安全分数， 按设备组的曝光分数
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 89012dce4aa5b74d09f071b23f7709b4bd0bf03c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771425"
---
# <a name="score-resource-type"></a>分数资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>方法

方法 |返回类型 |说明
:---|:---|:---
[获取曝光分数](get-exposure-score.md) | [分数](score.md) | 获取组织曝光分数。
[获取设备安全分数](get-device-secure-score.md) | [分数](score.md) | 获取组织设备安全分数。
[按设备组列出曝光分数](get-machine-group-exposure-score.md)| [分数](score.md) | 按设备组列出分数。

## <a name="properties"></a>属性

属性 |  类型    |   说明
:---|:---|:---
得分 | 双精度 | 当前分数。
时间 | 日期时间 | 调用此 API 的日期和时间。
RbacGroupName | String | 设备组名称。
