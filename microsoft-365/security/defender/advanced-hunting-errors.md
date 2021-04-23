---
title: 处理 Microsoft 365 Defender 高级搜寻中的错误
description: 了解使用高级搜寻时显示的错误
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构， kusto， 超时， 资源， 错误， 未知错误， 限制， 配额， 参数， 分配
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 32d50103c6476a89f24568edeea75a206e37e227
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952676"
---
# <a name="handle-advanced-hunting-errors"></a><span data-ttu-id="faa2c-104">处理高级搜寻错误</span><span class="sxs-lookup"><span data-stu-id="faa2c-104">Handle advanced hunting errors</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="faa2c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="faa2c-105">**Applies to:**</span></span>
- <span data-ttu-id="faa2c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="faa2c-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="faa2c-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="faa2c-107">Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="faa2c-108">高级搜寻显示错误，以通知语法错误以及查询命中预定义 [配额和使用参数时](advanced-hunting-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="faa2c-108">Advanced hunting displays errors to notify for syntax mistakes and whenever queries hit [predefined quotas and usage parameters](advanced-hunting-limits.md).</span></span> <span data-ttu-id="faa2c-109">有关如何解决或避免错误的提示，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="faa2c-109">Refer to the table below for tips on how to resolve or avoid errors.</span></span>

| <span data-ttu-id="faa2c-110">错误类型</span><span class="sxs-lookup"><span data-stu-id="faa2c-110">Error type</span></span> | <span data-ttu-id="faa2c-111">原因</span><span class="sxs-lookup"><span data-stu-id="faa2c-111">Cause</span></span> | <span data-ttu-id="faa2c-112">解决方案</span><span class="sxs-lookup"><span data-stu-id="faa2c-112">Resolution</span></span> | <span data-ttu-id="faa2c-113">错误消息示例</span><span class="sxs-lookup"><span data-stu-id="faa2c-113">Error message examples</span></span> |
|--|--|--|--|
| <span data-ttu-id="faa2c-114">语法错误</span><span class="sxs-lookup"><span data-stu-id="faa2c-114">Syntax errors</span></span> | <span data-ttu-id="faa2c-115">查询包含无法识别的名称，包括对不存在的运算符、列、函数或表的引用。</span><span class="sxs-lookup"><span data-stu-id="faa2c-115">The query contains unrecognized names, including references to nonexistent operators, columns, functions, or tables.</span></span> | <span data-ttu-id="faa2c-116">确保对 [Kusto 运算符和函数的引用](/azure/data-explorer/kusto/query/) 正确无误。</span><span class="sxs-lookup"><span data-stu-id="faa2c-116">Ensure references to [Kusto operators and functions](/azure/data-explorer/kusto/query/) are correct.</span></span> <span data-ttu-id="faa2c-117">检查 [架构，](advanced-hunting-schema-tables.md) 了解正确的高级搜寻列、函数和表。</span><span class="sxs-lookup"><span data-stu-id="faa2c-117">Check [the schema](advanced-hunting-schema-tables.md) for the correct advanced hunting columns, functions, and tables.</span></span> <span data-ttu-id="faa2c-118">将变量字符串括在引号中，以便识别它们。</span><span class="sxs-lookup"><span data-stu-id="faa2c-118">Enclose variable strings in quotes so they are recognized.</span></span> <span data-ttu-id="faa2c-119">编写查询时，请使用来自查询的自动完成IntelliSense。</span><span class="sxs-lookup"><span data-stu-id="faa2c-119">While writing your queries, use the autocomplete suggestions from IntelliSense.</span></span> | `A recognition error occurred.` |
| <span data-ttu-id="faa2c-120">语义错误</span><span class="sxs-lookup"><span data-stu-id="faa2c-120">Semantic errors</span></span> | <span data-ttu-id="faa2c-121">虽然查询使用有效的运算符、列、函数或表名称，但在其结构和结果逻辑中都有错误。</span><span class="sxs-lookup"><span data-stu-id="faa2c-121">While the query uses valid operator, column, function, or table names, there are errors in its structure and resulting logic.</span></span> <span data-ttu-id="faa2c-122">在某些情况下，高级搜寻可标识导致错误的特定运算符。</span><span class="sxs-lookup"><span data-stu-id="faa2c-122">In some cases, advanced hunting identifies the specific operator that caused the error.</span></span> | <span data-ttu-id="faa2c-123">检查查询结构中的错误。</span><span class="sxs-lookup"><span data-stu-id="faa2c-123">Check for errors in the structure of query.</span></span> <span data-ttu-id="faa2c-124">有关指南 [，请参阅 Kusto](/azure/data-explorer/kusto/query/) 文档。</span><span class="sxs-lookup"><span data-stu-id="faa2c-124">Refer to [Kusto documentation](/azure/data-explorer/kusto/query/) for guidance.</span></span> <span data-ttu-id="faa2c-125">编写查询时，请使用来自查询的自动完成IntelliSense。</span><span class="sxs-lookup"><span data-stu-id="faa2c-125">While writing your queries, use the autocomplete suggestions from IntelliSense.</span></span> |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| <span data-ttu-id="faa2c-126">超时</span><span class="sxs-lookup"><span data-stu-id="faa2c-126">Timeouts</span></span> | <span data-ttu-id="faa2c-127">查询只能在超时前的 [有限时段内运行](advanced-hunting-limits.md)。运行复杂查询时，此错误可能更频繁地发生。</span><span class="sxs-lookup"><span data-stu-id="faa2c-127">A query can only run within a [limited period before timing out](advanced-hunting-limits.md). This error can happen more frequently when running complex queries.</span></span> | [<span data-ttu-id="faa2c-128">优化查询</span><span class="sxs-lookup"><span data-stu-id="faa2c-128">Optimize the query</span></span>](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| <span data-ttu-id="faa2c-129">CPU 限制</span><span class="sxs-lookup"><span data-stu-id="faa2c-129">CPU throttling</span></span> | <span data-ttu-id="faa2c-130">同一租户中的查询已超出基于租户大小分配的 [CPU](advanced-hunting-limits.md) 资源。</span><span class="sxs-lookup"><span data-stu-id="faa2c-130">Queries in the same tenant have exceeded the [CPU resources](advanced-hunting-limits.md) that have been allocated based on tenant size.</span></span> | <span data-ttu-id="faa2c-131">该服务每 15 分钟、每天检查一次 CPU 资源使用率，在使用率超过分配的配额的 10% 后显示警告。</span><span class="sxs-lookup"><span data-stu-id="faa2c-131">The service checks CPU resource usage every 15 minutes and daily and displays warnings after usage exceeds 10% of the allocated quota.</span></span> <span data-ttu-id="faa2c-132">如果使用率达到 100%，该服务将阻止查询，直到下一个每日或 15 分钟周期之后。</span><span class="sxs-lookup"><span data-stu-id="faa2c-132">If you reach 100% utilization, the service blocks queries until after the next daily or 15-minute cycle.</span></span> [<span data-ttu-id="faa2c-133">优化查询以避免达到 CPU 配额</span><span class="sxs-lookup"><span data-stu-id="faa2c-133">Optimize your queries to avoid hitting CPU quotas</span></span>](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| <span data-ttu-id="faa2c-134">超过结果大小限制</span><span class="sxs-lookup"><span data-stu-id="faa2c-134">Result size limit exceeded</span></span>  | <span data-ttu-id="faa2c-135">查询的结果集的大小已超出最大大小。</span><span class="sxs-lookup"><span data-stu-id="faa2c-135">The aggregate size of the result set for the query has exceeded the maximum size.</span></span> <span data-ttu-id="faa2c-136">如果数据大小结果集，导致在 10，000 条记录的限制下截断不能减小到可接受的大小，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="faa2c-136">This error can occur if the result set is so large that truncation at the 10,000-record limit can't reduce it to an acceptable size.</span></span> <span data-ttu-id="faa2c-137">具有多个包含可调整内容列的结果更有可能受到此错误的影响。</span><span class="sxs-lookup"><span data-stu-id="faa2c-137">Results that have multiple columns with sizable content are more likely to be impacted by this error.</span></span> | [<span data-ttu-id="faa2c-138">优化查询</span><span class="sxs-lookup"><span data-stu-id="faa2c-138">Optimize the query</span></span>](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| <span data-ttu-id="faa2c-139">资源消耗过多</span><span class="sxs-lookup"><span data-stu-id="faa2c-139">Excessive resource consumption</span></span> | <span data-ttu-id="faa2c-140">查询占用了大量资源，并且已停止完成。</span><span class="sxs-lookup"><span data-stu-id="faa2c-140">The query has consumed excessive amounts of resources and has been stopped from completing.</span></span> <span data-ttu-id="faa2c-141">在某些情况下，高级搜寻可标识未优化的特定运算符。</span><span class="sxs-lookup"><span data-stu-id="faa2c-141">In some cases, advanced hunting identifies the specific operator that wasn't optimized.</span></span> | [<span data-ttu-id="faa2c-142">优化查询</span><span class="sxs-lookup"><span data-stu-id="faa2c-142">Optimize the query</span></span>](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| <span data-ttu-id="faa2c-143">未知错误</span><span class="sxs-lookup"><span data-stu-id="faa2c-143">Unknown errors</span></span> | <span data-ttu-id="faa2c-144">由于未知原因，查询失败。</span><span class="sxs-lookup"><span data-stu-id="faa2c-144">The query failed because of an unknown reason.</span></span> | <span data-ttu-id="faa2c-145">再次尝试运行查询。</span><span class="sxs-lookup"><span data-stu-id="faa2c-145">Try running the query again.</span></span> <span data-ttu-id="faa2c-146">如果查询继续返回未知错误，请通过门户联系 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="faa2c-146">Contact Microsoft through the portal if queries continue to return unknown errors.</span></span> | `An unexpected error occurred during query execution. Please try again in a few minutes.`



## <a name="related-topics"></a><span data-ttu-id="faa2c-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="faa2c-147">Related topics</span></span>
- [<span data-ttu-id="faa2c-148">高级搜寻最佳做法</span><span class="sxs-lookup"><span data-stu-id="faa2c-148">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="faa2c-149">配额和使用参数</span><span class="sxs-lookup"><span data-stu-id="faa2c-149">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="faa2c-150">了解架构</span><span class="sxs-lookup"><span data-stu-id="faa2c-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="faa2c-151">Kusto 查询语言概述</span><span class="sxs-lookup"><span data-stu-id="faa2c-151">Kusto Query Language overview</span></span>](/azure/data-explorer/kusto/query/)