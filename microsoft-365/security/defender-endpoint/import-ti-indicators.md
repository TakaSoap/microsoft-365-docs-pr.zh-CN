---
title: 导入指示器 API
description: 了解如何使用 Microsoft Defender for Endpoint 中的导入批量指示器 API。
keywords: api， 受支持的 api， 提交， ti， 指示器， 更新
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198241"
---
# <a name="import-indicators-api"></a><span data-ttu-id="291ac-104">导入指示器 API</span><span class="sxs-lookup"><span data-stu-id="291ac-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="291ac-105">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="291ac-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="291ac-106">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="291ac-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="291ac-107">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="291ac-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="291ac-108">API 说明</span><span class="sxs-lookup"><span data-stu-id="291ac-108">API description</span></span>
<span data-ttu-id="291ac-109">提交或更新一 [批指示器](ti-indicator.md) 实体。</span><span class="sxs-lookup"><span data-stu-id="291ac-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="291ac-110">不支持 IP 的 CIDR 表示法。</span><span class="sxs-lookup"><span data-stu-id="291ac-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="291ac-111">限制</span><span class="sxs-lookup"><span data-stu-id="291ac-111">Limitations</span></span>
1. <span data-ttu-id="291ac-112">此 API 的速率限制是每分钟 30 次调用。</span><span class="sxs-lookup"><span data-stu-id="291ac-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="291ac-113">每个租户的活动指示器数限制为 15，000 个。 [](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="291ac-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="291ac-114">一个 API 调用的最大批处理大小为 500。</span><span class="sxs-lookup"><span data-stu-id="291ac-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="291ac-115">权限</span><span class="sxs-lookup"><span data-stu-id="291ac-115">Permissions</span></span>
<span data-ttu-id="291ac-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="291ac-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="291ac-117">若要了解更多信息（包括如何选择权限），请参阅 [入门](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="291ac-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="291ac-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="291ac-118">Permission type</span></span> |   <span data-ttu-id="291ac-119">权限</span><span class="sxs-lookup"><span data-stu-id="291ac-119">Permission</span></span>  |   <span data-ttu-id="291ac-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="291ac-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="291ac-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="291ac-121">Application</span></span> |   <span data-ttu-id="291ac-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="291ac-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="291ac-123">"读取和写入指示器"</span><span class="sxs-lookup"><span data-stu-id="291ac-123">'Read and write Indicators'</span></span>
<span data-ttu-id="291ac-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="291ac-124">Application</span></span> |   <span data-ttu-id="291ac-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="291ac-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="291ac-126">"读取和写入所有指示器"</span><span class="sxs-lookup"><span data-stu-id="291ac-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="291ac-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="291ac-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="291ac-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="291ac-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="291ac-129">"读取和写入指示器"</span><span class="sxs-lookup"><span data-stu-id="291ac-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="291ac-130">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="291ac-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="291ac-131">请求标头</span><span class="sxs-lookup"><span data-stu-id="291ac-131">Request headers</span></span>

<span data-ttu-id="291ac-132">名称</span><span class="sxs-lookup"><span data-stu-id="291ac-132">Name</span></span> | <span data-ttu-id="291ac-133">类型</span><span class="sxs-lookup"><span data-stu-id="291ac-133">Type</span></span> | <span data-ttu-id="291ac-134">说明</span><span class="sxs-lookup"><span data-stu-id="291ac-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="291ac-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="291ac-135">Authorization</span></span> | <span data-ttu-id="291ac-136">String</span><span class="sxs-lookup"><span data-stu-id="291ac-136">String</span></span> | <span data-ttu-id="291ac-137">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="291ac-137">Bearer {token}.</span></span> <span data-ttu-id="291ac-138">**必需**。</span><span class="sxs-lookup"><span data-stu-id="291ac-138">**Required**.</span></span>
<span data-ttu-id="291ac-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="291ac-139">Content-Type</span></span> | <span data-ttu-id="291ac-140">string</span><span class="sxs-lookup"><span data-stu-id="291ac-140">string</span></span> | <span data-ttu-id="291ac-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="291ac-141">application/json.</span></span> <span data-ttu-id="291ac-142">**必需**。</span><span class="sxs-lookup"><span data-stu-id="291ac-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="291ac-143">请求正文</span><span class="sxs-lookup"><span data-stu-id="291ac-143">Request body</span></span>
<span data-ttu-id="291ac-144">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="291ac-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="291ac-145">参数</span><span class="sxs-lookup"><span data-stu-id="291ac-145">Parameter</span></span> | <span data-ttu-id="291ac-146">类型</span><span class="sxs-lookup"><span data-stu-id="291ac-146">Type</span></span>    | <span data-ttu-id="291ac-147">说明</span><span class="sxs-lookup"><span data-stu-id="291ac-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="291ac-148">指示器</span><span class="sxs-lookup"><span data-stu-id="291ac-148">Indicators</span></span> | <span data-ttu-id="291ac-149">列表<[指示器](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="291ac-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="291ac-150">指标 [列表](ti-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="291ac-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="291ac-151">**Required**</span><span class="sxs-lookup"><span data-stu-id="291ac-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="291ac-152">响应</span><span class="sxs-lookup"><span data-stu-id="291ac-152">Response</span></span>
- <span data-ttu-id="291ac-153">如果成功，此方法返回 200 - OK 响应代码，每个指示器包含导入结果列表，请参阅下面的示例。</span><span class="sxs-lookup"><span data-stu-id="291ac-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="291ac-154">如果未成功：此方法返回 400 - 错误请求。</span><span class="sxs-lookup"><span data-stu-id="291ac-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="291ac-155">错误的请求通常指示正文不正确。</span><span class="sxs-lookup"><span data-stu-id="291ac-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="291ac-156">示例</span><span class="sxs-lookup"><span data-stu-id="291ac-156">Example</span></span>

<span data-ttu-id="291ac-157">**请求**</span><span class="sxs-lookup"><span data-stu-id="291ac-157">**Request**</span></span>

<span data-ttu-id="291ac-158">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="291ac-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="291ac-159">**响应**</span><span class="sxs-lookup"><span data-stu-id="291ac-159">**Response**</span></span>

<span data-ttu-id="291ac-160">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="291ac-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="291ac-161">相关主题</span><span class="sxs-lookup"><span data-stu-id="291ac-161">Related topic</span></span>
- [<span data-ttu-id="291ac-162">管理指示器</span><span class="sxs-lookup"><span data-stu-id="291ac-162">Manage indicators</span></span>](manage-indicators.md)
