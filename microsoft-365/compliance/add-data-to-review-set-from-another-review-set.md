---
title: 将一个审阅集的数据添加到另一审阅集
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
description: 了解如何从一个审阅集选择文档，并分别在一个审阅案例的另一个审阅Advanced eDiscovery文档。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285176"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="d638b-103">从另一审阅集将数据添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="d638b-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="d638b-104">在某些情况下，可能需要从一个审阅集选择文档，在另一个审阅集单独处理它们。</span><span class="sxs-lookup"><span data-stu-id="d638b-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="d638b-105">如果已经挑选审阅集中的内容，并且要对数据子集运行分析，此方法尤其有用。</span><span class="sxs-lookup"><span data-stu-id="d638b-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="d638b-106">按照本文中的工作流将内容从一个审阅集添加到另一个审阅集。</span><span class="sxs-lookup"><span data-stu-id="d638b-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="d638b-107">创建审阅集</span><span class="sxs-lookup"><span data-stu-id="d638b-107">Create a review set</span></span>

<span data-ttu-id="d638b-108">在启动之前，你需要创建一个审阅集以将数据添加到。</span><span class="sxs-lookup"><span data-stu-id="d638b-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="d638b-109">可以在案例的"审阅集 **"选项卡上添加一** 个新的审阅集。</span><span class="sxs-lookup"><span data-stu-id="d638b-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="d638b-110">有关详细信息，请参阅创建 [审阅集](managing-review-sets.md#create-a-review-set)。</span><span class="sxs-lookup"><span data-stu-id="d638b-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="d638b-111">步骤 1：确定要添加到其他审阅集的内容</span><span class="sxs-lookup"><span data-stu-id="d638b-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="d638b-112">通过在源审阅集中选择特定文档，或者通过选择由审阅集查询返回的所有项目，可以将一个审阅集中的内容添加到另一个审阅集。</span><span class="sxs-lookup"><span data-stu-id="d638b-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="d638b-113">如果要添加选定项目，请选择项目，选择"**操作**"，然后选择"**添加到另一审阅集"。**</span><span class="sxs-lookup"><span data-stu-id="d638b-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![添加到"操作"菜单中的另一审阅集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="d638b-115">步骤 2：指定用于添加到另一审阅集的选项</span><span class="sxs-lookup"><span data-stu-id="d638b-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="d638b-116">在" **添加到其他审阅集选项** "飞出页中，选择要将项目添加到的审阅集。</span><span class="sxs-lookup"><span data-stu-id="d638b-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="d638b-117">选择是添加"**所有搜索结果"还是**"**所选项目"。**</span><span class="sxs-lookup"><span data-stu-id="d638b-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="d638b-118">其他信息提供了一些选项，用于包含项目的所有元数据，以及是否在将文档添加到新审阅集时从源审阅集选中) 标签"复选框来包括标记 (。</span><span class="sxs-lookup"><span data-stu-id="d638b-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![将数据添加到另一审阅集的选项](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="d638b-120">单击"**确定"** 后， (一个名为"将数据添加到另一审阅) ，以将内容添加到另一审阅集。</span><span class="sxs-lookup"><span data-stu-id="d638b-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="d638b-121">您可以转到"作业 **"** 选项卡并监视此作业的进度。</span><span class="sxs-lookup"><span data-stu-id="d638b-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="d638b-122">有关详细信息，请参阅管理 [作业](managing-jobs-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="d638b-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
