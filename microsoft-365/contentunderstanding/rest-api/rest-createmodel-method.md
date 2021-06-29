---
title: 创建模型
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
description: 使用 REST API 创建模型及其关联的内容类型。
ms.openlocfilehash: 0a1b6ef9b7e38f2c4f52082103530da432e3e855
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177149"
---
# <a name="create-model"></a><span data-ttu-id="2f77e-103">创建模型</span><span class="sxs-lookup"><span data-stu-id="2f77e-103">Create model</span></span>

<span data-ttu-id="2f77e-104">创建模型及其关联的内容类型。</span><span class="sxs-lookup"><span data-stu-id="2f77e-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="2f77e-105">请注意，此操作仅创建模型。</span><span class="sxs-lookup"><span data-stu-id="2f77e-105">Note that this only creates the model.</span></span> <span data-ttu-id="2f77e-106">它还需要在内容中心接受培训（请参阅[示例](rest-createmodel-method.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="2f77e-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="2f77e-107">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="2f77e-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="2f77e-108">URI 参数</span><span class="sxs-lookup"><span data-stu-id="2f77e-108">URI Parameters</span></span>

<span data-ttu-id="2f77e-109">无</span><span class="sxs-lookup"><span data-stu-id="2f77e-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="2f77e-110">请求标头</span><span class="sxs-lookup"><span data-stu-id="2f77e-110">Request headers</span></span>

| <span data-ttu-id="2f77e-111">标头</span><span class="sxs-lookup"><span data-stu-id="2f77e-111">Header</span></span> | <span data-ttu-id="2f77e-112">值</span><span class="sxs-lookup"><span data-stu-id="2f77e-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="2f77e-113">Accept</span><span class="sxs-lookup"><span data-stu-id="2f77e-113">Accept</span></span>|<span data-ttu-id="2f77e-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="2f77e-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="2f77e-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2f77e-115">Content-Type</span></span>|<span data-ttu-id="2f77e-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="2f77e-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="2f77e-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="2f77e-117">x-requestdigest</span></span>|<span data-ttu-id="2f77e-118">当前网站的适当摘要</span><span class="sxs-lookup"><span data-stu-id="2f77e-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="2f77e-119">请求正文</span><span class="sxs-lookup"><span data-stu-id="2f77e-119">Request body</span></span>

|<span data-ttu-id="2f77e-120">名称</span><span class="sxs-lookup"><span data-stu-id="2f77e-120">Name</span></span>    |<span data-ttu-id="2f77e-121">类型</span><span class="sxs-lookup"><span data-stu-id="2f77e-121">Type</span></span>   |<span data-ttu-id="2f77e-122">说明</span><span class="sxs-lookup"><span data-stu-id="2f77e-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="2f77e-123">_元数据</span><span class="sxs-lookup"><span data-stu-id="2f77e-123">_metadata</span></span>|  |<span data-ttu-id="2f77e-124">在 SPO 上设置对象元。</span><span class="sxs-lookup"><span data-stu-id="2f77e-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="2f77e-125">始终使用值：{"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="2f77e-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="2f77e-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="2f77e-126">ContentTypeGroup</span></span>|<span data-ttu-id="2f77e-127">字符串</span><span class="sxs-lookup"><span data-stu-id="2f77e-127">string</span></span>|<span data-ttu-id="2f77e-128">与模型关联的内容类型组。</span><span class="sxs-lookup"><span data-stu-id="2f77e-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="2f77e-129">默认为“智能文档内容类型”。</span><span class="sxs-lookup"><span data-stu-id="2f77e-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="2f77e-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="2f77e-130">ContentTypeName</span></span>|<span data-ttu-id="2f77e-131">字符串</span><span class="sxs-lookup"><span data-stu-id="2f77e-131">string</span></span>|<span data-ttu-id="2f77e-132">关联的内容类型名称。</span><span class="sxs-lookup"><span data-stu-id="2f77e-132">The associated content type name.</span></span> <span data-ttu-id="2f77e-133">创建的模型文件将具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="2f77e-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="2f77e-134">响应</span><span class="sxs-lookup"><span data-stu-id="2f77e-134">Responses</span></span>

| <span data-ttu-id="2f77e-135">名称</span><span class="sxs-lookup"><span data-stu-id="2f77e-135">Name</span></span>   | <span data-ttu-id="2f77e-136">类型</span><span class="sxs-lookup"><span data-stu-id="2f77e-136">Type</span></span>  | <span data-ttu-id="2f77e-137">说明</span><span class="sxs-lookup"><span data-stu-id="2f77e-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="2f77e-138">201 已创建</span><span class="sxs-lookup"><span data-stu-id="2f77e-138">201 Created</span></span>| |<span data-ttu-id="2f77e-139">成功</span><span class="sxs-lookup"><span data-stu-id="2f77e-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="2f77e-140">示例</span><span class="sxs-lookup"><span data-stu-id="2f77e-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="2f77e-141">创建名为“Contoso 合同”的新文档理解模型</span><span class="sxs-lookup"><span data-stu-id="2f77e-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="2f77e-142">示例请求</span><span class="sxs-lookup"><span data-stu-id="2f77e-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="2f77e-143">示例响应</span><span class="sxs-lookup"><span data-stu-id="2f77e-143">Sample response</span></span>

<span data-ttu-id="2f77e-144">**状态代码：** 201</span><span class="sxs-lookup"><span data-stu-id="2f77e-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="2f77e-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f77e-145">See also</span></span>

[<span data-ttu-id="2f77e-146">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="2f77e-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
