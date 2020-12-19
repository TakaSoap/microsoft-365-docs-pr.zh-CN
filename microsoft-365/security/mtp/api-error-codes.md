---
title: 常见的 Microsoft 365 Defender REST API 错误代码
description: 了解常见的 Microsoft 365 Defender REST API 错误代码
keywords: api， 错误， 代码， 常见错误， mtp， api 错误代码
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719210"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>常见的 Microsoft 365 Defender REST API 错误代码

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 威胁防护

> [!IMPORTANT]
> 某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

任何 Microsoft 365 Defender API 上的操作可能会返回错误代码。 每个错误响应都将包含一条错误消息，有助于解决问题。 表部分中的错误消息列提供了一些示例消息。 实际消息的内容因触发响应的因素而异。 表中用尖括号指示变量内容。

## <a name="error-codes"></a>错误代码

错误代码 | HTTP 状态代码 | 消息
-|-|-
BadRequest | BadRequest (400)  | 常规错误请求错误消息。
ODataError | BadRequest (400)  | 无效的 OData URI 查询 \<the specific error is specified\> 。
InvalidInput | BadRequest (400)  | 无效的输入 \<the invalid input\> 。
InvalidRequestBody | BadRequest (400)  | 无效的请求正文。
InvalidHashValue | BadRequest (400)  | 哈希 \<the invalid hash\> 值无效。
InvalidDomainName | BadRequest (400)  | 域名 \<the invalid domain\> 无效。
InvalidIpAddress | BadRequest (400)  | IP 地址 \<the invalid IP\> 无效。
InvalidUrl | BadRequest (400)  | URL \<the invalid URL\> 无效。
MaximumBatchSizeExceeded | BadRequest (400)  | 已超出最大批次大小。 Received： \<batch size received\> ， allowed： {batch size allowed}.
MissingRequiredParameter | BadRequest (400)  | 参数 \<the missing parameter\> 缺失。
OsPlatformNotSupported | BadRequest (400)  | 此操作 \<the client OS Platform\> 不支持 OS 平台。
ClientVersionNotSupported | BadRequest (400)  | \<The requested action\> 在客户端版本及 \<supported client version\> 以上版本上受支持。
未经授权 (Unauthorized) | 未授权 (401)  | 未经授权 (Unauthorized) <br /><br />*注意：通常是由无效或过期的授权标头导致的。*
禁止访问 (Forbidden) | 禁止使用 (403)  | 禁止访问 (Forbidden) <br /><br />*注意：有效的令牌，但操作权限不足*。
DisabledFeature | 禁止使用 (403)  | 租户功能未启用。
DisallowedOperation | 禁止使用 (403)  | \<the disallowed operation and the reason\>.
NotFound | 找不到 (404)  | "未找到常规"错误消息。
ResourceNotFound | 找不到 (404)  | 未找到 \<the requested resource\> 资源。
InternalServerError | 内部服务器错误 (500)  | *注意：无错误消息，重试该操作或联系 Microsoft（如果未解决）*

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

每个错误响应都包含用于跟踪的唯一 ID 参数。 此参数的属性名称是 *目标*。 当我们就错误联系我们时，附加此 ID 将帮助我们找到问题的根本原因。

## <a name="related-articles"></a>相关文章

- [Microsoft 365 Defender API 概述](api-overview.md)
- [支持的 Microsoft 365 Defender API](api-supported.md)
- [访问 Microsoft 365 Defender API](api-access.md)
- [了解 API 限制和许可](api-terms.md)
