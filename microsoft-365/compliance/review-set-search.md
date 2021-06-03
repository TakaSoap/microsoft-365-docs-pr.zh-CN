---
title: 查询审阅集内的内容
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
description: 了解如何在审阅集内创建和运行查询，以组织内容，以在Advanced eDiscovery审阅。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736390"
---
# <a name="query-and-filter-content-in-a-review-set"></a><span data-ttu-id="2a20a-103">查询和筛选审阅集内的内容</span><span class="sxs-lookup"><span data-stu-id="2a20a-103">Query and filter content in a review set</span></span>

<span data-ttu-id="2a20a-104">在大多数情况下，深入探究审阅集内的内容并组织该内容以促进更高效的审阅将非常有用。</span><span class="sxs-lookup"><span data-stu-id="2a20a-104">In most cases, it will be useful to dig deeper into the content in a review set and organize it to facilitate a more efficient review.</span></span> <span data-ttu-id="2a20a-105">在审阅集中使用筛选器和查询可帮助您重点关注满足审阅条件的文档的子集。</span><span class="sxs-lookup"><span data-stu-id="2a20a-105">Using filters and queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="default-filters"></a><span data-ttu-id="2a20a-106">默认筛选器</span><span class="sxs-lookup"><span data-stu-id="2a20a-106">Default filters</span></span>

<span data-ttu-id="2a20a-107">在审阅集内，有五个默认筛选器预加载到审阅集：</span><span class="sxs-lookup"><span data-stu-id="2a20a-107">In a review set, there are five default filters that are pre-loaded in the review set:</span></span>

- <span data-ttu-id="2a20a-108">关键字</span><span class="sxs-lookup"><span data-stu-id="2a20a-108">Keywords</span></span>
- <span data-ttu-id="2a20a-109">日期</span><span class="sxs-lookup"><span data-stu-id="2a20a-109">Date</span></span>
- <span data-ttu-id="2a20a-110">发件人/作者</span><span class="sxs-lookup"><span data-stu-id="2a20a-110">Sender/Author</span></span>
- <span data-ttu-id="2a20a-111">主题/标题</span><span class="sxs-lookup"><span data-stu-id="2a20a-111">Subject/Title</span></span>
- <span data-ttu-id="2a20a-112">标记</span><span class="sxs-lookup"><span data-stu-id="2a20a-112">Tags</span></span>

![默认筛选器类型](../media/DefaultFilterTypes.png)

<span data-ttu-id="2a20a-114">单击每个筛选器以展开它并分配一个值。</span><span class="sxs-lookup"><span data-stu-id="2a20a-114">Click each filter to expand it and assign a value.</span></span> <span data-ttu-id="2a20a-115">单击筛选器外部以自动将筛选器应用于审阅集。</span><span class="sxs-lookup"><span data-stu-id="2a20a-115">Click outside the filter to automatically apply the filter to the review set.</span></span> <span data-ttu-id="2a20a-116">以下屏幕截图显示了配置为显示日期范围内的文档的日期筛选器。</span><span class="sxs-lookup"><span data-stu-id="2a20a-116">The following screenshot shows the Date filter configured to show documents within a date range.</span></span>

![展开的默认筛选器](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a><span data-ttu-id="2a20a-118">添加或删除筛选器</span><span class="sxs-lookup"><span data-stu-id="2a20a-118">Add or remove filters</span></span>

<span data-ttu-id="2a20a-119">若要添加或删除为审阅集显示的筛选器，请选择"筛选器"以打开显示在飞出页上的筛选器面板。</span><span class="sxs-lookup"><span data-stu-id="2a20a-119">To add or remove filters that are displayed for the review set, select **Filters** to open the filter panel, which is displayed on a flyout page.</span></span> 

![筛选器面板](../media/FilterPanel.png)

<span data-ttu-id="2a20a-121">可用筛选器分为四个部分：</span><span class="sxs-lookup"><span data-stu-id="2a20a-121">The available filters are organized in four sections:</span></span>

- <span data-ttu-id="2a20a-122">**搜索**：提供不同搜索功能的筛选器。</span><span class="sxs-lookup"><span data-stu-id="2a20a-122">**Search**: Filters that provide different search capabilities.</span></span>

- <span data-ttu-id="2a20a-123">**分析&** 编码：运行文档分析作业或使用预测编码模型时生成& **添加到** 文档的属性筛选器。</span><span class="sxs-lookup"><span data-stu-id="2a20a-123">**Analytics & predictive coding**: Filters for properties generated and added to documents when you run the **Document & email analytic** job or use predictive coding models.</span></span>

- <span data-ttu-id="2a20a-124">**ID：** 用于筛选文档的所有 ID 属性。</span><span class="sxs-lookup"><span data-stu-id="2a20a-124">**IDs**: Filters for all ID properties of documents.</span></span>

- <span data-ttu-id="2a20a-125">**项目属性**：文档属性的筛选器。</span><span class="sxs-lookup"><span data-stu-id="2a20a-125">**Item properties**: Filters for document properties.</span></span> 

<span data-ttu-id="2a20a-126">展开每个部分，选择或取消选择筛选器以在筛选器集中添加或删除它们。</span><span class="sxs-lookup"><span data-stu-id="2a20a-126">Expand each section and select or deselect filters to add or remove them in the filter set.</span></span> <span data-ttu-id="2a20a-127">添加筛选器时，筛选器集会显示该筛选器。</span><span class="sxs-lookup"><span data-stu-id="2a20a-127">When you add a filter, it's displayed in the filter set.</span></span> 

![筛选器面板中的筛选器节和属性列表](../media/FilterPanel2.png)

> [!NOTE]
> <span data-ttu-id="2a20a-129">展开筛选器面板中的节时，您将注意到已选择默认筛选器类型。</span><span class="sxs-lookup"><span data-stu-id="2a20a-129">When you expand a section in the filter panel, you'll notice that the default filter types are selected.</span></span> <span data-ttu-id="2a20a-130">您可以保持选中状态或取消选择它们，然后从筛选器集中删除它们。</span><span class="sxs-lookup"><span data-stu-id="2a20a-130">You can keep these selected or deselect them and removed them from the filter set.</span></span> 

## <a name="filter-types"></a><span data-ttu-id="2a20a-131">筛选器类型</span><span class="sxs-lookup"><span data-stu-id="2a20a-131">Filter types</span></span>

<span data-ttu-id="2a20a-132">审阅集内每个可搜索字段都有一个对应的筛选器，可用于基于特定字段筛选项目。</span><span class="sxs-lookup"><span data-stu-id="2a20a-132">Every searchable field in a review set has a corresponding filter that you can use for filter items based on a specific field.</span></span>

<span data-ttu-id="2a20a-133">筛选器有多种类型：</span><span class="sxs-lookup"><span data-stu-id="2a20a-133">There are multiple types of filters:</span></span>

- <span data-ttu-id="2a20a-134">**Freetext：** 将自由文本筛选器应用于文本字段，如"Subject"。</span><span class="sxs-lookup"><span data-stu-id="2a20a-134">**Freetext**: A freetext filter is applied to text fields such as "Subject".</span></span> <span data-ttu-id="2a20a-135">可以通过用逗号分隔多个搜索词来列出这些搜索词。</span><span class="sxs-lookup"><span data-stu-id="2a20a-135">You can list multiple search terms by separating them with a comma.</span></span>

- <span data-ttu-id="2a20a-136">**Date**：日期筛选器用于"上次修改日期"等日期字段。</span><span class="sxs-lookup"><span data-stu-id="2a20a-136">**Date**: A date filter is used for date fields such as "Last modified date".</span></span>

- <span data-ttu-id="2a20a-137">**搜索选项**：搜索选项筛选器提供一个可能值列表 (每个值都显示一个复选框，你可以为审阅中的特定字段) 复选框。</span><span class="sxs-lookup"><span data-stu-id="2a20a-137">**Search options**: A search options filter provides a list of possible values (each value is displayed with a checkbox that you can select) for particular fields in the review.</span></span> <span data-ttu-id="2a20a-138">此筛选器用于审阅集可能值有限数量的字段，例如"发件人"。</span><span class="sxs-lookup"><span data-stu-id="2a20a-138">This filter is used for fields, such as "Sender", where there is a finite number of possible values in the review set.</span></span>

- <span data-ttu-id="2a20a-139">**关键字**：关键字条件是可用于搜索词的 freetext 条件的特定实例。</span><span class="sxs-lookup"><span data-stu-id="2a20a-139">**Keyword**: A keyword condition is a specific instance of freetext condition that you can use to search for terms.</span></span> <span data-ttu-id="2a20a-140">您还可以在此类型的筛选器中使用类似 KQL 的查询语言。</span><span class="sxs-lookup"><span data-stu-id="2a20a-140">You can also use KQL-like query language in this type of filter.</span></span> <span data-ttu-id="2a20a-141">有关详细信息，请参阅本主题中的查询语言和高级查询生成器部分。</span><span class="sxs-lookup"><span data-stu-id="2a20a-141">For more information, see the Query language and Advanced query builder sections in this topic.</span></span>

## <a name="include-and-exclude-filter-relationships"></a><span data-ttu-id="2a20a-142">包含和排除筛选器关系</span><span class="sxs-lookup"><span data-stu-id="2a20a-142">Include and exclude filter relationships</span></span>

<span data-ttu-id="2a20a-143">您可以选择更改特定筛选器的包含和排除关系。</span><span class="sxs-lookup"><span data-stu-id="2a20a-143">You have the option to change the include and exclude relationship for a particular filter.</span></span> <span data-ttu-id="2a20a-144">例如，在"标记"筛选器中，可以通过在下拉列表筛选器中选择"等于 **无** "来排除用特定标记标记的项目。</span><span class="sxs-lookup"><span data-stu-id="2a20a-144">For example, in the Tag filter, you can exclude items that are tagged with a particular tag by selecting **Equals none of** in the dropdown filter.</span></span> 

![排除标记筛选器](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a><span data-ttu-id="2a20a-146">将筛选器另存为查询</span><span class="sxs-lookup"><span data-stu-id="2a20a-146">Save filters as queries</span></span>

<span data-ttu-id="2a20a-147">对筛选器感到满意后，可以将筛选器组合另存为筛选器查询。</span><span class="sxs-lookup"><span data-stu-id="2a20a-147">After you are satisfied with your filters, you can save the filter combination as a filter query.</span></span> <span data-ttu-id="2a20a-148">这样，你可以在将来的审阅会话中应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="2a20a-148">This lets you apply the filter in the future review sessions.</span></span>

<span data-ttu-id="2a20a-149">若要保存筛选器，请选择 **"保存查询并** 命名它"。</span><span class="sxs-lookup"><span data-stu-id="2a20a-149">To save a filter, select **Save the query** and name it.</span></span> <span data-ttu-id="2a20a-150">您或其他审阅者可以通过选择"保存的筛选器查询"下拉列表并选择要应用于审阅集文档的筛选器查询来运行以前保存的筛选器查询。</span><span class="sxs-lookup"><span data-stu-id="2a20a-150">You or other reviewers can run previously saved filter queries by selecting the **Saved filter queries** dropdown and selecting a filter query to apply to review set documents.</span></span> 

![保存筛选器查询](../media/SaveFilterQuery.png)

<span data-ttu-id="2a20a-152">若要删除筛选器查询，请打开筛选面板并选择查询旁边的回收站图标。</span><span class="sxs-lookup"><span data-stu-id="2a20a-152">To delete a filter query, open the filter panel and select the trashcan icon next to the query.</span></span>

![删除筛选器查询](../media/DeleteFilterQuery.png)

## <a name="query-language"></a><span data-ttu-id="2a20a-154">查询语言</span><span class="sxs-lookup"><span data-stu-id="2a20a-154">Query language</span></span>

<span data-ttu-id="2a20a-155">除了使用筛选器之外，您还可以使用关键字筛选器中的 KQL 类似查询语言来构建审阅集搜索查询。</span><span class="sxs-lookup"><span data-stu-id="2a20a-155">In addition to using filters, you can also use a KQL-like query language in the Keywords filter to build your review set search query.</span></span> <span data-ttu-id="2a20a-156">审阅集查询的查询语言支持标准布尔运算符，如AND、OR、NOT和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="2a20a-156">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="2a20a-157">它还支持单字符通配符 (？) 和多字符通配符 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="2a20a-157">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="advanced-query-builder"></a><span data-ttu-id="2a20a-158">高级查询生成器</span><span class="sxs-lookup"><span data-stu-id="2a20a-158">Advanced query builder</span></span>

<span data-ttu-id="2a20a-159">您还可以生成更高级的查询来搜索审阅集内的文档。</span><span class="sxs-lookup"><span data-stu-id="2a20a-159">You can also build more advanced queries to search for documents in a review set.</span></span>

1. <span data-ttu-id="2a20a-160">打开筛选面板，选择" **筛选器"，** 然后展开" **搜索"** 部分。</span><span class="sxs-lookup"><span data-stu-id="2a20a-160">Open the filter panel, select **Filters**, and expand the **Search** section.</span></span>

  ![添加 KQL 筛选器](../media/AddKQLFilter.png)

2. <span data-ttu-id="2a20a-162">选择 **KQL 筛选器**，然后单击"**打开查询生成器"。**</span><span class="sxs-lookup"><span data-stu-id="2a20a-162">Select the **KQL** filter and click **Open query builder**.</span></span>

   <span data-ttu-id="2a20a-163">在此面板中，您可以使用查询生成器创建复杂的 KQL 查询。</span><span class="sxs-lookup"><span data-stu-id="2a20a-163">In this panel, you can create complex KQL queries by using the query builder.</span></span> <span data-ttu-id="2a20a-164">可以添加条件或添加条件组，这些条件组由 AND 或 **OR** 关系在逻辑上 **连接的多个条件** 组成。</span><span class="sxs-lookup"><span data-stu-id="2a20a-164">You can add conditions or add condition groups that are made up of multiple conditions that are logically connected by **AND** or **OR** relationships.</span></span>

   ![使用查询生成器配置复杂的筛选器查询](../media/ComplexQuery.png)
