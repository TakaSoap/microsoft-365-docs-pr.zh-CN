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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 54ae77c28523d3be6092e1567424d2d87a5f2927
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934785"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="83a96-104">常见的 REST API 错误代码</span><span class="sxs-lookup"><span data-stu-id="83a96-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="83a96-105">下表中列出的错误代码可能由任何 Microsoft Defender for Endpoint API 上的操作返回。</span><span class="sxs-lookup"><span data-stu-id="83a96-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="83a96-106">除了错误代码之外，每个错误响应还包含一条错误消息，有助于解决问题。</span><span class="sxs-lookup"><span data-stu-id="83a96-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="83a96-107">邮件是可更改的免费文本。</span><span class="sxs-lookup"><span data-stu-id="83a96-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="83a96-108">在页面底部，可以找到响应示例。</span><span class="sxs-lookup"><span data-stu-id="83a96-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="83a96-109">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="83a96-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="83a96-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="83a96-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="83a96-111">错误代码</span><span class="sxs-lookup"><span data-stu-id="83a96-111">Error code</span></span> |<span data-ttu-id="83a96-112">HTTP 状态代码</span><span class="sxs-lookup"><span data-stu-id="83a96-112">HTTP status code</span></span> |<span data-ttu-id="83a96-113">邮件</span><span class="sxs-lookup"><span data-stu-id="83a96-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="83a96-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="83a96-114">BadRequest</span></span> | <span data-ttu-id="83a96-115">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-115">BadRequest (400)</span></span> | <span data-ttu-id="83a96-116">常规错误请求错误消息。</span><span class="sxs-lookup"><span data-stu-id="83a96-116">General Bad Request error message.</span></span>
<span data-ttu-id="83a96-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="83a96-117">ODataError</span></span> | <span data-ttu-id="83a96-118">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-118">BadRequest (400)</span></span> | <span data-ttu-id="83a96-119">指定的特定错误 (OData URI 查询无效) 。</span><span class="sxs-lookup"><span data-stu-id="83a96-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="83a96-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="83a96-120">InvalidInput</span></span> | <span data-ttu-id="83a96-121">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-121">BadRequest (400)</span></span> | <span data-ttu-id="83a96-122">无效输入 {无效的输入}。</span><span class="sxs-lookup"><span data-stu-id="83a96-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="83a96-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="83a96-123">InvalidRequestBody</span></span> | <span data-ttu-id="83a96-124">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-124">BadRequest (400)</span></span> | <span data-ttu-id="83a96-125">无效的请求正文。</span><span class="sxs-lookup"><span data-stu-id="83a96-125">Invalid request body.</span></span>
<span data-ttu-id="83a96-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="83a96-126">InvalidHashValue</span></span> | <span data-ttu-id="83a96-127">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-127">BadRequest (400)</span></span> | <span data-ttu-id="83a96-128">哈希值 {无效的哈希}无效。</span><span class="sxs-lookup"><span data-stu-id="83a96-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="83a96-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="83a96-129">InvalidDomainName</span></span> | <span data-ttu-id="83a96-130">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-130">BadRequest (400)</span></span> | <span data-ttu-id="83a96-131">域名 {无效的域} 无效。</span><span class="sxs-lookup"><span data-stu-id="83a96-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="83a96-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="83a96-132">InvalidIpAddress</span></span> | <span data-ttu-id="83a96-133">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-133">BadRequest (400)</span></span> | <span data-ttu-id="83a96-134">IP 地址 {无效的 IP} 无效。</span><span class="sxs-lookup"><span data-stu-id="83a96-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="83a96-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="83a96-135">InvalidUrl</span></span> | <span data-ttu-id="83a96-136">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-136">BadRequest (400)</span></span> | <span data-ttu-id="83a96-137">URL {无效的 URL} 无效。</span><span class="sxs-lookup"><span data-stu-id="83a96-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="83a96-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="83a96-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="83a96-139">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-139">BadRequest (400)</span></span> | <span data-ttu-id="83a96-140">已超出最大批次大小。</span><span class="sxs-lookup"><span data-stu-id="83a96-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="83a96-141">Received： {batch size received}， allowed： {batch size allowed}.</span><span class="sxs-lookup"><span data-stu-id="83a96-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="83a96-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="83a96-142">MissingRequiredParameter</span></span> | <span data-ttu-id="83a96-143">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-143">BadRequest (400)</span></span> | <span data-ttu-id="83a96-144">参数 {缺少参数}。</span><span class="sxs-lookup"><span data-stu-id="83a96-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="83a96-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="83a96-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="83a96-146">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-146">BadRequest (400)</span></span> | <span data-ttu-id="83a96-147">此操作不支持 OS 平台 {the client OS Platform}。</span><span class="sxs-lookup"><span data-stu-id="83a96-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="83a96-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="83a96-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="83a96-149">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="83a96-149">BadRequest (400)</span></span> | <span data-ttu-id="83a96-150">{请求的操作} 在客户端版本 {支持的客户端版本} 及以上版本上受支持。</span><span class="sxs-lookup"><span data-stu-id="83a96-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="83a96-151">未经授权 (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="83a96-151">Unauthorized</span></span> | <span data-ttu-id="83a96-152">未经授权 (401) </span><span class="sxs-lookup"><span data-stu-id="83a96-152">Unauthorized (401)</span></span> | <span data-ttu-id="83a96-153">未授权 (或过期的授权标头) 。</span><span class="sxs-lookup"><span data-stu-id="83a96-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="83a96-154">禁止访问 (Forbidden)</span><span class="sxs-lookup"><span data-stu-id="83a96-154">Forbidden</span></span> | <span data-ttu-id="83a96-155">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="83a96-155">Forbidden (403)</span></span> | <span data-ttu-id="83a96-156">禁止 (有效令牌，但权限不足，无法) 。</span><span class="sxs-lookup"><span data-stu-id="83a96-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="83a96-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="83a96-157">DisabledFeature</span></span> | <span data-ttu-id="83a96-158">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="83a96-158">Forbidden (403)</span></span> | <span data-ttu-id="83a96-159">未启用租户功能。</span><span class="sxs-lookup"><span data-stu-id="83a96-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="83a96-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="83a96-160">DisallowedOperation</span></span> | <span data-ttu-id="83a96-161">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="83a96-161">Forbidden (403)</span></span> | <span data-ttu-id="83a96-162">{不允许的操作和原因}。</span><span class="sxs-lookup"><span data-stu-id="83a96-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="83a96-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="83a96-163">NotFound</span></span> | <span data-ttu-id="83a96-164">404 (未找到) </span><span class="sxs-lookup"><span data-stu-id="83a96-164">Not Found (404)</span></span> | <span data-ttu-id="83a96-165">"常规未找到"错误消息。</span><span class="sxs-lookup"><span data-stu-id="83a96-165">General Not Found error message.</span></span>
<span data-ttu-id="83a96-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="83a96-166">ResourceNotFound</span></span> | <span data-ttu-id="83a96-167">404 (未找到) </span><span class="sxs-lookup"><span data-stu-id="83a96-167">Not Found (404)</span></span> | <span data-ttu-id="83a96-168">未找到资源 {请求的资源}。</span><span class="sxs-lookup"><span data-stu-id="83a96-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="83a96-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="83a96-169">InternalServerError</span></span> | <span data-ttu-id="83a96-170">内部服务器错误 (500) </span><span class="sxs-lookup"><span data-stu-id="83a96-170">Internal Server Error (500)</span></span> | <span data-ttu-id="83a96-171"> (无错误消息，请重试) </span><span class="sxs-lookup"><span data-stu-id="83a96-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="83a96-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="83a96-172">TooManyRequests</span></span> | <span data-ttu-id="83a96-173">请求数过多 (429) </span><span class="sxs-lookup"><span data-stu-id="83a96-173">Too Many Requests (429)</span></span> | <span data-ttu-id="83a96-174">响应表示请求数或 CPU 达到配额限制。</span><span class="sxs-lookup"><span data-stu-id="83a96-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="83a96-175">正文参数区分大小写</span><span class="sxs-lookup"><span data-stu-id="83a96-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="83a96-176">提交的正文参数当前区分大小写。</span><span class="sxs-lookup"><span data-stu-id="83a96-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="83a96-177">如果遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 错误，可能是参数大写或小写字母错误导致的。</span><span class="sxs-lookup"><span data-stu-id="83a96-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="83a96-178">查看 API 文档页，并检查提交的参数是否与相关示例匹配。</span><span class="sxs-lookup"><span data-stu-id="83a96-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="83a96-179">相关请求 ID</span><span class="sxs-lookup"><span data-stu-id="83a96-179">Correlation request ID</span></span>

<span data-ttu-id="83a96-180">每个错误响应都包含用于跟踪的唯一 ID 参数。</span><span class="sxs-lookup"><span data-stu-id="83a96-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="83a96-181">此参数的属性名称为"target"。</span><span class="sxs-lookup"><span data-stu-id="83a96-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="83a96-182">当我们就错误联系我们时，附加此 ID 将有助于找到问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="83a96-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="83a96-183">示例</span><span class="sxs-lookup"><span data-stu-id="83a96-183">Examples</span></span>

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
