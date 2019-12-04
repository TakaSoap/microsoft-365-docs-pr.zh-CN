---
title: 创建 trainable 分类器（预览）
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 当 "准备就绪" 框中的一个可供使用时，使用 trainable 分类器将无法满足您的需求。 Microsoft 365 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以对其进行训练以识别各种类型的内容。 本主题介绍如何创建自定义分类器。
ms.openlocfilehash: cb3cda9777d692a56263e92cd908eb09bfa99895
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813370"
---
# <a name="creating-a-trainable-classifier-preview"></a><span data-ttu-id="8a47d-105">创建 trainable 分类器（预览）</span><span class="sxs-lookup"><span data-stu-id="8a47d-105">Creating a trainable classifier (preview)</span></span>

<span data-ttu-id="8a47d-106">当一个现成的类元中的一个无法满足您的需求时，使用 trainable 分类程序。</span><span class="sxs-lookup"><span data-stu-id="8a47d-106">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="8a47d-107">Microsoft 365 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以对其进行训练以识别各种类型的内容。</span><span class="sxs-lookup"><span data-stu-id="8a47d-107">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="8a47d-108">培训分类器首先需要为其提供人工挑选的示例，并正确匹配类别。</span><span class="sxs-lookup"><span data-stu-id="8a47d-108">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="8a47d-109">然后，在处理完这些后，通过为其混合使用正负样本来测试预测。</span><span class="sxs-lookup"><span data-stu-id="8a47d-109">Then, after it has processed those, you test the predictions by giving it a mix of positive and negative samples.</span></span>

<span data-ttu-id="8a47d-110">若要了解有关不同类型的分类器的详细信息，请参阅[trainable 类元入门（预览）](classifier-getting-started-with.md)</span><span class="sxs-lookup"><span data-stu-id="8a47d-110">To learn more about the different types of classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md)</span></span>

<span data-ttu-id="8a47d-111">此时间线反映了一个示例部署。</span><span class="sxs-lookup"><span data-stu-id="8a47d-111">This timeline reflects a sample deployment.</span></span>

![trainable-分类轴](media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="8a47d-113">第一次需要 trainable 分类器时，自愿加入是必需的。</span><span class="sxs-lookup"><span data-stu-id="8a47d-113">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="8a47d-114">Microsoft 365 需要在12天内完成组织内容的基准评估。</span><span class="sxs-lookup"><span data-stu-id="8a47d-114">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span>

## <a name="seed-content"></a><span data-ttu-id="8a47d-115">种子内容</span><span class="sxs-lookup"><span data-stu-id="8a47d-115">Seed content</span></span>

<span data-ttu-id="8a47d-116">当您希望 trainable 分类程序独立且准确地将项目标识为特定的内容类别时，您首先必须向其提供类别中的内容类型的多个示例。</span><span class="sxs-lookup"><span data-stu-id="8a47d-116">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="8a47d-117">此示例向 trainable 分类符进行的馈送称为*种子设定*。</span><span class="sxs-lookup"><span data-stu-id="8a47d-117">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="8a47d-118">种子内容由人选择，并被判定为表示内容的类别。</span><span class="sxs-lookup"><span data-stu-id="8a47d-118">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="8a47d-119">您需要至少有50个肯定样本以及多达500个。</span><span class="sxs-lookup"><span data-stu-id="8a47d-119">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="8a47d-120">Trainable 分类器将处理最多500个最近创建的示例（通过文件创建的日期/时间戳）。</span><span class="sxs-lookup"><span data-stu-id="8a47d-120">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="8a47d-121">提供的示例越多，分类器将产生的预测越精确。</span><span class="sxs-lookup"><span data-stu-id="8a47d-121">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

## <a name="testing-content"></a><span data-ttu-id="8a47d-122">测试内容</span><span class="sxs-lookup"><span data-stu-id="8a47d-122">Testing content</span></span>

<span data-ttu-id="8a47d-123">在 trainable 分类器处理足够的正样本以生成预测模型后，需要测试它所做的预测，以确定分类器能否正确区分与类别和项目不匹配的项目。</span><span class="sxs-lookup"><span data-stu-id="8a47d-123">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="8a47d-124">为此，请将其放在另一组中，这是一组人工挑选的内容，这些内容由应归入的类别和样本组成的样本组成。</span><span class="sxs-lookup"><span data-stu-id="8a47d-124">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="8a47d-125">在处理这些工作后，您需要手动浏览结果，并验证每个预测是否正确、不正确或是否不确定。</span><span class="sxs-lookup"><span data-stu-id="8a47d-125">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="8a47d-126">Trainable 分类器使用此反馈来改进其预测模型。</span><span class="sxs-lookup"><span data-stu-id="8a47d-126">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="8a47d-127">为获得最佳结果，您的测试示例集中有10000个项目，并且这些项目的分布为正和负匹配。</span><span class="sxs-lookup"><span data-stu-id="8a47d-127">For best results, have 10,000 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="8a47d-128">如何创建 trainable 类元</span><span class="sxs-lookup"><span data-stu-id="8a47d-128">How to create a trainable classifier</span></span>

1. <span data-ttu-id="8a47d-129">在50-500 种子内容项之间进行收集。</span><span class="sxs-lookup"><span data-stu-id="8a47d-129">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="8a47d-130">这些示例必须是那些强烈表示您希望 trainable 分类程序正确标识为分类类别中的内容类型的示例。</span><span class="sxs-lookup"><span data-stu-id="8a47d-130">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="8a47d-131">有关受支持的文件类型，请参阅[SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。</span><span class="sxs-lookup"><span data-stu-id="8a47d-131">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a47d-132">种子和测试示例项不得加密且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="8a47d-132">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a47d-133">请确保种子集中的项是类别的**强**示例。</span><span class="sxs-lookup"><span data-stu-id="8a47d-133">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="8a47d-134">Trainable 分类器最初根据您对其进行种子设定的内容生成模型。</span><span class="sxs-lookup"><span data-stu-id="8a47d-134">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="8a47d-135">分类器假定所有种子示例都是强的，并且无法知道样本是否为类别的弱匹配或负匹配。</span><span class="sxs-lookup"><span data-stu-id="8a47d-135">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="8a47d-136">将种子内容放在专门用于保存*种子内容*的 SharePoint Online 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8a47d-136">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="8a47d-137">请记下网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="8a47d-137">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="8a47d-138">如果为种子数据创建新的网站和文件夹，则在创建将使用该种子数据的 trainable 分类器之前，至少要为该位置编制索引一个小时。</span><span class="sxs-lookup"><span data-stu-id="8a47d-138">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="8a47d-139">使用合规性管理或安全管理员角色访问和开放**microsoft 365 合规性中心**或**microsoft 365 安全中心** > **数据分类**登录 microsoft 365 合规性中心</span><span class="sxs-lookup"><span data-stu-id="8a47d-139">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="8a47d-140">选择 " **Trainable 类元**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8a47d-140">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="8a47d-141">选择 "**创建 trainable 分类器**"。</span><span class="sxs-lookup"><span data-stu-id="8a47d-141">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="8a47d-142">为您希望此 trainable 分类`Name`器标识`Description`的项目类别的 "" 和 "" 字段填写相应的值。</span><span class="sxs-lookup"><span data-stu-id="8a47d-142">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="8a47d-143">为第2步中的种子内容网站输入确切的 SharePoint Online 网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="8a47d-143">Enter the exact SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="8a47d-144">选择`Add`。</span><span class="sxs-lookup"><span data-stu-id="8a47d-144">Choose `Add`.</span></span>

8. <span data-ttu-id="8a47d-145">查看设置并选择`Create trainable classifier`。</span><span class="sxs-lookup"><span data-stu-id="8a47d-145">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="8a47d-146">在24小时内，trainable 分类器将处理种子数据并生成一个预测模型。</span><span class="sxs-lookup"><span data-stu-id="8a47d-146">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="8a47d-147">分类器状态是`In progress`在处理种子数据时。</span><span class="sxs-lookup"><span data-stu-id="8a47d-147">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="8a47d-148">分类器处理完种子数据后，状态将更改为`Need test items`。</span><span class="sxs-lookup"><span data-stu-id="8a47d-148">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="8a47d-149">您现在可以通过选择分类器查看详细信息页。</span><span class="sxs-lookup"><span data-stu-id="8a47d-149">You can now view the details page by choosing the classifier.</span></span>


![trainable 分类器准备好进行测试](media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="8a47d-151">至少收集200个测试内容项。</span><span class="sxs-lookup"><span data-stu-id="8a47d-151">Collect at least 200 test content items.</span></span> <span data-ttu-id="8a47d-152">Microsoft 建议10000以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="8a47d-152">Microsoft recommends 10,000 for best results.</span></span> <span data-ttu-id="8a47d-153">这些项目应混合成强阳性的项目，而这些项目的性质不是很明显。</span><span class="sxs-lookup"><span data-stu-id="8a47d-153">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="8a47d-154">有关受支持的文件类型，请参阅[SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。</span><span class="sxs-lookup"><span data-stu-id="8a47d-154">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a47d-155">示例项目不能加密且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="8a47d-155">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="8a47d-156">将测试内容放置在专门用于保存*测试内容*的 SharePoint Online 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8a47d-156">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="8a47d-157">请记下 SharePoint Online 网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="8a47d-157">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="8a47d-158">如果为测试数据创建新的网站和文件夹，则在创建将使用该种子数据的 trainable 分类程序之前，至少要为该位置编制索引一个小时。</span><span class="sxs-lookup"><span data-stu-id="8a47d-158">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="8a47d-159">选择`Add items to test`。</span><span class="sxs-lookup"><span data-stu-id="8a47d-159">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="8a47d-160">为第12步中的测试内容网站输入确切的 SharePoint Online 网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="8a47d-160">Enter the exact SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="8a47d-161">选择`Add`。</span><span class="sxs-lookup"><span data-stu-id="8a47d-161">Choose `Add`.</span></span>

15. <span data-ttu-id="8a47d-162">通过选择`Done`完成向导。</span><span class="sxs-lookup"><span data-stu-id="8a47d-162">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="8a47d-163">您的 trainable 分类器将需要一个小时来处理测试文件。</span><span class="sxs-lookup"><span data-stu-id="8a47d-163">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="8a47d-164">当 trainable 分类器处理完测试文件后，"详细信息" 页上的状态将更改`Ready to review`为。</span><span class="sxs-lookup"><span data-stu-id="8a47d-164">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="8a47d-165">如果需要增加测试样本大小，请选择`Add items to test`并允许 trainable 分类器处理其他项。</span><span class="sxs-lookup"><span data-stu-id="8a47d-165">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![准备查看屏幕截图](media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="8a47d-167">选择`Tested items to review` "选项卡" 以查看项目。</span><span class="sxs-lookup"><span data-stu-id="8a47d-167">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="8a47d-168">Microsoft 365 将一次显示30个项目。</span><span class="sxs-lookup"><span data-stu-id="8a47d-168">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="8a47d-169">查看它们，然后在`We predict this item is "Relevant". Do you agree?`框中选择`Yes` " `No`或`Not sure, skip to next item`" 或 "" 或 ""。</span><span class="sxs-lookup"><span data-stu-id="8a47d-169">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="8a47d-170">模型准确性在每30个项目后自动更新。</span><span class="sxs-lookup"><span data-stu-id="8a47d-170">Model accuracy is automatically updated after every 30 items.</span></span>

!["查看项目" 框](media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="8a47d-172">查看*至少200个*项目。</span><span class="sxs-lookup"><span data-stu-id="8a47d-172">Review *at least* 200 items.</span></span>

<!-- insert Analyze steps here-->

20. <span data-ttu-id="8a47d-173">继续查看，直到准确性达到至少70%， `Publish the classifier`状态为。 `Ready to use`</span><span class="sxs-lookup"><span data-stu-id="8a47d-173">Continue to review until the accuracy reaches at least 70% and the `Publish the classifier` status is `Ready to use`.</span></span>

![准确性并准备好发布](media/classifier-trainable-review-ready-to-publish.png)

21. <span data-ttu-id="8a47d-175">发布分类器。</span><span class="sxs-lookup"><span data-stu-id="8a47d-175">Publish the classifier.</span></span>

22. <span data-ttu-id="8a47d-176">一旦发布分类器，便可作为基于条件和[通信合规性](communication-compliance.md)的[自动应用保留标签策略](labels.md#applying-a-retention-label-automatically-based-on-conditions)中的条件。</span><span class="sxs-lookup"><span data-stu-id="8a47d-176">Once published your classifier will be available as a condition in the [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and in [Communication compliance](communication-compliance.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="8a47d-177">分类器发布后，将无法通过任何其他培训，因此请务必确保您已经测试和检查了尽可能多的项目，以确保准确性尽可能高。</span><span class="sxs-lookup"><span data-stu-id="8a47d-177">Once a classifier is published, it can't go through any additional training, so be very sure that you have tested and reviewed as many items as possible to ensure that the accuracy is as high as possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a47d-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a47d-178">See also</span></span>

- [<span data-ttu-id="8a47d-179">可训练分类器入门（预览）</span><span class="sxs-lookup"><span data-stu-id="8a47d-179">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="8a47d-180">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="8a47d-180">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
