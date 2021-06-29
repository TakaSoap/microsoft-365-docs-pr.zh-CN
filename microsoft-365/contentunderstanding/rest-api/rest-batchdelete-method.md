---
title: 批处理删除
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: 使用 REST API 从一个或多个库中删除应用的文档理解模型。
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177233"
---
# <a name="batchdelete"></a><span data-ttu-id="fd53b-103">批处理删除</span><span class="sxs-lookup"><span data-stu-id="fd53b-103">BatchDelete</span></span>

<span data-ttu-id="fd53b-104">从一个或多个库中删除应用的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="fd53b-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="fd53b-105">请注意，必须先从所有库删除模型才能将其删除（请参阅 [示例](rest-batchdelete-method.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="fd53b-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="fd53b-106">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="fd53b-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="fd53b-107">URI 参数</span><span class="sxs-lookup"><span data-stu-id="fd53b-107">URI parameters</span></span>

<span data-ttu-id="fd53b-108">无</span><span class="sxs-lookup"><span data-stu-id="fd53b-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="fd53b-109">请求标头</span><span class="sxs-lookup"><span data-stu-id="fd53b-109">Request headers</span></span>

| <span data-ttu-id="fd53b-110">标头</span><span class="sxs-lookup"><span data-stu-id="fd53b-110">Header</span></span> | <span data-ttu-id="fd53b-111">值</span><span class="sxs-lookup"><span data-stu-id="fd53b-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="fd53b-112">Accept</span><span class="sxs-lookup"><span data-stu-id="fd53b-112">Accept</span></span>|<span data-ttu-id="fd53b-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="fd53b-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="fd53b-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="fd53b-114">Content-Type</span></span>|<span data-ttu-id="fd53b-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="fd53b-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="fd53b-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="fd53b-116">x-requestdigest</span></span>|<span data-ttu-id="fd53b-117">当前网站的相应摘要。</span><span class="sxs-lookup"><span data-stu-id="fd53b-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="fd53b-118">请求正文</span><span class="sxs-lookup"><span data-stu-id="fd53b-118">Request body</span></span>

| <span data-ttu-id="fd53b-119">Name</span><span class="sxs-lookup"><span data-stu-id="fd53b-119">Name</span></span> | <span data-ttu-id="fd53b-120">必需</span><span class="sxs-lookup"><span data-stu-id="fd53b-120">Required</span></span> | <span data-ttu-id="fd53b-121">类型</span><span class="sxs-lookup"><span data-stu-id="fd53b-121">Type</span></span> | <span data-ttu-id="fd53b-122">说明</span><span class="sxs-lookup"><span data-stu-id="fd53b-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="fd53b-123">出版物</span><span class="sxs-lookup"><span data-stu-id="fd53b-123">Publications</span></span>|<span data-ttu-id="fd53b-124">是</span><span class="sxs-lookup"><span data-stu-id="fd53b-124">yes</span></span>|<span data-ttu-id="fd53b-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="fd53b-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="fd53b-126">MachineLearningPublicationEntityData 集合，其中每个集合均指定了模型和目标文档库。</span><span class="sxs-lookup"><span data-stu-id="fd53b-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="fd53b-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="fd53b-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="fd53b-128">Name</span><span class="sxs-lookup"><span data-stu-id="fd53b-128">Name</span></span> | <span data-ttu-id="fd53b-129">必需</span><span class="sxs-lookup"><span data-stu-id="fd53b-129">Required</span></span> | <span data-ttu-id="fd53b-130">类型</span><span class="sxs-lookup"><span data-stu-id="fd53b-130">Type</span></span> | <span data-ttu-id="fd53b-131">说明</span><span class="sxs-lookup"><span data-stu-id="fd53b-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="fd53b-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="fd53b-132">ModelUniqueId</span></span>|<span data-ttu-id="fd53b-133">是</span><span class="sxs-lookup"><span data-stu-id="fd53b-133">yes</span></span>|<span data-ttu-id="fd53b-134">字符串</span><span class="sxs-lookup"><span data-stu-id="fd53b-134">string</span></span>|<span data-ttu-id="fd53b-135">模型文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fd53b-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="fd53b-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="fd53b-136">TargetSiteUrl</span></span>|<span data-ttu-id="fd53b-137">是</span><span class="sxs-lookup"><span data-stu-id="fd53b-137">yes</span></span>|<span data-ttu-id="fd53b-138">字符串</span><span class="sxs-lookup"><span data-stu-id="fd53b-138">string</span></span>|<span data-ttu-id="fd53b-139">目标库网站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="fd53b-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="fd53b-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="fd53b-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="fd53b-141">是</span><span class="sxs-lookup"><span data-stu-id="fd53b-141">yes</span></span>|<span data-ttu-id="fd53b-142">字符串</span><span class="sxs-lookup"><span data-stu-id="fd53b-142">string</span></span>|<span data-ttu-id="fd53b-143">目标库的 Web 的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd53b-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="fd53b-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="fd53b-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="fd53b-145">是</span><span class="sxs-lookup"><span data-stu-id="fd53b-145">yes</span></span>|<span data-ttu-id="fd53b-146">字符串</span><span class="sxs-lookup"><span data-stu-id="fd53b-146">string</span></span>|<span data-ttu-id="fd53b-147">目标库的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd53b-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="fd53b-148">响应</span><span class="sxs-lookup"><span data-stu-id="fd53b-148">Response</span></span>

| <span data-ttu-id="fd53b-149">名称</span><span class="sxs-lookup"><span data-stu-id="fd53b-149">Name</span></span>   | <span data-ttu-id="fd53b-150">类型</span><span class="sxs-lookup"><span data-stu-id="fd53b-150">Type</span></span>  | <span data-ttu-id="fd53b-151">说明</span><span class="sxs-lookup"><span data-stu-id="fd53b-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="fd53b-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="fd53b-152">200 OK</span></span>||<span data-ttu-id="fd53b-153">这是一个自定义 API，用于支持从多文档库中删除模型。</span><span class="sxs-lookup"><span data-stu-id="fd53b-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="fd53b-154">如果部分成功，仍可返回 200 OK，调用方需要检查响应正文，以了解模型是否已成功从文档库中删除。</span><span class="sxs-lookup"><span data-stu-id="fd53b-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="fd53b-155">响应正文</span><span class="sxs-lookup"><span data-stu-id="fd53b-155">Response Body</span></span>
| <span data-ttu-id="fd53b-156">名称</span><span class="sxs-lookup"><span data-stu-id="fd53b-156">Name</span></span>   | <span data-ttu-id="fd53b-157">类型</span><span class="sxs-lookup"><span data-stu-id="fd53b-157">Type</span></span>  | <span data-ttu-id="fd53b-158">说明</span><span class="sxs-lookup"><span data-stu-id="fd53b-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="fd53b-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="fd53b-159">TotalSuccesses</span></span>|<span data-ttu-id="fd53b-160">int</span><span class="sxs-lookup"><span data-stu-id="fd53b-160">int</span></span>|<span data-ttu-id="fd53b-161">从文档库中成功删除的模型的总数。</span><span class="sxs-lookup"><span data-stu-id="fd53b-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="fd53b-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="fd53b-162">TotalFailures</span></span>|<span data-ttu-id="fd53b-163">int</span><span class="sxs-lookup"><span data-stu-id="fd53b-163">int</span></span>|<span data-ttu-id="fd53b-164">未能从文档库中删除的模型的总数。</span><span class="sxs-lookup"><span data-stu-id="fd53b-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="fd53b-165">详细信息</span><span class="sxs-lookup"><span data-stu-id="fd53b-165">Details</span></span>|<span data-ttu-id="fd53b-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="fd53b-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="fd53b-167">MachineLearningPublicationResult 的集合，其中每个集合均指定了从文档库中删除模型的详细结果。</span><span class="sxs-lookup"><span data-stu-id="fd53b-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="fd53b-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="fd53b-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="fd53b-169">名称</span><span class="sxs-lookup"><span data-stu-id="fd53b-169">Name</span></span>   | <span data-ttu-id="fd53b-170">类型</span><span class="sxs-lookup"><span data-stu-id="fd53b-170">Type</span></span>  | <span data-ttu-id="fd53b-171">说明</span><span class="sxs-lookup"><span data-stu-id="fd53b-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="fd53b-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="fd53b-172">StatusCode</span></span>|<span data-ttu-id="fd53b-173">int</span><span class="sxs-lookup"><span data-stu-id="fd53b-173">int</span></span>|<span data-ttu-id="fd53b-174">HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="fd53b-174">The HTTP status code.</span></span>|
|<span data-ttu-id="fd53b-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="fd53b-175">ErrorMessage</span></span>|<span data-ttu-id="fd53b-176">string</span><span class="sxs-lookup"><span data-stu-id="fd53b-176">string</span></span>|<span data-ttu-id="fd53b-177">将模型应用到文档库时会显示错误内容的错误消息。</span><span class="sxs-lookup"><span data-stu-id="fd53b-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="fd53b-178">出版物</span><span class="sxs-lookup"><span data-stu-id="fd53b-178">Publication</span></span>|<span data-ttu-id="fd53b-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="fd53b-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="fd53b-180">它指定了模型信息和目标文档库。</span><span class="sxs-lookup"><span data-stu-id="fd53b-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="fd53b-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="fd53b-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="fd53b-182">名称</span><span class="sxs-lookup"><span data-stu-id="fd53b-182">Name</span></span> | <span data-ttu-id="fd53b-183">类型</span><span class="sxs-lookup"><span data-stu-id="fd53b-183">Type</span></span> | <span data-ttu-id="fd53b-184">说明</span><span class="sxs-lookup"><span data-stu-id="fd53b-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="fd53b-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="fd53b-185">ModelUniqueId</span></span>|<span data-ttu-id="fd53b-186">字符串</span><span class="sxs-lookup"><span data-stu-id="fd53b-186">string</span></span>|<span data-ttu-id="fd53b-187">模型文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fd53b-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="fd53b-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="fd53b-188">TargetSiteUrl</span></span>|<span data-ttu-id="fd53b-189">字符串</span><span class="sxs-lookup"><span data-stu-id="fd53b-189">string</span></span>|<span data-ttu-id="fd53b-190">目标库网站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="fd53b-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="fd53b-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="fd53b-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="fd53b-192">字符串</span><span class="sxs-lookup"><span data-stu-id="fd53b-192">string</span></span>|<span data-ttu-id="fd53b-193">目标库的 Web 的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd53b-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="fd53b-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="fd53b-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="fd53b-195">字符串</span><span class="sxs-lookup"><span data-stu-id="fd53b-195">string</span></span>|<span data-ttu-id="fd53b-196">目标库的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd53b-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="fd53b-197">示例</span><span class="sxs-lookup"><span data-stu-id="fd53b-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="fd53b-198">从存储库网站中的合同文档库中删除模型</span><span class="sxs-lookup"><span data-stu-id="fd53b-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="fd53b-199">此示例中，Contoso 合同文档理解模型的 ID 为 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="fd53b-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="fd53b-200">示例请求</span><span class="sxs-lookup"><span data-stu-id="fd53b-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a><span data-ttu-id="fd53b-201">示例响应</span><span class="sxs-lookup"><span data-stu-id="fd53b-201">Sample response</span></span>

<span data-ttu-id="fd53b-202">在响应中，TotalFailures 和 TotalSuccesses 指从指定库中删除模型的失败和成功次数。</span><span class="sxs-lookup"><span data-stu-id="fd53b-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="fd53b-203">**状态代码：** 200</span><span class="sxs-lookup"><span data-stu-id="fd53b-203">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="fd53b-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd53b-204">See also</span></span>

[<span data-ttu-id="fd53b-205">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="fd53b-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
