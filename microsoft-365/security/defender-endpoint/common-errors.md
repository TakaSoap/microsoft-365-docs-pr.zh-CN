---
title: 常见的 Microsoft Defender 终结点 API 错误
description: 包含说明的常见 Microsoft Defender 终结点 API 错误列表。
keywords: API， Microsoft Defender for Endpoint API， 错误， 疑难解答
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
ms.openlocfilehash: 406706f5ceba4268cfad99dec07d76e15f447b2b
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171253"
---
# <a name="common-rest-api-error-codes"></a>常见的 REST API 错误代码



[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* 下表中列出的错误代码可能由任何 Microsoft Defender for Endpoint API 上的操作返回。
* 除了错误代码之外，每个错误响应还包含一条错误消息，有助于解决问题。
* 邮件是可更改的免费文本。
* 在页面底部，可以找到响应示例。

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

错误代码|HTTP 状态代码|邮件
---|---|---
BadRequest|BadRequest (400) |常规错误请求错误消息。
ODataError|BadRequest (400) |指定的特定错误 (OData URI 查询无效) 。
InvalidInput|BadRequest (400) |无效输入 {无效的输入}。
InvalidRequestBody|BadRequest (400) |无效的请求正文。
InvalidHashValue|BadRequest (400) |哈希值 {无效的哈希}无效。
InvalidDomainName|BadRequest (400) |域名 {无效的域} 无效。
InvalidIpAddress|BadRequest (400) |IP 地址 {无效的 IP} 无效。
InvalidUrl|BadRequest (400) |URL {无效的 URL} 无效。
MaximumBatchSizeExceeded|BadRequest (400) |已超出最大批次大小。 Received： {batch size received}， allowed： {batch size allowed}.
MissingRequiredParameter|BadRequest (400) |参数 {缺少参数}。
OsPlatformNotSupported|BadRequest (400) |此操作不支持 OS 平台 {the client OS Platform}。
ClientVersionNotSupported|BadRequest (400) |{请求的操作} 在客户端版本 {支持的客户端版本} 及以上版本上受支持。
未经授权 (Unauthorized)|未经授权 (401) |未授权 (或过期的授权标头) 。
禁止访问 (Forbidden)|禁止 (403) |禁止 (有效令牌，但权限不足，无法) 。
DisabledFeature|禁止 (403) |未启用租户功能。
DisallowedOperation|禁止 (403) |{不允许的操作和原因}。
NotFound|404 (未找到) |"常规未找到"错误消息。
ResourceNotFound|404 (未找到) |未找到资源 {请求的资源}。
InternalServerError|内部服务器错误 (500) | (无错误消息，请重试) 
TooManyRequests|请求过多 (429) |响应表示请求数或 CPU 达到配额限制。

## <a name="body-parameters-are-case-sensitive"></a>正文参数区分大小写

提交的正文参数当前区分大小写。

如果遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 错误，可能是参数大写或小写字母错误导致的。

查看 API 文档页，并检查提交的参数是否与相关示例匹配。

## <a name="correlation-request-id"></a>相关请求 ID

每个错误响应都包含用于跟踪的唯一 ID 参数。

此参数的属性名称为"target"。

当我们就错误联系我们时，附加此 ID 将有助于找到问题的根本原因。

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
