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
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285278"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="7d5a9-103">标记审阅集内的文档Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7d5a9-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="7d5a9-104">组织审阅集内的内容对于完成电子数据展示过程中的各种工作流非常重要。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="7d5a9-105">这包括：</span><span class="sxs-lookup"><span data-stu-id="7d5a9-105">This includes:</span></span>

- <span data-ttu-id="7d5a9-106">剔除不必要的内容</span><span class="sxs-lookup"><span data-stu-id="7d5a9-106">Culling unnecessary content</span></span>

- <span data-ttu-id="7d5a9-107">确定相关内容</span><span class="sxs-lookup"><span data-stu-id="7d5a9-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="7d5a9-108">确定必须由专家或律师审阅的内容</span><span class="sxs-lookup"><span data-stu-id="7d5a9-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="7d5a9-109">当专家、律师或其他用户审阅审阅集内容时，可以使用标签来捕获他们有关内容的意见。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="7d5a9-110">例如，如果意图是剔除不必要的内容，用户可以使用标记（如"无响应"）标记文档。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="7d5a9-111">在审阅和标记内容后，可创建审阅集搜索以排除标记为"无响应"的任何内容，这将从电子数据展示工作流中的下一步骤中清除此内容。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="7d5a9-112">可以针对每个案例自定义标记面板，以便标记可以支持预期的审阅工作流。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="7d5a9-113">标记类型</span><span class="sxs-lookup"><span data-stu-id="7d5a9-113">Tag types</span></span>

<span data-ttu-id="7d5a9-114">Advanced eDiscovery两种类型的标记：</span><span class="sxs-lookup"><span data-stu-id="7d5a9-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="7d5a9-115">**单个选项标记** - 限制用户选择组中单个标记。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="7d5a9-116">这可用于确保用户不会选择冲突标记，如"响应"和"无响应"。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="7d5a9-117">这些按钮将显示为单选按钮。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="7d5a9-118">**多个选择标记** - 允许用户选择一个组内的多个标记。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="7d5a9-119">它们将显示为复选框。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="7d5a9-120">标记结构</span><span class="sxs-lookup"><span data-stu-id="7d5a9-120">Tag structure</span></span>

<span data-ttu-id="7d5a9-121">除了标记类型之外，标记面板中标记组织方式的结构还可用于使标记文档更为直观。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="7d5a9-122">标记按节分组。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-122">Tags are grouped by sections.</span></span> <span data-ttu-id="7d5a9-123">审阅集搜索支持按标记和按标记部分搜索。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="7d5a9-124">这意味着您可以创建审阅集搜索来检索用节中的任何标记标记的文档。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![标记面板中的标记部分](../media/Tagtypes.png)

<span data-ttu-id="7d5a9-126">可以通过在节中嵌套标记来进一步组织标记。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="7d5a9-127">例如，如果目的是标识和标记特权内容，可以使用嵌套来明确用户可以将文档标记为"Privileged"，并检查相应的嵌套标记来选择特权类型。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![标记节中的嵌套标记](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="7d5a9-129">应用标记</span><span class="sxs-lookup"><span data-stu-id="7d5a9-129">Applying tags</span></span>

<span data-ttu-id="7d5a9-130">有几种方法将标记应用于内容。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="7d5a9-131">标记单个文档</span><span class="sxs-lookup"><span data-stu-id="7d5a9-131">Tagging a single document</span></span>

<span data-ttu-id="7d5a9-132">查看审阅集内的文档时，可以通过单击"标记"面板来显示审阅 **可以使用的标记**。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![单击"标记面板"以显示标记面板](../media/Singledoctag.png)

<span data-ttu-id="7d5a9-134">这样，你能够将标记应用于查看器中显示的文档。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="7d5a9-135">批量标记</span><span class="sxs-lookup"><span data-stu-id="7d5a9-135">Bulk tagging</span></span>

<span data-ttu-id="7d5a9-136">可以通过在结果网格中选择多个文件，然后使用标记面板中的标记（类似于标记单个文档）完成批量标记。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="7d5a9-137">批量取消标记可以通过选择两次标记完成;第一次单击将应用标记，第二次选择将确保已清除所有选定文件的标记。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![自动生成的手机描述的屏幕截图](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="7d5a9-139">批量标记时，标记面板将显示针对面板中每个标记标记的文件计数。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="7d5a9-140">其他审阅面板中的标记</span><span class="sxs-lookup"><span data-stu-id="7d5a9-140">Tagging in other review panels</span></span>

<span data-ttu-id="7d5a9-141">查看文档时，可以使用其他审阅面板查看结果网格中文档的其他特征。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="7d5a9-142">这包括查看其他相关文档、电子邮件线程、近重复项和哈希重复项。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="7d5a9-143">例如，在使用文档系列审阅 (查看相关文档时) ，可以通过批量标记相关文档来大大减少审阅时间。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="7d5a9-144">例如，如果电子邮件具有多个附件，并且您希望确保整个系列都一致标记。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="7d5a9-145">例如，下面介绍在使用文档系列审阅面板时如何 **显示** 标记面板：</span><span class="sxs-lookup"><span data-stu-id="7d5a9-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="7d5a9-146">打开所选文档的审阅面板后 (例如，在"文档系列审阅"面板中显示相关内容的列表，单击文档系列审阅面板下的"标记文档"。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="7d5a9-147">标记面板显示为弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="7d5a9-148">选择一个或多个标记以应用所选文档。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="7d5a9-149">若要标记所有文档，请选择"文档系列"面板中的所有文档，单击"标记文档"，然后选择要应用于整个文档系列的标签。</span><span class="sxs-lookup"><span data-stu-id="7d5a9-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![自动生成的社交媒体文章描述的屏幕截图](../media/Relatedtag.png)
