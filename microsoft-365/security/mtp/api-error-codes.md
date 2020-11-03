---
title: 常见 Microsoft 365 Defender REST API 错误代码
description: 了解常见的 Microsoft 365 Defender REST API 错误代码
keywords: api、错误、代码、常见错误、mtp、api 错误代码
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
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846004"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>常见 Microsoft 365 Defender REST API 错误代码

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

下表中列出的错误代码可能由任何 Microsoft 365 Defender Api 上的操作返回。

每个错误响应都包含一条错误消息，可帮助解决该问题。

邮件是可更改的自由文本。

在页面底部，您可以找到响应示例。

错误代码 |HTTP 状态代码 |邮件 
:---|:---|:---
BadRequest | BadRequest (400)  | 一般错误的请求错误消息。
ODataError | BadRequest (400)  | OData URI 查询无效 () 指定了特定错误。
InvalidInput | BadRequest (400)  | 无效输入 {无效输入}。
InvalidRequestBody | BadRequest (400)  | 请求正文无效。
InvalidHashValue | BadRequest (400)  | 哈希值 {无效的哈希} 无效。
InvalidDomainName | BadRequest (400)  | 域名 {无效域} 无效。
InvalidIpAddress | BadRequest (400)  | IP 地址 {无效的 IP} 无效。
InvalidUrl | BadRequest (400)  | URL {无效的 URL} 无效。
MaximumBatchSizeExceeded | BadRequest (400)  | 超出了最大批处理大小。 已接收： {已接收批处理大小}，允许： {允许批处理大小}。
MissingRequiredParameter | BadRequest (400)  | 参数 {缺少的参数} 缺失。
OsPlatformNotSupported | BadRequest (400)  | 此操作不支持 OS Platform {client OS Platform}。
ClientVersionNotSupported | BadRequest (400)  | {客户端版本 {支持的客户端版本）和更高版本支持所请求的操作。
未经授权 (Unauthorized) | 未经授权的 (401)  | 未经授权 (通常是无效或已过期的授权标头) 。
禁止访问 (Forbidden) | 禁止 (403)  | 禁止 (有效令牌，但权限不足，无法执行操作) 。
DisabledFeature | 禁止 (403)  | 未启用租户功能。
DisallowedOperation | 禁止 (403)  | {不允许的操作和原因。
NotFound | 找不到 (404)  | 找不到常规错误消息。
ResourceNotFound | 找不到 (404)  | 资源 {找不到请求的资源}。
InternalServerError | 内部服务器错误 (500)  |  (不会出现错误消息，请重试操作，否则请与我们联系（如果它未得到解决) 

## <a name="body-parameters-are-case-sensitive"></a>正文参数区分大小写

提交的正文参数当前区分大小写。
<br>如果遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 错误，则可能是由错误的参数大写或小写字母导致的。
<br>建议您查看 API 文档页，并检查提交的参数是否与相关的示例相匹配。

## <a name="correlation-request-id"></a>关联请求 ID

每个错误响应包含一个用于跟踪的唯一 ID 参数。
<br>此参数的属性名称为 "target"。
<br>在与我们联系时，附加此 ID 可帮助查找问题的根本原因。

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

