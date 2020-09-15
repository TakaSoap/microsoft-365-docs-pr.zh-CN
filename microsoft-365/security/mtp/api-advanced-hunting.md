---
title: 高级搜寻 Api
description: 了解如何使用 Microsoft 威胁防护 API 运行高级搜寻查询
keywords: 高级搜寻、Api、api、MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650174"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="c538f-104">高级搜寻 Api</span><span class="sxs-lookup"><span data-stu-id="c538f-104">Advanced hunting APIs</span></span>

<span data-ttu-id="c538f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c538f-105">**Applies to:**</span></span>
- <span data-ttu-id="c538f-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="c538f-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c538f-107">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="c538f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c538f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="c538f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="c538f-109">限制</span><span class="sxs-lookup"><span data-stu-id="c538f-109">Limitations</span></span>
1. <span data-ttu-id="c538f-110">只能对最近30天的数据运行查询。</span><span class="sxs-lookup"><span data-stu-id="c538f-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="c538f-111">结果将包含最多100000行。</span><span class="sxs-lookup"><span data-stu-id="c538f-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="c538f-112">执行次数限制为每个租户：每分钟最多15个呼叫、每小时15分钟的运行时间和4小时的运行时间。</span><span class="sxs-lookup"><span data-stu-id="c538f-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="c538f-113">单个请求的最大执行时间为10分钟。</span><span class="sxs-lookup"><span data-stu-id="c538f-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="c538f-114">权限</span><span class="sxs-lookup"><span data-stu-id="c538f-114">Permissions</span></span>
<span data-ttu-id="c538f-115">若要调用此 API，必须有以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="c538f-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c538f-116">若要了解详细信息，包括如何选择权限，请参阅 [访问 Microsoft 威胁防护 api](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c538f-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="c538f-117">权限类型</span><span class="sxs-lookup"><span data-stu-id="c538f-117">Permission type</span></span> |   <span data-ttu-id="c538f-118">权限</span><span class="sxs-lookup"><span data-stu-id="c538f-118">Permission</span></span>  |   <span data-ttu-id="c538f-119">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="c538f-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c538f-120">应用程序</span><span class="sxs-lookup"><span data-stu-id="c538f-120">Application</span></span> |   <span data-ttu-id="c538f-121">AdvancedHunting</span><span class="sxs-lookup"><span data-stu-id="c538f-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="c538f-122">"运行高级查询"</span><span class="sxs-lookup"><span data-stu-id="c538f-122">'Run advanced queries'</span></span>
<span data-ttu-id="c538f-123">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="c538f-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c538f-124">AdvancedHunting。请阅读</span><span class="sxs-lookup"><span data-stu-id="c538f-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="c538f-125">"运行高级查询"</span><span class="sxs-lookup"><span data-stu-id="c538f-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="c538f-126">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="c538f-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c538f-127">用户需要具有 "查看数据" AD 角色</span><span class="sxs-lookup"><span data-stu-id="c538f-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="c538f-128">用户需要具有基于设备组设置的设备的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c538f-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="c538f-129">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="c538f-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="c538f-130">请求标头</span><span class="sxs-lookup"><span data-stu-id="c538f-130">Request headers</span></span>

<span data-ttu-id="c538f-131">标头</span><span class="sxs-lookup"><span data-stu-id="c538f-131">Header</span></span> | <span data-ttu-id="c538f-132">值</span><span class="sxs-lookup"><span data-stu-id="c538f-132">Value</span></span> 
:---|:---
<span data-ttu-id="c538f-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="c538f-133">Authorization</span></span> | <span data-ttu-id="c538f-134">持有者 {令牌}。</span><span class="sxs-lookup"><span data-stu-id="c538f-134">Bearer {token}.</span></span> <span data-ttu-id="c538f-135">\*\*\*\* 必需。</span><span class="sxs-lookup"><span data-stu-id="c538f-135">**Required**.</span></span>
<span data-ttu-id="c538f-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c538f-136">Content-Type</span></span>    | <span data-ttu-id="c538f-137">application/json</span><span class="sxs-lookup"><span data-stu-id="c538f-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="c538f-138">请求正文</span><span class="sxs-lookup"><span data-stu-id="c538f-138">Request body</span></span>
<span data-ttu-id="c538f-139">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="c538f-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="c538f-140">参数</span><span class="sxs-lookup"><span data-stu-id="c538f-140">Parameter</span></span> | <span data-ttu-id="c538f-141">类型</span><span class="sxs-lookup"><span data-stu-id="c538f-141">Type</span></span>    | <span data-ttu-id="c538f-142">描述</span><span class="sxs-lookup"><span data-stu-id="c538f-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="c538f-143">查询</span><span class="sxs-lookup"><span data-stu-id="c538f-143">Query</span></span> | <span data-ttu-id="c538f-144">文本</span><span class="sxs-lookup"><span data-stu-id="c538f-144">Text</span></span> |  <span data-ttu-id="c538f-145">要运行的查询。</span><span class="sxs-lookup"><span data-stu-id="c538f-145">The query to run.</span></span> <span data-ttu-id="c538f-146">\*\*\*\* 必需。</span><span class="sxs-lookup"><span data-stu-id="c538f-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="c538f-147">响应</span><span class="sxs-lookup"><span data-stu-id="c538f-147">Response</span></span>
<span data-ttu-id="c538f-148">如果成功，此方法在响应正文中返回 200 OK 和 _类_ 对象。</span><span class="sxs-lookup"><span data-stu-id="c538f-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="c538f-149">Response 对象分为3个部分 (属性) ：</span><span class="sxs-lookup"><span data-stu-id="c538f-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="c538f-150">```Stats``` -查询性能统计信息。</span><span class="sxs-lookup"><span data-stu-id="c538f-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="c538f-151">```Schema``` -响应的架构，每个列的名称类型对的列表。</span><span class="sxs-lookup"><span data-stu-id="c538f-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="c538f-152">```Results``` -高级搜寻事件的列表。</span><span class="sxs-lookup"><span data-stu-id="c538f-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="c538f-153">示例</span><span class="sxs-lookup"><span data-stu-id="c538f-153">Example</span></span>

<span data-ttu-id="c538f-154">请求</span><span class="sxs-lookup"><span data-stu-id="c538f-154">Request</span></span>

<span data-ttu-id="c538f-155">下面是一个请求示例。</span><span class="sxs-lookup"><span data-stu-id="c538f-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="c538f-156">响应</span><span class="sxs-lookup"><span data-stu-id="c538f-156">Response</span></span>

<span data-ttu-id="c538f-157">下面是一个响应示例。</span><span class="sxs-lookup"><span data-stu-id="c538f-157">Here is an example of the response.</span></span>


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a><span data-ttu-id="c538f-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="c538f-158">Related topic</span></span>
- [<span data-ttu-id="c538f-159">访问 Microsoft 威胁防护 Api</span><span class="sxs-lookup"><span data-stu-id="c538f-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
