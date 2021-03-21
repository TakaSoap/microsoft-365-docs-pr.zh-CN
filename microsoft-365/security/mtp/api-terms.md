---
title: Microsoft 365 Defender API 许可证和使用条款
description: Microsoft 365 Defender 中 API 的许可和使用条款说明
keywords: api， api， 许可， 条款， api， 法律， 通知， 行为准则
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 06926bc58f29fcf80d09819545e2455813f27a5f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922158"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender API 许可证和使用条款

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>正式条款

Microsoft 365 Defender API 受 [Microsoft API 许可证和使用条款约束](/legal/microsoft-apis/terms-of-use)。

## <a name="legal-notices"></a>法律声明

Microsoft 和任何参与者根据 Creative Commons Attribution 4.0 国际公共许可证授予你 Microsoft 文档以及此存储库中的其他内容的许可证。 [](https://github.com/MicrosoftDocs/microsoft-365-docs) 有关详细信息，请参阅 [LICENSE](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) 文件。

本文档中引用的 Microsoft、Windows、Microsoft Azure 和/或其他 Microsoft 产品和服务可能是 Microsoft 在美国和/或其他国家/地区中的商标或注册商标。

此项目的许可证不授予你使用任何 Microsoft 名称、徽标或商标的权利。 可以在 Microsoft 商标上找到 Microsoft 的一般 [商标准则](https://go.microsoft.com/fwlink/?LinkID=254653)。

隐私信息可在 Microsoft 隐私 [上找到](https://privacy.microsoft.com)。

Microsoft 和任何参与者保留所有其他权利，无论是其各自的版权、专利还是商标，无论是通过暗示、阻止拼写还是以其他方式。

## <a name="other-restrictions"></a>其他限制

高级搜寻 API [对返回](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) 的结果数和可查询的数据有一些限制。

1. 只能查询过去 30 天的数据。
1. 结果最多包含 100，000 行。

### <a name="quotas-and-resource-allocation"></a>配额和资源分配

Microsoft 365 Defender API 具有限制阈值。

- **事件 API：** 每分钟最多 50 个调用或每小时 1500 个调用。
- **高级搜寻 API：** 每分钟最多 15 次调用，每小时 10 分钟运行时间，每天 4 小时运行时间。

指示限制的 HTTP 响应状态代码为 `429` 。

如果请求受到限制，响应正文将指示可以开始再次提出请求的时间。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [支持的 Microsoft 365 Defender API](api-supported.md)
- [访问 Microsoft 365 Defender API](api-access.md)