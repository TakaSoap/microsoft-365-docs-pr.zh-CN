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
ms.technology: mde
ms.openlocfilehash: ff43f6c46d89bc92cd1dc2a4fb0f329757b8f69e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166460"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="e444b-104">获取文件统计信息 API</span><span class="sxs-lookup"><span data-stu-id="e444b-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e444b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e444b-105">**Applies to:**</span></span>
- [<span data-ttu-id="e444b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e444b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e444b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e444b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e444b-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e444b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e444b-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e444b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e444b-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="e444b-110">API description</span></span>
<span data-ttu-id="e444b-111">检索给定文件的统计信息。</span><span class="sxs-lookup"><span data-stu-id="e444b-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="e444b-112">限制</span><span class="sxs-lookup"><span data-stu-id="e444b-112">Limitations</span></span>
1. <span data-ttu-id="e444b-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="e444b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e444b-114">权限</span><span class="sxs-lookup"><span data-stu-id="e444b-114">Permissions</span></span>
<span data-ttu-id="e444b-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="e444b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e444b-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e444b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e444b-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="e444b-117">Permission type</span></span> |   <span data-ttu-id="e444b-118">权限</span><span class="sxs-lookup"><span data-stu-id="e444b-118">Permission</span></span>  |   <span data-ttu-id="e444b-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="e444b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e444b-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="e444b-120">Application</span></span> |   <span data-ttu-id="e444b-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="e444b-121">File.Read.All</span></span> | <span data-ttu-id="e444b-122">"读取文件配置文件"</span><span class="sxs-lookup"><span data-stu-id="e444b-122">'Read file profiles'</span></span>
<span data-ttu-id="e444b-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="e444b-123">Delegated (work or school account)</span></span> | <span data-ttu-id="e444b-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="e444b-124">File.Read.All</span></span> | <span data-ttu-id="e444b-125">"读取文件配置文件"</span><span class="sxs-lookup"><span data-stu-id="e444b-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="e444b-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="e444b-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e444b-127">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="e444b-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e444b-128">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="e444b-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="e444b-129">请求标头</span><span class="sxs-lookup"><span data-stu-id="e444b-129">Request headers</span></span>

<span data-ttu-id="e444b-130">名称</span><span class="sxs-lookup"><span data-stu-id="e444b-130">Name</span></span> | <span data-ttu-id="e444b-131">类型</span><span class="sxs-lookup"><span data-stu-id="e444b-131">Type</span></span> | <span data-ttu-id="e444b-132">说明</span><span class="sxs-lookup"><span data-stu-id="e444b-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="e444b-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="e444b-133">Authorization</span></span> | <span data-ttu-id="e444b-134">String</span><span class="sxs-lookup"><span data-stu-id="e444b-134">String</span></span> | <span data-ttu-id="e444b-135">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="e444b-135">Bearer {token}.</span></span> <span data-ttu-id="e444b-136">**必需**。</span><span class="sxs-lookup"><span data-stu-id="e444b-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="e444b-137">请求 URI 参数</span><span class="sxs-lookup"><span data-stu-id="e444b-137">Request URI parameters</span></span>

<span data-ttu-id="e444b-138">名称</span><span class="sxs-lookup"><span data-stu-id="e444b-138">Name</span></span> | <span data-ttu-id="e444b-139">类型</span><span class="sxs-lookup"><span data-stu-id="e444b-139">Type</span></span> | <span data-ttu-id="e444b-140">说明</span><span class="sxs-lookup"><span data-stu-id="e444b-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="e444b-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="e444b-141">lookBackHours</span></span> | <span data-ttu-id="e444b-142">Int32</span><span class="sxs-lookup"><span data-stu-id="e444b-142">Int32</span></span> | <span data-ttu-id="e444b-143">定义我们重新搜索以获取统计信息的小时数。</span><span class="sxs-lookup"><span data-stu-id="e444b-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="e444b-144">默认为 30 天。</span><span class="sxs-lookup"><span data-stu-id="e444b-144">Defaults to 30 days.</span></span> <span data-ttu-id="e444b-145">**可选。**</span><span class="sxs-lookup"><span data-stu-id="e444b-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e444b-146">请求正文</span><span class="sxs-lookup"><span data-stu-id="e444b-146">Request body</span></span>
<span data-ttu-id="e444b-147">Empty</span><span class="sxs-lookup"><span data-stu-id="e444b-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e444b-148">响应</span><span class="sxs-lookup"><span data-stu-id="e444b-148">Response</span></span>
<span data-ttu-id="e444b-149">如果成功且文件存在 - 200 正常，正文中提供统计数据。</span><span class="sxs-lookup"><span data-stu-id="e444b-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="e444b-150">如果文件不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="e444b-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="e444b-151">示例</span><span class="sxs-lookup"><span data-stu-id="e444b-151">Example</span></span>

<span data-ttu-id="e444b-152">**请求**</span><span class="sxs-lookup"><span data-stu-id="e444b-152">**Request**</span></span>

<span data-ttu-id="e444b-153">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="e444b-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="e444b-154">**响应**</span><span class="sxs-lookup"><span data-stu-id="e444b-154">**Response**</span></span>

<span data-ttu-id="e444b-155">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="e444b-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
