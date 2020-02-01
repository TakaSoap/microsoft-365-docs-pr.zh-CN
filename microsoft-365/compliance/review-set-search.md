---
title: 查询审阅集中的数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 4005b1e379b138f4eb22bb5c11e1f278185dc65e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597609"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="dfb2f-102">查询审阅集中的数据</span><span class="sxs-lookup"><span data-stu-id="dfb2f-102">Query the data in a review set</span></span>

<span data-ttu-id="dfb2f-103">在大多数情况下，能够深入查看评审集中的数据并整理这些数据以促进更高效的审阅，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-103">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="dfb2f-104">在审阅集中使用查询可帮助您将重点放在符合评审条件的文档子集上。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-104">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="dfb2f-105">在审阅集中创建和运行查询</span><span class="sxs-lookup"><span data-stu-id="dfb2f-105">Creating and running a query in a review set</span></span>

<span data-ttu-id="dfb2f-106">若要在审阅集中对文档创建和运行查询，请单击 "审阅集" 中的 "**新建查询**"。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-106">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="dfb2f-107">命名查询并定义条件后，单击 "**保存**" 以保存并运行查询。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-107">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="dfb2f-108">若要运行以前保存的查询，请单击已保存的查询。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-108">To run a query that has been previously saved, click a saved query.</span></span>

![查看集查询](media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="dfb2f-110">生成审阅集查询</span><span class="sxs-lookup"><span data-stu-id="dfb2f-110">Building a review set query</span></span>

<span data-ttu-id="dfb2f-111">可以在关键字条件卡中使用条件卡片和查询语言的组合来构建查询。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-111">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="dfb2f-112">您还可以将条件卡组合成一个块（称为 "*条件组*"），以生成更复杂的查询。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-112">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="dfb2f-113">有关可以搜索的元数据属性的列表和说明，请参阅[高级电子数据展示中的文档元数据字段](document-metadata-fields-in-Advanced-eDiscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-113">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="dfb2f-114">条件卡片</span><span class="sxs-lookup"><span data-stu-id="dfb2f-114">Condition cards</span></span>

<span data-ttu-id="dfb2f-115">审阅集中的每个可搜索字段都有一个对应的条件卡，可用于生成查询。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-115">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="dfb2f-116">有多种类型的条件卡：</span><span class="sxs-lookup"><span data-stu-id="dfb2f-116">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="dfb2f-117">Freetext： freetext 条件卡用于文本字段，如 subject。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-117">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="dfb2f-118">您可以通过用逗号分隔多个搜索词来列出它们。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-118">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="dfb2f-119">日期：日期条件卡片用于日期字段（如 "上次修改日期"）。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-119">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="dfb2f-120">搜索选项：搜索选项条件卡片将为您的审阅集中的特定字段提供可能的值列表。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-120">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="dfb2f-121">这用于在您的审核集中有有限数量的可能值的字段，如发件人。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-121">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="dfb2f-122">关键字：关键字条件卡是 freetext 条件卡的特定实例，可用于搜索术语，或在中使用类似 KQL 的查询语言。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-122">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="dfb2f-123">有关更多详细信息，请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-123">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="dfb2f-124">查询语言</span><span class="sxs-lookup"><span data-stu-id="dfb2f-124">Query language</span></span>

<span data-ttu-id="dfb2f-125">除了条件卡片之外，还可以在关键字卡片中使用类似 KQL 的查询语言来生成查询。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-125">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="dfb2f-126">评审 set 查询的查询语言支持标准布尔运算符，例如**AND**、 **OR**、 **NOT**和**NEAR**。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-126">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="dfb2f-127">它还支持单字符通配符（？）和多字符通配符（\*）。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-127">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="dfb2f-128">使用筛选器</span><span class="sxs-lookup"><span data-stu-id="dfb2f-128">Using filters</span></span>

<span data-ttu-id="dfb2f-129">除了可以保存的查询之外，还可以使用审阅设置筛选器将其他条件快速应用于审阅集查询。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-129">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="dfb2f-130">这可帮助您进一步优化由审阅集查询显示的结果。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-130">This helps you further refine the results displayed by a review set query.</span></span>

![查看设置筛选器](media/AeDReviewSetFilters.png)

<span data-ttu-id="dfb2f-132">筛选器与查询的区别在于以下两个重要方式：</span><span class="sxs-lookup"><span data-stu-id="dfb2f-132">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="dfb2f-133">筛选器是瞬态的。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-133">Filters are transient.</span></span> <span data-ttu-id="dfb2f-134">它们不会保留在现有会话之外。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-134">They don't persist beyond the existing session.</span></span> <span data-ttu-id="dfb2f-135">换言之，不能保存筛选器。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-135">In other words, you can't save a filter.</span></span> <span data-ttu-id="dfb2f-136">查询保存到审阅集，并在打开评审集时访问它们。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-136">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="dfb2f-137">筛选器始终是累加的。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-137">Filters are always additive.</span></span> <span data-ttu-id="dfb2f-138">除了当前的审阅集查询之外，还将应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-138">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="dfb2f-139">应用不同的查询将替换当前查询返回的结果。</span><span class="sxs-lookup"><span data-stu-id="dfb2f-139">Applying a different query will replace the results returned by the current query.</span></span>
