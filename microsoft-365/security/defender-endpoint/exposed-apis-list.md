---
title: 支持的 Microsoft Defender for Endpoint API
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8623a4932c23748e35af480613c1e5baac3bbcf6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191895"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>支持的 Microsoft Defender for Endpoint API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="endpoint-uri-and-versioning"></a>终结点 URI 和版本控制

### <a name="endpoint-uri"></a>终结点 URI

> 服务基 URI 为： [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> 基于查询的 OData 具有"/api"前缀。 例如，若要获取通知，可以将 GET 请求发送到 [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>版本控制

> API 支持版本控制。
>
> 当前版本为 **V1.0。**
>
> 若要使用特定版本，请使用此格式 `https://api.securitycenter.microsoft.com/api/{Version}` ：。 例如：`https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> 如果不指定任何版本 (例如) `https://api.securitycenter.microsoft.com/api/alerts` 将进入最新版本。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

详细了解可在其中运行 API 调用的单个受支持实体，以及诸如 HTTP 请求值、请求标头和预期响应等详细信息。

## <a name="in-this-section"></a>本节内容

主题 | 说明
:---|:---
[高级搜寻](run-advanced-query-api.md) | 从 API 运行查询。
[警报方法和属性](alerts.md) | 运行 API 调用，如 \- 获取警报、创建警报、更新警报等。
[导出每个设备的评估方法和属性](get-assessment-methods-properties.md) | 运行 API 调用以按设备收集漏洞评估，例如：导出安全配置评估、导出软件清单评估、导出软件漏洞评估和增量导出软件 \- 漏洞评估。
[自动调查方法和属性](investigation.md) | 运行 API 调用，如 \- 获取调查集合。
[获取域相关警报](get-domain-related-alerts.md) | 运行 API 调用，如 \- 获取与域相关的设备、域统计信息等。
[文件方法和属性](files.md) | 运行 API 调用，如 \- 获取文件信息、文件相关警报、文件相关设备和文件统计信息。
[指示器方法和属性](ti-indicator.md) | 运行 API 调用，如 \- 获取指示器、创建指示器和删除指示器。
[获取 IP 相关警报](get-ip-related-alerts.md) | 运行 API 调用， \- 如获取与 IP 相关的警报和获取 IP 统计信息。
[计算机方法和属性](machine.md) | 运行 API 调用，如获取设备、按 ID 获取设备、有关已登录用户的信息 \- 、编辑标记等。
[计算机操作方法和属性](machineaction.md) | 运行 API 调用， \- 如隔离、运行防病毒扫描等。
[建议方法和属性](recommendation.md) | 运行 API 调用，例如 \- 按 ID 获取建议。
[修正活动方法和属性](get-remediation-methods-properties.md) | 运行 API 调用（如 \- 获取所有修正任务、获取公开的设备修正任务和按 id 获取一个修正任务）。
[分数方法和属性](score.md) | 运行 API 调用（如 \- 获取曝光分数或获取设备安全分数）。
[软件方法和属性](software.md) | 运行 API 调用，如 \- 按软件列出漏洞。
[用户方法](user.md) | 运行 API 调用，如 \- 获取与用户相关的警报和与用户相关的设备。
[漏洞方法和属性](vulnerability.md) | 按漏洞运行 API 调用 \- ，如列表设备。

## <a name="see-also"></a>另请参阅

- [适用于终结点的 Microsoft Defender API](apis-intro.md)

- [Microsoft Defender for Endpoint API 发行说明](api-release-notes.md)
