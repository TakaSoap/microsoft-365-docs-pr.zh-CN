---
title: 针对高级电子数据展示的 CJK/双字节支持
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解 Microsoft 365 中的高级电子数据展示如何支持中文、日语和朝鲜语 (CJK) 语言，这些语言使用双字节字符集。
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626930"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="b5cd8-103">适用于高级电子数据展示的 CJK 语言支持</span><span class="sxs-lookup"><span data-stu-id="b5cd8-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="b5cd8-104">高级电子数据展示支持双字节字符集语言 (这些语言包括简体中文、繁体中文、日语和朝鲜语，在审阅集中统称为以下高级方案的 *CJK* 语言) ：</span><span class="sxs-lookup"><span data-stu-id="b5cd8-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="b5cd8-105">[查询评审集中的数据](review-set-search.md)时。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="b5cd8-106">在 [审阅集中标记文档](tagging-documents.md)时。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="b5cd8-107">通过使用接近重复检测、电子邮件线程和主题分析来 [分析评审集合中的事例数据](analyzing-data-in-review-set.md) 时。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b5cd8-108">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="b5cd8-108">Frequently asked questions</span></span>

<span data-ttu-id="b5cd8-109">**如何创建搜索以收集包含 CJK 字符的项目？**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="b5cd8-110">在高级电子数据展示中搜索内容时，可以使用 CJK 字符进行 [关键字搜索](building-search-queries.md#keyword-searches)、 [关键字查询和搜索条件](keyword-queries-and-search-conditions.md) 。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="b5cd8-111">搜索核心电子数据展示和内容搜索中的内容时，也支持搜索 CJK 字符。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="b5cd8-112">我们为所有 [搜索运算符](keyword-queries-and-search-conditions.md#search-operators) 和 [搜索条件](keyword-queries-and-search-conditions.md#search-conditions)（包括布尔运算符 **and**、 **OR**、 **NOT**和 **NEAR**）提供 CJK 支持。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="b5cd8-113">如果你确信内容位置或项目包含 CJK 字符，但搜索不返回任何结果，请单击 "查询语言-国家/地区" 图标</span><span class="sxs-lookup"><span data-stu-id="b5cd8-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![查询语言-内容搜索中的国家/地区图标](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="b5cd8-115">并为搜索选择对应的语言国家区域性代码值。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="b5cd8-116">默认语言/区域是中性的。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-116">The default language/region is neutral.</span></span>

<span data-ttu-id="b5cd8-117">**是否可以一次搜索多个语言？**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="b5cd8-118">这取决于您的搜索方案。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="b5cd8-119">当您在高级电子数据展示中 [查询审阅集中的数据](review-set-search.md) 时，您可以搜索多种语言。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="b5cd8-120">[创建用于收集数据的搜索](create-search-to-collect-data.md)时，请为目标的每种语言创建单独的搜索。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="b5cd8-121">例如，如果要搜索同时包含中文和朝鲜语的文档，请选择 "中文" 作为第一个查询，然后选择 "朝鲜语" 作为第二个查询。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="b5cd8-122">**我看不到查询语言-国家/地区图标在审阅集中选择查询的语言。如何在审阅集搜索中指定查询语言？**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="b5cd8-123">对于审阅集查询，无需指定文档语言。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="b5cd8-124">将内容添加到审阅集时，高级电子数据展示将自动检测文档语言。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="b5cd8-125">这有助于优化评审集中的查询结果。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="b5cd8-126">**是否可以查看 [文件元数据](view-documents-in-review-set.md#file-metadata)中检测到的语言？**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="b5cd8-127">否，在文件元数据中看不到检测到的语言。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="b5cd8-128">**能否按文档语言在审阅集中进行筛选**？</span><span class="sxs-lookup"><span data-stu-id="b5cd8-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="b5cd8-129">否，不能在审阅集中对文档语言进行筛选、排序或搜索。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="b5cd8-130">**此 CJK 发布的检查集方案是否会影响我现有的搜索和审阅集？**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="b5cd8-131">否，现有搜索和审阅集都不会更改。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="b5cd8-132">您无需对现有数据重新编制索引，英语文本的搜索结果也将相同。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="b5cd8-133">**如何将我的显示语言更改为中文、日语或朝鲜语？**</span><span class="sxs-lookup"><span data-stu-id="b5cd8-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="b5cd8-134">有关如何更改显示语言和时区的信息，请参阅 [如何设置 Office 365 的语言和区域设置](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="b5cd8-135">已知问题</span><span class="sxs-lookup"><span data-stu-id="b5cd8-135">Known issues</span></span>

- <span data-ttu-id="b5cd8-136">OCR 不支持从图像文件中 CJK 字符</span><span class="sxs-lookup"><span data-stu-id="b5cd8-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="b5cd8-137">CJK 语言不支持电子邮件文件 (例如，\* .eml 和 \* .msg) 中的 [批注视图](view-documents-in-review-set.md#annotate-view) 。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="b5cd8-138">CJK 语言不支持 [文本视图](view-documents-in-review-set.md#text-view) 中的搜索词突出显示。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="b5cd8-139">用于分析数据的 [相关性模块](using-relevance.md) 不支持 CJK 语言。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="b5cd8-140">CJK 语言不支持[基于查询的保留](managing-holds.md#manage-non-custodial-holds)。</span><span class="sxs-lookup"><span data-stu-id="b5cd8-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
