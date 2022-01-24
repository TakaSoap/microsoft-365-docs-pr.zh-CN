---
title: 受支持的 Microsoft 365 Defender API
description: 受支持的 Microsoft 365 Defender API
keywords: Microsoft 365 Defender、API、api
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
ms.custom: api
ms.openlocfilehash: 1785186f778c489cb4a254fe39cc41921a4de86e
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62170999"
---
# <a name="supported-microsoft-365-defender-apis"></a>受支持的 Microsoft 365 Defender API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

## <a name="list-of-available-apis"></a>可用 API 列表

文章 | 说明
-|-
[高级搜寻 API](api-advanced-hunting.md) | 运行高级搜寻查询。
[事件 API](api-incident.md) | 列出和更新事件以及其他实际任务。
[Streaming API](streaming-api.md) | 在单个数据流中发生时发送实时事件和警报。

### <a name="endpoint-uris"></a>终结点 URI

这两个主要 API 的基本 URI 是 https://api.security.microsoft.com ：。 为了提高性能，请使用距离地理位置更近的服务器：

- 美国：api-us.security.microsoft.com
- 欧洲：api-eu.security.microsoft.com
- 英国：api-uk.security.microsoft.com

可以通过访问 获取令牌 https://api.security.microsoft.com 。

路径上的所有 `/api` API 都使用 [OData](/odata/overview) 协议;例如， https://api.security.microsoft.com/api/incidents 。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [访问Microsoft 365 Defender API](api-access.md)
- [Streaming API](../defender-endpoint/raw-data-export.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
