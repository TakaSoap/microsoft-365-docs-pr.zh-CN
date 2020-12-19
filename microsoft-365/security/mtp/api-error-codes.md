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
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="f9a63-104">常见的 Microsoft 365 Defender REST API 错误代码</span><span class="sxs-lookup"><span data-stu-id="f9a63-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f9a63-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f9a63-105">**Applies to:**</span></span>

- <span data-ttu-id="f9a63-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f9a63-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9a63-107">某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="f9a63-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f9a63-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f9a63-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f9a63-109">任何 Microsoft 365 Defender API 上的操作可能会返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="f9a63-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="f9a63-110">每个错误响应都将包含一条错误消息，有助于解决问题。</span><span class="sxs-lookup"><span data-stu-id="f9a63-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="f9a63-111">表部分中的错误消息列提供了一些示例消息。</span><span class="sxs-lookup"><span data-stu-id="f9a63-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="f9a63-112">实际消息的内容因触发响应的因素而异。</span><span class="sxs-lookup"><span data-stu-id="f9a63-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="f9a63-113">表中用尖括号指示变量内容。</span><span class="sxs-lookup"><span data-stu-id="f9a63-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="f9a63-114">错误代码</span><span class="sxs-lookup"><span data-stu-id="f9a63-114">Error codes</span></span>

<span data-ttu-id="f9a63-115">错误代码</span><span class="sxs-lookup"><span data-stu-id="f9a63-115">Error code</span></span> | <span data-ttu-id="f9a63-116">HTTP 状态代码</span><span class="sxs-lookup"><span data-stu-id="f9a63-116">HTTP status code</span></span> | <span data-ttu-id="f9a63-117">消息</span><span class="sxs-lookup"><span data-stu-id="f9a63-117">Message</span></span>
-|-|-
<span data-ttu-id="f9a63-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="f9a63-118">BadRequest</span></span> | <span data-ttu-id="f9a63-119">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-119">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-120">常规错误请求错误消息。</span><span class="sxs-lookup"><span data-stu-id="f9a63-120">General Bad Request error message.</span></span>
<span data-ttu-id="f9a63-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="f9a63-121">ODataError</span></span> | <span data-ttu-id="f9a63-122">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-122">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-123">无效的 OData URI 查询 \<the specific error is specified\> 。</span><span class="sxs-lookup"><span data-stu-id="f9a63-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="f9a63-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="f9a63-124">InvalidInput</span></span> | <span data-ttu-id="f9a63-125">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-125">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-126">无效的输入 \<the invalid input\> 。</span><span class="sxs-lookup"><span data-stu-id="f9a63-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="f9a63-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="f9a63-127">InvalidRequestBody</span></span> | <span data-ttu-id="f9a63-128">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-128">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-129">无效的请求正文。</span><span class="sxs-lookup"><span data-stu-id="f9a63-129">Invalid request body.</span></span>
<span data-ttu-id="f9a63-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="f9a63-130">InvalidHashValue</span></span> | <span data-ttu-id="f9a63-131">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-131">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-132">哈希 \<the invalid hash\> 值无效。</span><span class="sxs-lookup"><span data-stu-id="f9a63-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="f9a63-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="f9a63-133">InvalidDomainName</span></span> | <span data-ttu-id="f9a63-134">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-134">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-135">域名 \<the invalid domain\> 无效。</span><span class="sxs-lookup"><span data-stu-id="f9a63-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="f9a63-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="f9a63-136">InvalidIpAddress</span></span> | <span data-ttu-id="f9a63-137">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-137">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-138">IP 地址 \<the invalid IP\> 无效。</span><span class="sxs-lookup"><span data-stu-id="f9a63-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="f9a63-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="f9a63-139">InvalidUrl</span></span> | <span data-ttu-id="f9a63-140">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-140">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-141">URL \<the invalid URL\> 无效。</span><span class="sxs-lookup"><span data-stu-id="f9a63-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="f9a63-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="f9a63-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="f9a63-143">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-143">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-144">已超出最大批次大小。</span><span class="sxs-lookup"><span data-stu-id="f9a63-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="f9a63-145">Received： \<batch size received\> ， allowed： {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="f9a63-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="f9a63-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="f9a63-146">MissingRequiredParameter</span></span> | <span data-ttu-id="f9a63-147">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-147">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-148">参数 \<the missing parameter\> 缺失。</span><span class="sxs-lookup"><span data-stu-id="f9a63-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="f9a63-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="f9a63-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="f9a63-150">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-150">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-151">此操作 \<the client OS Platform\> 不支持 OS 平台。</span><span class="sxs-lookup"><span data-stu-id="f9a63-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="f9a63-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="f9a63-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="f9a63-153">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="f9a63-153">BadRequest (400)</span></span> | <span data-ttu-id="f9a63-154">\<The requested action\> 在客户端版本及 \<supported client version\> 以上版本上受支持。</span><span class="sxs-lookup"><span data-stu-id="f9a63-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="f9a63-155">未经授权 (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="f9a63-155">Unauthorized</span></span> | <span data-ttu-id="f9a63-156">未授权 (401) </span><span class="sxs-lookup"><span data-stu-id="f9a63-156">Unauthorized (401)</span></span> | <span data-ttu-id="f9a63-157">未经授权 (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="f9a63-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="f9a63-158">*注意：通常是由无效或过期的授权标头导致的。*</span><span class="sxs-lookup"><span data-stu-id="f9a63-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="f9a63-159">禁止访问 (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="f9a63-159">Forbidden</span></span> | <span data-ttu-id="f9a63-160">禁止使用 (403) </span><span class="sxs-lookup"><span data-stu-id="f9a63-160">Forbidden (403)</span></span> | <span data-ttu-id="f9a63-161">禁止访问 (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="f9a63-161">Forbidden</span></span> <br /><br /><span data-ttu-id="f9a63-162">*注意：有效的令牌，但操作权限不足*。</span><span class="sxs-lookup"><span data-stu-id="f9a63-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="f9a63-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="f9a63-163">DisabledFeature</span></span> | <span data-ttu-id="f9a63-164">禁止使用 (403) </span><span class="sxs-lookup"><span data-stu-id="f9a63-164">Forbidden (403)</span></span> | <span data-ttu-id="f9a63-165">租户功能未启用。</span><span class="sxs-lookup"><span data-stu-id="f9a63-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="f9a63-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="f9a63-166">DisallowedOperation</span></span> | <span data-ttu-id="f9a63-167">禁止使用 (403) </span><span class="sxs-lookup"><span data-stu-id="f9a63-167">Forbidden (403)</span></span> | <span data-ttu-id="f9a63-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="f9a63-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="f9a63-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="f9a63-169">NotFound</span></span> | <span data-ttu-id="f9a63-170">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="f9a63-170">Not Found (404)</span></span> | <span data-ttu-id="f9a63-171">"未找到常规"错误消息。</span><span class="sxs-lookup"><span data-stu-id="f9a63-171">General Not Found error message.</span></span>
<span data-ttu-id="f9a63-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="f9a63-172">ResourceNotFound</span></span> | <span data-ttu-id="f9a63-173">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="f9a63-173">Not Found (404)</span></span> | <span data-ttu-id="f9a63-174">未找到 \<the requested resource\> 资源。</span><span class="sxs-lookup"><span data-stu-id="f9a63-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="f9a63-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="f9a63-175">InternalServerError</span></span> | <span data-ttu-id="f9a63-176">内部服务器错误 (500) </span><span class="sxs-lookup"><span data-stu-id="f9a63-176">Internal Server Error (500)</span></span> | <span data-ttu-id="f9a63-177">*注意：无错误消息，重试该操作或联系 Microsoft（如果未解决）*</span><span class="sxs-lookup"><span data-stu-id="f9a63-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="f9a63-178">示例</span><span class="sxs-lookup"><span data-stu-id="f9a63-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="f9a63-179">Body 参数</span><span class="sxs-lookup"><span data-stu-id="f9a63-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9a63-180">正文参数区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f9a63-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="f9a63-181">如果遇到 *InvalidRequestBody* 或 *MissingRequiredParameter* 错误，这可能是由拼写错误导致的。</span><span class="sxs-lookup"><span data-stu-id="f9a63-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="f9a63-182">查看 API 文档并检查提交的参数是否与相关示例匹配。</span><span class="sxs-lookup"><span data-stu-id="f9a63-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="f9a63-183">跟踪 ID</span><span class="sxs-lookup"><span data-stu-id="f9a63-183">Tracking ID</span></span>

<span data-ttu-id="f9a63-184">每个错误响应都包含用于跟踪的唯一 ID 参数。</span><span class="sxs-lookup"><span data-stu-id="f9a63-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="f9a63-185">此参数的属性名称是 *目标*。</span><span class="sxs-lookup"><span data-stu-id="f9a63-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="f9a63-186">当我们就错误联系我们时，附加此 ID 将帮助我们找到问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="f9a63-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f9a63-187">相关文章</span><span class="sxs-lookup"><span data-stu-id="f9a63-187">Related articles</span></span>

- [<span data-ttu-id="f9a63-188">Microsoft 365 Defender API 概述</span><span class="sxs-lookup"><span data-stu-id="f9a63-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f9a63-189">支持的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="f9a63-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="f9a63-190">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="f9a63-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="f9a63-191">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="f9a63-191">Learn about API limits and licensing</span></span>](api-terms.md)
