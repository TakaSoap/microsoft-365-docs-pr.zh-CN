---
title: 获取模型和库信息
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
description: 使用 REST API 获取有关模型及应用该模型的库的信息。
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904166"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="a5f1e-103">获取模型和库信息</span><span class="sxs-lookup"><span data-stu-id="a5f1e-103">Get model and library information</span></span>

<span data-ttu-id="a5f1e-104">获取有关模型及应用该模型的库的信息（请参阅[示例](rest-getmodelandlibraryinfo.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="a5f1e-105">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="a5f1e-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="a5f1e-106">URI 参数</span><span class="sxs-lookup"><span data-stu-id="a5f1e-106">URI parameters</span></span>

| <span data-ttu-id="a5f1e-107">名称</span><span class="sxs-lookup"><span data-stu-id="a5f1e-107">Name</span></span> | <span data-ttu-id="a5f1e-108">位置</span><span class="sxs-lookup"><span data-stu-id="a5f1e-108">In</span></span> | <span data-ttu-id="a5f1e-109">必需</span><span class="sxs-lookup"><span data-stu-id="a5f1e-109">Required</span></span> | <span data-ttu-id="a5f1e-110">类型</span><span class="sxs-lookup"><span data-stu-id="a5f1e-110">Type</span></span> | <span data-ttu-id="a5f1e-111">说明</span><span class="sxs-lookup"><span data-stu-id="a5f1e-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a5f1e-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a5f1e-112">ModelUniqueId</span></span>|<span data-ttu-id="a5f1e-113">查询</span><span class="sxs-lookup"><span data-stu-id="a5f1e-113">query</span></span>|<span data-ttu-id="a5f1e-114">True</span><span class="sxs-lookup"><span data-stu-id="a5f1e-114">True</span></span>|<span data-ttu-id="a5f1e-115">GUID</span><span class="sxs-lookup"><span data-stu-id="a5f1e-115">GUID</span></span>|<span data-ttu-id="a5f1e-116">模型文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="a5f1e-117">请求标头</span><span class="sxs-lookup"><span data-stu-id="a5f1e-117">Request headers</span></span>

| <span data-ttu-id="a5f1e-118">标头</span><span class="sxs-lookup"><span data-stu-id="a5f1e-118">Header</span></span> | <span data-ttu-id="a5f1e-119">值</span><span class="sxs-lookup"><span data-stu-id="a5f1e-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="a5f1e-120">Accept</span><span class="sxs-lookup"><span data-stu-id="a5f1e-120">Accept</span></span>|<span data-ttu-id="a5f1e-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="a5f1e-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="a5f1e-122">请求正文</span><span class="sxs-lookup"><span data-stu-id="a5f1e-122">Request body</span></span>

| <span data-ttu-id="a5f1e-123">Name</span><span class="sxs-lookup"><span data-stu-id="a5f1e-123">Name</span></span> | <span data-ttu-id="a5f1e-124">必需</span><span class="sxs-lookup"><span data-stu-id="a5f1e-124">Required</span></span> | <span data-ttu-id="a5f1e-125">类型</span><span class="sxs-lookup"><span data-stu-id="a5f1e-125">Type</span></span> | <span data-ttu-id="a5f1e-126">说明</span><span class="sxs-lookup"><span data-stu-id="a5f1e-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a5f1e-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a5f1e-127">ModelUniqueId</span></span>|<span data-ttu-id="a5f1e-128">是</span><span class="sxs-lookup"><span data-stu-id="a5f1e-128">yes</span></span>|<span data-ttu-id="a5f1e-129">字符串</span><span class="sxs-lookup"><span data-stu-id="a5f1e-129">string</span></span>|<span data-ttu-id="a5f1e-130">模型文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="a5f1e-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="a5f1e-131">TargetSiteUrl</span></span>|<span data-ttu-id="a5f1e-132">是</span><span class="sxs-lookup"><span data-stu-id="a5f1e-132">yes</span></span>|<span data-ttu-id="a5f1e-133">字符串</span><span class="sxs-lookup"><span data-stu-id="a5f1e-133">string</span></span>|<span data-ttu-id="a5f1e-134">目标库网站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="a5f1e-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a5f1e-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="a5f1e-136">是</span><span class="sxs-lookup"><span data-stu-id="a5f1e-136">yes</span></span>|<span data-ttu-id="a5f1e-137">字符串</span><span class="sxs-lookup"><span data-stu-id="a5f1e-137">string</span></span>|<span data-ttu-id="a5f1e-138">目标库的 Web 的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="a5f1e-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a5f1e-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="a5f1e-140">是</span><span class="sxs-lookup"><span data-stu-id="a5f1e-140">yes</span></span>|<span data-ttu-id="a5f1e-141">字符串</span><span class="sxs-lookup"><span data-stu-id="a5f1e-141">string</span></span>|<span data-ttu-id="a5f1e-142">目标库的服务器相应的 URL。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="a5f1e-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="a5f1e-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="a5f1e-144">是</span><span class="sxs-lookup"><span data-stu-id="a5f1e-144">yes</span></span>|<span data-ttu-id="a5f1e-145">int</span><span class="sxs-lookup"><span data-stu-id="a5f1e-145">int</span></span>|<span data-ttu-id="a5f1e-146">指示目标库是否被删除的标记。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="a5f1e-147">响应</span><span class="sxs-lookup"><span data-stu-id="a5f1e-147">Response</span></span>

| <span data-ttu-id="a5f1e-148">名称</span><span class="sxs-lookup"><span data-stu-id="a5f1e-148">Name</span></span>   | <span data-ttu-id="a5f1e-149">类型</span><span class="sxs-lookup"><span data-stu-id="a5f1e-149">Type</span></span>  | <span data-ttu-id="a5f1e-150">说明</span><span class="sxs-lookup"><span data-stu-id="a5f1e-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a5f1e-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="a5f1e-151">200 OK</span></span>| |<span data-ttu-id="a5f1e-152">成功</span><span class="sxs-lookup"><span data-stu-id="a5f1e-152">Success</span></span>|
|<span data-ttu-id="a5f1e-153">201 已创建</span><span class="sxs-lookup"><span data-stu-id="a5f1e-153">201 Created</span></span>| |<span data-ttu-id="a5f1e-154">请注意，由于此 API 支持将模型应用到多个库，因此即使将模型应用于其中一个库失败，也可能会返回 201。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="a5f1e-155">检查响应正文，了解模型是否已成功应用于所有指定的库。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="a5f1e-156">请参阅[请求正文](rest-getmodelandlibraryinfo.md#request-body)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="a5f1e-157">示例</span><span class="sxs-lookup"><span data-stu-id="a5f1e-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="a5f1e-158">在存储库网站获取有关合同模型和主要文档库的信息</span><span class="sxs-lookup"><span data-stu-id="a5f1e-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="a5f1e-159">此示例中，Contoso 合同文档理解模型的 ID 为 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="a5f1e-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="a5f1e-160">示例请求</span><span class="sxs-lookup"><span data-stu-id="a5f1e-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="a5f1e-161">示例响应</span><span class="sxs-lookup"><span data-stu-id="a5f1e-161">Sample response</span></span>

<span data-ttu-id="a5f1e-162">**状态代码：** 200</span><span class="sxs-lookup"><span data-stu-id="a5f1e-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="a5f1e-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5f1e-163">See also</span></span>

[<span data-ttu-id="a5f1e-164">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="a5f1e-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
