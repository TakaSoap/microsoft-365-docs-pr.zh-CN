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
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904167"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="5b581-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="5b581-103">UpdateModelSettings</span></span>

<span data-ttu-id="5b581-104">更新 SharePoint Syntex 文档理解模型的可用模型设置（关联的保留标签和模型说明）（请参阅[示例](rest-updatemodelsettings-method.md#examples)）。</span><span class="sxs-lookup"><span data-stu-id="5b581-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="5b581-105">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="5b581-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="5b581-106">URI 参数</span><span class="sxs-lookup"><span data-stu-id="5b581-106">URI parameters</span></span>

<span data-ttu-id="5b581-107">无</span><span class="sxs-lookup"><span data-stu-id="5b581-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="5b581-108">请求标头</span><span class="sxs-lookup"><span data-stu-id="5b581-108">Request headers</span></span>

| <span data-ttu-id="5b581-109">标头</span><span class="sxs-lookup"><span data-stu-id="5b581-109">Header</span></span> | <span data-ttu-id="5b581-110">值</span><span class="sxs-lookup"><span data-stu-id="5b581-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="5b581-111">Accept</span><span class="sxs-lookup"><span data-stu-id="5b581-111">Accept</span></span>|<span data-ttu-id="5b581-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="5b581-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="5b581-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5b581-113">Content-Type</span></span>|<span data-ttu-id="5b581-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="5b581-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="5b581-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="5b581-115">x-requestdigest</span></span>|<span data-ttu-id="5b581-116">当前网站的相应摘要。</span><span class="sxs-lookup"><span data-stu-id="5b581-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="5b581-117">请求正文</span><span class="sxs-lookup"><span data-stu-id="5b581-117">Request body</span></span>

|<span data-ttu-id="5b581-118">名称</span><span class="sxs-lookup"><span data-stu-id="5b581-118">Name</span></span>    |<span data-ttu-id="5b581-119">类型</span><span class="sxs-lookup"><span data-stu-id="5b581-119">Type</span></span>   |<span data-ttu-id="5b581-120">说明</span><span class="sxs-lookup"><span data-stu-id="5b581-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="5b581-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="5b581-121">ModelSettings</span></span>|<span data-ttu-id="5b581-122">字符串</span><span class="sxs-lookup"><span data-stu-id="5b581-122">string</span></span>|<span data-ttu-id="5b581-123">模型设置的 JSON。</span><span class="sxs-lookup"><span data-stu-id="5b581-123">JSON of model settings.</span></span>|
|<span data-ttu-id="5b581-124">说明</span><span class="sxs-lookup"><span data-stu-id="5b581-124">Description</span></span>|<span data-ttu-id="5b581-125">string</span><span class="sxs-lookup"><span data-stu-id="5b581-125">string</span></span>|<span data-ttu-id="5b581-126">模型说明。</span><span class="sxs-lookup"><span data-stu-id="5b581-126">The model description.</span></span>|
|<span data-ttu-id="5b581-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="5b581-127">RetentionLabel</span></span>| |<span data-ttu-id="5b581-128">关联标签的信息（标签 ID 和名称）。</span><span class="sxs-lookup"><span data-stu-id="5b581-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="5b581-129">响应</span><span class="sxs-lookup"><span data-stu-id="5b581-129">Responses</span></span>

| <span data-ttu-id="5b581-130">名称</span><span class="sxs-lookup"><span data-stu-id="5b581-130">Name</span></span>   | <span data-ttu-id="5b581-131">类型</span><span class="sxs-lookup"><span data-stu-id="5b581-131">Type</span></span>  | <span data-ttu-id="5b581-132">说明</span><span class="sxs-lookup"><span data-stu-id="5b581-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="5b581-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="5b581-133">200 OK</span></span>| |<span data-ttu-id="5b581-134">成功</span><span class="sxs-lookup"><span data-stu-id="5b581-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="5b581-135">示例</span><span class="sxs-lookup"><span data-stu-id="5b581-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="5b581-136">Contoso 合同更新模型设置</span><span class="sxs-lookup"><span data-stu-id="5b581-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="5b581-137">此示例中，更新了模型说明和“标准保留”保留标签。</span><span class="sxs-lookup"><span data-stu-id="5b581-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="5b581-138">保留标签的 ID 为 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`。</span><span class="sxs-lookup"><span data-stu-id="5b581-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="5b581-139">示例请求</span><span class="sxs-lookup"><span data-stu-id="5b581-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="5b581-140">示例响应</span><span class="sxs-lookup"><span data-stu-id="5b581-140">Sample response</span></span>

<span data-ttu-id="5b581-141">**状态代码：** 200</span><span class="sxs-lookup"><span data-stu-id="5b581-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="5b581-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b581-142">See also</span></span>

[<span data-ttu-id="5b581-143">Syntex 文档理解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="5b581-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
