---
title: 获取文件统计信息 API
description: 了解如何使用获取文件统计信息 API 检索 Microsoft Defender for Endpoint 中给定文件的统计信息。
keywords: api， 图形 api， 受支持的 api， 获取， 文件， 统计信息
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 826b2ff25363f1d9a6276e1a42a10c1cf4995904
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998808"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="af567-104">获取文件统计信息 API</span><span class="sxs-lookup"><span data-stu-id="af567-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af567-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="af567-105">**Applies to:**</span></span>
- [<span data-ttu-id="af567-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af567-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="af567-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af567-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="af567-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="af567-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af567-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="af567-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="af567-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="af567-110">API description</span></span>
<span data-ttu-id="af567-111">检索给定文件的统计信息。</span><span class="sxs-lookup"><span data-stu-id="af567-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="af567-112">限制</span><span class="sxs-lookup"><span data-stu-id="af567-112">Limitations</span></span>
1. <span data-ttu-id="af567-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="af567-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="af567-114">权限</span><span class="sxs-lookup"><span data-stu-id="af567-114">Permissions</span></span>
<span data-ttu-id="af567-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="af567-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="af567-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="af567-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="af567-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="af567-117">Permission type</span></span> |   <span data-ttu-id="af567-118">权限</span><span class="sxs-lookup"><span data-stu-id="af567-118">Permission</span></span>  |   <span data-ttu-id="af567-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="af567-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="af567-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="af567-120">Application</span></span> |   <span data-ttu-id="af567-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="af567-121">File.Read.All</span></span> | <span data-ttu-id="af567-122">"读取文件配置文件"</span><span class="sxs-lookup"><span data-stu-id="af567-122">'Read file profiles'</span></span>
<span data-ttu-id="af567-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="af567-123">Delegated (work or school account)</span></span> | <span data-ttu-id="af567-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="af567-124">File.Read.All</span></span> | <span data-ttu-id="af567-125">"读取文件配置文件"</span><span class="sxs-lookup"><span data-stu-id="af567-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="af567-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="af567-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="af567-127">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="af567-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="af567-128">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="af567-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="af567-129">请求标头</span><span class="sxs-lookup"><span data-stu-id="af567-129">Request headers</span></span>

<span data-ttu-id="af567-130">名称</span><span class="sxs-lookup"><span data-stu-id="af567-130">Name</span></span> | <span data-ttu-id="af567-131">类型</span><span class="sxs-lookup"><span data-stu-id="af567-131">Type</span></span> | <span data-ttu-id="af567-132">说明</span><span class="sxs-lookup"><span data-stu-id="af567-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="af567-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="af567-133">Authorization</span></span> | <span data-ttu-id="af567-134">String</span><span class="sxs-lookup"><span data-stu-id="af567-134">String</span></span> | <span data-ttu-id="af567-135">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="af567-135">Bearer {token}.</span></span> <span data-ttu-id="af567-136">**必需**。</span><span class="sxs-lookup"><span data-stu-id="af567-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="af567-137">请求 URI 参数</span><span class="sxs-lookup"><span data-stu-id="af567-137">Request URI parameters</span></span>

<span data-ttu-id="af567-138">名称</span><span class="sxs-lookup"><span data-stu-id="af567-138">Name</span></span> | <span data-ttu-id="af567-139">类型</span><span class="sxs-lookup"><span data-stu-id="af567-139">Type</span></span> | <span data-ttu-id="af567-140">说明</span><span class="sxs-lookup"><span data-stu-id="af567-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="af567-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="af567-141">lookBackHours</span></span> | <span data-ttu-id="af567-142">Int32</span><span class="sxs-lookup"><span data-stu-id="af567-142">Int32</span></span> | <span data-ttu-id="af567-143">定义我们重新搜索以获取统计信息的小时数。</span><span class="sxs-lookup"><span data-stu-id="af567-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="af567-144">默认为 30 天。</span><span class="sxs-lookup"><span data-stu-id="af567-144">Defaults to 30 days.</span></span> <span data-ttu-id="af567-145">**可选。**</span><span class="sxs-lookup"><span data-stu-id="af567-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="af567-146">请求正文</span><span class="sxs-lookup"><span data-stu-id="af567-146">Request body</span></span>
<span data-ttu-id="af567-147">Empty</span><span class="sxs-lookup"><span data-stu-id="af567-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="af567-148">响应</span><span class="sxs-lookup"><span data-stu-id="af567-148">Response</span></span>
<span data-ttu-id="af567-149">如果成功且文件存在 - 200 正常，正文中提供统计数据。</span><span class="sxs-lookup"><span data-stu-id="af567-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="af567-150">如果文件不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="af567-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="af567-151">示例</span><span class="sxs-lookup"><span data-stu-id="af567-151">Example</span></span>

<span data-ttu-id="af567-152">**请求**</span><span class="sxs-lookup"><span data-stu-id="af567-152">**Request**</span></span>

<span data-ttu-id="af567-153">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="af567-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="af567-154">**响应**</span><span class="sxs-lookup"><span data-stu-id="af567-154">**Response**</span></span>

<span data-ttu-id="af567-155">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="af567-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "organizationPrevalence": 14850,
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globallyPrevalence": 705012,
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
