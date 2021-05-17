---
title: CJK/Double Byte 对 Advanced eDiscovery
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
description: Learn how Advanced eDiscovery in Microsoft 365 supports Chinese， Japanese， and Korean (CJK) languages， which use a double-byte character set.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926598"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="6b64b-103">CJK 语言支持Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6b64b-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="6b64b-104">Advanced eDiscovery支持双字节字符集语言 (包括简体中文、繁体中文、日语和朝鲜语，这些语言统称为 *CJK* 语言) ，用于审阅集的以下高级方案：</span><span class="sxs-lookup"><span data-stu-id="6b64b-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="6b64b-105">查询 [审阅集 内的数据时](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="6b64b-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="6b64b-106">在审阅 [集 内标记文档时](tagging-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="6b64b-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="6b64b-107">当你 [使用近重复检测、](analyzing-data-in-review-set.md) 电子邮件线程和主题分析来分析审阅集内的情况数据时。</span><span class="sxs-lookup"><span data-stu-id="6b64b-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6b64b-108">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6b64b-108">Frequently asked questions</span></span>

<span data-ttu-id="6b64b-109">**如何创建搜索以收集包含 CJK 字符的项目？**</span><span class="sxs-lookup"><span data-stu-id="6b64b-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="6b64b-110">在搜索关键字搜索中的内容时，[](building-search-queries.md#keyword-searches)可以将 CJK 字符用于关键字搜索、关键字查询和Advanced eDiscovery。 [](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="6b64b-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="6b64b-111">在核心电子数据展示和内容搜索中搜索内容时，也支持搜索 CJK 字符。</span><span class="sxs-lookup"><span data-stu-id="6b64b-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="6b64b-112">我们针对所有搜索运算符和搜索条件 [](keyword-queries-and-search-conditions.md#search-operators)（包括布尔 [](keyword-queries-and-search-conditions.md#search-conditions)运算符 **AND** **、OR、NOT** 和 **NEAR）** 提供 CJK 支持。 </span><span class="sxs-lookup"><span data-stu-id="6b64b-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="6b64b-113">如果您确定内容位置或项目包含 CJK 字符，但搜索不会返回任何结果，请单击查询语言-国家/地区图标</span><span class="sxs-lookup"><span data-stu-id="6b64b-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![内容搜索中的查询语言国家/地区图标](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="6b64b-115">并选择相应的语言国家/地区区域性代码值进行搜索。</span><span class="sxs-lookup"><span data-stu-id="6b64b-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="6b64b-116">默认语言/区域是中性的。</span><span class="sxs-lookup"><span data-stu-id="6b64b-116">The default language/region is neutral.</span></span>

<span data-ttu-id="6b64b-117">**能否同时搜索多种语言？**</span><span class="sxs-lookup"><span data-stu-id="6b64b-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="6b64b-118">这取决于你的搜索方案。</span><span class="sxs-lookup"><span data-stu-id="6b64b-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="6b64b-119">在[查询评价集](review-set-search.md)内的数据时Advanced eDiscovery，可以搜索多种语言。</span><span class="sxs-lookup"><span data-stu-id="6b64b-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="6b64b-120">创建 [搜索以收集数据时](create-search-to-collect-data.md)，请为所面向的每种语言创建单独的搜索。</span><span class="sxs-lookup"><span data-stu-id="6b64b-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="6b64b-121">例如，如果要搜索同时包含中文和朝鲜语的文档，请选择"中文"作为第一个查询，并选择"朝鲜语"作为第二个查询。</span><span class="sxs-lookup"><span data-stu-id="6b64b-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="6b64b-122">**我看不到查询语言-国家/地区图标来选择审阅集内查询的语言。如何在审阅集搜索中指定查询语言？**</span><span class="sxs-lookup"><span data-stu-id="6b64b-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="6b64b-123">对于审阅集查询，无需指定文档语言。</span><span class="sxs-lookup"><span data-stu-id="6b64b-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="6b64b-124">Advanced eDiscovery内容添加到审阅集时自动检测文档语言。</span><span class="sxs-lookup"><span data-stu-id="6b64b-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="6b64b-125">这有助于在审阅集内优化查询结果。</span><span class="sxs-lookup"><span data-stu-id="6b64b-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="6b64b-126">**能否在文件元数据中查看 [检测到的语言](view-documents-in-review-set.md#file-metadata)？**</span><span class="sxs-lookup"><span data-stu-id="6b64b-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="6b64b-127">否，在文件元数据中看不到检测到的语言。</span><span class="sxs-lookup"><span data-stu-id="6b64b-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="6b64b-128">**我能否在审阅集内按文档语言进行筛选**？</span><span class="sxs-lookup"><span data-stu-id="6b64b-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="6b64b-129">否，不能按审阅集内的文档语言进行筛选、排序或搜索。</span><span class="sxs-lookup"><span data-stu-id="6b64b-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="6b64b-130">**此 CJK 版本用于审阅集方案是否会影响我的任何现有搜索和审阅集？**</span><span class="sxs-lookup"><span data-stu-id="6b64b-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="6b64b-131">否，现有的搜索和审阅集不会更改。</span><span class="sxs-lookup"><span data-stu-id="6b64b-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="6b64b-132">无需对现有数据重新索引，英文文本的搜索结果将相同。</span><span class="sxs-lookup"><span data-stu-id="6b64b-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="6b64b-133">**如何将显示语言更改为中文、日语或朝鲜语？**</span><span class="sxs-lookup"><span data-stu-id="6b64b-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="6b64b-134">若要了解如何更改显示语言和时区，请参阅如何为用户设置语言和[Office 365。](/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="6b64b-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="6b64b-135">已知问题</span><span class="sxs-lookup"><span data-stu-id="6b64b-135">Known issues</span></span>

- <span data-ttu-id="6b64b-136">OCR 不支持图像文件的 CJK 字符</span><span class="sxs-lookup"><span data-stu-id="6b64b-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="6b64b-137">CJK (不支持批注视图中) \*.eml 和 \*.msg[](view-documents-in-review-set.md#annotate-view)等电子邮件文件。</span><span class="sxs-lookup"><span data-stu-id="6b64b-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="6b64b-138">CJK 语言不支持 [在](view-documents-in-review-set.md#text-view) 文本视图中突出显示搜索词。</span><span class="sxs-lookup"><span data-stu-id="6b64b-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="6b64b-139">[用于分析数据](using-relevance.md)的相关性模块不支持 CJK 语言。</span><span class="sxs-lookup"><span data-stu-id="6b64b-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="6b64b-140">[CJK](managing-holds.md#manage-non-custodial-holds) 语言不支持基于查询的保留。</span><span class="sxs-lookup"><span data-stu-id="6b64b-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>