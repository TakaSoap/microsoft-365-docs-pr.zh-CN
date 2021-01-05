---
title: 在高级电子数据展示中生成搜索查询
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
description: 在 Microsoft 365 中使用高级电子数据展示搜索数据时，使用关键字和条件缩小搜索范围。
ms.openlocfilehash: 8ec1e099625bb081f8a915f08ac818fddcc2b60d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751109"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a><span data-ttu-id="0e0d0-103">在高级电子数据展示中生成搜索集合查询</span><span class="sxs-lookup"><span data-stu-id="0e0d0-103">Build search collection queries in Advanced eDiscovery</span></span>

<span data-ttu-id="0e0d0-104">构建搜索查询以收集高级电子数据展示案例中的数据时，可以使用关键字查找特定内容和条件，以缩小搜索范围以返回与法律调查最相关的项目。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-104">When building search queries to collect data in an Advanced eDiscovery case, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![使用关键字和条件缩小搜索结果范围](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="0e0d0-106">关键字搜索</span><span class="sxs-lookup"><span data-stu-id="0e0d0-106">Keyword searches</span></span>

<span data-ttu-id="0e0d0-107">在搜索查询的 **"关键字"** 框中键入关键字查询。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="0e0d0-108">可以指定关键字、电子邮件属性（如发送日期和接收日期）或文档属性（如文件名或上次更改文档的日期）。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="0e0d0-109">可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="0e0d0-110">您还可以在 SharePoint 和 OneDrive (中的文档中搜索敏感信息（如社会安全号码) ，而不是电子邮件 (中的) ）或搜索在外部共享的文档。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="0e0d0-111">如果将" **关键字"框** 留空，则位于指定内容位置的所有内容都位于搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>

## <a name="keyword-list"></a><span data-ttu-id="0e0d0-112">关键字列表</span><span class="sxs-lookup"><span data-stu-id="0e0d0-112">Keyword list</span></span>

<span data-ttu-id="0e0d0-113">或者，也可以选中"显示关键字 **列表** "复选框，并在每行中键入关键字或关键字短语。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-113">Alternatively, you can select the **Show keyword list** check box and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="0e0d0-114">每行中的关键字由逻辑运算符 (在搜索查询语法) 中表示为 *c：s，* 其功能类似于所创建的搜索查询中的 **OR** 运算符。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-114">The keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="0e0d0-115">这意味着任何行中包含任何关键字的项均在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-115">This means items that contain any keyword in any row are in the search results.</span></span> <span data-ttu-id="0e0d0-116">您可以在高级电子数据展示搜索查询的关键字列表中最多添加 180 行。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-116">You can add up to 180 rows in the keyword list in Advanced eDiscovery search queries.</span></span>

![使用关键字列表获取查询中每个关键字的统计信息](../media/KeywordListSearch.png)

<span data-ttu-id="0e0d0-118">为什么使用关键字列表？</span><span class="sxs-lookup"><span data-stu-id="0e0d0-118">Why use the keyword list?</span></span> <span data-ttu-id="0e0d0-119">您可以获取显示关键字列表中每个关键字匹配的项数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-119">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="0e0d0-120">这可以帮助您快速识别最有效且最 (最) 关键字。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-120">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="0e0d0-121">您还可以使用关键字短语 (关键字) 列表中的行中的括号。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-121">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="0e0d0-122">有关搜索统计信息详细信息，请参阅 [搜索统计信息](search-statistics-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-122">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="0e0d0-123">条件</span><span class="sxs-lookup"><span data-stu-id="0e0d0-123">Conditions</span></span>

<span data-ttu-id="0e0d0-124">您可以添加搜索条件以缩小搜索范围并返回更精确的结果集。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-124">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="0e0d0-125">每个条件向开始搜索时创建和运行的搜索查询添加一个子句。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-125">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="0e0d0-126">条件在逻辑上由逻辑运算符 (在搜索查询语法中表示为 *c：) c（* 在功能上与 **AND** 运算符类似）连接到关键字框中指定的关键字查询。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-126">A condition is logically connected to the keyword query specified in the keyword box by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="0e0d0-127">这意味着项目必须满足关键字查询和要包括在搜索结果中的一个或多个条件。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-127">That means items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="0e0d0-128">这就是条件如何帮助缩小结果范围的原理。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-128">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="0e0d0-129">有关可在搜索查询中使用的条件的列表和说明，请参阅关键字查询和搜索条件中的"搜索 [条件"部分](keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="0e0d0-129">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
