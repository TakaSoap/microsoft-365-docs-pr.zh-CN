---
title: 软件方法和属性
description: 检索最近的警报。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f0f15f8a3cf7f40bd1fd2e64d4d37466cc12d67e
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61122077"
---
# <a name="software-resource-type"></a>软件资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methods

<br>

****

|方法|返回类型|说明|
|---|---|---|
|[列出软件](get-software.md)|软件集合|列出组织软件清单|
|[按 ID 获取软件](get-software-by-id.md)|软件|按软件 ID 获取特定软件|
|[列出软件版本分发](get-software-ver-distribution.md)|通讯组集合|按软件 ID 列出软件版本分发|
|[按软件列出计算机](get-machines-by-software.md)|MachineRef 集合|检索与软件 ID 关联的设备列表|
|[按软件列出漏洞](get-vuln-by-software.md)|[漏洞](vulnerability.md) 集合|检索与软件 ID 关联的漏洞列表|
|[查找缺失的 KBS](get-missing-kbs-software.md)|KB 集合|获取与软件 ID 关联的缺失的 KB 列表|
|

## <a name="properties"></a>属性

<br>

****

|属性|类型|说明|
|---|---|---|
|id|String|软件 ID|
|名称|String|软件名称|
|供应商|String|软件发布者名称|
|漏洞|长型|发现的漏洞数量|
|publicExploit|Boolean|存在针对某些漏洞的公共攻击|
|activeAlert|Boolean|活动警报与此软件关联|
|exposedMachines|长型|公开的设备数量|
|impactScore|双精度|此软件的曝光评分影响|
|
