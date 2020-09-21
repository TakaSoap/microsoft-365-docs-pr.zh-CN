---
title: '如何重新培训内容资源管理器中的分类器 (预览) '
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在内容资源管理器中向 trainable 分类器提供反馈。
ms.openlocfilehash: 0fbce595894cbbf2a017fc1bf657b14a5b812e29
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132300"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="e606a-103">如何重新培训内容资源管理器中的分类器 (预览) </span><span class="sxs-lookup"><span data-stu-id="e606a-103">How to retrain a classifier in content explorer (preview)</span></span>

<span data-ttu-id="e606a-104">Microsoft 365 trainable 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以进行培训以识别这些类型的内容。</span><span class="sxs-lookup"><span data-stu-id="e606a-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="e606a-105">经过培训后，您可以使用它来确定应用 Office 灵敏度标签、通信合规性策略和保留标签策略的项目。</span><span class="sxs-lookup"><span data-stu-id="e606a-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="e606a-106">本文介绍了如何通过提供其他反馈来提高自定义 trainable 分类器和某些预先培训的分类程序的性能。</span><span class="sxs-lookup"><span data-stu-id="e606a-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="e606a-107">若要了解有关不同类型的分类器的详细信息，请参阅 [了解 trainable 类元 (preview) ](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="e606a-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="e606a-108">权限</span><span class="sxs-lookup"><span data-stu-id="e606a-108">Permissions</span></span>

<span data-ttu-id="e606a-109">要访问 Microsoft 365 合规性中心中的分类器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e606a-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="e606a-110">合规性管理员角色或合规性数据管理员是培训分类器所必需的</span><span class="sxs-lookup"><span data-stu-id="e606a-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="e606a-111">在这些情况下，您需要具有这些权限的帐户才能使用分类器：</span><span class="sxs-lookup"><span data-stu-id="e606a-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="e606a-112">保留标签策略方案：记录管理和保留管理角色</span><span class="sxs-lookup"><span data-stu-id="e606a-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="e606a-113">整体工作流</span><span class="sxs-lookup"><span data-stu-id="e606a-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e606a-114">您可以在内容资源管理器中提供反馈，以自动应用保留标签策略以交换项目并将分类器作为条件使用。</span><span class="sxs-lookup"><span data-stu-id="e606a-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="e606a-115">**如果没有将保留标签自动应用于交换项目并使用分类器作为条件的保留策略，请停止此处。**</span><span class="sxs-lookup"><span data-stu-id="e606a-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="e606a-116">在使用分类器时，您可能需要增加所进行的分类的精度。</span><span class="sxs-lookup"><span data-stu-id="e606a-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="e606a-117">为此，请评估为其标识为匹配或不匹配的项目所做分类的质量。</span><span class="sxs-lookup"><span data-stu-id="e606a-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="e606a-118">在对分类器进行30个评估之后，它将接受反馈并自动 retrains 自身。</span><span class="sxs-lookup"><span data-stu-id="e606a-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="e606a-119">若要了解有关重新培训分类器的整个工作流的详细信息，请参阅 [Process flow for 可再培训分类器](classifier-learn-about.md#retraining-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="e606a-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="e606a-120">分类器必须已发布且在可 retrained 之前使用。</span><span class="sxs-lookup"><span data-stu-id="e606a-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="e606a-121">如何重新培训内容资源管理器中的分类器 (预览) </span><span class="sxs-lookup"><span data-stu-id="e606a-121">How to retrain a classifier in content explorer (preview)</span></span>

1. <span data-ttu-id="e606a-122">使用合规性管理员或安全管理员角色访问权限登录 microsoft 365 合规中心，并打开**Microsoft 365 合规性中心**  >  **数据分类**  >  **内容浏览器**。</span><span class="sxs-lookup"><span data-stu-id="e606a-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="e606a-123">在 " **标签上的筛选器"、"信息类型" 或 "类别** " 列表中，展开 **Trainable 分类**器。</span><span class="sxs-lookup"><span data-stu-id="e606a-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e606a-124">在 trainable 分类程序标题下显示聚合项可能需要长达八天的时间。</span><span class="sxs-lookup"><span data-stu-id="e606a-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="e606a-125">选择您在自动应用保留标签策略中使用的 trainable 分类符。</span><span class="sxs-lookup"><span data-stu-id="e606a-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="e606a-126">这是你将提供反馈的 trainable 分类符。</span><span class="sxs-lookup"><span data-stu-id="e606a-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="e606a-127">如果某项在 " **保留标签** " 列中有条目，则表示该项目已归类为 `match` 。</span><span class="sxs-lookup"><span data-stu-id="e606a-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="e606a-128">如果某项在 " **保留标签** " 列中没有条目，则表示它已归类为 `close match` 。</span><span class="sxs-lookup"><span data-stu-id="e606a-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="e606a-129">您可以通过提供对项目的反馈来提高最大分类程序的精度 `close match` 。</span><span class="sxs-lookup"><span data-stu-id="e606a-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="e606a-130">选择一个项目并打开它。</span><span class="sxs-lookup"><span data-stu-id="e606a-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="e606a-131">您可以通过选择所有项目并在命令栏中选择 " **改进分类** " 来同时提供对多个项目的反馈。</span><span class="sxs-lookup"><span data-stu-id="e606a-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="e606a-132">选择 " **提供反馈**"。</span><span class="sxs-lookup"><span data-stu-id="e606a-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="e606a-133">在 " **详细反馈** " 窗格中，如果项目是真正的正数，请选择 " **匹配**"。</span><span class="sxs-lookup"><span data-stu-id="e606a-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="e606a-134">如果项目是误报，则表示它不正确包含在类别中，请选择 " **不匹配**"。</span><span class="sxs-lookup"><span data-stu-id="e606a-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="e606a-135">如果有更适合该项目的另一个分类器，则可以从 " **建议其他 trainable 类元** " 列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e606a-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="e606a-136">这将触发其他分类器来评估项目。</span><span class="sxs-lookup"><span data-stu-id="e606a-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="e606a-137">选择 " **发送反馈** " 以发送对 `match` 、 `not a match` 分类和建议其他 trainable 类元的评估。</span><span class="sxs-lookup"><span data-stu-id="e606a-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="e606a-138">向分类器提供30个反馈的实例后，它将自动重新培训。</span><span class="sxs-lookup"><span data-stu-id="e606a-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="e606a-139">重新培训可能需要一到四个小时的时间。</span><span class="sxs-lookup"><span data-stu-id="e606a-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="e606a-140">分类器每日只能有两次 retrained。</span><span class="sxs-lookup"><span data-stu-id="e606a-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e606a-141">此信息会转到租户中的分类器，而 **不会返回到 Microsoft**。</span><span class="sxs-lookup"><span data-stu-id="e606a-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="e606a-142">打开 \*\*Trainable 类元 (预览) \*\*。</span><span class="sxs-lookup"><span data-stu-id="e606a-142">Open **Trainable classifiers (preview)**.</span></span>
10. <span data-ttu-id="e606a-143">在通信合规性策略中使用的分类符将显示在 " **重新培训** " 标题下。</span><span class="sxs-lookup"><span data-stu-id="e606a-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![重新培训状态中的分类符](../media/classifier-retraining.png)

11. <span data-ttu-id="e606a-145">重新培训完成后，选择分类器打开重新培训概述。</span><span class="sxs-lookup"><span data-stu-id="e606a-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分类器重新培训结果概述](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="e606a-147">查看建议的操作，以及分类器的 retrained 和当前已发布版本的预测比较。</span><span class="sxs-lookup"><span data-stu-id="e606a-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="e606a-148">如果您对重新培训的结果感到满意，请选择 " **重新发布**"。</span><span class="sxs-lookup"><span data-stu-id="e606a-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="e606a-149">如果对重新培训的结果不满意，可以选择在通信合规性接口中向分类器提供其他反馈，并启动另一个重新培训周期，或者不执行任何操作，这种情况下将继续使用分类器的当前已发布版本。</span><span class="sxs-lookup"><span data-stu-id="e606a-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="e606a-150">有关重新发布建议的详细信息</span><span class="sxs-lookup"><span data-stu-id="e606a-150">Details on republishing recommendations</span></span>

<span data-ttu-id="e606a-151">以下是有关我们如何阐明重新发布 retrained 分类符或建议进一步重新培训的建议的一些信息。</span><span class="sxs-lookup"><span data-stu-id="e606a-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="e606a-152">这需要对 trainable 分类器的工作方式稍有深入了解。</span><span class="sxs-lookup"><span data-stu-id="e606a-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="e606a-153">重新培训后，我们会使用反馈以及任何最初用于培训分类器的项目来评估分类器的性能。</span><span class="sxs-lookup"><span data-stu-id="e606a-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="e606a-154">对于内置模型，用于培训分类器的项是 Microsoft 用来生成模型的项。</span><span class="sxs-lookup"><span data-stu-id="e606a-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="e606a-155">对于自定义模型，在原始培训中使用的项目分类器来自您为进行测试和查看而添加的网站。</span><span class="sxs-lookup"><span data-stu-id="e606a-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="e606a-156">我们比较 retrained 和已发布分类器的两组项目的性能数字，以提供有关是否有改进重新发布的建议。</span><span class="sxs-lookup"><span data-stu-id="e606a-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e606a-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e606a-157">See also</span></span>

- [<span data-ttu-id="e606a-158">了解 trainable 分类 (预览) </span><span class="sxs-lookup"><span data-stu-id="e606a-158">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="e606a-159">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="e606a-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
