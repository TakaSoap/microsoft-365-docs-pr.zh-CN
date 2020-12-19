---
title: 支持的 Microsoft 365 Defender API
description: 支持的 Microsoft 365 Defender API
keywords: MTP， API， api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719318"
---
# <a name="supported-microsoft-365-defender-apis"></a>支持的 Microsoft 365 Defender API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="list-of-available-apis"></a>可用 API 列表

文章 | 说明
-|-
[高级搜寻 API](api-advanced-hunting.md) | 运行高级搜寻查询。
[事件 API](api-incident.md) | 列出和更新事件以及其他实际任务。

### <a name="endpoint-uris"></a>终结点 URI

两个主要 API 的基 URI 为： https://api.security.microsoft.com 。 为了提高性能，请使用距离地理位置更近的服务器：

- 美国：api-us.security.microsoft.com
- 欧洲：api-eu.security.microsoft.com
- 英国：api-uk.security.microsoft.com

可以通过访问获取令牌 https://api.security.microsoft.com 。

路径上的所有 API `/api` 都使用[OData](https://docs.microsoft.com/odata/overview)协议;例如， https://api.security.microsoft.com/api/incidents

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [访问 Microsoft 威胁防护 API](api-access.md)
- [了解 API 限制和许可](api-terms.md)
- [了解错误代码](api-error-codes.md)
