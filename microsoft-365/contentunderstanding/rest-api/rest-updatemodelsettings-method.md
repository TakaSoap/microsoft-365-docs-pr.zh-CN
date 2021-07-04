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
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288643"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="484e5-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="484e5-103">UpdateModelSettings</span></span>

<span data-ttu-id="484e5-104">更新 SharePoint Syntex 文档理解模型的可用模型设置（关联的保留标签和模型说明）（请参阅[示例](rest-updatemodelsettings-method.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="484e5-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="484e5-105">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="484e5-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="484e5-106">URI 参数</span><span class="sxs-lookup"><span data-stu-id="484e5-106">URI parameters</span></span>

|<span data-ttu-id="484e5-107">名称</span><span class="sxs-lookup"><span data-stu-id="484e5-107">Name</span></span> |<span data-ttu-id="484e5-108">位置</span><span class="sxs-lookup"><span data-stu-id="484e5-108">In</span></span> |<span data-ttu-id="484e5-109">必需</span><span class="sxs-lookup"><span data-stu-id="484e5-109">Required</span></span>|<span data-ttu-id="484e5-110">类型</span><span class="sxs-lookup"><span data-stu-id="484e5-110">Type</span></span>|<span data-ttu-id="484e5-111">说明</span><span class="sxs-lookup"><span data-stu-id="484e5-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="484e5-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="484e5-112">modelFileName</span></span>|<span data-ttu-id="484e5-113">查询</span><span class="sxs-lookup"><span data-stu-id="484e5-113">query</span></span>|<span data-ttu-id="484e5-114">True</span><span class="sxs-lookup"><span data-stu-id="484e5-114">True</span></span>|<span data-ttu-id="484e5-115">string</span><span class="sxs-lookup"><span data-stu-id="484e5-115">string</span></span>|<span data-ttu-id="484e5-116">Syntex 模型文件的名称。</span><span class="sxs-lookup"><span data-stu-id="484e5-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="484e5-117">请求标头</span><span class="sxs-lookup"><span data-stu-id="484e5-117">Request headers</span></span>

| <span data-ttu-id="484e5-118">标头</span><span class="sxs-lookup"><span data-stu-id="484e5-118">Header</span></span> | <span data-ttu-id="484e5-119">值</span><span class="sxs-lookup"><span data-stu-id="484e5-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="484e5-120">Accept</span><span class="sxs-lookup"><span data-stu-id="484e5-120">Accept</span></span>|<span data-ttu-id="484e5-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="484e5-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="484e5-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="484e5-122">Content-Type</span></span>|<span data-ttu-id="484e5-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="484e5-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="484e5-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="484e5-124">x-requestdigest</span></span>|<span data-ttu-id="484e5-125">当前网站的相应摘要。</span><span class="sxs-lookup"><span data-stu-id="484e5-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="484e5-126">请求正文</span><span class="sxs-lookup"><span data-stu-id="484e5-126">Request body</span></span>

|<span data-ttu-id="484e5-127">名称</span><span class="sxs-lookup"><span data-stu-id="484e5-127">Name</span></span>    |<span data-ttu-id="484e5-128">类型</span><span class="sxs-lookup"><span data-stu-id="484e5-128">Type</span></span>   |<span data-ttu-id="484e5-129">说明</span><span class="sxs-lookup"><span data-stu-id="484e5-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="484e5-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="484e5-130">ModelSettings</span></span>|<span data-ttu-id="484e5-131">字符串</span><span class="sxs-lookup"><span data-stu-id="484e5-131">string</span></span>|<span data-ttu-id="484e5-132">模型设置的 JSON。</span><span class="sxs-lookup"><span data-stu-id="484e5-132">JSON of model settings.</span></span>|
|<span data-ttu-id="484e5-133">说明</span><span class="sxs-lookup"><span data-stu-id="484e5-133">Description</span></span>|<span data-ttu-id="484e5-134">string</span><span class="sxs-lookup"><span data-stu-id="484e5-134">string</span></span>|<span data-ttu-id="484e5-135">模型说明。</span><span class="sxs-lookup"><span data-stu-id="484e5-135">The model description.</span></span>|
|<span data-ttu-id="484e5-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="484e5-136">RetentionLabel</span></span>| |<span data-ttu-id="484e5-137">关联标签的信息（标签 ID 和名称）。</span><span class="sxs-lookup"><span data-stu-id="484e5-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="484e5-138">响应</span><span class="sxs-lookup"><span data-stu-id="484e5-138">Responses</span></span>

| <span data-ttu-id="484e5-139">名称</span><span class="sxs-lookup"><span data-stu-id="484e5-139">Name</span></span>   | <span data-ttu-id="484e5-140">类型</span><span class="sxs-lookup"><span data-stu-id="484e5-140">Type</span></span>  | <span data-ttu-id="484e5-141">说明</span><span class="sxs-lookup"><span data-stu-id="484e5-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="484e5-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="484e5-142">200 OK</span></span>| |<span data-ttu-id="484e5-143">成功</span><span class="sxs-lookup"><span data-stu-id="484e5-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="484e5-144">示例</span><span class="sxs-lookup"><span data-stu-id="484e5-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="484e5-145">Contoso 合同更新模型设置</span><span class="sxs-lookup"><span data-stu-id="484e5-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="484e5-146">此示例中，更新了模型说明和“标准保留”保留标签。</span><span class="sxs-lookup"><span data-stu-id="484e5-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="484e5-147">保留标签的 ID 为 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`。</span><span class="sxs-lookup"><span data-stu-id="484e5-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="484e5-148">示例请求</span><span class="sxs-lookup"><span data-stu-id="484e5-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="484e5-149">示例响应</span><span class="sxs-lookup"><span data-stu-id="484e5-149">Sample response</span></span>

<span data-ttu-id="484e5-150">**状态代码：** 200</span><span class="sxs-lookup"><span data-stu-id="484e5-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="484e5-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="484e5-151">See also</span></span>

[<span data-ttu-id="484e5-152">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="484e5-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
