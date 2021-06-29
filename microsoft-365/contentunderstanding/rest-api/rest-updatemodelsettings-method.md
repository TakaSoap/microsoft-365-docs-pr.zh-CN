---
title: UpdateModelSettings
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
description: 使用 REST API 更新 SharePoint Syntex 文档理解模型的可用模型设置。
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177161"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="f3395-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="f3395-103">UpdateModelSettings</span></span>

<span data-ttu-id="f3395-104">更新 SharePoint Syntex 文档理解模型的可用模型设置（关联的保留标签和模型说明）（请参阅[示例](rest-updatemodelsettings-method.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="f3395-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="f3395-105">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="f3395-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="f3395-106">URI 参数</span><span class="sxs-lookup"><span data-stu-id="f3395-106">URI parameters</span></span>

|<span data-ttu-id="f3395-107">名称</span><span class="sxs-lookup"><span data-stu-id="f3395-107">Name</span></span> |<span data-ttu-id="f3395-108">位置</span><span class="sxs-lookup"><span data-stu-id="f3395-108">In</span></span> |<span data-ttu-id="f3395-109">必需</span><span class="sxs-lookup"><span data-stu-id="f3395-109">Required</span></span>|<span data-ttu-id="f3395-110">类型</span><span class="sxs-lookup"><span data-stu-id="f3395-110">Type</span></span>|<span data-ttu-id="f3395-111">说明</span><span class="sxs-lookup"><span data-stu-id="f3395-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="f3395-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="f3395-112">modelFileName</span></span>|<span data-ttu-id="f3395-113">查询</span><span class="sxs-lookup"><span data-stu-id="f3395-113">query</span></span>|<span data-ttu-id="f3395-114">True</span><span class="sxs-lookup"><span data-stu-id="f3395-114">True</span></span>|<span data-ttu-id="f3395-115">string</span><span class="sxs-lookup"><span data-stu-id="f3395-115">string</span></span>|<span data-ttu-id="f3395-116">Syntex 模型文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f3395-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="f3395-117">请求标头</span><span class="sxs-lookup"><span data-stu-id="f3395-117">Request headers</span></span>

| <span data-ttu-id="f3395-118">标头</span><span class="sxs-lookup"><span data-stu-id="f3395-118">Header</span></span> | <span data-ttu-id="f3395-119">值</span><span class="sxs-lookup"><span data-stu-id="f3395-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="f3395-120">Accept</span><span class="sxs-lookup"><span data-stu-id="f3395-120">Accept</span></span>|<span data-ttu-id="f3395-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="f3395-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="f3395-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f3395-122">Content-Type</span></span>|<span data-ttu-id="f3395-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="f3395-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="f3395-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="f3395-124">x-requestdigest</span></span>|<span data-ttu-id="f3395-125">当前网站的相应摘要。</span><span class="sxs-lookup"><span data-stu-id="f3395-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="f3395-126">请求正文</span><span class="sxs-lookup"><span data-stu-id="f3395-126">Request body</span></span>

|<span data-ttu-id="f3395-127">名称</span><span class="sxs-lookup"><span data-stu-id="f3395-127">Name</span></span>    |<span data-ttu-id="f3395-128">类型</span><span class="sxs-lookup"><span data-stu-id="f3395-128">Type</span></span>   |<span data-ttu-id="f3395-129">说明</span><span class="sxs-lookup"><span data-stu-id="f3395-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="f3395-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="f3395-130">ModelSettings</span></span>|<span data-ttu-id="f3395-131">字符串</span><span class="sxs-lookup"><span data-stu-id="f3395-131">string</span></span>|<span data-ttu-id="f3395-132">模型设置的 JSON。</span><span class="sxs-lookup"><span data-stu-id="f3395-132">JSON of model settings.</span></span>|
|<span data-ttu-id="f3395-133">说明</span><span class="sxs-lookup"><span data-stu-id="f3395-133">Description</span></span>|<span data-ttu-id="f3395-134">string</span><span class="sxs-lookup"><span data-stu-id="f3395-134">string</span></span>|<span data-ttu-id="f3395-135">模型说明。</span><span class="sxs-lookup"><span data-stu-id="f3395-135">The model description.</span></span>|
|<span data-ttu-id="f3395-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="f3395-136">RetentionLabel</span></span>| |<span data-ttu-id="f3395-137">关联标签的信息（标签 ID 和名称）。</span><span class="sxs-lookup"><span data-stu-id="f3395-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="f3395-138">响应</span><span class="sxs-lookup"><span data-stu-id="f3395-138">Responses</span></span>

| <span data-ttu-id="f3395-139">名称</span><span class="sxs-lookup"><span data-stu-id="f3395-139">Name</span></span>   | <span data-ttu-id="f3395-140">类型</span><span class="sxs-lookup"><span data-stu-id="f3395-140">Type</span></span>  | <span data-ttu-id="f3395-141">说明</span><span class="sxs-lookup"><span data-stu-id="f3395-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="f3395-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="f3395-142">200 OK</span></span>| |<span data-ttu-id="f3395-143">成功</span><span class="sxs-lookup"><span data-stu-id="f3395-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="f3395-144">示例</span><span class="sxs-lookup"><span data-stu-id="f3395-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="f3395-145">Contoso 合同更新模型设置</span><span class="sxs-lookup"><span data-stu-id="f3395-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="f3395-146">此示例中，更新了模型说明和“标准保留”保留标签。</span><span class="sxs-lookup"><span data-stu-id="f3395-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="f3395-147">保留标签的 ID 为 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`。</span><span class="sxs-lookup"><span data-stu-id="f3395-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="f3395-148">示例请求</span><span class="sxs-lookup"><span data-stu-id="f3395-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="f3395-149">示例响应</span><span class="sxs-lookup"><span data-stu-id="f3395-149">Sample response</span></span>

<span data-ttu-id="f3395-150">**状态代码：** 200</span><span class="sxs-lookup"><span data-stu-id="f3395-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="f3395-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3395-151">See also</span></span>

[<span data-ttu-id="f3395-152">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="f3395-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
