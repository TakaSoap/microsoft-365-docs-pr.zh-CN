---
title: 支持的 Microsoft 365 Defender API
description: 支持的 Microsoft 365 Defender API
keywords: MTP， API， api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054605"
---
# <a name="supported-microsoft-365-defender-apis"></a>支持的 Microsoft 365 Defender API 

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

### <a name="endpoint-uris"></a>终结点 URI

这两个主要 API 的基本 URI 是 https://api.security.microsoft.com ：。 为了提高性能，请使用距离地理位置更近的服务器：

- 美国：api-us.security.microsoft.com
- 欧洲：api-eu.security.microsoft.com
- 英国：api-uk.security.microsoft.com

可以通过访问 获取令牌 https://api.security.microsoft.com 。

路径上的所有 `/api` API 都使用 [OData](/odata/overview) 协议;例如， https://api.security.microsoft.com/api/incidents 。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [访问 Microsoft 威胁防护 API](api-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)