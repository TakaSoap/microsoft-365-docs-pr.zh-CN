---
title: 标记审阅集中的文档
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
description: 在审阅集内标记文档有助于删除不必要的内容，并识别Advanced eDiscovery内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736243"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="62e8b-103">标记审阅集内的文档Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="62e8b-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="62e8b-104">组织审阅集内的内容对于完成电子数据展示过程中的各种工作流非常重要。</span><span class="sxs-lookup"><span data-stu-id="62e8b-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="62e8b-105">这包括：</span><span class="sxs-lookup"><span data-stu-id="62e8b-105">This includes:</span></span>

- <span data-ttu-id="62e8b-106">剔除不必要的内容</span><span class="sxs-lookup"><span data-stu-id="62e8b-106">Culling unnecessary content</span></span>

- <span data-ttu-id="62e8b-107">确定相关内容</span><span class="sxs-lookup"><span data-stu-id="62e8b-107">Identifying relevant content</span></span>

- <span data-ttu-id="62e8b-108">确定必须由专家或律师审阅的内容</span><span class="sxs-lookup"><span data-stu-id="62e8b-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="62e8b-109">当专家、律师或其他用户审阅审阅集内容时，可以使用标签来捕获他们有关内容的意见。</span><span class="sxs-lookup"><span data-stu-id="62e8b-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="62e8b-110">例如，如果意图是剔除不必要的内容，用户可以使用标记（如"无响应"）标记文档。</span><span class="sxs-lookup"><span data-stu-id="62e8b-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="62e8b-111">在审阅和标记内容后，可创建审阅集搜索以排除标记为"无响应"的任何内容。</span><span class="sxs-lookup"><span data-stu-id="62e8b-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="62e8b-112">此过程消除了电子数据展示工作流中下一步中无响应的内容。</span><span class="sxs-lookup"><span data-stu-id="62e8b-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="62e8b-113">审阅集内的标签面板可以针对每个案例进行自定义，以便标记支持针对该案例的预定审阅工作流。</span><span class="sxs-lookup"><span data-stu-id="62e8b-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="62e8b-114">标记的范围是一个Advanced eDiscovery的情况。</span><span class="sxs-lookup"><span data-stu-id="62e8b-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="62e8b-115">这意味着一个案例只能有一组标记，审阅者可以使用这些标记标记审阅集文档。</span><span class="sxs-lookup"><span data-stu-id="62e8b-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="62e8b-116">不能设置一组不同的标记，以用于同一情况下的不同审阅集。</span><span class="sxs-lookup"><span data-stu-id="62e8b-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="62e8b-117">标记类型</span><span class="sxs-lookup"><span data-stu-id="62e8b-117">Tag types</span></span>

<span data-ttu-id="62e8b-118">Advanced eDiscovery两种类型的标记：</span><span class="sxs-lookup"><span data-stu-id="62e8b-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="62e8b-119">**单个选项标记**：限制审阅者选择组内的单个标记。</span><span class="sxs-lookup"><span data-stu-id="62e8b-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="62e8b-120">这些类型的标记可用于确保审阅者不会选择冲突标记，如"响应式"和"无响应"。</span><span class="sxs-lookup"><span data-stu-id="62e8b-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="62e8b-121">单个选项标记显示为单选按钮。</span><span class="sxs-lookup"><span data-stu-id="62e8b-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="62e8b-122">**多个选择标记**：允许审阅选择一个组内的多个标记。</span><span class="sxs-lookup"><span data-stu-id="62e8b-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="62e8b-123">这些类型的标记显示为复选框。</span><span class="sxs-lookup"><span data-stu-id="62e8b-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="62e8b-124">标记结构</span><span class="sxs-lookup"><span data-stu-id="62e8b-124">Tag structure</span></span>

<span data-ttu-id="62e8b-125">除了标记类型之外，标记面板中标记组织方式的结构还可用于使标记文档更为直观。</span><span class="sxs-lookup"><span data-stu-id="62e8b-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="62e8b-126">标记按节分组。</span><span class="sxs-lookup"><span data-stu-id="62e8b-126">Tags are grouped by sections.</span></span> <span data-ttu-id="62e8b-127">审阅集搜索支持按标记和按标记部分搜索。</span><span class="sxs-lookup"><span data-stu-id="62e8b-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="62e8b-128">这意味着您可以创建审阅集搜索来检索用节中的任何标记标记的文档。</span><span class="sxs-lookup"><span data-stu-id="62e8b-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![标记面板中的标记部分](../media/TagTypes.png)

<span data-ttu-id="62e8b-130">您可以通过在节中嵌套标记来进一步组织标记。</span><span class="sxs-lookup"><span data-stu-id="62e8b-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="62e8b-131">例如，如果目的是标识和标记特权内容，可以使用嵌套来明确审阅者可以将文档标记为"Privileged"，并检查相应的嵌套标记来选择特权类型。</span><span class="sxs-lookup"><span data-stu-id="62e8b-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![标记节中的嵌套标记](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="62e8b-133">创建标记</span><span class="sxs-lookup"><span data-stu-id="62e8b-133">Create tags</span></span>

<span data-ttu-id="62e8b-134">在将标记应用于审阅集内的文档之前，您需要创建一个标记结构。</span><span class="sxs-lookup"><span data-stu-id="62e8b-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="62e8b-135">打开审阅集并导航到命令栏，然后选择"**按查询标记"。**</span><span class="sxs-lookup"><span data-stu-id="62e8b-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="62e8b-136">在标记面板中，选择" **管理标记选项"**</span><span class="sxs-lookup"><span data-stu-id="62e8b-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="62e8b-137">选择 **"添加标记"部分**。</span><span class="sxs-lookup"><span data-stu-id="62e8b-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="62e8b-138">键入标记组标题和可选说明，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="62e8b-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="62e8b-139">选择标记组标题旁边的三点下拉菜单，然后单击添加 **复选框** 或 **添加选项按钮**。</span><span class="sxs-lookup"><span data-stu-id="62e8b-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="62e8b-140">键入复选框或选项按钮的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="62e8b-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="62e8b-141">重复此过程以创建新的标记节、标记选项和复选框。</span><span class="sxs-lookup"><span data-stu-id="62e8b-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![配置标记结构](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="62e8b-143">应用标记</span><span class="sxs-lookup"><span data-stu-id="62e8b-143">Applying tags</span></span>

<span data-ttu-id="62e8b-144">标记结构就位后，审阅者可以将标记应用于审阅集内的文档。</span><span class="sxs-lookup"><span data-stu-id="62e8b-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="62e8b-145">有两种不同的应用标记的方法：</span><span class="sxs-lookup"><span data-stu-id="62e8b-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="62e8b-146">标记文件</span><span class="sxs-lookup"><span data-stu-id="62e8b-146">Tag files</span></span>

- <span data-ttu-id="62e8b-147">按查询标记</span><span class="sxs-lookup"><span data-stu-id="62e8b-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="62e8b-148">标记文件</span><span class="sxs-lookup"><span data-stu-id="62e8b-148">Tag files</span></span>

<span data-ttu-id="62e8b-149">无论是选择审阅集的单个项目还是多个项目，都可以单击命令栏中的"标记文件"，将标记应用于其选择。</span><span class="sxs-lookup"><span data-stu-id="62e8b-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="62e8b-150">在标记面板中，可以选择一个标记，该标记将自动应用于所选文档。</span><span class="sxs-lookup"><span data-stu-id="62e8b-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![标记选定文件](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="62e8b-152">标记将仅应用于项目列表中的选定项目。</span><span class="sxs-lookup"><span data-stu-id="62e8b-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="62e8b-153">按查询标记</span><span class="sxs-lookup"><span data-stu-id="62e8b-153">Tag by query</span></span>

<span data-ttu-id="62e8b-154">通过按查询标记，你可以将标记应用于由当前在审阅集应用的筛选器查询显示的所有项目。</span><span class="sxs-lookup"><span data-stu-id="62e8b-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="62e8b-155">取消选择审阅集内的所有项目，然后转到命令栏，然后选择"**按查询标记"。**</span><span class="sxs-lookup"><span data-stu-id="62e8b-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="62e8b-156">在标记面板中，选择要应用的标签。</span><span class="sxs-lookup"><span data-stu-id="62e8b-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="62e8b-157">在 **"标记选择** "下拉列表下，有三个选项指示要应用标记的项。</span><span class="sxs-lookup"><span data-stu-id="62e8b-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="62e8b-158">**与已应用的查询匹配的项**：将标记应用于与筛选器查询条件匹配的特定项目。</span><span class="sxs-lookup"><span data-stu-id="62e8b-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="62e8b-159">**包含关联的系列项目**：将标记应用于与筛选器查询条件及其关联的系列项匹配的特定项。</span><span class="sxs-lookup"><span data-stu-id="62e8b-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="62e8b-160">*系列项* 是共享相同 FamilyId 元数据值的项。</span><span class="sxs-lookup"><span data-stu-id="62e8b-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="62e8b-161">**包含关联的对话项目**：将标记应用于与筛选器查询条件匹配的项目及其关联的对话项目。</span><span class="sxs-lookup"><span data-stu-id="62e8b-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="62e8b-162">*会话项目* 是共享相同 ConversationId 元数据值的项。</span><span class="sxs-lookup"><span data-stu-id="62e8b-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![标记选择](../media/TagByQuery2.png)

4. <span data-ttu-id="62e8b-164">单击 **"开始标记作业** "以触发标记作业。</span><span class="sxs-lookup"><span data-stu-id="62e8b-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="62e8b-165">标记筛选器</span><span class="sxs-lookup"><span data-stu-id="62e8b-165">Tag filter</span></span>

<span data-ttu-id="62e8b-166">使用审阅集的标记筛选器，根据项目的标记方法从查询结果中快速查找或排除项目。</span><span class="sxs-lookup"><span data-stu-id="62e8b-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="62e8b-167">选择 **"筛选器** "展开筛选器面板。</span><span class="sxs-lookup"><span data-stu-id="62e8b-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="62e8b-168">选择并展开 **"项目属性"。**</span><span class="sxs-lookup"><span data-stu-id="62e8b-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="62e8b-169">向下滚动以查找名为 Tag 的 **筛选器**，选中复选框，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="62e8b-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="62e8b-170">若要在查询中包括或排除具有特定标记的项目，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="62e8b-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="62e8b-171">**包含项目**：选择标记值 **，然后选择下拉菜单** 中的"等于任意项"。</span><span class="sxs-lookup"><span data-stu-id="62e8b-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="62e8b-172">或</span><span class="sxs-lookup"><span data-stu-id="62e8b-172">Or</span></span>

   - <span data-ttu-id="62e8b-173">**排除项目**：选择标记值，然后选择下拉菜单中的" **等于无** "。</span><span class="sxs-lookup"><span data-stu-id="62e8b-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![标记筛选器排除项目](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="62e8b-175">请务必刷新页面，以确保标记筛选器显示标记结构的最新更改。</span><span class="sxs-lookup"><span data-stu-id="62e8b-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
