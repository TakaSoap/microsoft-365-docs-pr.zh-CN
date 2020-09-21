---
title: '如何重新培训通信合规性 (预览中的分类器) '
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
description: 了解如何在通信合规性中向 trainable 分类器提供反馈。
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132299"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a><span data-ttu-id="9061b-103">如何重新培训通信合规性 (预览中的分类器) </span><span class="sxs-lookup"><span data-stu-id="9061b-103">How to retrain a classifier in communications compliance (preview)</span></span>

<span data-ttu-id="9061b-104">Microsoft 365 trainable 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以进行培训以识别这些类型的内容。</span><span class="sxs-lookup"><span data-stu-id="9061b-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="9061b-105">经过培训后，您可以使用它来确定应用 Office 灵敏度标签、通信合规性策略和保留标签策略的项目。</span><span class="sxs-lookup"><span data-stu-id="9061b-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="9061b-106">本文介绍了如何通过提供其他反馈来提高自定义 trainable 分类器和某些预先培训的分类程序的性能。</span><span class="sxs-lookup"><span data-stu-id="9061b-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="9061b-107">若要了解有关不同类型的分类器的详细信息，请参阅 [了解 trainable 类元 (preview) ](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="9061b-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="9061b-108">权限</span><span class="sxs-lookup"><span data-stu-id="9061b-108">Permissions</span></span>

<span data-ttu-id="9061b-109">要访问 Microsoft 365 合规性中心中的分类器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9061b-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="9061b-110">合规性管理员角色或合规性数据管理员是培训分类器所必需的</span><span class="sxs-lookup"><span data-stu-id="9061b-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="9061b-111">在这些情况下，您需要具有这些权限的帐户才能使用分类器：</span><span class="sxs-lookup"><span data-stu-id="9061b-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="9061b-112">通信合规性策略方案：内部人员风险管理管理员、监管审核管理员</span><span class="sxs-lookup"><span data-stu-id="9061b-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="9061b-113">整体工作流</span><span class="sxs-lookup"><span data-stu-id="9061b-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9061b-114">在使用分类器作为条件的合规性解决方案中提供反馈。</span><span class="sxs-lookup"><span data-stu-id="9061b-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="9061b-115">**如果您没有使用分类器作为条件的通信合规性策略，请在此处停止。**</span><span class="sxs-lookup"><span data-stu-id="9061b-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="9061b-116">在使用分类器时，您可能需要增加所进行的分类的精度。</span><span class="sxs-lookup"><span data-stu-id="9061b-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="9061b-117">为此，请评估为其标识为匹配或不匹配的项目所做分类的质量。</span><span class="sxs-lookup"><span data-stu-id="9061b-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="9061b-118">在对分类器进行30个评估之后，它将接受反馈并自动 retrains 自身。</span><span class="sxs-lookup"><span data-stu-id="9061b-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="9061b-119">若要了解有关重新培训分类器的整个工作流的详细信息，请参阅 [Process flow for 可再培训分类器](classifier-learn-about.md#retraining-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="9061b-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="9061b-120">分类器必须已发布且在可 retrained 之前使用。</span><span class="sxs-lookup"><span data-stu-id="9061b-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a><span data-ttu-id="9061b-121">如何重新培训通信合规性策略中的分类器 (预览) </span><span class="sxs-lookup"><span data-stu-id="9061b-121">How to retrain a classifier in communication compliance policies (preview)</span></span>

1. <span data-ttu-id="9061b-122">打开使用分类器作为条件的通信合规性策略，并从 " **待定** " 列表中选择已标识的项之一。</span><span class="sxs-lookup"><span data-stu-id="9061b-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="9061b-123">选择省略号并 **改进分类**。</span><span class="sxs-lookup"><span data-stu-id="9061b-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="9061b-124">在 " **详细反馈** " 窗格中，如果项目是真正的正数，请选择 " **匹配**"。</span><span class="sxs-lookup"><span data-stu-id="9061b-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="9061b-125">如果项目是误报，则表示它不正确包含在类别中，请选择 " **不匹配**"。</span><span class="sxs-lookup"><span data-stu-id="9061b-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="9061b-126">如果有更适合该项目的另一个分类器，则可以从 " **建议其他 trainable 类元** " 列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="9061b-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="9061b-127">这将触发其他分类器来评估项目。</span><span class="sxs-lookup"><span data-stu-id="9061b-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="9061b-128">您可以通过选择所有项目并在命令栏中选择 " **提供详细反馈** " 来同时提供对多个项目的反馈。</span><span class="sxs-lookup"><span data-stu-id="9061b-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="9061b-129">选择 " **发送反馈** " 以发送对 `match` 、 `not a match` 分类和建议其他 trainable 类元的评估。</span><span class="sxs-lookup"><span data-stu-id="9061b-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="9061b-130">向分类器提供30个反馈的实例后，它将自动重新培训。</span><span class="sxs-lookup"><span data-stu-id="9061b-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="9061b-131">重新培训可能需要1-4 小时。</span><span class="sxs-lookup"><span data-stu-id="9061b-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="9061b-132">分类器每日只能有两次 retrained。</span><span class="sxs-lookup"><span data-stu-id="9061b-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9061b-133">此信息会转到租户中的分类器，而 **不会返回到 Microsoft**。</span><span class="sxs-lookup"><span data-stu-id="9061b-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="9061b-134">打开**Microsoft 365 合规性中心**中的 "**数据分类**" 页。</span><span class="sxs-lookup"><span data-stu-id="9061b-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="9061b-135">打开 \*\*Trainable 类元 (预览) \*\*。</span><span class="sxs-lookup"><span data-stu-id="9061b-135">Open **Trainable classifiers (preview)**.</span></span>
8. <span data-ttu-id="9061b-136">在通信合规性策略中使用的分类符将显示在 " **重新培训** " 标题下。</span><span class="sxs-lookup"><span data-stu-id="9061b-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![重新培训状态中的分类符](../media/classifier-retraining.png)

9. <span data-ttu-id="9061b-138">重新培训完成后，选择分类器打开重新培训概述。</span><span class="sxs-lookup"><span data-stu-id="9061b-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分类器重新培训结果概述](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="9061b-140">查看建议的操作，以及分类器的 retrained 和当前已发布版本的预测比较。</span><span class="sxs-lookup"><span data-stu-id="9061b-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="9061b-141">如果您对重新培训的结果感到满意，请选择 " **重新发布**"。</span><span class="sxs-lookup"><span data-stu-id="9061b-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="9061b-142">如果对重新培训的结果不满意，可以选择在通信合规性接口中向分类器提供其他反馈，并启动另一个重新培训周期，或者不执行任何操作，这种情况下将继续使用分类器的当前已发布版本。</span><span class="sxs-lookup"><span data-stu-id="9061b-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="9061b-143">有关重新发布建议的详细信息</span><span class="sxs-lookup"><span data-stu-id="9061b-143">Details on republishing recommendations</span></span>

<span data-ttu-id="9061b-144">以下是有关我们如何阐明重新发布 retrained 分类符或建议进一步重新培训的建议的一些信息。</span><span class="sxs-lookup"><span data-stu-id="9061b-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="9061b-145">这需要对 trainable 分类器的工作方式稍有深入了解。</span><span class="sxs-lookup"><span data-stu-id="9061b-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="9061b-146">重新培训后，我们会使用反馈以及任何最初用于培训分类器的项目来评估分类器的性能。</span><span class="sxs-lookup"><span data-stu-id="9061b-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="9061b-147">对于内置模型，用于培训分类器的项是 Microsoft 用来生成模型的项。</span><span class="sxs-lookup"><span data-stu-id="9061b-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="9061b-148">对于自定义模型，在原始培训中使用的项目分类器来自您为进行测试和查看而添加的网站。</span><span class="sxs-lookup"><span data-stu-id="9061b-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="9061b-149">我们比较 retrained 和已发布分类器的两组项目的性能数字，以提供有关是否有改进重新发布的建议。</span><span class="sxs-lookup"><span data-stu-id="9061b-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="9061b-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9061b-150">See also</span></span>

- [<span data-ttu-id="9061b-151">了解 trainable 分类 (预览) </span><span class="sxs-lookup"><span data-stu-id="9061b-151">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="9061b-152">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="9061b-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
