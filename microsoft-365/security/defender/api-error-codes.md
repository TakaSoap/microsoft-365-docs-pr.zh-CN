---
title: 常见的 Microsoft 365 Defender REST API 错误代码
description: 了解常见的 Microsoft 365 Defender REST API 错误代码
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932877"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="cb214-104">常见的 Microsoft 365 Defender REST API 错误代码</span><span class="sxs-lookup"><span data-stu-id="cb214-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cb214-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="cb214-105">**Applies to:**</span></span>

- <span data-ttu-id="cb214-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb214-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb214-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="cb214-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cb214-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="cb214-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cb214-109">任何 Defender API 上的操作可能会返回Microsoft 365代码。</span><span class="sxs-lookup"><span data-stu-id="cb214-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="cb214-110">每个错误响应都将包含一条错误消息，有助于解决问题。</span><span class="sxs-lookup"><span data-stu-id="cb214-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="cb214-111">表部分中的错误消息列提供了一些示例消息。</span><span class="sxs-lookup"><span data-stu-id="cb214-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="cb214-112">实际消息的内容因触发响应的因素而异。</span><span class="sxs-lookup"><span data-stu-id="cb214-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="cb214-113">表中用尖括号指示变量内容。</span><span class="sxs-lookup"><span data-stu-id="cb214-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="cb214-114">错误代码</span><span class="sxs-lookup"><span data-stu-id="cb214-114">Error codes</span></span>

<span data-ttu-id="cb214-115">错误代码</span><span class="sxs-lookup"><span data-stu-id="cb214-115">Error code</span></span> | <span data-ttu-id="cb214-116">HTTP 状态代码</span><span class="sxs-lookup"><span data-stu-id="cb214-116">HTTP status code</span></span> | <span data-ttu-id="cb214-117">邮件</span><span class="sxs-lookup"><span data-stu-id="cb214-117">Message</span></span>
-|-|-
<span data-ttu-id="cb214-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="cb214-118">BadRequest</span></span> | <span data-ttu-id="cb214-119">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-119">BadRequest (400)</span></span> | <span data-ttu-id="cb214-120">常规错误请求错误消息。</span><span class="sxs-lookup"><span data-stu-id="cb214-120">General Bad Request error message.</span></span>
<span data-ttu-id="cb214-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="cb214-121">ODataError</span></span> | <span data-ttu-id="cb214-122">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-122">BadRequest (400)</span></span> | <span data-ttu-id="cb214-123">无效的 OData URI 查询 \<the specific error is specified\> 。</span><span class="sxs-lookup"><span data-stu-id="cb214-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="cb214-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="cb214-124">InvalidInput</span></span> | <span data-ttu-id="cb214-125">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-125">BadRequest (400)</span></span> | <span data-ttu-id="cb214-126">输入无效 \<the invalid input\> 。</span><span class="sxs-lookup"><span data-stu-id="cb214-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="cb214-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="cb214-127">InvalidRequestBody</span></span> | <span data-ttu-id="cb214-128">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-128">BadRequest (400)</span></span> | <span data-ttu-id="cb214-129">无效的请求正文。</span><span class="sxs-lookup"><span data-stu-id="cb214-129">Invalid request body.</span></span>
<span data-ttu-id="cb214-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="cb214-130">InvalidHashValue</span></span> | <span data-ttu-id="cb214-131">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-131">BadRequest (400)</span></span> | <span data-ttu-id="cb214-132">哈希 \<the invalid hash\> 值无效。</span><span class="sxs-lookup"><span data-stu-id="cb214-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="cb214-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="cb214-133">InvalidDomainName</span></span> | <span data-ttu-id="cb214-134">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-134">BadRequest (400)</span></span> | <span data-ttu-id="cb214-135">域名 \<the invalid domain\> 无效。</span><span class="sxs-lookup"><span data-stu-id="cb214-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="cb214-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="cb214-136">InvalidIpAddress</span></span> | <span data-ttu-id="cb214-137">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-137">BadRequest (400)</span></span> | <span data-ttu-id="cb214-138">IP 地址 \<the invalid IP\> 无效。</span><span class="sxs-lookup"><span data-stu-id="cb214-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="cb214-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="cb214-139">InvalidUrl</span></span> | <span data-ttu-id="cb214-140">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-140">BadRequest (400)</span></span> | <span data-ttu-id="cb214-141">URL \<the invalid URL\> 无效。</span><span class="sxs-lookup"><span data-stu-id="cb214-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="cb214-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="cb214-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="cb214-143">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-143">BadRequest (400)</span></span> | <span data-ttu-id="cb214-144">已超出最大批次大小。</span><span class="sxs-lookup"><span data-stu-id="cb214-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="cb214-145">Received： \<batch size received\> ， allowed： {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="cb214-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="cb214-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="cb214-146">MissingRequiredParameter</span></span> | <span data-ttu-id="cb214-147">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-147">BadRequest (400)</span></span> | <span data-ttu-id="cb214-148">参数 \<the missing parameter\> 缺失。</span><span class="sxs-lookup"><span data-stu-id="cb214-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="cb214-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="cb214-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="cb214-150">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-150">BadRequest (400)</span></span> | <span data-ttu-id="cb214-151">此操作 \<the client OS Platform\> 不支持操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="cb214-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="cb214-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="cb214-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="cb214-153">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="cb214-153">BadRequest (400)</span></span> | <span data-ttu-id="cb214-154">\<The requested action\> 在客户端版本及 \<supported client version\> 以上版本上受支持。</span><span class="sxs-lookup"><span data-stu-id="cb214-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="cb214-155">未经授权 (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="cb214-155">Unauthorized</span></span> | <span data-ttu-id="cb214-156">未经授权 (401) </span><span class="sxs-lookup"><span data-stu-id="cb214-156">Unauthorized (401)</span></span> | <span data-ttu-id="cb214-157">未经授权 (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="cb214-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="cb214-158">*注意：通常是由无效或过期的授权标头导致的。*</span><span class="sxs-lookup"><span data-stu-id="cb214-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="cb214-159">禁止访问 (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="cb214-159">Forbidden</span></span> | <span data-ttu-id="cb214-160">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="cb214-160">Forbidden (403)</span></span> | <span data-ttu-id="cb214-161">禁止访问 (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="cb214-161">Forbidden</span></span> <br /><br /><span data-ttu-id="cb214-162">*注意：有效令牌，但操作权限不足*。</span><span class="sxs-lookup"><span data-stu-id="cb214-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="cb214-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="cb214-163">DisabledFeature</span></span> | <span data-ttu-id="cb214-164">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="cb214-164">Forbidden (403)</span></span> | <span data-ttu-id="cb214-165">未启用租户功能。</span><span class="sxs-lookup"><span data-stu-id="cb214-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="cb214-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="cb214-166">DisallowedOperation</span></span> | <span data-ttu-id="cb214-167">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="cb214-167">Forbidden (403)</span></span> | <span data-ttu-id="cb214-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="cb214-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="cb214-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="cb214-169">NotFound</span></span> | <span data-ttu-id="cb214-170">404 (未找到) </span><span class="sxs-lookup"><span data-stu-id="cb214-170">Not Found (404)</span></span> | <span data-ttu-id="cb214-171">"常规未找到"错误消息。</span><span class="sxs-lookup"><span data-stu-id="cb214-171">General Not Found error message.</span></span>
<span data-ttu-id="cb214-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="cb214-172">ResourceNotFound</span></span> | <span data-ttu-id="cb214-173">404 (未找到) </span><span class="sxs-lookup"><span data-stu-id="cb214-173">Not Found (404)</span></span> | <span data-ttu-id="cb214-174">未找到 \<the requested resource\> 资源。</span><span class="sxs-lookup"><span data-stu-id="cb214-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="cb214-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="cb214-175">InternalServerError</span></span> | <span data-ttu-id="cb214-176">内部服务器错误 (500) </span><span class="sxs-lookup"><span data-stu-id="cb214-176">Internal Server Error (500)</span></span> | <span data-ttu-id="cb214-177">*注意：无错误消息，请重试该操作或联系 Microsoft（如果未解决）*</span><span class="sxs-lookup"><span data-stu-id="cb214-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="cb214-178">示例</span><span class="sxs-lookup"><span data-stu-id="cb214-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="cb214-179">Body 参数</span><span class="sxs-lookup"><span data-stu-id="cb214-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb214-180">正文参数区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cb214-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="cb214-181">如果遇到 *InvalidRequestBody* 或 *MissingRequiredParameter* 错误，这可能是由拼写错误导致的。</span><span class="sxs-lookup"><span data-stu-id="cb214-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="cb214-182">查看 API 文档并检查提交的参数是否与相关示例匹配。</span><span class="sxs-lookup"><span data-stu-id="cb214-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="cb214-183">跟踪 ID</span><span class="sxs-lookup"><span data-stu-id="cb214-183">Tracking ID</span></span>

<span data-ttu-id="cb214-184">每个错误响应都包含用于跟踪的唯一 ID 参数。</span><span class="sxs-lookup"><span data-stu-id="cb214-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="cb214-185">此参数的属性名称是 *目标*。</span><span class="sxs-lookup"><span data-stu-id="cb214-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="cb214-186">当我们就错误联系我们时，附加此 ID 将有助于我们找到问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="cb214-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cb214-187">相关文章</span><span class="sxs-lookup"><span data-stu-id="cb214-187">Related articles</span></span>

- [<span data-ttu-id="cb214-188">Microsoft 365Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="cb214-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cb214-189">支持的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="cb214-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="cb214-190">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="cb214-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="cb214-191">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="cb214-191">Learn about API limits and licensing</span></span>](api-terms.md)
