---
title: 常见的 Microsoft 威胁防护 REST API 错误代码
description: 了解常见的 Microsoft 威胁防护 REST API 错误代码
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
ms.openlocfilehash: 81375b919b52ff895e5ec7014feb747b1a0eae65
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201335"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a><span data-ttu-id="d573e-104">常见的 Microsoft 威胁防护 REST API 错误代码</span><span class="sxs-lookup"><span data-stu-id="d573e-104">Common Microsoft Threat Protection REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d573e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d573e-105">**Applies to:**</span></span>
- <span data-ttu-id="d573e-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="d573e-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="d573e-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="d573e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d573e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="d573e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d573e-109">下表中列出的错误代码可能由任何 Microsoft 威胁防护 Api 上的操作返回。</span><span class="sxs-lookup"><span data-stu-id="d573e-109">The error codes listed in the following table may be returned by an operation on any of Microsoft Threat Protection APIs.</span></span>

<span data-ttu-id="d573e-110">每个错误响应都包含一条错误消息，可帮助解决该问题。</span><span class="sxs-lookup"><span data-stu-id="d573e-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="d573e-111">邮件是可更改的自由文本。</span><span class="sxs-lookup"><span data-stu-id="d573e-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="d573e-112">在页面底部，您可以找到响应示例。</span><span class="sxs-lookup"><span data-stu-id="d573e-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="d573e-113">错误代码</span><span class="sxs-lookup"><span data-stu-id="d573e-113">Error code</span></span> |<span data-ttu-id="d573e-114">HTTP 状态代码</span><span class="sxs-lookup"><span data-stu-id="d573e-114">HTTP status code</span></span> |<span data-ttu-id="d573e-115">邮件</span><span class="sxs-lookup"><span data-stu-id="d573e-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="d573e-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="d573e-116">BadRequest</span></span> | <span data-ttu-id="d573e-117">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-117">BadRequest (400)</span></span> | <span data-ttu-id="d573e-118">一般错误的请求错误消息。</span><span class="sxs-lookup"><span data-stu-id="d573e-118">General Bad Request error message.</span></span>
<span data-ttu-id="d573e-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="d573e-119">ODataError</span></span> | <span data-ttu-id="d573e-120">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-120">BadRequest (400)</span></span> | <span data-ttu-id="d573e-121">OData URI 查询无效 () 指定了特定错误。</span><span class="sxs-lookup"><span data-stu-id="d573e-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="d573e-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="d573e-122">InvalidInput</span></span> | <span data-ttu-id="d573e-123">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-123">BadRequest (400)</span></span> | <span data-ttu-id="d573e-124">无效输入 {无效输入}。</span><span class="sxs-lookup"><span data-stu-id="d573e-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="d573e-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="d573e-125">InvalidRequestBody</span></span> | <span data-ttu-id="d573e-126">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-126">BadRequest (400)</span></span> | <span data-ttu-id="d573e-127">请求正文无效。</span><span class="sxs-lookup"><span data-stu-id="d573e-127">Invalid request body.</span></span>
<span data-ttu-id="d573e-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="d573e-128">InvalidHashValue</span></span> | <span data-ttu-id="d573e-129">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-129">BadRequest (400)</span></span> | <span data-ttu-id="d573e-130">哈希值 {无效的哈希} 无效。</span><span class="sxs-lookup"><span data-stu-id="d573e-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="d573e-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="d573e-131">InvalidDomainName</span></span> | <span data-ttu-id="d573e-132">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-132">BadRequest (400)</span></span> | <span data-ttu-id="d573e-133">域名 {无效域} 无效。</span><span class="sxs-lookup"><span data-stu-id="d573e-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="d573e-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="d573e-134">InvalidIpAddress</span></span> | <span data-ttu-id="d573e-135">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-135">BadRequest (400)</span></span> | <span data-ttu-id="d573e-136">IP 地址 {无效的 IP} 无效。</span><span class="sxs-lookup"><span data-stu-id="d573e-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="d573e-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="d573e-137">InvalidUrl</span></span> | <span data-ttu-id="d573e-138">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-138">BadRequest (400)</span></span> | <span data-ttu-id="d573e-139">URL {无效的 URL} 无效。</span><span class="sxs-lookup"><span data-stu-id="d573e-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="d573e-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="d573e-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="d573e-141">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-141">BadRequest (400)</span></span> | <span data-ttu-id="d573e-142">超出了最大批处理大小。</span><span class="sxs-lookup"><span data-stu-id="d573e-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="d573e-143">已接收： {已接收批处理大小}，允许： {允许批处理大小}。</span><span class="sxs-lookup"><span data-stu-id="d573e-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="d573e-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="d573e-144">MissingRequiredParameter</span></span> | <span data-ttu-id="d573e-145">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-145">BadRequest (400)</span></span> | <span data-ttu-id="d573e-146">参数 {缺少的参数} 缺失。</span><span class="sxs-lookup"><span data-stu-id="d573e-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="d573e-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="d573e-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="d573e-148">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-148">BadRequest (400)</span></span> | <span data-ttu-id="d573e-149">此操作不支持 OS Platform {client OS Platform}。</span><span class="sxs-lookup"><span data-stu-id="d573e-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="d573e-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="d573e-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="d573e-151">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="d573e-151">BadRequest (400)</span></span> | <span data-ttu-id="d573e-152">{客户端版本 {支持的客户端版本）和更高版本支持所请求的操作。</span><span class="sxs-lookup"><span data-stu-id="d573e-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="d573e-153">未经授权 (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="d573e-153">Unauthorized</span></span> | <span data-ttu-id="d573e-154">未经授权的 (401) </span><span class="sxs-lookup"><span data-stu-id="d573e-154">Unauthorized (401)</span></span> | <span data-ttu-id="d573e-155">未经授权 (通常是无效或已过期的授权标头) 。</span><span class="sxs-lookup"><span data-stu-id="d573e-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="d573e-156">禁止访问 (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="d573e-156">Forbidden</span></span> | <span data-ttu-id="d573e-157">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="d573e-157">Forbidden (403)</span></span> | <span data-ttu-id="d573e-158">禁止 (有效令牌，但权限不足，无法执行操作) 。</span><span class="sxs-lookup"><span data-stu-id="d573e-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="d573e-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="d573e-159">DisabledFeature</span></span> | <span data-ttu-id="d573e-160">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="d573e-160">Forbidden (403)</span></span> | <span data-ttu-id="d573e-161">未启用租户功能。</span><span class="sxs-lookup"><span data-stu-id="d573e-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="d573e-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="d573e-162">DisallowedOperation</span></span> | <span data-ttu-id="d573e-163">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="d573e-163">Forbidden (403)</span></span> | <span data-ttu-id="d573e-164">{不允许的操作和原因。</span><span class="sxs-lookup"><span data-stu-id="d573e-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="d573e-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="d573e-165">NotFound</span></span> | <span data-ttu-id="d573e-166">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="d573e-166">Not Found (404)</span></span> | <span data-ttu-id="d573e-167">找不到常规错误消息。</span><span class="sxs-lookup"><span data-stu-id="d573e-167">General Not Found error message.</span></span>
<span data-ttu-id="d573e-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="d573e-168">ResourceNotFound</span></span> | <span data-ttu-id="d573e-169">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="d573e-169">Not Found (404)</span></span> | <span data-ttu-id="d573e-170">资源 {找不到请求的资源}。</span><span class="sxs-lookup"><span data-stu-id="d573e-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="d573e-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="d573e-171">InternalServerError</span></span> | <span data-ttu-id="d573e-172">内部服务器错误 (500) </span><span class="sxs-lookup"><span data-stu-id="d573e-172">Internal Server Error (500)</span></span> | <span data-ttu-id="d573e-173"> (不会出现错误消息，请重试操作，否则请与我们联系（如果它未得到解决) </span><span class="sxs-lookup"><span data-stu-id="d573e-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="d573e-174">正文参数区分大小写</span><span class="sxs-lookup"><span data-stu-id="d573e-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="d573e-175">提交的正文参数当前区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d573e-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="d573e-176">如果遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 错误，则可能是由错误的参数大写或小写字母导致的。</span><span class="sxs-lookup"><span data-stu-id="d573e-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="d573e-177">建议您查看 API 文档页，并检查提交的参数是否与相关的示例相匹配。</span><span class="sxs-lookup"><span data-stu-id="d573e-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="d573e-178">关联请求 ID</span><span class="sxs-lookup"><span data-stu-id="d573e-178">Correlation request ID</span></span>

<span data-ttu-id="d573e-179">每个错误响应包含一个用于跟踪的唯一 ID 参数。</span><span class="sxs-lookup"><span data-stu-id="d573e-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="d573e-180">此参数的属性名称为 "target"。</span><span class="sxs-lookup"><span data-stu-id="d573e-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="d573e-181">在与我们联系时，附加此 ID 可帮助查找问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="d573e-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="d573e-182">示例</span><span class="sxs-lookup"><span data-stu-id="d573e-182">Examples</span></span>

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

