---
title: Microsoft 365 Defender 高级搜寻 API
description: 了解如何使用 Microsoft 365 Defender 的高级搜寻 API 运行高级搜寻查询
keywords: 高级搜寻， API， api， MTP， M365 Defender， Microsoft 365 Defender
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
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719376"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="786b9-104">Microsoft 365 Defender 高级搜寻 API</span><span class="sxs-lookup"><span data-stu-id="786b9-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="786b9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="786b9-105">**Applies to:**</span></span>

- <span data-ttu-id="786b9-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="786b9-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="786b9-107">某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="786b9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="786b9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="786b9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="786b9-109">[高级搜寻](advanced-hunting-overview.md)是威胁搜寻工具，它使用专门[](advanced-hunting-query-language.md)构造的查询来检查 Microsoft 365 Defender 中过去 30 天的事件数据。</span><span class="sxs-lookup"><span data-stu-id="786b9-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="786b9-110">可以使用高级搜寻查询来检查异常活动、检测可能的威胁，甚至响应攻击。</span><span class="sxs-lookup"><span data-stu-id="786b9-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="786b9-111">高级搜寻 API 允许你以编程方式查询事件数据。</span><span class="sxs-lookup"><span data-stu-id="786b9-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="786b9-112">配额和资源分配</span><span class="sxs-lookup"><span data-stu-id="786b9-112">Quotas and resource allocation</span></span>

<span data-ttu-id="786b9-113">下列条件与所有查询相关。</span><span class="sxs-lookup"><span data-stu-id="786b9-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="786b9-114">查询将浏览并返回过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="786b9-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="786b9-115">结果可返回最多 100，000 行。</span><span class="sxs-lookup"><span data-stu-id="786b9-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="786b9-116">每个租户每分钟最多可以拨打 10 个呼叫。</span><span class="sxs-lookup"><span data-stu-id="786b9-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="786b9-117">每个租户每小时有 10 分钟的运行时间。</span><span class="sxs-lookup"><span data-stu-id="786b9-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="786b9-118">每个租户的运行时间总小时数为四小时。</span><span class="sxs-lookup"><span data-stu-id="786b9-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="786b9-119">如果单个请求运行超过 10 分钟，它将退出并返回错误。</span><span class="sxs-lookup"><span data-stu-id="786b9-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="786b9-120">HTTP 响应代码指示你已按发送的请求数或分配的运行时间达到 `429` 配额。</span><span class="sxs-lookup"><span data-stu-id="786b9-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="786b9-121">响应正文将包括重置达到的配额之前的时间。</span><span class="sxs-lookup"><span data-stu-id="786b9-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="786b9-122">权限</span><span class="sxs-lookup"><span data-stu-id="786b9-122">Permissions</span></span>

<span data-ttu-id="786b9-123">调用高级搜寻 API 需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="786b9-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="786b9-124">若要了解更多信息（包括如何选择权限），请参阅 [Access the Microsoft 365 Defender Protection API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="786b9-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="786b9-125">权限类型</span><span class="sxs-lookup"><span data-stu-id="786b9-125">Permission type</span></span> | <span data-ttu-id="786b9-126">权限</span><span class="sxs-lookup"><span data-stu-id="786b9-126">Permission</span></span> | <span data-ttu-id="786b9-127">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="786b9-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="786b9-128">应用程序</span><span class="sxs-lookup"><span data-stu-id="786b9-128">Application</span></span> | <span data-ttu-id="786b9-129">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="786b9-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="786b9-130">运行高级查询</span><span class="sxs-lookup"><span data-stu-id="786b9-130">Run advanced queries</span></span>
<span data-ttu-id="786b9-131">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="786b9-131">Delegated (work or school account)</span></span> | <span data-ttu-id="786b9-132">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="786b9-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="786b9-133">运行高级查询</span><span class="sxs-lookup"><span data-stu-id="786b9-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="786b9-134">使用用户凭据获取令牌时：</span><span class="sxs-lookup"><span data-stu-id="786b9-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="786b9-135">用户需要具有"查看数据"AD 角色</span><span class="sxs-lookup"><span data-stu-id="786b9-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="786b9-136">用户需要基于设备组设置访问设备。</span><span class="sxs-lookup"><span data-stu-id="786b9-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="786b9-137">HTTP 请求</span><span class="sxs-lookup"><span data-stu-id="786b9-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="786b9-138">请求标头</span><span class="sxs-lookup"><span data-stu-id="786b9-138">Request headers</span></span>

<span data-ttu-id="786b9-139">标头</span><span class="sxs-lookup"><span data-stu-id="786b9-139">Header</span></span> | <span data-ttu-id="786b9-140">值</span><span class="sxs-lookup"><span data-stu-id="786b9-140">Value</span></span>
-|-
<span data-ttu-id="786b9-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="786b9-141">Authorization</span></span> | <span data-ttu-id="786b9-142">Bearer {token} **注意：必需**</span><span class="sxs-lookup"><span data-stu-id="786b9-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="786b9-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="786b9-143">Content-Type</span></span> | <span data-ttu-id="786b9-144">application/json</span><span class="sxs-lookup"><span data-stu-id="786b9-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="786b9-145">请求正文</span><span class="sxs-lookup"><span data-stu-id="786b9-145">Request body</span></span>

<span data-ttu-id="786b9-146">在请求正文中，提供具有以下参数的 JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="786b9-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="786b9-147">参数</span><span class="sxs-lookup"><span data-stu-id="786b9-147">Parameter</span></span> | <span data-ttu-id="786b9-148">类型</span><span class="sxs-lookup"><span data-stu-id="786b9-148">Type</span></span> | <span data-ttu-id="786b9-149">说明</span><span class="sxs-lookup"><span data-stu-id="786b9-149">Description</span></span>
-|-|-
<span data-ttu-id="786b9-150">查询</span><span class="sxs-lookup"><span data-stu-id="786b9-150">Query</span></span> | <span data-ttu-id="786b9-151">文本</span><span class="sxs-lookup"><span data-stu-id="786b9-151">Text</span></span> | <span data-ttu-id="786b9-152">要运行的查询。</span><span class="sxs-lookup"><span data-stu-id="786b9-152">The query to run.</span></span> <span data-ttu-id="786b9-153">**注意：必需**</span><span class="sxs-lookup"><span data-stu-id="786b9-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="786b9-154">响应</span><span class="sxs-lookup"><span data-stu-id="786b9-154">Response</span></span>

<span data-ttu-id="786b9-155">如果成功，此方法将在响应正文中返回 `200 OK` 和 _QueryResponse_ 对象。</span><span class="sxs-lookup"><span data-stu-id="786b9-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="786b9-156">响应对象包含三个顶级属性：</span><span class="sxs-lookup"><span data-stu-id="786b9-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="786b9-157">Stats - 查询性能统计信息的字典。</span><span class="sxs-lookup"><span data-stu-id="786b9-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="786b9-158">Schema - 响应的架构，即每个Name-Type对的列表。</span><span class="sxs-lookup"><span data-stu-id="786b9-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="786b9-159">结果 - 高级搜寻事件列表。</span><span class="sxs-lookup"><span data-stu-id="786b9-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="786b9-160">示例</span><span class="sxs-lookup"><span data-stu-id="786b9-160">Example</span></span>

<span data-ttu-id="786b9-161">在下面的示例中，用户发送下面的查询，并接收包含 、和 的 API 响应 `Stats` `Schema` 对象 `Results` 。</span><span class="sxs-lookup"><span data-stu-id="786b9-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="786b9-162">查询</span><span class="sxs-lookup"><span data-stu-id="786b9-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="786b9-163">Response 对象</span><span class="sxs-lookup"><span data-stu-id="786b9-163">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="786b9-164">相关文章</span><span class="sxs-lookup"><span data-stu-id="786b9-164">Related articles</span></span>

- [<span data-ttu-id="786b9-165">访问 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="786b9-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="786b9-166">了解 API 限制和许可</span><span class="sxs-lookup"><span data-stu-id="786b9-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="786b9-167">了解错误代码</span><span class="sxs-lookup"><span data-stu-id="786b9-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="786b9-168">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="786b9-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
