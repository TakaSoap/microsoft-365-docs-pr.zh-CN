---
title: Microsoft 365Defender 高级搜寻 API
description: 了解如何使用 Defender 的高级搜寻 API Microsoft 365高级搜寻查询
keywords: 高级搜寻， API， api， M365 Defender， Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c988a609a329c8f7f8988314e56aae942beebac5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932889"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="1cf0a-104">Microsoft 365Defender 高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="1cf0a-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1cf0a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-105">**Applies to:**</span></span>

- <span data-ttu-id="1cf0a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1cf0a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cf0a-107">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1cf0a-108">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1cf0a-109">[高级搜寻](advanced-hunting-overview.md)是一种威胁搜寻工具，它[](advanced-hunting-query-language.md)使用专门构造的查询来检查 Microsoft 365 Defender 中过去 30 天的事件数据。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="1cf0a-110">可以使用高级搜寻查询来检查异常活动、检测可能的威胁，甚至响应攻击。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="1cf0a-111">高级搜寻 API 允许你以编程方式查询事件数据。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="1cf0a-112">配额和资源分配</span><span class="sxs-lookup"><span data-stu-id="1cf0a-112">Quotas and resource allocation</span></span>

<span data-ttu-id="1cf0a-113">下列条件与所有查询相关。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="1cf0a-114">查询将浏览并返回过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="1cf0a-115">结果最多返回 100，000 行。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="1cf0a-116">每个租户每分钟最多可以拨打 15 次呼叫。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="1cf0a-117">每个租户每小时有 10 分钟的运行时间。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="1cf0a-118">每个租户每天的总运行时间为四小时。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="1cf0a-119">如果单个请求运行的时间超过 10 分钟，它将退出并返回错误。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="1cf0a-120">HTTP 响应代码指示你已按发送的请求数或按分配的运行时间 `429` 达到配额。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="1cf0a-121">阅读响应正文，了解已达到的限制。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="1cf0a-122">上面列出的所有配额 (例如，每个租户大小每) 15 次呼叫。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="1cf0a-123">这些配额是最小值。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="1cf0a-124">Permissions</span><span class="sxs-lookup"><span data-stu-id="1cf0a-124">Permissions</span></span>

<span data-ttu-id="1cf0a-125">调用高级搜寻 API 需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="1cf0a-126">若要了解更多信息（包括如何选择权限），请参阅访问[Microsoft 365 Defender 保护 API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="1cf0a-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="1cf0a-127">权限类型</span><span class="sxs-lookup"><span data-stu-id="1cf0a-127">Permission type</span></span> | <span data-ttu-id="1cf0a-128">权限</span><span class="sxs-lookup"><span data-stu-id="1cf0a-128">Permission</span></span> | <span data-ttu-id="1cf0a-129">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="1cf0a-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="1cf0a-130">应用程序</span><span class="sxs-lookup"><span data-stu-id="1cf0a-130">Application</span></span> | <span data-ttu-id="1cf0a-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="1cf0a-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="1cf0a-132">运行高级查询</span><span class="sxs-lookup"><span data-stu-id="1cf0a-132">Run advanced queries</span></span>
<span data-ttu-id="1cf0a-133">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="1cf0a-133">Delegated (work or school account)</span></span> | <span data-ttu-id="1cf0a-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="1cf0a-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="1cf0a-135">运行高级查询</span><span class="sxs-lookup"><span data-stu-id="1cf0a-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="1cf0a-136">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="1cf0a-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="1cf0a-137">用户需要具有"查看数据"AD 角色</span><span class="sxs-lookup"><span data-stu-id="1cf0a-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="1cf0a-138">用户需要基于设备组设置访问设备。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="1cf0a-139">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="1cf0a-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="1cf0a-140">请求标头</span><span class="sxs-lookup"><span data-stu-id="1cf0a-140">Request headers</span></span>

<span data-ttu-id="1cf0a-141">标头</span><span class="sxs-lookup"><span data-stu-id="1cf0a-141">Header</span></span> | <span data-ttu-id="1cf0a-142">值</span><span class="sxs-lookup"><span data-stu-id="1cf0a-142">Value</span></span>
-|-
<span data-ttu-id="1cf0a-143">Authorization</span><span class="sxs-lookup"><span data-stu-id="1cf0a-143">Authorization</span></span> | <span data-ttu-id="1cf0a-144">Bearer {token} **注意：必需**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="1cf0a-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1cf0a-145">Content-Type</span></span> | <span data-ttu-id="1cf0a-146">application/json</span><span class="sxs-lookup"><span data-stu-id="1cf0a-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="1cf0a-147">请求正文</span><span class="sxs-lookup"><span data-stu-id="1cf0a-147">Request body</span></span>

<span data-ttu-id="1cf0a-148">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="1cf0a-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="1cf0a-149">参数</span><span class="sxs-lookup"><span data-stu-id="1cf0a-149">Parameter</span></span> | <span data-ttu-id="1cf0a-150">类型</span><span class="sxs-lookup"><span data-stu-id="1cf0a-150">Type</span></span> | <span data-ttu-id="1cf0a-151">说明</span><span class="sxs-lookup"><span data-stu-id="1cf0a-151">Description</span></span>
-|-|-
<span data-ttu-id="1cf0a-152">查询</span><span class="sxs-lookup"><span data-stu-id="1cf0a-152">Query</span></span> | <span data-ttu-id="1cf0a-153">文本</span><span class="sxs-lookup"><span data-stu-id="1cf0a-153">Text</span></span> | <span data-ttu-id="1cf0a-154">要运行的查询。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-154">The query to run.</span></span> <span data-ttu-id="1cf0a-155">**注意：必需**</span><span class="sxs-lookup"><span data-stu-id="1cf0a-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="1cf0a-156">响应</span><span class="sxs-lookup"><span data-stu-id="1cf0a-156">Response</span></span>

<span data-ttu-id="1cf0a-157">如果成功，此方法将在响应正文中 `200 OK` 返回 和 _QueryResponse_ 对象。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="1cf0a-158">response 对象包含三个顶级属性：</span><span class="sxs-lookup"><span data-stu-id="1cf0a-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="1cf0a-159">Stats - 查询性能统计信息的字典。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="1cf0a-160">Schema - 响应的架构，每个列Name-Type对的列表。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="1cf0a-161">结果 - 高级搜寻事件列表。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="1cf0a-162">示例</span><span class="sxs-lookup"><span data-stu-id="1cf0a-162">Example</span></span>

<span data-ttu-id="1cf0a-163">在下面的示例中，用户发送下面的查询并接收包含 、 和 的 API 响应 `Stats` `Schema` 对象 `Results` 。</span><span class="sxs-lookup"><span data-stu-id="1cf0a-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="1cf0a-164">查询</span><span class="sxs-lookup"><span data-stu-id="1cf0a-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="1cf0a-165">Response 对象</span><span class="sxs-lookup"><span data-stu-id="1cf0a-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="1cf0a-166">相关文章</span><span class="sxs-lookup"><span data-stu-id="1cf0a-166">Related articles</span></span>

- [<span data-ttu-id="1cf0a-167">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1cf0a-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1cf0a-168">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="1cf0a-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1cf0a-169">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="1cf0a-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="1cf0a-170">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="1cf0a-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
