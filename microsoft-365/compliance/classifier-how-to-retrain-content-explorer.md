---
title: 如何重新训练内容资源管理器中的分类器
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
description: 了解如何在内容资源管理器中向可训练分类器提供反馈。
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793060"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="f0a8b-103">如何重新训练内容资源管理器中的分类器</span><span class="sxs-lookup"><span data-stu-id="f0a8b-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="f0a8b-104">可Microsoft 365分类器是一种工具，你可以训练它，通过提供要查看的示例来识别各种类型的内容。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="f0a8b-105">接受培训后，可用于标识用于应用敏感度Office、通信合规性策略和保留标签策略的项目。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="f0a8b-106">本文介绍了如何通过提供其他反馈来提高自定义可训练分类器以及一些预先训练的分类器的性能。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="f0a8b-107">若要详细了解不同类型的分类器，请参阅 [了解可训练分类器](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="f0a8b-108">观看此视频，简要了解调整和重新调试过程。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="f0a8b-109">你仍然需要阅读此完整文章才能获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="f0a8b-110">权限</span><span class="sxs-lookup"><span data-stu-id="f0a8b-110">Permissions</span></span>

<span data-ttu-id="f0a8b-111">若要访问分类器Microsoft 365合规中心：</span><span class="sxs-lookup"><span data-stu-id="f0a8b-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="f0a8b-112">要求合规性管理员角色或合规性数据管理员对分类器进行培训</span><span class="sxs-lookup"><span data-stu-id="f0a8b-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="f0a8b-113">在这些情况下，你需要具有这些权限的帐户才能使用分类器：</span><span class="sxs-lookup"><span data-stu-id="f0a8b-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="f0a8b-114">保留标签策略方案：记录管理和保留管理角色</span><span class="sxs-lookup"><span data-stu-id="f0a8b-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="f0a8b-115">总体工作流</span><span class="sxs-lookup"><span data-stu-id="f0a8b-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0a8b-116">在内容资源管理器中提供反馈，以自动应用保留标签策略Exchange项并使用分类器作为条件。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="f0a8b-117">**如果没有保留策略，该保留策略自动将保留标签应用于Exchange并使用分类器作为条件，请在此处停止。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="f0a8b-118">使用分类器时，可能需要提高分类器所分类的精度。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="f0a8b-119">为此，可评估对已标识为匹配项或不匹配项进行的分类质量。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="f0a8b-120">对分类器进行 30 次评估后，它将接受该反馈并自动自我重新培训。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="f0a8b-121">若要了解有关重新设置分类器的整体工作流的更多信息，请参阅用于重新设置 [分类器的流程](classifier-learn-about.md#retraining-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="f0a8b-122">必须先发布并使用分类器，然后才能重新设置分类器。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="f0a8b-123">如何重新训练内容资源管理器中的分类器</span><span class="sxs-lookup"><span data-stu-id="f0a8b-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="f0a8b-124">使用合规性管理员Microsoft 365安全管理员角色访问权限登录到合规性中心，然后打开Microsoft 365 **中心**  >  **数据** 分类  >  **内容资源管理器"。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="f0a8b-125">在"**筛选标签、信息类型** 或类别"列表下，展开 **"可训练分类器"。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0a8b-126">聚合项目最多可能需要 8 天才能显示在可训练分类器标题下。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="f0a8b-127">选择在自动应用保留标签策略中使用的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="f0a8b-128">这是你要提供反馈的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a8b-129">如果某个项目在"保留标签"列中有一个条目，则意味着该项目被分类为 `match` 。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="f0a8b-130">如果某个项目在"保留标签"列中没有条目，则意味着该项目被分类为 `close match` 。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="f0a8b-131">通过提供有关项目的反馈，可以最大提高分类器 `close match` 精度。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="f0a8b-132">选择一个项目并打开它。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="f0a8b-133">通过选择所有项目，然后在命令栏中选择"改进分类"，可以同时 **提供多个项目** 的反馈。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="f0a8b-134">选择 **"提供反馈"。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="f0a8b-135">在"**详细反馈"** 窗格中，如果项目为真正的正数，请选择"匹配 **"。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="f0a8b-136">如果项目为误报，即分类中未正确包含，请选择"**不匹配"。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="f0a8b-137">如果有另一个分类器更适用于该项目，您可以从"建议其他可训练分类器"**列表中选择它。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="f0a8b-138">这将触发其他分类器来评估该项目。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="f0a8b-139">选择 **"发送** 反馈"发送对 `match` 、分类的评估， `not a match` 并推荐其他可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="f0a8b-140">向分类器提供 30 个反馈实例后，分类器将自动重新播放。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="f0a8b-141">重新培训可能需要 1 到 4 个小时。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="f0a8b-142">每天只能重新对分类器进行两次重新分类。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0a8b-143">此信息将转到租户中的分类器 **，不会返回到 Microsoft。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="f0a8b-144">打开 **可训练分类器**。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="f0a8b-145">通信合规性策略中使用的分类器将显示在"重新培训" **标题** 下。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![正在重新分类状态的分类器](../media/classifier-retraining.png)

11. <span data-ttu-id="f0a8b-147">完成重新培训后，选择分类器以打开重新培训概述。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分类器重新分类结果概述](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="f0a8b-149">查看建议的操作，以及分类器重新更新和当前发布的版本预测比较。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="f0a8b-150">如果对重新发布的结果感到满意，请选择"**重新发布"。**</span><span class="sxs-lookup"><span data-stu-id="f0a8b-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="f0a8b-151">如果您对重新设置的结果不满意，可以选择在内容资源管理器界面中向分类器提供其他反馈，并开始另一个重新设置循环，或者不执行任何操作，在这种情况下将继续使用当前发布的分类器版本。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Content Explorer interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="f0a8b-152">有关重新发布建议的详细信息</span><span class="sxs-lookup"><span data-stu-id="f0a8b-152">Details on republishing recommendations</span></span>

<span data-ttu-id="f0a8b-153">下面提供一些有关我们如何重新发布重新发布的分类器或建议进一步重新编制的建议的信息。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="f0a8b-154">这需要更深入地了解可训练分类器如何工作。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="f0a8b-155">经过重新测试后，我们将评估具有反馈的项以及最初用于训练分类器的任何项上的分类器性能。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="f0a8b-156">对于内置模型，用于训练分类器的项目是 Microsoft 用于生成模型的项目。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="f0a8b-157">对于自定义模型，原始培训中使用的分类器项目来自已添加用于测试和审阅的网站。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="f0a8b-158">我们将比较经过重新检查和发布的分类器这两组项目的性能数字，以提供有关重新发布是否有改进的建议。</span><span class="sxs-lookup"><span data-stu-id="f0a8b-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="f0a8b-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0a8b-159">See also</span></span>

- [<span data-ttu-id="f0a8b-160">了解可训练的分类器</span><span class="sxs-lookup"><span data-stu-id="f0a8b-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="f0a8b-161">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="f0a8b-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)