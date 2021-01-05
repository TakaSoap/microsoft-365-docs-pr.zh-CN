---
title: 如何在内容资源管理器中重新分类分类器
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
ms.openlocfilehash: 786ebb682e9cdd96c0c6503294bd4f316f777f68
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752617"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="f5fa8-103">如何在内容资源管理器中重新分类分类器</span><span class="sxs-lookup"><span data-stu-id="f5fa8-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="f5fa8-104">Microsoft 365 可训练分类器是一种工具，你可以训练它，通过提供要查看的示例来识别各种类型的内容。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="f5fa8-105">接受培训后，可以使用它标识用于应用 Office 敏感度标签、通信合规性策略和保留标签策略的项目。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="f5fa8-106">本文介绍了如何通过提供其他反馈来提高自定义可训练分类器以及一些预先训练的分类器的性能。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="f5fa8-107">若要详细了解不同类型的分类器，请参阅"[了解可训练分类器"。](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="f5fa8-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="f5fa8-108">权限</span><span class="sxs-lookup"><span data-stu-id="f5fa8-108">Permissions</span></span>

<span data-ttu-id="f5fa8-109">若要访问 Microsoft 365 合规中心中的分类器：</span><span class="sxs-lookup"><span data-stu-id="f5fa8-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="f5fa8-110">要求合规性管理员角色或合规性数据管理员对分类器进行培训</span><span class="sxs-lookup"><span data-stu-id="f5fa8-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="f5fa8-111">在这些情况下，你需要具有这些权限的帐户才能使用分类器：</span><span class="sxs-lookup"><span data-stu-id="f5fa8-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="f5fa8-112">保留标签策略方案：记录管理和保留管理角色</span><span class="sxs-lookup"><span data-stu-id="f5fa8-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="f5fa8-113">总体工作流</span><span class="sxs-lookup"><span data-stu-id="f5fa8-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5fa8-114">您可以在内容资源管理器中提供反馈，以将保留标签策略自动应用于 Exchange 项目，并使用分类器作为条件。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="f5fa8-115">**如果没有将保留标签自动应用于 Exchange 项目并使用分类器作为条件的保留策略，请在此处停止。**</span><span class="sxs-lookup"><span data-stu-id="f5fa8-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="f5fa8-116">使用分类器时，你可能希望提高分类的精度。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="f5fa8-117">为此，您可以评估针对其标识为匹配或不匹配的项目进行的分类的质量。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="f5fa8-118">为分类器进行 30 次评估后，它接受该反馈并自动自我调整。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="f5fa8-119">若要了解有关重新设置分类器的总体工作流，请参阅用于重新设置分类器 [的过程流](classifier-learn-about.md#retraining-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="f5fa8-120">分类器必须先发布并使用，然后才能重新进行分类。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="f5fa8-121">如何在内容资源管理器中重新分类分类器</span><span class="sxs-lookup"><span data-stu-id="f5fa8-121">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="f5fa8-122">使用合规性管理员或安全管理员角色访问权限登录到 Microsoft 365 合规中心，并打开 **Microsoft 365 合规** 中心  >  **数据分类**  >  **内容资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="f5fa8-123">在 **标签、信息类型** 或类别列表上的筛选器下，展开 **可训练分类器**。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5fa8-124">聚合项目最多可能需要八天才能显示在可训练分类器标题下。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="f5fa8-125">选择在自动应用保留标签策略中使用的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="f5fa8-126">这是你要提供反馈的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="f5fa8-127">如果某个项目在"保留" **标签列中有** 一个条目，则意味着该项目被分类为 `match` 。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="f5fa8-128">如果某个项目在"保留标签"列中没有条目，则意味着该项目被分类为 `close match` 。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="f5fa8-129">通过提供有关项目的反馈，可以最大提高分类器 `close match` 精度。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="f5fa8-130">选择一个项目并打开它。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="f5fa8-131">可以通过选择所有项，然后在命令栏中选择"改进分类"来同时提供 **对多个项目** 的反馈。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="f5fa8-132">选择 **"提供反馈"。**</span><span class="sxs-lookup"><span data-stu-id="f5fa8-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="f5fa8-133">在 **"详细反馈"** 窗格中，如果项目为真正，请选择"**匹配"。**</span><span class="sxs-lookup"><span data-stu-id="f5fa8-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="f5fa8-134">如果项目为误报，即类别未正确包含，请选择"**不匹配"。**</span><span class="sxs-lookup"><span data-stu-id="f5fa8-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="f5fa8-135">如果有另一个分类器更适用于该项目，您可以从"建议 **其他可** 训练分类器"列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="f5fa8-136">这将触发其他分类器来评估项目。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="f5fa8-137">选择 **"发送反馈** "以发送对分类的评估， `match` `not a match` 并推荐其他可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="f5fa8-138">向分类器提供 30 个反馈实例后，分类器将自动重新播放。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="f5fa8-139">重新培训可能需要 1 到 4 个小时。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="f5fa8-140">分类器每天只能重新训练两次。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5fa8-141">此信息将转到租户中的分类器 **，不会返回到 Microsoft。**</span><span class="sxs-lookup"><span data-stu-id="f5fa8-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="f5fa8-142">打开 **可训练分类器**。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-142">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="f5fa8-143">通信合规性策略中使用的分类器将显示在重新培训 **标题** 下。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![正在重新分类状态的分类器](../media/classifier-retraining.png)

11. <span data-ttu-id="f5fa8-145">完成重新培训后，选择分类器打开培训概述。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分类器重新分析结果概述](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="f5fa8-147">查看建议的操作，以及分类器经过重新审阅和当前发布的版本的预测比较。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="f5fa8-148">如果你对重新设置的结果感到满意，请选择 **"重新发布"。**</span><span class="sxs-lookup"><span data-stu-id="f5fa8-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="f5fa8-149">如果对重新设置的结果不满意，可以选择在通信合规性界面中向分类器提供其他反馈，并开始另一个改进周期，或者不执行任何操作，在这种情况下将继续使用当前发布的分类器版本。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="f5fa8-150">有关重新发布建议的详细信息</span><span class="sxs-lookup"><span data-stu-id="f5fa8-150">Details on republishing recommendations</span></span>

<span data-ttu-id="f5fa8-151">下面是一些有关我们如何制定重新发布经过重新分析的分类器的建议或建议进一步重新编制的建议的信息。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="f5fa8-152">这需要更深入地了解可训练分类器如何工作。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="f5fa8-153">在重新测试后，我们将评估分类器对具有反馈的项以及最初用于训练分类器的任何项的性能。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="f5fa8-154">对于内置模型，用于训练分类器的项目是 Microsoft 用来生成模型的项目。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="f5fa8-155">对于自定义模型，原始培训中使用的分类器项目来自已添加用于测试和审阅的网站。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="f5fa8-156">我们将比较经过优化和发布的分类器的项目集的性能数字，以提供有关重新发布是否有改进的建议。</span><span class="sxs-lookup"><span data-stu-id="f5fa8-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="f5fa8-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5fa8-157">See also</span></span>

- [<span data-ttu-id="f5fa8-158">了解可训练分类器</span><span class="sxs-lookup"><span data-stu-id="f5fa8-158">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="f5fa8-159">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="f5fa8-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
