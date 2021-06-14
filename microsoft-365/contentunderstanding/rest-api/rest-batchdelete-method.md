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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904161"
---
# <a name="batchdelete"></a><span data-ttu-id="69788-103">批处理删除</span><span class="sxs-lookup"><span data-stu-id="69788-103">BatchDelete</span></span>

<span data-ttu-id="69788-104">从一个或多个库中删除应用的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="69788-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="69788-105">请注意，必须先从所有库删除模型才能将其删除（请参阅 [示例](rest-batchdelete-method.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="69788-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="69788-106">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="69788-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="69788-107">URI 参数</span><span class="sxs-lookup"><span data-stu-id="69788-107">URI parameters</span></span>

<span data-ttu-id="69788-108">无</span><span class="sxs-lookup"><span data-stu-id="69788-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="69788-109">请求标头</span><span class="sxs-lookup"><span data-stu-id="69788-109">Request headers</span></span>

| <span data-ttu-id="69788-110">标头</span><span class="sxs-lookup"><span data-stu-id="69788-110">Header</span></span> | <span data-ttu-id="69788-111">值</span><span class="sxs-lookup"><span data-stu-id="69788-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="69788-112">Accept</span><span class="sxs-lookup"><span data-stu-id="69788-112">Accept</span></span>|<span data-ttu-id="69788-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="69788-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="69788-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="69788-114">Content-Type</span></span>|<span data-ttu-id="69788-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="69788-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="69788-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="69788-116">x-requestdigest</span></span>|<span data-ttu-id="69788-117">当前网站的相应摘要。</span><span class="sxs-lookup"><span data-stu-id="69788-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="69788-118">请求正文</span><span class="sxs-lookup"><span data-stu-id="69788-118">Request body</span></span>

| <span data-ttu-id="69788-119">Name</span><span class="sxs-lookup"><span data-stu-id="69788-119">Name</span></span> | <span data-ttu-id="69788-120">必需</span><span class="sxs-lookup"><span data-stu-id="69788-120">Required</span></span> | <span data-ttu-id="69788-121">类型</span><span class="sxs-lookup"><span data-stu-id="69788-121">Type</span></span> | <span data-ttu-id="69788-122">说明</span><span class="sxs-lookup"><span data-stu-id="69788-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="69788-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="69788-123">ModelUniqueId</span></span>|<span data-ttu-id="69788-124">是</span><span class="sxs-lookup"><span data-stu-id="69788-124">yes</span></span>|<span data-ttu-id="69788-125">字符串</span><span class="sxs-lookup"><span data-stu-id="69788-125">string</span></span>|<span data-ttu-id="69788-126">模型文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="69788-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="69788-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="69788-127">TargetSiteUrl</span></span>|<span data-ttu-id="69788-128">是</span><span class="sxs-lookup"><span data-stu-id="69788-128">yes</span></span>|<span data-ttu-id="69788-129">字符串</span><span class="sxs-lookup"><span data-stu-id="69788-129">string</span></span>|<span data-ttu-id="69788-130">目标库网站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="69788-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="69788-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="69788-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="69788-132">是</span><span class="sxs-lookup"><span data-stu-id="69788-132">yes</span></span>|<span data-ttu-id="69788-133">字符串</span><span class="sxs-lookup"><span data-stu-id="69788-133">string</span></span>|<span data-ttu-id="69788-134">目标库的 Web 的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="69788-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="69788-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="69788-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="69788-136">是</span><span class="sxs-lookup"><span data-stu-id="69788-136">yes</span></span>|<span data-ttu-id="69788-137">字符串</span><span class="sxs-lookup"><span data-stu-id="69788-137">string</span></span>|<span data-ttu-id="69788-138">目标库的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="69788-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="69788-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="69788-139">ViewOption</span></span>|<span data-ttu-id="69788-140">否</span><span class="sxs-lookup"><span data-stu-id="69788-140">no</span></span>|<span data-ttu-id="69788-141">string</span><span class="sxs-lookup"><span data-stu-id="69788-141">string</span></span>|<span data-ttu-id="69788-142">指定是否将新模型视图设置为库默认值。</span><span class="sxs-lookup"><span data-stu-id="69788-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="69788-143">响应</span><span class="sxs-lookup"><span data-stu-id="69788-143">Response</span></span>

| <span data-ttu-id="69788-144">名称</span><span class="sxs-lookup"><span data-stu-id="69788-144">Name</span></span>   | <span data-ttu-id="69788-145">类型</span><span class="sxs-lookup"><span data-stu-id="69788-145">Type</span></span>  | <span data-ttu-id="69788-146">说明</span><span class="sxs-lookup"><span data-stu-id="69788-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="69788-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="69788-147">200 OK</span></span>| |<span data-ttu-id="69788-148">成功</span><span class="sxs-lookup"><span data-stu-id="69788-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="69788-149">示例</span><span class="sxs-lookup"><span data-stu-id="69788-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="69788-150">从存储库网站中的合同文档库中删除模型</span><span class="sxs-lookup"><span data-stu-id="69788-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="69788-151">此示例中，Contoso 合同文档理解模型的 ID 为 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="69788-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="69788-152">示例请求</span><span class="sxs-lookup"><span data-stu-id="69788-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="69788-153">示例响应</span><span class="sxs-lookup"><span data-stu-id="69788-153">Sample response</span></span>

<span data-ttu-id="69788-154">在响应中，TotalFailures 和 TotalSuccesses 指应用于指定库的模型的失败和成功次数。</span><span class="sxs-lookup"><span data-stu-id="69788-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="69788-155">**状态代码：** 200</span><span class="sxs-lookup"><span data-stu-id="69788-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="69788-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69788-156">See also</span></span>

[<span data-ttu-id="69788-157">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="69788-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
