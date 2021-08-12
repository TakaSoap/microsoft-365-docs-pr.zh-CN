---
title: 建议方法和属性
description: 检索最近的警报。
keywords: api， 图形 api， 受支持的 api， 获取， 警报， 最近
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9361e791eafad1a3d7243a0d11821c9286c5e3bebf64f878af1e72cda6bfa952
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53829107"
---
# <a name="recommendation-resource-type"></a>建议资源类型

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>方法
方法 |返回类型 |说明
:---|:---|:---
[列出所有建议](get-all-recommendations.md) | 建议集合 | 检索影响组织的所有安全建议的列表
[按 Id 获取建议](get-recommendation-by-id.md) | 建议 | 按 ID 检索安全建议
[获取建议软件](get-recommendation-software.md)| [软件](software.md) | 检索与特定软件相关的安全建议
[获取建议设备](get-recommendation-machines.md)|MachineRef 集合 | 检索与安全建议关联的设备列表
[获取建议漏洞](get-recommendation-vulnerabilities.md) | [漏洞](vulnerability.md) 集合 | 检索与安全建议关联的漏洞列表


## <a name="properties"></a>属性
属性 |   类型   |   说明
:---|:---|:---
id | String | 建议 ID
productName | String | 相关软件名称  
recommendationName | String | 建议名称
漏洞 | 长型 | 发现的漏洞数量
供应商 | String | 相关供应商名称
recommendedVersion | 字符串 | 建议版本
recommendationCategory | String | 建议类别。 可能的值包括："Accounts"、"Application"、"Network"、"OS"、"SecurityStack"
subCategory | String | 建议子类别
severityScore | 双精度 | 配置对组织的 Microsoft 设备安全分数的潜在影响 (1-10) 
publicExploit | 布尔 | 公共攻击可用 
activeAlert | 布尔 | 活动警报与此建议关联
associatedThreats | String collection | 威胁分析报告与此建议关联
remediationType | 字符串 | 修正类型。 可能的值是："ConfigurationChange"、"Update"、"Upgrade"、"Uninstall"
状态 | 枚举 | 建议例外状态。 可能的值是："Active"和"Exception"
configScoreImpact | 双精度 | Microsoft 设备影响安全分数
exposureImpacte | 双精度 | 曝光分数影响
totalMachineCount | 长型 | 已安装设备的数量
exposedMachinesCount | 长型 | 向漏洞公开的已安装设备的数量
nonProductivityImpactedAssets | 长型 | 不受影响的设备数量  
relatedComponent | 字符串 |  相关软件组件
