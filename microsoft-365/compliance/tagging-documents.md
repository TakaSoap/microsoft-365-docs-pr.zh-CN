---
title: 标记审阅集中的文档
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
description: 在审阅集中标记文档有助于删除不必要的内容，并在高级电子数据展示事例中标识相关内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 445bf9a0ee5959c4972920a74e7bd1596d9edca1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034546"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="f0884-103">标记审阅集中的文档</span><span class="sxs-lookup"><span data-stu-id="f0884-103">Tag documents in a review set</span></span>

<span data-ttu-id="f0884-104">在查看集中组织内容对于在电子数据展示过程中完成各种工作流非常重要。</span><span class="sxs-lookup"><span data-stu-id="f0884-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="f0884-105">具体包括：</span><span class="sxs-lookup"><span data-stu-id="f0884-105">This includes:</span></span>

- <span data-ttu-id="f0884-106">剔除不必要的内容</span><span class="sxs-lookup"><span data-stu-id="f0884-106">Culling unnecessary content</span></span>

- <span data-ttu-id="f0884-107">标识相关内容</span><span class="sxs-lookup"><span data-stu-id="f0884-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="f0884-108">确定必须由专家或律师审阅的内容</span><span class="sxs-lookup"><span data-stu-id="f0884-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="f0884-109">当专家、律师或其他用户查看审阅集中的内容时，可以使用标记来捕获与内容相关的观点。</span><span class="sxs-lookup"><span data-stu-id="f0884-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="f0884-110">例如，如果意图挑选不必要的内容，则用户可以使用标记（如 "无响应"）标记文档。</span><span class="sxs-lookup"><span data-stu-id="f0884-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="f0884-111">在审阅并标记内容之后，可以创建审阅集搜索，以排除任何标记为 "无响应" 的内容，这将消除电子数据展示工作流中的后续步骤中的内容。</span><span class="sxs-lookup"><span data-stu-id="f0884-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="f0884-112">可以为每种情况自定义标签面板，以便标记可以支持预期的审阅工作流。</span><span class="sxs-lookup"><span data-stu-id="f0884-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="f0884-113">标记类型</span><span class="sxs-lookup"><span data-stu-id="f0884-113">Tag types</span></span>

<span data-ttu-id="f0884-114">高级电子数据展示提供了两种类型的标记：</span><span class="sxs-lookup"><span data-stu-id="f0884-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="f0884-115">**单个选择标记**-限制用户在组中选择一个标记。</span><span class="sxs-lookup"><span data-stu-id="f0884-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="f0884-116">这有助于确保用户不选择相互冲突的标记，如 "响应式" 和 "无响应"。</span><span class="sxs-lookup"><span data-stu-id="f0884-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="f0884-117">这些按钮将显示为单选按钮。</span><span class="sxs-lookup"><span data-stu-id="f0884-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="f0884-118">**多选项标记**-允许用户选择组中的多个标记。</span><span class="sxs-lookup"><span data-stu-id="f0884-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="f0884-119">这些将显示为复选框。</span><span class="sxs-lookup"><span data-stu-id="f0884-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="f0884-120">标记结构</span><span class="sxs-lookup"><span data-stu-id="f0884-120">Tag structure</span></span>

<span data-ttu-id="f0884-121">除了标记类型之外，标记面板中的标记组织方式的结构可用于使标签文档更加直观。</span><span class="sxs-lookup"><span data-stu-id="f0884-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="f0884-122">标记按节分组。</span><span class="sxs-lookup"><span data-stu-id="f0884-122">Tags are grouped by sections.</span></span> <span data-ttu-id="f0884-123">查看 "设置搜索支持按标记和按标记搜索" 部分的功能。</span><span class="sxs-lookup"><span data-stu-id="f0884-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="f0884-124">这意味着您可以创建审阅集搜索，以检索标记为某一节中的任何标记的文档。</span><span class="sxs-lookup"><span data-stu-id="f0884-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![标记面板中的标记部分](../media/Tagtypes.png)

<span data-ttu-id="f0884-126">可以通过在节中嵌套标记来进一步对标记进行组织。</span><span class="sxs-lookup"><span data-stu-id="f0884-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="f0884-127">例如，如果目的是标识和标记特权内容，则可以使用嵌套来清楚地表明用户可以将文档标记为 "特权"，并通过检查适当的嵌套标记来选择特权类型。</span><span class="sxs-lookup"><span data-stu-id="f0884-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![标记部分中的嵌套标记](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="f0884-129">应用标记</span><span class="sxs-lookup"><span data-stu-id="f0884-129">Applying tags</span></span>

<span data-ttu-id="f0884-130">有几种方法可将标记应用于内容。</span><span class="sxs-lookup"><span data-stu-id="f0884-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="f0884-131">为单个文档添加标签</span><span class="sxs-lookup"><span data-stu-id="f0884-131">Tagging a single document</span></span>

<span data-ttu-id="f0884-132">在审阅集中查看文档时，可以通过单击 **"添加标签" 面板**显示审阅可使用的标签。</span><span class="sxs-lookup"><span data-stu-id="f0884-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![单击 "标记面板" 以显示标记面板](../media/Singledoctag.png)

<span data-ttu-id="f0884-134">这将使您能够对显示在查看器中的文档应用标记。</span><span class="sxs-lookup"><span data-stu-id="f0884-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="f0884-135">批量标记</span><span class="sxs-lookup"><span data-stu-id="f0884-135">Bulk tagging</span></span>

<span data-ttu-id="f0884-136">可以通过在 "结果" 网格中选择多个文件，然后在 "**标记" 面板**中使用类似于单个文档的标记，来完成批量标记。</span><span class="sxs-lookup"><span data-stu-id="f0884-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="f0884-137">可以通过选择两次标记来完成批量取消标记操作;第一次单击将应用标记，第二个选择将确保清除所有选定文件的标记。</span><span class="sxs-lookup"><span data-stu-id="f0884-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![自动生成的蜂窝电话说明的屏幕截图](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="f0884-139">批量标记时，加标签面板将显示为面板中的每个标记标记的文件数。</span><span class="sxs-lookup"><span data-stu-id="f0884-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="f0884-140">在其他审阅面板中进行标记</span><span class="sxs-lookup"><span data-stu-id="f0884-140">Tagging in other review panels</span></span>

<span data-ttu-id="f0884-141">审阅文档时，可以使用其他审阅面板查看 "结果" 网格中文档的其他特征。</span><span class="sxs-lookup"><span data-stu-id="f0884-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="f0884-142">这包括查看其他相关文档、电子邮件线索、临近重复项和哈希重复项。</span><span class="sxs-lookup"><span data-stu-id="f0884-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="f0884-143">例如，当您查看相关文档时（通过使用 "**文档系列**" 审阅面板），您可以通过批量标记相关文档显著减少审阅时间。</span><span class="sxs-lookup"><span data-stu-id="f0884-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="f0884-144">例如，如果电子邮件中有多个附件，并且您希望确保整个系列的标签一致。</span><span class="sxs-lookup"><span data-stu-id="f0884-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="f0884-145">例如，下面介绍了如何在使用**文档系列**审阅面板时显示 "**标记" 面板**：</span><span class="sxs-lookup"><span data-stu-id="f0884-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="f0884-146">对所选文档打开 "审阅" 面板（例如，在 "**文档系列**" 审阅面板中显示相关内容列表时，请单击 "文档系列" 审阅面板下的 "**标记文档**"。</span><span class="sxs-lookup"><span data-stu-id="f0884-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="f0884-147">"标记" 面板显示为弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="f0884-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="f0884-148">选择一个或多个标记以应用选定的文档。</span><span class="sxs-lookup"><span data-stu-id="f0884-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="f0884-149">若要标记所有文档，请在 "**文档系列**" 面板中选择 "所有文档"，单击 "**标记文档**"，然后选择要应用于整个文档系列的标记。</span><span class="sxs-lookup"><span data-stu-id="f0884-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![自动生成的社交媒体帖子说明的屏幕截图](../media/Relatedtag.png)
