---
title: 批处理应用模型
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
description: 使用 REST API 将文档理解模型应用至一个或多个库。
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286533"
---
# <a name="batch-apply-model"></a><span data-ttu-id="17962-103">批处理应用模型</span><span class="sxs-lookup"><span data-stu-id="17962-103">Batch Apply model</span></span>

<span data-ttu-id="17962-104">将经过培训的文档理解模型应用（或同步）到一个或多个库（请参阅 [示例](rest-applymodel-method.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="17962-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="17962-105">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="17962-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="17962-106">URI 参数</span><span class="sxs-lookup"><span data-stu-id="17962-106">URI parameters</span></span>

<span data-ttu-id="17962-107">无</span><span class="sxs-lookup"><span data-stu-id="17962-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="17962-108">请求标头</span><span class="sxs-lookup"><span data-stu-id="17962-108">Request headers</span></span>

| <span data-ttu-id="17962-109">标头</span><span class="sxs-lookup"><span data-stu-id="17962-109">Header</span></span> | <span data-ttu-id="17962-110">值</span><span class="sxs-lookup"><span data-stu-id="17962-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="17962-111">Accept</span><span class="sxs-lookup"><span data-stu-id="17962-111">Accept</span></span>|<span data-ttu-id="17962-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="17962-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="17962-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="17962-113">Content-Type</span></span>|<span data-ttu-id="17962-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="17962-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="17962-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="17962-115">x-requestdigest</span></span>|<span data-ttu-id="17962-116">当前网站的相应摘要。</span><span class="sxs-lookup"><span data-stu-id="17962-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="17962-117">请求正文</span><span class="sxs-lookup"><span data-stu-id="17962-117">Request body</span></span>

| <span data-ttu-id="17962-118">Name</span><span class="sxs-lookup"><span data-stu-id="17962-118">Name</span></span> | <span data-ttu-id="17962-119">必需</span><span class="sxs-lookup"><span data-stu-id="17962-119">Required</span></span> | <span data-ttu-id="17962-120">类型</span><span class="sxs-lookup"><span data-stu-id="17962-120">Type</span></span> | <span data-ttu-id="17962-121">说明</span><span class="sxs-lookup"><span data-stu-id="17962-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="17962-122">_metadata</span><span class="sxs-lookup"><span data-stu-id="17962-122">__metadata</span></span>|<span data-ttu-id="17962-123">是</span><span class="sxs-lookup"><span data-stu-id="17962-123">yes</span></span>|<span data-ttu-id="17962-124">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-124">string</span></span>|<span data-ttu-id="17962-125">在 SPO 上设置对象元。</span><span class="sxs-lookup"><span data-stu-id="17962-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="17962-126">始终使用值：{"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}。</span><span class="sxs-lookup"><span data-stu-id="17962-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="17962-127">出版物</span><span class="sxs-lookup"><span data-stu-id="17962-127">Publications</span></span>|<span data-ttu-id="17962-128">是</span><span class="sxs-lookup"><span data-stu-id="17962-128">yes</span></span>|<span data-ttu-id="17962-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="17962-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="17962-130">MachineLearningPublicationEntityData 集合，其中每个集合均指定了模型和目标文档库。</span><span class="sxs-lookup"><span data-stu-id="17962-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="17962-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="17962-131">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="17962-132">Name</span><span class="sxs-lookup"><span data-stu-id="17962-132">Name</span></span> | <span data-ttu-id="17962-133">必需</span><span class="sxs-lookup"><span data-stu-id="17962-133">Required</span></span> | <span data-ttu-id="17962-134">类型</span><span class="sxs-lookup"><span data-stu-id="17962-134">Type</span></span> | <span data-ttu-id="17962-135">说明</span><span class="sxs-lookup"><span data-stu-id="17962-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="17962-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="17962-136">ModelUniqueId</span></span>|<span data-ttu-id="17962-137">是</span><span class="sxs-lookup"><span data-stu-id="17962-137">yes</span></span>|<span data-ttu-id="17962-138">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-138">string</span></span>|<span data-ttu-id="17962-139">模型文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="17962-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="17962-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="17962-140">TargetSiteUrl</span></span>|<span data-ttu-id="17962-141">是</span><span class="sxs-lookup"><span data-stu-id="17962-141">yes</span></span>|<span data-ttu-id="17962-142">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-142">string</span></span>|<span data-ttu-id="17962-143">目标库网站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="17962-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="17962-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="17962-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="17962-145">是</span><span class="sxs-lookup"><span data-stu-id="17962-145">yes</span></span>|<span data-ttu-id="17962-146">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-146">string</span></span>|<span data-ttu-id="17962-147">目标库的 Web 的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="17962-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="17962-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="17962-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="17962-149">是</span><span class="sxs-lookup"><span data-stu-id="17962-149">yes</span></span>|<span data-ttu-id="17962-150">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-150">string</span></span>|<span data-ttu-id="17962-151">目标库的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="17962-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="17962-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="17962-152">ViewOption</span></span>|<span data-ttu-id="17962-153">否</span><span class="sxs-lookup"><span data-stu-id="17962-153">no</span></span>|<span data-ttu-id="17962-154">string</span><span class="sxs-lookup"><span data-stu-id="17962-154">string</span></span>|<span data-ttu-id="17962-155">指定是否将新模型视图设置为库默认值。</span><span class="sxs-lookup"><span data-stu-id="17962-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="17962-156">响应</span><span class="sxs-lookup"><span data-stu-id="17962-156">Response</span></span>

| <span data-ttu-id="17962-157">名称</span><span class="sxs-lookup"><span data-stu-id="17962-157">Name</span></span>   | <span data-ttu-id="17962-158">类型</span><span class="sxs-lookup"><span data-stu-id="17962-158">Type</span></span>  | <span data-ttu-id="17962-159">说明</span><span class="sxs-lookup"><span data-stu-id="17962-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="17962-160">201 已创建</span><span class="sxs-lookup"><span data-stu-id="17962-160">201 Created</span></span>||<span data-ttu-id="17962-p102">这是一个自定义 API，用于支持将模型应用至多个文档库。如果部分成功，仍可返回已创建的 201，调用方需要检查响应正文，以了解模型是否已成功应用至文档库。</span><span class="sxs-lookup"><span data-stu-id="17962-p102">This is a customized API to support applying a model to multi document libraries. In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="17962-163">响应正文</span><span class="sxs-lookup"><span data-stu-id="17962-163">Response Body</span></span>

| <span data-ttu-id="17962-164">名称</span><span class="sxs-lookup"><span data-stu-id="17962-164">Name</span></span>   | <span data-ttu-id="17962-165">类型</span><span class="sxs-lookup"><span data-stu-id="17962-165">Type</span></span>  | <span data-ttu-id="17962-166">说明</span><span class="sxs-lookup"><span data-stu-id="17962-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="17962-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="17962-167">TotalSuccesses</span></span>|<span data-ttu-id="17962-168">int</span><span class="sxs-lookup"><span data-stu-id="17962-168">int</span></span>|<span data-ttu-id="17962-169">成功应用至文档库的模型的总数。</span><span class="sxs-lookup"><span data-stu-id="17962-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="17962-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="17962-170">TotalFailures</span></span>|<span data-ttu-id="17962-171">int</span><span class="sxs-lookup"><span data-stu-id="17962-171">int</span></span>|<span data-ttu-id="17962-172">未能应用至文档库的模型的总数。</span><span class="sxs-lookup"><span data-stu-id="17962-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="17962-173">详细信息</span><span class="sxs-lookup"><span data-stu-id="17962-173">Details</span></span>|<span data-ttu-id="17962-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="17962-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="17962-175">MachineLearningPublicationResult 的集合，其中每个集合均指定了将模型应用至文档库的详细结果。</span><span class="sxs-lookup"><span data-stu-id="17962-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="17962-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="17962-176">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="17962-177">名称</span><span class="sxs-lookup"><span data-stu-id="17962-177">Name</span></span>   | <span data-ttu-id="17962-178">类型</span><span class="sxs-lookup"><span data-stu-id="17962-178">Type</span></span>  | <span data-ttu-id="17962-179">说明</span><span class="sxs-lookup"><span data-stu-id="17962-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="17962-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="17962-180">StatusCode</span></span>|<span data-ttu-id="17962-181">int</span><span class="sxs-lookup"><span data-stu-id="17962-181">int</span></span>|<span data-ttu-id="17962-182">HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="17962-182">The HTTP status code.</span></span>|
|<span data-ttu-id="17962-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="17962-183">ErrorMessage</span></span>|<span data-ttu-id="17962-184">string</span><span class="sxs-lookup"><span data-stu-id="17962-184">string</span></span>|<span data-ttu-id="17962-185">将模型应用到文档库时会显示错误内容的错误消息。</span><span class="sxs-lookup"><span data-stu-id="17962-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="17962-186">出版物</span><span class="sxs-lookup"><span data-stu-id="17962-186">Publication</span></span>|<span data-ttu-id="17962-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="17962-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="17962-188">它指定了模型信息和目标文档库。</span><span class="sxs-lookup"><span data-stu-id="17962-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="17962-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="17962-189">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="17962-190">名称</span><span class="sxs-lookup"><span data-stu-id="17962-190">Name</span></span> | <span data-ttu-id="17962-191">类型</span><span class="sxs-lookup"><span data-stu-id="17962-191">Type</span></span> | <span data-ttu-id="17962-192">说明</span><span class="sxs-lookup"><span data-stu-id="17962-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="17962-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="17962-193">ModelUniqueId</span></span>|<span data-ttu-id="17962-194">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-194">string</span></span>|<span data-ttu-id="17962-195">模型文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="17962-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="17962-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="17962-196">TargetSiteUrl</span></span>|<span data-ttu-id="17962-197">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-197">string</span></span>|<span data-ttu-id="17962-198">目标库网站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="17962-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="17962-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="17962-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="17962-200">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-200">string</span></span>|<span data-ttu-id="17962-201">目标库的 Web 的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="17962-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="17962-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="17962-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="17962-203">字符串</span><span class="sxs-lookup"><span data-stu-id="17962-203">string</span></span>|<span data-ttu-id="17962-204">目标库的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="17962-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="17962-205">示例</span><span class="sxs-lookup"><span data-stu-id="17962-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="17962-206">从存储库网站中的合同文档库中应用模型</span><span class="sxs-lookup"><span data-stu-id="17962-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="17962-207">此示例中，Contoso 合同文档理解模型的 ID 为 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="17962-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="17962-208">示例请求</span><span class="sxs-lookup"><span data-stu-id="17962-208">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="17962-209">示例响应</span><span class="sxs-lookup"><span data-stu-id="17962-209">Sample response</span></span>

<span data-ttu-id="17962-210">在响应中，TotalFailures 和 TotalSuccesses 指应用于指定库的模型的失败和成功次数。</span><span class="sxs-lookup"><span data-stu-id="17962-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="17962-211">**状态代码：** 201</span><span class="sxs-lookup"><span data-stu-id="17962-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="17962-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17962-212">See also</span></span>

[<span data-ttu-id="17962-213">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="17962-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
