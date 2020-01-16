---
title: Microsoft 威胁防护中的高级搜寻概述
description: 了解 Microsoft 365 中的高级搜寻查询以及如何使用它们来主动查找网络中的威胁和弱点
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、架构、kusto、microsoft 365、Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 791eee143c80e00a3fdb1fa4dbde8bbf41612e9a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210347"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="817e4-104">通过 Microsoft 威胁防护中的高级搜寻主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="817e4-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="817e4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="817e4-105">**Applies to:**</span></span>
- <span data-ttu-id="817e4-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="817e4-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="817e4-107">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="817e4-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="817e4-108">你可以主动检查网络中的事件来找到感兴趣的指示器和实体。</span><span class="sxs-lookup"><span data-stu-id="817e4-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="817e4-109">灵活访问数据有助于无约束搜寻已知威胁和潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="817e4-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="817e4-110">在 Microsoft 365 安全中心中，高级搜索支持从 Microsoft Defender ATP 中查看数据的查询，其中包含来自载入设备的数据和 Office 365 ATP，从而提供来自电子邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="817e4-110">In the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="817e4-111">若要使用高级搜寻，请[打开 Microsoft 威胁防护](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="817e4-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="817e4-112">高级搜寻入门</span><span class="sxs-lookup"><span data-stu-id="817e4-112">Get started with advanced hunting</span></span>

<span data-ttu-id="817e4-113">我们建议执行几个步骤来通过高级搜寻快速启动并运行。</span><span class="sxs-lookup"><span data-stu-id="817e4-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="817e4-114">学习目标</span><span class="sxs-lookup"><span data-stu-id="817e4-114">Learning goal</span></span> | <span data-ttu-id="817e4-115">说明</span><span class="sxs-lookup"><span data-stu-id="817e4-115">Description</span></span> | <span data-ttu-id="817e4-116">资源</span><span class="sxs-lookup"><span data-stu-id="817e4-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="817e4-117">**了解语言**</span><span class="sxs-lookup"><span data-stu-id="817e4-117">**Get a feel for the language**</span></span> | <span data-ttu-id="817e4-118">高级搜寻基于 [Kusto 查询语言](https://docs.microsoft.com/azure/kusto/query/)，支持相同的语法和运算符。</span><span class="sxs-lookup"><span data-stu-id="817e4-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="817e4-119">通过运行第一个查询开始学习查询语言。</span><span class="sxs-lookup"><span data-stu-id="817e4-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="817e4-120">查询语言概述</span><span class="sxs-lookup"><span data-stu-id="817e4-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="817e4-121">**了解架构**</span><span class="sxs-lookup"><span data-stu-id="817e4-121">**Understand the schema**</span></span> | <span data-ttu-id="817e4-122">更好地大致了解架构及其列中的表。</span><span class="sxs-lookup"><span data-stu-id="817e4-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="817e4-123">这将帮助你确定在何处查找数据以及如何构建查询。</span><span class="sxs-lookup"><span data-stu-id="817e4-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="817e4-124">架构参考</span><span class="sxs-lookup"><span data-stu-id="817e4-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="817e4-125">**使用预定义查询**</span><span class="sxs-lookup"><span data-stu-id="817e4-125">**Use predefined queries**</span></span> | <span data-ttu-id="817e4-126">浏览涵盖不同威胁搜寻方案的预定义查询集合。</span><span class="sxs-lookup"><span data-stu-id="817e4-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="817e4-127">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="817e4-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="817e4-128">**优化查询**</span><span class="sxs-lookup"><span data-stu-id="817e4-128">**Optimize queries**</span></span> | <span data-ttu-id="817e4-129">了解如何创建高效查询以及组合电子邮件和设备中的数据的查询。</span><span class="sxs-lookup"><span data-stu-id="817e4-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="817e4-130">[查询最佳做法](advanced-hunting-shared-queries.md)，[跨设备和电子邮件搜寻](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="817e4-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="817e4-131">编写查询时获取帮助</span><span class="sxs-lookup"><span data-stu-id="817e4-131">Get help as you write queries</span></span>
<span data-ttu-id="817e4-132">利用以下功能更快地编写查询：</span><span class="sxs-lookup"><span data-stu-id="817e4-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="817e4-133">**自动建议** — 编写查询时，高级搜寻会提供建议。</span><span class="sxs-lookup"><span data-stu-id="817e4-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="817e4-134">**架构参考** — 工作区域旁边提供了包含表及其列的列表的架构参考。</span><span class="sxs-lookup"><span data-stu-id="817e4-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="817e4-135">有关详细信息，请将鼠标悬停在某个项上。</span><span class="sxs-lookup"><span data-stu-id="817e4-135">For more information, hover over an item.</span></span> <span data-ttu-id="817e4-136">双击某个项，将其插入到查询编辑器中。</span><span class="sxs-lookup"><span data-stu-id="817e4-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="817e4-137">查询结果中的明细</span><span class="sxs-lookup"><span data-stu-id="817e4-137">Drilldown from query results</span></span>
<span data-ttu-id="817e4-138">若要查看有关查询结果中的实体（如计算机、文件、用户、IP 地址和 URL）的详细信息，只需单击实体标识符。</span><span class="sxs-lookup"><span data-stu-id="817e4-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="817e4-139">这将为 Microsoft Defender 安全中心中的所选实体打开详细的配置文件页。</span><span class="sxs-lookup"><span data-stu-id="817e4-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="817e4-140">调整结果中的查询</span><span class="sxs-lookup"><span data-stu-id="817e4-140">Tweak your queries from the results</span></span>
<span data-ttu-id="817e4-141">右键单击结果集中的值以快速增强查询。</span><span class="sxs-lookup"><span data-stu-id="817e4-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="817e4-142">可以使用这些选项执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="817e4-142">You can use the options to:</span></span>

- <span data-ttu-id="817e4-143">显式查找选定值 (`==`)</span><span class="sxs-lookup"><span data-stu-id="817e4-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="817e4-144">从查询中排除选定值 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="817e4-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="817e4-145">获取用于将值添加到查询的更高级运算符，如 `contains`、`starts with` 和 `ends with`</span><span class="sxs-lookup"><span data-stu-id="817e4-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Microsoft Defender ATP 高级搜寻结果集的图像](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="817e4-147">筛选查询结果</span><span class="sxs-lookup"><span data-stu-id="817e4-147">Filter the query results</span></span>
<span data-ttu-id="817e4-148">右侧显示的筛选器提供结果集的摘要。</span><span class="sxs-lookup"><span data-stu-id="817e4-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="817e4-149">每列都有其自己的部分，其中列出了该列找到的非重复值和实例数。</span><span class="sxs-lookup"><span data-stu-id="817e4-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="817e4-150">选择要包括或排除的值上的“+”或“-”按钮，然后选择“运行查询”\*\*\*\* 来优化查询。</span><span class="sxs-lookup"><span data-stu-id="817e4-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![高级搜寻筛选器的图像](../images/advanced-hunting-filter.png)

<span data-ttu-id="817e4-152">应用筛选器以修改查询并运行查询后，将相应更新结果。</span><span class="sxs-lookup"><span data-stu-id="817e4-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="817e4-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="817e4-153">Related topics</span></span>
- [<span data-ttu-id="817e4-154">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="817e4-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="817e4-155">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="817e4-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="817e4-156">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="817e4-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="817e4-157">了解架构</span><span class="sxs-lookup"><span data-stu-id="817e4-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="817e4-158">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="817e4-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)