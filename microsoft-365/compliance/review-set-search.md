---
title: 查询审阅集中的数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在审阅集内创建和运行查询，以组织数据，以在Advanced eDiscovery审阅。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345796"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="9b3af-103">查询审阅集中的数据</span><span class="sxs-lookup"><span data-stu-id="9b3af-103">Query the data in a review set</span></span>

<span data-ttu-id="9b3af-104">在大多数情况下，能够深入了解审阅集内的数据并组织该数据以促进更高效的审阅将非常有用。</span><span class="sxs-lookup"><span data-stu-id="9b3af-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="9b3af-105">在审阅集中使用查询可帮助您重点关注满足审阅条件的文档的子集。</span><span class="sxs-lookup"><span data-stu-id="9b3af-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="9b3af-106">在审阅集内创建和运行查询</span><span class="sxs-lookup"><span data-stu-id="9b3af-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="9b3af-107">若要创建并运行对审阅集内文档的查询，请选择审阅 **集** 内的新查询。</span><span class="sxs-lookup"><span data-stu-id="9b3af-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="9b3af-108">命名查询并定义条件后，选择" **保存** "保存并运行查询。</span><span class="sxs-lookup"><span data-stu-id="9b3af-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="9b3af-109">若要运行以前保存的查询，请选择已保存的查询。</span><span class="sxs-lookup"><span data-stu-id="9b3af-109">To run a query that has been previously saved, select a saved query.</span></span>

![查看集查询](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="9b3af-111">生成审阅集查询</span><span class="sxs-lookup"><span data-stu-id="9b3af-111">Building a review set query</span></span>

<span data-ttu-id="9b3af-112">您可以使用关键字、属性和条件组合在"关键字"条件中生成查询。</span><span class="sxs-lookup"><span data-stu-id="9b3af-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="9b3af-113">还可以将条件分组为一个 (一个称为条件) 构建更复杂的查询的块。</span><span class="sxs-lookup"><span data-stu-id="9b3af-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="9b3af-114">有关可以搜索的元数据属性的列表和说明，请参阅 [高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="9b3af-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="9b3af-115">条件</span><span class="sxs-lookup"><span data-stu-id="9b3af-115">Conditions</span></span>

<span data-ttu-id="9b3af-116">审阅集内每个可搜索字段都有一个可用于生成查询的相应条件。</span><span class="sxs-lookup"><span data-stu-id="9b3af-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="9b3af-117">存在多种类型的条件：</span><span class="sxs-lookup"><span data-stu-id="9b3af-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="9b3af-118">Freetext：自由文本条件用于文本字段，如主题。</span><span class="sxs-lookup"><span data-stu-id="9b3af-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="9b3af-119">可以通过用逗号分隔出多个搜索词来列出这些搜索词。</span><span class="sxs-lookup"><span data-stu-id="9b3af-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="9b3af-120">Date：日期条件用于日期字段，如上次修改日期。</span><span class="sxs-lookup"><span data-stu-id="9b3af-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="9b3af-121">搜索选项：搜索选项条件将提供审阅集内特定字段的可能值列表。</span><span class="sxs-lookup"><span data-stu-id="9b3af-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="9b3af-122">这用于审阅集可能值有限数量的字段（如发件人）。</span><span class="sxs-lookup"><span data-stu-id="9b3af-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="9b3af-123">关键字：关键字条件是可用于搜索词或使用 KQL 类似查询语言的 freetext 条件的特定实例。</span><span class="sxs-lookup"><span data-stu-id="9b3af-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="9b3af-124">有关详细信息，请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="9b3af-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="9b3af-125">查询语言</span><span class="sxs-lookup"><span data-stu-id="9b3af-125">Query language</span></span>

<span data-ttu-id="9b3af-126">除了条件之外，您还可以在"关键字"条件中使用类似 KQL 的查询语言来构建查询。</span><span class="sxs-lookup"><span data-stu-id="9b3af-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="9b3af-127">审阅集查询的查询语言支持标准布尔运算符，如AND、OR、NOT和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="9b3af-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="9b3af-128">它还支持单字符通配符 (？) 和多字符通配符 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="9b3af-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="9b3af-129">筛选器</span><span class="sxs-lookup"><span data-stu-id="9b3af-129">Filters</span></span>

<span data-ttu-id="9b3af-130">除了可以保存的查询之外，您还可以使用审阅集筛选器将其他条件快速应用于审阅集查询。</span><span class="sxs-lookup"><span data-stu-id="9b3af-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="9b3af-131">使用筛选器可帮助您进一步优化审阅集查询显示的结果。</span><span class="sxs-lookup"><span data-stu-id="9b3af-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![审阅集筛选器](../media/AeDReviewSetFilters.png)

<span data-ttu-id="9b3af-133">筛选器与查询有两种显著区别：</span><span class="sxs-lookup"><span data-stu-id="9b3af-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="9b3af-134">筛选器是暂时性的。</span><span class="sxs-lookup"><span data-stu-id="9b3af-134">Filters are transient.</span></span> <span data-ttu-id="9b3af-135">它们不会延续到现有会话之外。</span><span class="sxs-lookup"><span data-stu-id="9b3af-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="9b3af-136">换句话说，无法保存筛选器。</span><span class="sxs-lookup"><span data-stu-id="9b3af-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="9b3af-137">查询将保存到审阅集，并且只要打开审阅集，就会访问查询。</span><span class="sxs-lookup"><span data-stu-id="9b3af-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="9b3af-138">筛选器始终是累加的。</span><span class="sxs-lookup"><span data-stu-id="9b3af-138">Filters are always additive.</span></span> <span data-ttu-id="9b3af-139">除当前审阅集查询外，还应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="9b3af-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="9b3af-140">应用其他查询将替换当前查询返回的结果。</span><span class="sxs-lookup"><span data-stu-id="9b3af-140">Applying a different query will replace the results returned by the current query.</span></span>
