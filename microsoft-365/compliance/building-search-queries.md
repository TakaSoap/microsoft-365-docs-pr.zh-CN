---
title: 在高级电子数据展示中构建搜索查询
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: 在 Microsoft 365 中使用高级电子数据展示搜索数据时，请使用关键字和条件缩小搜索范围。
ms.openlocfilehash: 3ddd9c38f16fc2dd0fcb96e5fffc79ebbacdbda4
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285798"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a><span data-ttu-id="73e14-103">在高级电子数据展示中构建搜索集合查询</span><span class="sxs-lookup"><span data-stu-id="73e14-103">Build search collection queries in Advanced eDiscovery</span></span>

<span data-ttu-id="73e14-104">在生成搜索查询以在高级电子数据展示事例中收集数据时，可以使用关键字查找特定内容和条件，以缩小搜索范围，以返回与法律调查最相关的项目。</span><span class="sxs-lookup"><span data-stu-id="73e14-104">When building search queries to collect data in an Advanced eDiscovery case, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![使用关键字和条件缩小搜索结果范围](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="73e14-106">关键字搜索</span><span class="sxs-lookup"><span data-stu-id="73e14-106">Keyword searches</span></span>

<span data-ttu-id="73e14-107">在搜索查询的 " **关键字** " 框中键入关键字查询。</span><span class="sxs-lookup"><span data-stu-id="73e14-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="73e14-108">您可以指定关键字、电子邮件属性（如发送和接收日期）或文档属性（如文件名或文档的上次更改日期）。</span><span class="sxs-lookup"><span data-stu-id="73e14-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="73e14-109">可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="73e14-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="73e14-110">您还可以搜索敏感信息 (例如，在 SharePoint 和 (OneDrive 中的文档中) 的社会保险号) 的电子邮件中，或搜索在外部共享的文档。</span><span class="sxs-lookup"><span data-stu-id="73e14-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="73e14-111">如果将 " **关键字** " 框留空，则位于指定内容位置的所有内容都将位于搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="73e14-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>
    
<span data-ttu-id="73e14-112">或者，也可以选中 " **显示关键字列表** " 复选框，并在每行中键入关键字或关键字短语。</span><span class="sxs-lookup"><span data-stu-id="73e14-112">Alternatively, you can select the **Show keyword list** check box and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="73e14-113">如果执行此操作，则每行中的关键字都通过逻辑运算符连接 (该运算符表示为搜索查询语法) 中的 *c:s* ，该运算符在所创建的搜索查询中的 **OR** 运算符的功能类似。</span><span class="sxs-lookup"><span data-stu-id="73e14-113">If you do this, the keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="73e14-114">这意味着搜索结果中包含任意行中包含任意关键字的项。</span><span class="sxs-lookup"><span data-stu-id="73e14-114">This means items that contain any keyword in any row are in the search results.</span></span>

![使用关键字列表获取查询中每个关键字的统计信息](../media/KeywordListSearch.png)

<span data-ttu-id="73e14-116">为什么使用关键字列表？</span><span class="sxs-lookup"><span data-stu-id="73e14-116">Why use the keyword list?</span></span> <span data-ttu-id="73e14-117">您可以获取统计信息，以显示与关键字列表中的每个关键字匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="73e14-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="73e14-118">这可以帮助您快速找出最 (和最不) 有效的关键字。</span><span class="sxs-lookup"><span data-stu-id="73e14-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="73e14-119">您还可以使用关键字短语 () 关键字列表中行中的括号括起的关键字短语。</span><span class="sxs-lookup"><span data-stu-id="73e14-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="73e14-120">有关搜索统计信息的详细信息，请参阅 [搜索统计](search-statistics.md)信息。</span><span class="sxs-lookup"><span data-stu-id="73e14-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="73e14-121">为了帮助减少由大型关键字列表导致的问题，在关键字列表中限制为最多20行。</span><span class="sxs-lookup"><span data-stu-id="73e14-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="73e14-122">条件</span><span class="sxs-lookup"><span data-stu-id="73e14-122">Conditions</span></span>
    
<span data-ttu-id="73e14-123">您可以添加搜索条件以缩小搜索范围，并返回更精致的结果集。</span><span class="sxs-lookup"><span data-stu-id="73e14-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="73e14-124">每个条件向开始搜索时创建和运行的搜索查询添加一个子句。</span><span class="sxs-lookup"><span data-stu-id="73e14-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="73e14-125">条件以逻辑方式连接到关键字框中指定的关键字查询，逻辑运算符 (它表示为与**AND**运算符功能类似的搜索查询语法) 中的*c:c* 。</span><span class="sxs-lookup"><span data-stu-id="73e14-125">A condition is logically connected to the keyword query specified in the keyword box by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="73e14-126">这意味着项目必须同时满足关键字查询和要包含在搜索结果中的一个或多个条件。</span><span class="sxs-lookup"><span data-stu-id="73e14-126">That means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="73e14-127">这就是条件如何帮助缩小结果范围的原理。</span><span class="sxs-lookup"><span data-stu-id="73e14-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="73e14-128">有关可在搜索查询中使用的条件的列表和说明，请参阅 [关键字查询和搜索条件](keyword-queries-and-search-conditions.md#search-conditions)中的 "搜索条件" 部分。</span><span class="sxs-lookup"><span data-stu-id="73e14-128">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
