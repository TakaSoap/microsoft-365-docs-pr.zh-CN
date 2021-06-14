---
title: 创建分类请求
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
description: 使用 REST API 创建请求，使用训练后的文档理解模型对一个或多个文件进行分类。
ms.openlocfilehash: 6a218db181368c2837d570062b6101bc3bacfb05
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904162"
---
# <a name="create-classification-request"></a><span data-ttu-id="279c3-103">创建分类请求</span><span class="sxs-lookup"><span data-stu-id="279c3-103">Create classification request</span></span>

<span data-ttu-id="279c3-104">创建一个请求，使用应用的文档理解模型对一个或多个文件进行分类（请参阅[示例](rest-createclassificationrequest.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="279c3-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="279c3-105">SharePoint Online（和本地 SharePoint 2016 及更高版本）REST 服务支持合并多个请求。</span><span class="sxs-lookup"><span data-stu-id="279c3-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="279c3-106">使用 OData $batch 查询选项，将多个请求合并到一个服务调用中。</span><span class="sxs-lookup"><span data-stu-id="279c3-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="279c3-107">此方法可用于一次将数百个文档的分类工作项排入队列。</span><span class="sxs-lookup"><span data-stu-id="279c3-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="279c3-108">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="279c3-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="279c3-109">URI 参数</span><span class="sxs-lookup"><span data-stu-id="279c3-109">URI Parameters</span></span>

<span data-ttu-id="279c3-110">无</span><span class="sxs-lookup"><span data-stu-id="279c3-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="279c3-111">请求标头</span><span class="sxs-lookup"><span data-stu-id="279c3-111">Request headers</span></span>

| <span data-ttu-id="279c3-112">标头</span><span class="sxs-lookup"><span data-stu-id="279c3-112">Header</span></span> | <span data-ttu-id="279c3-113">值</span><span class="sxs-lookup"><span data-stu-id="279c3-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="279c3-114">Accept</span><span class="sxs-lookup"><span data-stu-id="279c3-114">Accept</span></span>|<span data-ttu-id="279c3-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="279c3-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="279c3-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="279c3-116">Content-Type</span></span>|<span data-ttu-id="279c3-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="279c3-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="279c3-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="279c3-118">x-requestdigest</span></span>|<span data-ttu-id="279c3-119">当前网站的适当摘要</span><span class="sxs-lookup"><span data-stu-id="279c3-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="279c3-120">请求正文</span><span class="sxs-lookup"><span data-stu-id="279c3-120">Request body</span></span>

|<span data-ttu-id="279c3-121">名称</span><span class="sxs-lookup"><span data-stu-id="279c3-121">Name</span></span>    |<span data-ttu-id="279c3-122">类型</span><span class="sxs-lookup"><span data-stu-id="279c3-122">Type</span></span>   |<span data-ttu-id="279c3-123">说明</span><span class="sxs-lookup"><span data-stu-id="279c3-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="279c3-124">_元数据</span><span class="sxs-lookup"><span data-stu-id="279c3-124">_metadata</span></span>|<span data-ttu-id="279c3-125">字符串</span><span class="sxs-lookup"><span data-stu-id="279c3-125">string</span></span> |<span data-ttu-id="279c3-126">在 SPO 上设置对象元。</span><span class="sxs-lookup"><span data-stu-id="279c3-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="279c3-127">始终使用值：{"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="279c3-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="279c3-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="279c3-128">TargetSiteId</span></span>|<span data-ttu-id="279c3-129">guid</span><span class="sxs-lookup"><span data-stu-id="279c3-129">guid</span></span>|<span data-ttu-id="279c3-130">要分类的文件所在网站的 ID。</span><span class="sxs-lookup"><span data-stu-id="279c3-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="279c3-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="279c3-131">TargetWebId</span></span>|<span data-ttu-id="279c3-132">guid</span><span class="sxs-lookup"><span data-stu-id="279c3-132">guid</span></span>|<span data-ttu-id="279c3-133">要分类的文件所在 Web 的 ID。</span><span class="sxs-lookup"><span data-stu-id="279c3-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="279c3-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="279c3-134">TargetUniqueId</span></span>|<span data-ttu-id="279c3-135">guid</span><span class="sxs-lookup"><span data-stu-id="279c3-135">guid</span></span>|<span data-ttu-id="279c3-136">要分类的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="279c3-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="279c3-137">响应</span><span class="sxs-lookup"><span data-stu-id="279c3-137">Responses</span></span>

| <span data-ttu-id="279c3-138">名称</span><span class="sxs-lookup"><span data-stu-id="279c3-138">Name</span></span>   | <span data-ttu-id="279c3-139">类型</span><span class="sxs-lookup"><span data-stu-id="279c3-139">Type</span></span>  | <span data-ttu-id="279c3-140">说明</span><span class="sxs-lookup"><span data-stu-id="279c3-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="279c3-141">201 已创建</span><span class="sxs-lookup"><span data-stu-id="279c3-141">201 Created</span></span>| |<span data-ttu-id="279c3-142">成功</span><span class="sxs-lookup"><span data-stu-id="279c3-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="279c3-143">示例</span><span class="sxs-lookup"><span data-stu-id="279c3-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="279c3-144">将对 ID 为"e6cff8b7-c90c-4564-b5b8-033449090932"的文件进行分类的请求排入队列</span><span class="sxs-lookup"><span data-stu-id="279c3-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="279c3-145">示例请求</span><span class="sxs-lookup"><span data-stu-id="279c3-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="279c3-146">示例响应</span><span class="sxs-lookup"><span data-stu-id="279c3-146">Sample response</span></span>

<span data-ttu-id="279c3-147">**状态代码：** 201</span><span class="sxs-lookup"><span data-stu-id="279c3-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="279c3-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="279c3-148">See also</span></span>

[<span data-ttu-id="279c3-149">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="279c3-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
