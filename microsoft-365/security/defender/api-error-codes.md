---
title: 常见Microsoft 365 Defender REST API 错误代码
description: 了解 REST API Microsoft 365 Defender代码
keywords: api， 错误， 代码， 常见错误， Microsoft 365 Defender， api 错误代码
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
ms.openlocfilehash: b43f9548419d3bab10501aa133637b8e2c5583fd
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374750"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>常见Microsoft 365 Defender REST API 错误代码

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

任何一个 API 上的操作可能会返回错误Microsoft 365 Defender代码。 每个错误响应都将包含一条错误消息，有助于解决问题。 表部分中的错误消息列提供了一些示例消息。 实际消息的内容因触发响应的因素而异。 表中用尖括号指示变量内容。

## <a name="error-codes"></a>错误代码

错误代码 | HTTP 状态代码 | 邮件
-|-|-
BadRequest | BadRequest (400)  | 常规错误请求错误消息。
ODataError | BadRequest (400)  | 无效的 OData URI 查询 \<the specific error is specified\> 。
InvalidInput | BadRequest (400)  | 输入无效 \<the invalid input\> 。
InvalidRequestBody | BadRequest (400)  | 无效的请求正文。
InvalidHashValue | BadRequest (400)  | 哈希 \<the invalid hash\> 值无效。
InvalidDomainName | BadRequest (400)  | 域名 \<the invalid domain\> 无效。
InvalidIpAddress | BadRequest (400)  | IP 地址 \<the invalid IP\> 无效。
InvalidUrl | BadRequest (400)  | URL \<the invalid URL\> 无效。
MaximumBatchSizeExceeded | BadRequest (400)  | 已超出最大批次大小。 Received： \<batch size received\> ， allowed： {batch size allowed}.
MissingRequiredParameter | BadRequest (400)  | 参数 \<the missing parameter\> 缺失。
OsPlatformNotSupported | BadRequest (400)  | 此操作 \<the client OS Platform\> 不支持操作系统平台。
ClientVersionNotSupported | BadRequest (400)  | \<The requested action\> 在客户端版本及 \<supported client version\> 以上版本上受支持。
未经授权 (Unauthorized) | 未经授权 (401)  | 未经授权 (Unauthorized) <br /><br />*注意：通常是由无效或过期的授权标头导致的。*
禁止访问 (Forbidden) | 禁止 (403)  | 禁止访问 (Forbidden) <br /><br />*注意：有效令牌，但操作权限不足*。
DisabledFeature | 禁止 (403)  | 未启用租户功能。
DisallowedOperation | 禁止 (403)  | \<the disallowed operation and the reason\>.
NotFound | 在 404 (未找到)  | "常规未找到"错误消息。
ResourceNotFound | 在 404 (未找到)  | 未找到 \<the requested resource\> 资源。
InternalServerError | 内部服务器错误 (500)  | *注意：无错误消息，请重试该操作或联系 [Microsoft（](../../admin/get-help-support.md) 如果未解决）*

## <a name="examples"></a>示例

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a>Body 参数

> [!IMPORTANT]
> 正文参数区分大小写。

如果遇到 *InvalidRequestBody* 或 *MissingRequiredParameter* 错误，这可能是由拼写错误导致的。 查看 API 文档并检查提交的参数是否与相关示例匹配。

## <a name="tracking-id"></a>跟踪 ID

每个错误响应都包含用于跟踪的唯一 ID 参数。 此参数的属性名称是 *目标*。 当我们就错误联系我们时，附加此 ID 将有助于我们找到问题的根本原因。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [受支持的 Microsoft 365 Defender API](api-supported.md)
- [访问Microsoft 365 Defender API](api-access.md)
- [了解 API 限制和许可](api-terms.md)
