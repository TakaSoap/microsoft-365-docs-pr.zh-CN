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
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="61126-104">常见 Microsoft 365 Defender REST API 错误代码</span><span class="sxs-lookup"><span data-stu-id="61126-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="61126-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="61126-105">**Applies to:**</span></span>
- <span data-ttu-id="61126-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61126-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="61126-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="61126-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="61126-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="61126-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="61126-109">下表中列出的错误代码可能由任何 Microsoft 365 Defender Api 上的操作返回。</span><span class="sxs-lookup"><span data-stu-id="61126-109">The error codes listed in the following table may be returned by an operation on any of Microsoft 365 Defender APIs.</span></span>

<span data-ttu-id="61126-110">每个错误响应都包含一条错误消息，可帮助解决该问题。</span><span class="sxs-lookup"><span data-stu-id="61126-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="61126-111">邮件是可更改的自由文本。</span><span class="sxs-lookup"><span data-stu-id="61126-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="61126-112">在页面底部，您可以找到响应示例。</span><span class="sxs-lookup"><span data-stu-id="61126-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="61126-113">错误代码</span><span class="sxs-lookup"><span data-stu-id="61126-113">Error code</span></span> |<span data-ttu-id="61126-114">HTTP 状态代码</span><span class="sxs-lookup"><span data-stu-id="61126-114">HTTP status code</span></span> |<span data-ttu-id="61126-115">邮件</span><span class="sxs-lookup"><span data-stu-id="61126-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="61126-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="61126-116">BadRequest</span></span> | <span data-ttu-id="61126-117">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-117">BadRequest (400)</span></span> | <span data-ttu-id="61126-118">一般错误的请求错误消息。</span><span class="sxs-lookup"><span data-stu-id="61126-118">General Bad Request error message.</span></span>
<span data-ttu-id="61126-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="61126-119">ODataError</span></span> | <span data-ttu-id="61126-120">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-120">BadRequest (400)</span></span> | <span data-ttu-id="61126-121">OData URI 查询无效 () 指定了特定错误。</span><span class="sxs-lookup"><span data-stu-id="61126-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="61126-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="61126-122">InvalidInput</span></span> | <span data-ttu-id="61126-123">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-123">BadRequest (400)</span></span> | <span data-ttu-id="61126-124">无效输入 {无效输入}。</span><span class="sxs-lookup"><span data-stu-id="61126-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="61126-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="61126-125">InvalidRequestBody</span></span> | <span data-ttu-id="61126-126">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-126">BadRequest (400)</span></span> | <span data-ttu-id="61126-127">请求正文无效。</span><span class="sxs-lookup"><span data-stu-id="61126-127">Invalid request body.</span></span>
<span data-ttu-id="61126-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="61126-128">InvalidHashValue</span></span> | <span data-ttu-id="61126-129">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-129">BadRequest (400)</span></span> | <span data-ttu-id="61126-130">哈希值 {无效的哈希} 无效。</span><span class="sxs-lookup"><span data-stu-id="61126-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="61126-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="61126-131">InvalidDomainName</span></span> | <span data-ttu-id="61126-132">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-132">BadRequest (400)</span></span> | <span data-ttu-id="61126-133">域名 {无效域} 无效。</span><span class="sxs-lookup"><span data-stu-id="61126-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="61126-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="61126-134">InvalidIpAddress</span></span> | <span data-ttu-id="61126-135">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-135">BadRequest (400)</span></span> | <span data-ttu-id="61126-136">IP 地址 {无效的 IP} 无效。</span><span class="sxs-lookup"><span data-stu-id="61126-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="61126-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="61126-137">InvalidUrl</span></span> | <span data-ttu-id="61126-138">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-138">BadRequest (400)</span></span> | <span data-ttu-id="61126-139">URL {无效的 URL} 无效。</span><span class="sxs-lookup"><span data-stu-id="61126-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="61126-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="61126-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="61126-141">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-141">BadRequest (400)</span></span> | <span data-ttu-id="61126-142">超出了最大批处理大小。</span><span class="sxs-lookup"><span data-stu-id="61126-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="61126-143">已接收： {已接收批处理大小}，允许： {允许批处理大小}。</span><span class="sxs-lookup"><span data-stu-id="61126-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="61126-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="61126-144">MissingRequiredParameter</span></span> | <span data-ttu-id="61126-145">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-145">BadRequest (400)</span></span> | <span data-ttu-id="61126-146">参数 {缺少的参数} 缺失。</span><span class="sxs-lookup"><span data-stu-id="61126-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="61126-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="61126-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="61126-148">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-148">BadRequest (400)</span></span> | <span data-ttu-id="61126-149">此操作不支持 OS Platform {client OS Platform}。</span><span class="sxs-lookup"><span data-stu-id="61126-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="61126-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="61126-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="61126-151">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="61126-151">BadRequest (400)</span></span> | <span data-ttu-id="61126-152">{客户端版本 {支持的客户端版本）和更高版本支持所请求的操作。</span><span class="sxs-lookup"><span data-stu-id="61126-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="61126-153">未经授权 (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="61126-153">Unauthorized</span></span> | <span data-ttu-id="61126-154">未经授权的 (401) </span><span class="sxs-lookup"><span data-stu-id="61126-154">Unauthorized (401)</span></span> | <span data-ttu-id="61126-155">未经授权 (通常是无效或已过期的授权标头) 。</span><span class="sxs-lookup"><span data-stu-id="61126-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="61126-156">禁止访问 (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="61126-156">Forbidden</span></span> | <span data-ttu-id="61126-157">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="61126-157">Forbidden (403)</span></span> | <span data-ttu-id="61126-158">禁止 (有效令牌，但权限不足，无法执行操作) 。</span><span class="sxs-lookup"><span data-stu-id="61126-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="61126-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="61126-159">DisabledFeature</span></span> | <span data-ttu-id="61126-160">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="61126-160">Forbidden (403)</span></span> | <span data-ttu-id="61126-161">未启用租户功能。</span><span class="sxs-lookup"><span data-stu-id="61126-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="61126-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="61126-162">DisallowedOperation</span></span> | <span data-ttu-id="61126-163">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="61126-163">Forbidden (403)</span></span> | <span data-ttu-id="61126-164">{不允许的操作和原因。</span><span class="sxs-lookup"><span data-stu-id="61126-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="61126-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="61126-165">NotFound</span></span> | <span data-ttu-id="61126-166">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="61126-166">Not Found (404)</span></span> | <span data-ttu-id="61126-167">找不到常规错误消息。</span><span class="sxs-lookup"><span data-stu-id="61126-167">General Not Found error message.</span></span>
<span data-ttu-id="61126-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="61126-168">ResourceNotFound</span></span> | <span data-ttu-id="61126-169">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="61126-169">Not Found (404)</span></span> | <span data-ttu-id="61126-170">资源 {找不到请求的资源}。</span><span class="sxs-lookup"><span data-stu-id="61126-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="61126-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="61126-171">InternalServerError</span></span> | <span data-ttu-id="61126-172">内部服务器错误 (500) </span><span class="sxs-lookup"><span data-stu-id="61126-172">Internal Server Error (500)</span></span> | <span data-ttu-id="61126-173"> (不会出现错误消息，请重试操作，否则请与我们联系（如果它未得到解决) </span><span class="sxs-lookup"><span data-stu-id="61126-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="61126-174">正文参数区分大小写</span><span class="sxs-lookup"><span data-stu-id="61126-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="61126-175">提交的正文参数当前区分大小写。</span><span class="sxs-lookup"><span data-stu-id="61126-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="61126-176">如果遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 错误，则可能是由错误的参数大写或小写字母导致的。</span><span class="sxs-lookup"><span data-stu-id="61126-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="61126-177">建议您查看 API 文档页，并检查提交的参数是否与相关的示例相匹配。</span><span class="sxs-lookup"><span data-stu-id="61126-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="61126-178">关联请求 ID</span><span class="sxs-lookup"><span data-stu-id="61126-178">Correlation request ID</span></span>

<span data-ttu-id="61126-179">每个错误响应包含一个用于跟踪的唯一 ID 参数。</span><span class="sxs-lookup"><span data-stu-id="61126-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="61126-180">此参数的属性名称为 "target"。</span><span class="sxs-lookup"><span data-stu-id="61126-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="61126-181">在与我们联系时，附加此 ID 可帮助查找问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="61126-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="61126-182">示例</span><span class="sxs-lookup"><span data-stu-id="61126-182">Examples</span></span>

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

