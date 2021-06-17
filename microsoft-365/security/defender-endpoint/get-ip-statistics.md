---
title: 获取 IP 统计信息 API
description: 使用 Microsoft Defender for Endpoint 获取你的 IP 的最新统计信息。
keywords: api， 图形 api， 受支持的 api， 获取， ip， 统计信息， 普遍程度
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
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998724"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="34287-104">获取 IP 统计信息 API</span><span class="sxs-lookup"><span data-stu-id="34287-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="34287-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="34287-105">**Applies to:**</span></span>
- [<span data-ttu-id="34287-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="34287-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="34287-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34287-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="34287-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="34287-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34287-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="34287-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="34287-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="34287-110">API description</span></span>
<span data-ttu-id="34287-111">检索给定 IP 的统计信息。</span><span class="sxs-lookup"><span data-stu-id="34287-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="34287-112">限制</span><span class="sxs-lookup"><span data-stu-id="34287-112">Limitations</span></span>
1. <span data-ttu-id="34287-113">此 API 的速率限制是每分钟 100 个调用和每小时 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="34287-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="34287-114">权限</span><span class="sxs-lookup"><span data-stu-id="34287-114">Permissions</span></span>
<span data-ttu-id="34287-115">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="34287-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="34287-116">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="34287-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="34287-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="34287-117">Permission type</span></span> |   <span data-ttu-id="34287-118">权限</span><span class="sxs-lookup"><span data-stu-id="34287-118">Permission</span></span>  |   <span data-ttu-id="34287-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="34287-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="34287-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="34287-120">Application</span></span> |   <span data-ttu-id="34287-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="34287-121">Ip.Read.All</span></span> |   <span data-ttu-id="34287-122">"读取 IP 地址配置文件"</span><span class="sxs-lookup"><span data-stu-id="34287-122">'Read IP address profiles'</span></span>
<span data-ttu-id="34287-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="34287-123">Delegated (work or school account)</span></span> | <span data-ttu-id="34287-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="34287-124">Ip.Read.All</span></span> |  <span data-ttu-id="34287-125">"读取 IP 地址配置文件"</span><span class="sxs-lookup"><span data-stu-id="34287-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="34287-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="34287-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="34287-127">用户至少需要具有以下角色权限："查看数据"权限 (有关详细信息，请参阅创建和管理) [](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="34287-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="34287-128">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="34287-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="34287-129">请求标头</span><span class="sxs-lookup"><span data-stu-id="34287-129">Request headers</span></span>

<span data-ttu-id="34287-130">名称</span><span class="sxs-lookup"><span data-stu-id="34287-130">Name</span></span> | <span data-ttu-id="34287-131">类型</span><span class="sxs-lookup"><span data-stu-id="34287-131">Type</span></span> | <span data-ttu-id="34287-132">说明</span><span class="sxs-lookup"><span data-stu-id="34287-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="34287-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="34287-133">Authorization</span></span> | <span data-ttu-id="34287-134">String</span><span class="sxs-lookup"><span data-stu-id="34287-134">String</span></span> | <span data-ttu-id="34287-135">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="34287-135">Bearer {token}.</span></span> <span data-ttu-id="34287-136">**必需**。</span><span class="sxs-lookup"><span data-stu-id="34287-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="34287-137">请求 URI 参数</span><span class="sxs-lookup"><span data-stu-id="34287-137">Request URI parameters</span></span>

<span data-ttu-id="34287-138">名称</span><span class="sxs-lookup"><span data-stu-id="34287-138">Name</span></span> | <span data-ttu-id="34287-139">类型</span><span class="sxs-lookup"><span data-stu-id="34287-139">Type</span></span> | <span data-ttu-id="34287-140">说明</span><span class="sxs-lookup"><span data-stu-id="34287-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="34287-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="34287-141">lookBackHours</span></span> | <span data-ttu-id="34287-142">Int32</span><span class="sxs-lookup"><span data-stu-id="34287-142">Int32</span></span> | <span data-ttu-id="34287-143">定义我们重新搜索以获取统计信息的小时数。</span><span class="sxs-lookup"><span data-stu-id="34287-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="34287-144">默认为 30 天。</span><span class="sxs-lookup"><span data-stu-id="34287-144">Defaults to 30 days.</span></span> <span data-ttu-id="34287-145">**可选。**</span><span class="sxs-lookup"><span data-stu-id="34287-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="34287-146">请求正文</span><span class="sxs-lookup"><span data-stu-id="34287-146">Request body</span></span>
<span data-ttu-id="34287-147">Empty</span><span class="sxs-lookup"><span data-stu-id="34287-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="34287-148">响应</span><span class="sxs-lookup"><span data-stu-id="34287-148">Response</span></span>
<span data-ttu-id="34287-149">如果成功且 ip 存在 - 200 正常，正文中具有统计数据。</span><span class="sxs-lookup"><span data-stu-id="34287-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="34287-150">IP 不存在 - 404 未找到。</span><span class="sxs-lookup"><span data-stu-id="34287-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="34287-151">示例</span><span class="sxs-lookup"><span data-stu-id="34287-151">Example</span></span>

<span data-ttu-id="34287-152">**请求**</span><span class="sxs-lookup"><span data-stu-id="34287-152">**Request**</span></span>

<span data-ttu-id="34287-153">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="34287-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="34287-154">**响应**</span><span class="sxs-lookup"><span data-stu-id="34287-154">**Response**</span></span>

<span data-ttu-id="34287-155">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="34287-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="34287-156">名称</span><span class="sxs-lookup"><span data-stu-id="34287-156">Name</span></span> | <span data-ttu-id="34287-157">说明</span><span class="sxs-lookup"><span data-stu-id="34287-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="34287-158">组织普遍程度</span><span class="sxs-lookup"><span data-stu-id="34287-158">Organization prevalence</span></span> | <span data-ttu-id="34287-159">打开到此 IP 的网络连接的设备数。</span><span class="sxs-lookup"><span data-stu-id="34287-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="34287-160">首次看到组织</span><span class="sxs-lookup"><span data-stu-id="34287-160">Org first seen</span></span> | <span data-ttu-id="34287-161">组织中此 IP 的第一个连接。</span><span class="sxs-lookup"><span data-stu-id="34287-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="34287-162">上次查看组织</span><span class="sxs-lookup"><span data-stu-id="34287-162">Org last seen</span></span>  | <span data-ttu-id="34287-163">组织中此 IP 的最后一个连接。</span><span class="sxs-lookup"><span data-stu-id="34287-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="34287-164">此统计信息基于过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="34287-164">This statistic information is based on data from the past 30 days.</span></span> 
