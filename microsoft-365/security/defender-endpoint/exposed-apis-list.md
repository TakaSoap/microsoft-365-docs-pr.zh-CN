---
title: 支持的 Microsoft Defender 终结点 API
ms.reviewer: ''
description: 了解可在其中创建 API 调用的特定受支持的 Microsoft Defender 终结点实体。
keywords: api， 受支持的 api， 参与者， 警报， 设备， 用户， 域， ip， 文件， 高级查询， 高级搜寻
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
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198314"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>支持的 Microsoft Defender 终结点 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>终结点 URI 和版本控制

### <a name="endpoint-uri"></a>终结点 URI：           

> 服务基 URI 为： https://api.securitycenter.microsoft.com
> 
> 基于查询的 OData 具有"/api"前缀。 例如，若要获取通知，可以将 GET 请求发送到 https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>版本控制：

> API 支持版本控制。
> 
> 当前版本为 **V1.0。**
> 
> 若要使用特定版本，请使用此格式 `https://api.securitycenter.microsoft.com/api/{Version}` ：。 例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> 如果不指定任何版本 (例如) https://api.securitycenter.microsoft.com/api/alerts 将进入最新版本。


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


详细了解可在其中运行 API 调用的单个受支持实体，以及诸如 HTTP 请求值、请求标头和预期响应等详细信息。

## <a name="in-this-section"></a>本节内容

主题 | 说明
:---|:---
高级搜寻 | 从 API 运行查询。
警报 | 运行 API 调用，如获取警报、创建警报、更新警报等。
域 | 运行 API 调用，如获取与域相关的设备、域统计信息等。
文件 | 运行 API 调用，如获取文件信息、文件相关警报、文件相关设备和文件统计信息。
IP | 运行 API 调用，如获取与 IP 相关的警报和获取 IP 统计信息。
计算机 | 运行 API 调用，如获取设备、按 ID 获取设备、有关已登录用户的信息、编辑标记等。
计算机操作 | 运行 API 调用，如隔离、运行防病毒扫描等。
指示器 | 运行 API 调用，例如创建指示器、获取指示器和删除指示器。
用户 | 运行 API 调用，例如获取与用户相关的警报和与用户相关的设备。
得分 | 运行 API 调用（如获取曝光分数或获取设备安全分数）。
软件 | 运行 API 调用，如按软件列出漏洞。
漏洞 | 按漏洞运行 API 调用，如列表设备。
建议 | 运行 API 调用，如按 ID 获取建议。

## <a name="see-also"></a>另请参阅
- [适用于终结点的 Microsoft Defender API](apis-intro.md)
