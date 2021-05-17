---
title: 获取域统计信息 API
description: 了解如何使用获取域统计信息 API 检索 Microsoft Defender for Endpoint 中给定域的统计信息。
keywords: api， 图形 api， 受支持的 api， 获取， 域， 域相关设备
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: eef06657d7f691a89e5985640431c2cc706557b4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166464"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="28863-104">获取域统计信息 API</span><span class="sxs-lookup"><span data-stu-id="28863-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28863-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="28863-105">**Applies to:**</span></span>
- [<span data-ttu-id="28863-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="28863-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28863-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28863-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="28863-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="28863-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="28863-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="28863-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="28863-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="28863-110">API description</span></span>
<span data-ttu-id="28863-111">检索给定域上的统计信息。</span><span class="sxs-lookup"><span data-stu-id="28863-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="28863-112">限制</span><span class="sxs-lookup"><span data-stu-id="28863-112">Limitations</span></span>
1. <span data-ttu-id="28863-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="28863-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="28863-114">权限</span><span class="sxs-lookup"><span data-stu-id="28863-114">Permissions</span></span>
<span data-ttu-id="28863-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="28863-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="28863-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="28863-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="28863-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="28863-117">Permission type</span></span> |   <span data-ttu-id="28863-118">权限</span><span class="sxs-lookup"><span data-stu-id="28863-118">Permission</span></span>  |   <span data-ttu-id="28863-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="28863-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="28863-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="28863-120">Application</span></span> |   <span data-ttu-id="28863-121">URL。Read.All</span><span class="sxs-lookup"><span data-stu-id="28863-121">URL.Read.All</span></span> |  <span data-ttu-id="28863-122">"读取 URL"</span><span class="sxs-lookup"><span data-stu-id="28863-122">'Read URLs'</span></span>
<span data-ttu-id="28863-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="28863-123">Delegated (work or school account)</span></span> | <span data-ttu-id="28863-124">URL。Read.All</span><span class="sxs-lookup"><span data-stu-id="28863-124">URL.Read.All</span></span> | <span data-ttu-id="28863-125">"读取 URL"</span><span class="sxs-lookup"><span data-stu-id="28863-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="28863-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="28863-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="28863-127">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="28863-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="28863-128">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="28863-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="28863-129">请求标头</span><span class="sxs-lookup"><span data-stu-id="28863-129">Request headers</span></span>

<span data-ttu-id="28863-130">标头</span><span class="sxs-lookup"><span data-stu-id="28863-130">Header</span></span> | <span data-ttu-id="28863-131">值</span><span class="sxs-lookup"><span data-stu-id="28863-131">Value</span></span> 
:---|:---
<span data-ttu-id="28863-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="28863-132">Authorization</span></span> | <span data-ttu-id="28863-133">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="28863-133">Bearer {token}.</span></span> <span data-ttu-id="28863-134">**必需**。</span><span class="sxs-lookup"><span data-stu-id="28863-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="28863-135">请求 URI 参数</span><span class="sxs-lookup"><span data-stu-id="28863-135">Request URI parameters</span></span>

<span data-ttu-id="28863-136">名称</span><span class="sxs-lookup"><span data-stu-id="28863-136">Name</span></span> | <span data-ttu-id="28863-137">类型</span><span class="sxs-lookup"><span data-stu-id="28863-137">Type</span></span> | <span data-ttu-id="28863-138">说明</span><span class="sxs-lookup"><span data-stu-id="28863-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="28863-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="28863-139">lookBackHours</span></span> | <span data-ttu-id="28863-140">Int32</span><span class="sxs-lookup"><span data-stu-id="28863-140">Int32</span></span> | <span data-ttu-id="28863-141">定义我们重新搜索以获取统计信息的小时数。</span><span class="sxs-lookup"><span data-stu-id="28863-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="28863-142">默认为 30 天。</span><span class="sxs-lookup"><span data-stu-id="28863-142">Defaults to 30 days.</span></span> <span data-ttu-id="28863-143">**可选。**</span><span class="sxs-lookup"><span data-stu-id="28863-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="28863-144">请求正文</span><span class="sxs-lookup"><span data-stu-id="28863-144">Request body</span></span>
<span data-ttu-id="28863-145">Empty</span><span class="sxs-lookup"><span data-stu-id="28863-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="28863-146">响应</span><span class="sxs-lookup"><span data-stu-id="28863-146">Response</span></span>
<span data-ttu-id="28863-147">如果成功且域存在 - 200 正常，响应正文中具有 statistics 对象。</span><span class="sxs-lookup"><span data-stu-id="28863-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="28863-148">如果域不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="28863-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="28863-149">示例</span><span class="sxs-lookup"><span data-stu-id="28863-149">Example</span></span>

<span data-ttu-id="28863-150">**请求**</span><span class="sxs-lookup"><span data-stu-id="28863-150">**Request**</span></span>

<span data-ttu-id="28863-151">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="28863-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="28863-152">**响应**</span><span class="sxs-lookup"><span data-stu-id="28863-152">**Response**</span></span>

<span data-ttu-id="28863-153">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="28863-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
