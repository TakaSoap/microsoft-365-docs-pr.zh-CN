---
title: 高级搜寻 API
ms.reviewer: ''
description: 了解如何使用高级搜寻 API 在 Microsoft Defender for Endpoint 上运行高级查询。 了解限制并查看示例。
keywords: api， 受支持的 api， 高级搜寻， 查询
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
ms.openlocfilehash: 40487143ff18cedb76c9f3f33c52cab24687c282
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604365"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="bce0b-105">高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="bce0b-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bce0b-106">**适用于：Microsoft** [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bce0b-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bce0b-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="bce0b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bce0b-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="bce0b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="bce0b-109">限制</span><span class="sxs-lookup"><span data-stu-id="bce0b-109">Limitations</span></span>

1. <span data-ttu-id="bce0b-110">只能对过去 30 天的数据运行查询。</span><span class="sxs-lookup"><span data-stu-id="bce0b-110">You can only run a query on data from the last 30 days.</span></span>

2. <span data-ttu-id="bce0b-111">结果最多包含 100，000 行。</span><span class="sxs-lookup"><span data-stu-id="bce0b-111">The results will include a maximum of 100,000 rows.</span></span>

3. <span data-ttu-id="bce0b-112">每个租户的执行次数受到限制：</span><span class="sxs-lookup"><span data-stu-id="bce0b-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="bce0b-113">API 调用：每分钟最多 45 个调用，每小时最多 1500 个调用。</span><span class="sxs-lookup"><span data-stu-id="bce0b-113">API calls: Up to 45 calls per minute, up to 1500 calls per hour.</span></span>
   - <span data-ttu-id="bce0b-114">执行时间：每小时运行 10 分钟，一天运行 3 小时。</span><span class="sxs-lookup"><span data-stu-id="bce0b-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>

4. <span data-ttu-id="bce0b-115">单个请求的最大执行时间为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="bce0b-115">The maximal execution time of a single request is 10 minutes.</span></span>

5. <span data-ttu-id="bce0b-116">429 响应表示达到请求数或 CPU 的配额限制。</span><span class="sxs-lookup"><span data-stu-id="bce0b-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="bce0b-117">读取响应正文，了解已达到的限制。</span><span class="sxs-lookup"><span data-stu-id="bce0b-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="bce0b-118">权限</span><span class="sxs-lookup"><span data-stu-id="bce0b-118">Permissions</span></span>

<span data-ttu-id="bce0b-119">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="bce0b-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bce0b-120">若要了解更多信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bce0b-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bce0b-121">权限类型</span><span class="sxs-lookup"><span data-stu-id="bce0b-121">Permission type</span></span> |   <span data-ttu-id="bce0b-122">权限</span><span class="sxs-lookup"><span data-stu-id="bce0b-122">Permission</span></span>  |   <span data-ttu-id="bce0b-123">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="bce0b-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bce0b-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="bce0b-124">Application</span></span> |   <span data-ttu-id="bce0b-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="bce0b-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="bce0b-126">"运行高级查询"</span><span class="sxs-lookup"><span data-stu-id="bce0b-126">'Run advanced queries'</span></span>
<span data-ttu-id="bce0b-127">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="bce0b-127">Delegated (work or school account)</span></span> | <span data-ttu-id="bce0b-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="bce0b-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="bce0b-129">"运行高级查询"</span><span class="sxs-lookup"><span data-stu-id="bce0b-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="bce0b-130">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="bce0b-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bce0b-131">用户需要具有"查看数据"AD 角色</span><span class="sxs-lookup"><span data-stu-id="bce0b-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="bce0b-132">用户需要具有对设备的访问权限，根据设备组设置 (请参阅创建和管理 [设备](machine-groups.md) 组，了解) </span><span class="sxs-lookup"><span data-stu-id="bce0b-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bce0b-133">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="bce0b-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="bce0b-134">请求标头</span><span class="sxs-lookup"><span data-stu-id="bce0b-134">Request headers</span></span>

<span data-ttu-id="bce0b-135">标头</span><span class="sxs-lookup"><span data-stu-id="bce0b-135">Header</span></span> | <span data-ttu-id="bce0b-136">值</span><span class="sxs-lookup"><span data-stu-id="bce0b-136">Value</span></span> 
:---|:---
<span data-ttu-id="bce0b-137">Authorization</span><span class="sxs-lookup"><span data-stu-id="bce0b-137">Authorization</span></span> | <span data-ttu-id="bce0b-138">Bearer {token}。</span><span class="sxs-lookup"><span data-stu-id="bce0b-138">Bearer {token}.</span></span> <span data-ttu-id="bce0b-139">**必需**。</span><span class="sxs-lookup"><span data-stu-id="bce0b-139">**Required**.</span></span>
<span data-ttu-id="bce0b-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bce0b-140">Content-Type</span></span>    | <span data-ttu-id="bce0b-141">application/json</span><span class="sxs-lookup"><span data-stu-id="bce0b-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="bce0b-142">请求正文</span><span class="sxs-lookup"><span data-stu-id="bce0b-142">Request body</span></span>

<span data-ttu-id="bce0b-143">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="bce0b-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="bce0b-144">参数</span><span class="sxs-lookup"><span data-stu-id="bce0b-144">Parameter</span></span> | <span data-ttu-id="bce0b-145">类型</span><span class="sxs-lookup"><span data-stu-id="bce0b-145">Type</span></span>    | <span data-ttu-id="bce0b-146">Description</span><span class="sxs-lookup"><span data-stu-id="bce0b-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="bce0b-147">查询</span><span class="sxs-lookup"><span data-stu-id="bce0b-147">Query</span></span> | <span data-ttu-id="bce0b-148">文本</span><span class="sxs-lookup"><span data-stu-id="bce0b-148">Text</span></span> |  <span data-ttu-id="bce0b-149">要运行的查询。</span><span class="sxs-lookup"><span data-stu-id="bce0b-149">The query to run.</span></span> <span data-ttu-id="bce0b-150">**必需**。</span><span class="sxs-lookup"><span data-stu-id="bce0b-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="bce0b-151">响应</span><span class="sxs-lookup"><span data-stu-id="bce0b-151">Response</span></span>

<span data-ttu-id="bce0b-152">如果成功，此方法在响应正文中返回 200 OK 和 _QueryResponse_ 对象。</span><span class="sxs-lookup"><span data-stu-id="bce0b-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="bce0b-153">示例</span><span class="sxs-lookup"><span data-stu-id="bce0b-153">Example</span></span>

##### <a name="request"></a><span data-ttu-id="bce0b-154">请求</span><span class="sxs-lookup"><span data-stu-id="bce0b-154">Request</span></span>

<span data-ttu-id="bce0b-155">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="bce0b-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a><span data-ttu-id="bce0b-156">响应</span><span class="sxs-lookup"><span data-stu-id="bce0b-156">Response</span></span>

<span data-ttu-id="bce0b-157">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="bce0b-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="bce0b-158">为简洁起见，可能会截断此处所示的响应对象。</span><span class="sxs-lookup"><span data-stu-id="bce0b-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="bce0b-159">将从实际调用中返回所有属性。</span><span class="sxs-lookup"><span data-stu-id="bce0b-159">All of the properties will be returned from an actual call.</span></span>

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="bce0b-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="bce0b-160">Related topics</span></span>

- [<span data-ttu-id="bce0b-161">Microsoft Defender for Endpoint API 简介</span><span class="sxs-lookup"><span data-stu-id="bce0b-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="bce0b-162">门户中的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="bce0b-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bce0b-163">通过 PowerShell 高级搜寻</span><span class="sxs-lookup"><span data-stu-id="bce0b-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
