---
title: 支持的 Microsoft 365 Defender Api
description: 支持的 Microsoft 365 Defender Api
keywords: MTP、Api、api
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844956"
---
# <a name="supported-microsoft-365-defender-apis"></a>支持的 Microsoft 365 Defender Api 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


### <a name="end-point-uris"></a>终结点 Uri：

- 服务基 URI 为： https://api.security.microsoft.com <br>

>[!NOTE]
>为获得更好的性能，你可以使用服务器近距离你的地理位置：
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - 令牌获取的资源应为： https://api.security.microsoft.com

 - Path 下的所有 Api ```/api``` 都是 OData api。 举例. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>可用 Api 的列表：

主题 | 说明
:---|:---
[高级搜寻 API](api-advanced-hunting.md) | 从 API 运行高级搜寻查询。
[事件 API](api-incident.md) | 运行与事件相关的 API 调用，例如：列出事件、更新事件等。
