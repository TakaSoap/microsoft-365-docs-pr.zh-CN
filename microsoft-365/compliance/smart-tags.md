---
title: 在智能标记中设置Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: 智能标记使你可以应用机器学习功能，在查看事件案例Advanced eDiscovery功能。 使用智能标记组显示机器学习检测模型（如律师-客户特权模型）的结果。
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081079"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="60fa1-104">在智能标记中设置Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="60fa1-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="60fa1-105">机器学习 (ML) 功能Advanced eDiscovery审阅审阅集内案例文档时，提高决策流程的效率。</span><span class="sxs-lookup"><span data-stu-id="60fa1-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="60fa1-106">智能标记是一种将ML记录决策的方法：在审阅过程中标记文档时。</span><span class="sxs-lookup"><span data-stu-id="60fa1-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="60fa1-107">创建智能标记组时，与智能标记组关联的 ML 模型的结果决策与标记组中标记的标记一起显示。</span><span class="sxs-lookup"><span data-stu-id="60fa1-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="60fa1-108">这有助于在查看ML文档时，内线查看结果信息。</span><span class="sxs-lookup"><span data-stu-id="60fa1-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="60fa1-109">如何设置智能标记组</span><span class="sxs-lookup"><span data-stu-id="60fa1-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="60fa1-110">在审阅集内，单击 **"管理审阅集"，** 然后单击"**管理标记"。**</span><span class="sxs-lookup"><span data-stu-id="60fa1-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="60fa1-111">单击 **"添加标记组**"，然后选择"**添加智能标记组"。**</span><span class="sxs-lookup"><span data-stu-id="60fa1-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="60fa1-112">选择要ML组关联的标记模型。</span><span class="sxs-lookup"><span data-stu-id="60fa1-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="60fa1-113">这将创建一个标记组 *和 N* 个子标记，其中 *N* 是模型可能的输出数。</span><span class="sxs-lookup"><span data-stu-id="60fa1-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="60fa1-114">例如，律师 [-客户特权检测模型](attorney-privilege-detection.md) 有两个可能的输出：</span><span class="sxs-lookup"><span data-stu-id="60fa1-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="60fa1-115">**正** – 用于标记包含律师-客户特权内容的文档。</span><span class="sxs-lookup"><span data-stu-id="60fa1-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="60fa1-116">**负** – 用于标记不包含律师-客户特权内容的文档。</span><span class="sxs-lookup"><span data-stu-id="60fa1-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="60fa1-117">如果选择此模型，将创建一个包含两个子标记 (一个名为 Positive 的子标记，另一个名为 **Negative** 的子标记) 审阅集创建一个名为 **Negative** 的标记。</span><span class="sxs-lookup"><span data-stu-id="60fa1-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="60fa1-118">本示例中，每个子标记对应于律师-客户特权检测模型可能的输出之一。</span><span class="sxs-lookup"><span data-stu-id="60fa1-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="60fa1-119">（可选）您可以重命名标记组和子标记。</span><span class="sxs-lookup"><span data-stu-id="60fa1-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="60fa1-120">例如，你可以将 **Positive** 标记重命名为 **Privileged，** 将 **Negative** 标记重命名为 **Not privileged**。</span><span class="sxs-lookup"><span data-stu-id="60fa1-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="60fa1-121">如何使用智能标记</span><span class="sxs-lookup"><span data-stu-id="60fa1-121">How to use smart tags</span></span>

<span data-ttu-id="60fa1-122">查看文档时，模型的结果将显示在相应的子标记旁边。</span><span class="sxs-lookup"><span data-stu-id="60fa1-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="60fa1-123">例如，如果您有一个智能标记组用于律师-客户特权检测，并且您查看了一个可能特权的文档，则相应标记旁边将显示该结论的原因。</span><span class="sxs-lookup"><span data-stu-id="60fa1-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="60fa1-124">请注意，标记不会自动应用于文档。</span><span class="sxs-lookup"><span data-stu-id="60fa1-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="60fa1-125">审阅者决定如何标记文档。</span><span class="sxs-lookup"><span data-stu-id="60fa1-125">The reviewer makes the decision about how to tag the document.</span></span>
