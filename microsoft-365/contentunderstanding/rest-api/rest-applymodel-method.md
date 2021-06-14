---
title: 应用模型
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
description: 使用 REST API 将文档理解模型应用于一个或多个库。
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904206"
---
# <a name="apply-model"></a><span data-ttu-id="34ed1-103">应用模型</span><span class="sxs-lookup"><span data-stu-id="34ed1-103">Apply model</span></span>

<span data-ttu-id="34ed1-104">将经过培训的文档理解模型应用（或同步）到一个或多个库（请参阅 [示例](rest-applymodel-method.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="34ed1-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="34ed1-105">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="34ed1-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="34ed1-106">URI 参数</span><span class="sxs-lookup"><span data-stu-id="34ed1-106">URI parameters</span></span>

<span data-ttu-id="34ed1-107">无</span><span class="sxs-lookup"><span data-stu-id="34ed1-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="34ed1-108">请求标头</span><span class="sxs-lookup"><span data-stu-id="34ed1-108">Request headers</span></span>

| <span data-ttu-id="34ed1-109">标头</span><span class="sxs-lookup"><span data-stu-id="34ed1-109">Header</span></span> | <span data-ttu-id="34ed1-110">值</span><span class="sxs-lookup"><span data-stu-id="34ed1-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="34ed1-111">Accept</span><span class="sxs-lookup"><span data-stu-id="34ed1-111">Accept</span></span>|<span data-ttu-id="34ed1-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="34ed1-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="34ed1-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="34ed1-113">Content-Type</span></span>|<span data-ttu-id="34ed1-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="34ed1-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="34ed1-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="34ed1-115">x-requestdigest</span></span>|<span data-ttu-id="34ed1-116">当前网站的相应摘要。</span><span class="sxs-lookup"><span data-stu-id="34ed1-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="34ed1-117">请求正文</span><span class="sxs-lookup"><span data-stu-id="34ed1-117">Request body</span></span>

| <span data-ttu-id="34ed1-118">Name</span><span class="sxs-lookup"><span data-stu-id="34ed1-118">Name</span></span> | <span data-ttu-id="34ed1-119">必需</span><span class="sxs-lookup"><span data-stu-id="34ed1-119">Required</span></span> | <span data-ttu-id="34ed1-120">类型</span><span class="sxs-lookup"><span data-stu-id="34ed1-120">Type</span></span> | <span data-ttu-id="34ed1-121">说明</span><span class="sxs-lookup"><span data-stu-id="34ed1-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="34ed1-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="34ed1-122">ModelUniqueId</span></span>|<span data-ttu-id="34ed1-123">是</span><span class="sxs-lookup"><span data-stu-id="34ed1-123">yes</span></span>|<span data-ttu-id="34ed1-124">字符串</span><span class="sxs-lookup"><span data-stu-id="34ed1-124">string</span></span>|<span data-ttu-id="34ed1-125">模型文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="34ed1-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="34ed1-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="34ed1-126">TargetSiteUrl</span></span>|<span data-ttu-id="34ed1-127">是</span><span class="sxs-lookup"><span data-stu-id="34ed1-127">yes</span></span>|<span data-ttu-id="34ed1-128">字符串</span><span class="sxs-lookup"><span data-stu-id="34ed1-128">string</span></span>|<span data-ttu-id="34ed1-129">目标库网站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="34ed1-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="34ed1-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="34ed1-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="34ed1-131">是</span><span class="sxs-lookup"><span data-stu-id="34ed1-131">yes</span></span>|<span data-ttu-id="34ed1-132">字符串</span><span class="sxs-lookup"><span data-stu-id="34ed1-132">string</span></span>|<span data-ttu-id="34ed1-133">目标库的 Web 的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="34ed1-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="34ed1-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="34ed1-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="34ed1-135">是</span><span class="sxs-lookup"><span data-stu-id="34ed1-135">yes</span></span>|<span data-ttu-id="34ed1-136">字符串</span><span class="sxs-lookup"><span data-stu-id="34ed1-136">string</span></span>|<span data-ttu-id="34ed1-137">目标库的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="34ed1-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="34ed1-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="34ed1-138">ViewOption</span></span>|<span data-ttu-id="34ed1-139">否</span><span class="sxs-lookup"><span data-stu-id="34ed1-139">no</span></span>|<span data-ttu-id="34ed1-140">string</span><span class="sxs-lookup"><span data-stu-id="34ed1-140">string</span></span>|<span data-ttu-id="34ed1-141">指定是否将新模型视图设置为库默认值。</span><span class="sxs-lookup"><span data-stu-id="34ed1-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="34ed1-142">响应</span><span class="sxs-lookup"><span data-stu-id="34ed1-142">Response</span></span>

| <span data-ttu-id="34ed1-143">名称</span><span class="sxs-lookup"><span data-stu-id="34ed1-143">Name</span></span>   | <span data-ttu-id="34ed1-144">类型</span><span class="sxs-lookup"><span data-stu-id="34ed1-144">Type</span></span>  | <span data-ttu-id="34ed1-145">说明</span><span class="sxs-lookup"><span data-stu-id="34ed1-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="34ed1-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="34ed1-146">200 OK</span></span>| |<span data-ttu-id="34ed1-147">成功</span><span class="sxs-lookup"><span data-stu-id="34ed1-147">Success</span></span>|
|<span data-ttu-id="34ed1-148">201 已创建</span><span class="sxs-lookup"><span data-stu-id="34ed1-148">201 Created</span></span>| |<span data-ttu-id="34ed1-149">请注意，由于此 API 支持将模型应用到多个库，因此即使将模型应用于其中一个库失败，也可能会返回 201。</span><span class="sxs-lookup"><span data-stu-id="34ed1-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="34ed1-150">检查响应正文，了解模型是否已成功应用于所有指定的库。</span><span class="sxs-lookup"><span data-stu-id="34ed1-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="34ed1-151">请参阅[请求正文](rest-applymodel-method.md#request-body)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="34ed1-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="34ed1-152">示例</span><span class="sxs-lookup"><span data-stu-id="34ed1-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="34ed1-153">从存储库网站中的合同文档库中应用模型</span><span class="sxs-lookup"><span data-stu-id="34ed1-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="34ed1-154">此示例中，Contoso 合同文档理解模型的 ID 为 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="34ed1-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="34ed1-155">示例请求</span><span class="sxs-lookup"><span data-stu-id="34ed1-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="34ed1-156">示例响应</span><span class="sxs-lookup"><span data-stu-id="34ed1-156">Sample response</span></span>

<span data-ttu-id="34ed1-157">在响应中，TotalFailures 和 TotalSuccesses 指应用于指定库的模型的失败和成功次数。</span><span class="sxs-lookup"><span data-stu-id="34ed1-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="34ed1-158">**状态代码：** 200</span><span class="sxs-lookup"><span data-stu-id="34ed1-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="34ed1-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34ed1-159">See also</span></span>

[<span data-ttu-id="34ed1-160">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="34ed1-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
