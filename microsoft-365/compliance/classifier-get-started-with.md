---
title: 可训练分类器（预览版）入门
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
description: Microsoft 365 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以对其进行训练以识别各种类型的内容。 本文介绍如何创建和培训自定义分类器，以及如何重新培训它们以提高准确性。
ms.openlocfilehash: fd6bc68a8bc373d9d02e23b73971b28ce8761cd9
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132312"
---
# <a name="get-started-with-trainable-classifiers-preview"></a><span data-ttu-id="13d62-104">可训练分类器（预览版）入门</span><span class="sxs-lookup"><span data-stu-id="13d62-104">Get started with trainable classifiers (preview)</span></span>

<span data-ttu-id="13d62-105">Microsoft 365 trainable 分类器是一种工具，通过使其示例能够查看各种类型的内容，您可以进行培训以识别这些类型的内容。</span><span class="sxs-lookup"><span data-stu-id="13d62-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="13d62-106">经过培训后，您可以使用它来确定应用 Office 灵敏度标签、通信合规性策略和保留标签策略的项目。</span><span class="sxs-lookup"><span data-stu-id="13d62-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="13d62-107">创建自定义 trainable 分类器首先涉及为其提供人工挑选的示例，并与类别正确匹配。</span><span class="sxs-lookup"><span data-stu-id="13d62-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="13d62-108">然后，在处理这些程序后，通过为其提供混合的正负样本来测试该分类程序的预测能力。</span><span class="sxs-lookup"><span data-stu-id="13d62-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="13d62-109">本文介绍如何创建和培训自定义分类器，以及如何通过重新培训在其生命周期中提高自定义 trainable 分类器和预培训的分类器的性能。</span><span class="sxs-lookup"><span data-stu-id="13d62-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="13d62-110">若要了解有关不同类型的分类器的详细信息，请参阅 [了解 trainable 类元 (preview) ](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="13d62-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13d62-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="13d62-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="13d62-112">许可要求</span><span class="sxs-lookup"><span data-stu-id="13d62-112">Licensing requirements</span></span>

<span data-ttu-id="13d62-113">分类器是 Microsoft 365 E5 或 E5 合规性功能。</span><span class="sxs-lookup"><span data-stu-id="13d62-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="13d62-114">您必须拥有其中一种订阅才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="13d62-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="13d62-115">权限</span><span class="sxs-lookup"><span data-stu-id="13d62-115">Permissions</span></span>

<span data-ttu-id="13d62-116">若要访问 UI 中的分类器：</span><span class="sxs-lookup"><span data-stu-id="13d62-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="13d62-117">全局管理员需要自愿加入租户来创建自定义分类器</span><span class="sxs-lookup"><span data-stu-id="13d62-117">the Global admin needs to opt in for the tenant to create custom classifiers</span></span>
- <span data-ttu-id="13d62-118">合规性管理员角色或合规性数据管理员是培训分类器所必需的</span><span class="sxs-lookup"><span data-stu-id="13d62-118">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="13d62-119">在这些情况下，您需要具有这些权限的帐户才能使用分类器：</span><span class="sxs-lookup"><span data-stu-id="13d62-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="13d62-120">保留标签策略方案：记录管理和保留管理角色</span><span class="sxs-lookup"><span data-stu-id="13d62-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="13d62-121">敏感度标签策略方案：安全管理员、合规性管理员、合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="13d62-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="13d62-122">通信合规性策略方案：内部人员风险管理管理员、监管审核管理员</span><span class="sxs-lookup"><span data-stu-id="13d62-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="13d62-123">默认情况下，只有创建自定义分类器的用户才可以训练和查看该分类器所做的预测。</span><span class="sxs-lookup"><span data-stu-id="13d62-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span> <span data-ttu-id="13d62-124">如果您希望其他人能够培训和查看分类器预测，请参阅 [为他人定型和审阅权限](#give-others-train-and-review-rights)。</span><span class="sxs-lookup"><span data-stu-id="13d62-124">If you want others to be able to train and review classifier predictions, see [Give others train and review rights](#give-others-train-and-review-rights).</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="13d62-125">准备自定义 trainable 分类器</span><span class="sxs-lookup"><span data-stu-id="13d62-125">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="13d62-126">在进行深入研究之前，了解创建自定义 trainable 分类器所涉及的内容非常有用。</span><span class="sxs-lookup"><span data-stu-id="13d62-126">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="13d62-127">日程表</span><span class="sxs-lookup"><span data-stu-id="13d62-127">Timeline</span></span>

<span data-ttu-id="13d62-128">此时间线反映了 trainable 分类器的示例部署。</span><span class="sxs-lookup"><span data-stu-id="13d62-128">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-分类轴](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="13d62-130">第一次需要 trainable 分类器时，自愿加入是必需的。</span><span class="sxs-lookup"><span data-stu-id="13d62-130">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="13d62-131">Microsoft 365 需要在12天内完成组织内容的基准评估。</span><span class="sxs-lookup"><span data-stu-id="13d62-131">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="13d62-132">请与全局管理员联系以启动自愿加入过程。</span><span class="sxs-lookup"><span data-stu-id="13d62-132">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="13d62-133">整体工作流</span><span class="sxs-lookup"><span data-stu-id="13d62-133">Overall workflow</span></span>

<span data-ttu-id="13d62-134">若要了解有关创建自定义 trainable 分类器的整体工作流的详细信息，请参阅 [创建 customer trainable 类元的过程流](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="13d62-134">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span></span>

### <a name="seed-content"></a><span data-ttu-id="13d62-135">种子内容</span><span class="sxs-lookup"><span data-stu-id="13d62-135">Seed content</span></span>

<span data-ttu-id="13d62-136">当您希望 trainable 分类程序独立且准确地将项目标识为特定的内容类别时，您首先必须向其提供类别中的内容类型的多个示例。</span><span class="sxs-lookup"><span data-stu-id="13d62-136">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="13d62-137">此示例向 trainable 分类符进行的馈送称为 *种子设定*。</span><span class="sxs-lookup"><span data-stu-id="13d62-137">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="13d62-138">种子内容由人选择，并被判定为表示内容的类别。</span><span class="sxs-lookup"><span data-stu-id="13d62-138">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="13d62-139">您需要至少有50个肯定样本以及多达500个。</span><span class="sxs-lookup"><span data-stu-id="13d62-139">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="13d62-140">Trainable 分类器将最多处理500个最近创建的示例， (由文件创建的日期/时间戳) 。</span><span class="sxs-lookup"><span data-stu-id="13d62-140">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="13d62-141">提供的示例越多，分类器将产生的预测越精确。</span><span class="sxs-lookup"><span data-stu-id="13d62-141">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="13d62-142">测试内容</span><span class="sxs-lookup"><span data-stu-id="13d62-142">Testing content</span></span>

<span data-ttu-id="13d62-143">在 trainable 分类器处理足够的正样本以生成预测模型后，需要测试它所做的预测，以确定分类器能否正确区分与类别和项目不匹配的项目。</span><span class="sxs-lookup"><span data-stu-id="13d62-143">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="13d62-144">为此，请将其放在另一组中，这是一组人工挑选的内容，这些内容由应归入的类别和样本组成的样本组成。</span><span class="sxs-lookup"><span data-stu-id="13d62-144">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="13d62-145">在处理这些工作后，您需要手动浏览结果，并验证每个预测是否正确、不正确或是否不确定。</span><span class="sxs-lookup"><span data-stu-id="13d62-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="13d62-146">Trainable 分类器使用此反馈来改进其预测模型。</span><span class="sxs-lookup"><span data-stu-id="13d62-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="13d62-147">为获得最佳效果，测试示例集中至少有200个项目，并且这些项目的平均分布为正和负匹配。</span><span class="sxs-lookup"><span data-stu-id="13d62-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="13d62-148">如何创建 trainable 类元</span><span class="sxs-lookup"><span data-stu-id="13d62-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="13d62-149">在50-500 种子内容项之间进行收集。</span><span class="sxs-lookup"><span data-stu-id="13d62-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="13d62-150">这些示例必须是那些强烈表示您希望 trainable 分类程序正确标识为分类类别中的内容类型的示例。</span><span class="sxs-lookup"><span data-stu-id="13d62-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="13d62-151">有关受支持的文件类型，请参阅 [SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 。</span><span class="sxs-lookup"><span data-stu-id="13d62-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13d62-152">种子和测试示例项不得加密且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="13d62-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13d62-153">请确保种子集中的项是类别的 **强** 示例。</span><span class="sxs-lookup"><span data-stu-id="13d62-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="13d62-154">Trainable 分类器最初根据您对其进行种子设定的内容生成模型。</span><span class="sxs-lookup"><span data-stu-id="13d62-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="13d62-155">分类器假定所有种子示例都是强的，并且无法知道样本是否为类别的弱匹配或负匹配。</span><span class="sxs-lookup"><span data-stu-id="13d62-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="13d62-156">将种子内容放在专门用于保存 *种子内容*的 SharePoint Online 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="13d62-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="13d62-157">请记下网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="13d62-157">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="13d62-158">如果为种子数据创建新的网站和文件夹，则在创建将使用该种子数据的 trainable 分类器之前，至少要为该位置编制索引一个小时。</span><span class="sxs-lookup"><span data-stu-id="13d62-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="13d62-159">使用合规性管理或安全管理员角色访问和开放**microsoft 365 合规性中心**或**microsoft 365 安全中心**  >  **数据分类**登录 microsoft 365 合规性中心</span><span class="sxs-lookup"><span data-stu-id="13d62-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="13d62-160">选择 " **Trainable 类元** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="13d62-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="13d62-161">选择 " **创建 trainable 分类器**"。</span><span class="sxs-lookup"><span data-stu-id="13d62-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="13d62-162">为 `Name` `Description` 您希望此 trainable 分类器标识的项目类别的 "" 和 "" 字段填写相应的值。</span><span class="sxs-lookup"><span data-stu-id="13d62-162">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="13d62-163">从步骤2中的种子内容网站选取 SharePoint Online 网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="13d62-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="13d62-164">选择 `Add` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-164">Choose `Add`.</span></span>

8. <span data-ttu-id="13d62-165">查看设置并选择 `Create trainable classifier` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="13d62-166">在24小时内，trainable 分类器将处理种子数据并生成一个预测模型。</span><span class="sxs-lookup"><span data-stu-id="13d62-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="13d62-167">分类器状态是 `In progress` 在处理种子数据时。</span><span class="sxs-lookup"><span data-stu-id="13d62-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="13d62-168">分类器处理完种子数据后，状态将更改为 `Need test items` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="13d62-169">您现在可以通过选择分类器查看详细信息页。</span><span class="sxs-lookup"><span data-stu-id="13d62-169">You can now view the details page by choosing the classifier.</span></span>


![trainable 分类器准备好进行测试](../media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="13d62-171">至少收集200个测试内容项 (10000 最大) 以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="13d62-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="13d62-172">这些项目应混合成强阳性的项目，而这些项目的性质不是很明显。</span><span class="sxs-lookup"><span data-stu-id="13d62-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="13d62-173">有关受支持的文件类型，请参阅 [SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 。</span><span class="sxs-lookup"><span data-stu-id="13d62-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13d62-174">示例项目不能加密且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="13d62-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="13d62-175">将测试内容放置在专门用于保存 *测试内容*的 SharePoint Online 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="13d62-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="13d62-176">请记下 SharePoint Online 网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="13d62-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="13d62-177">如果为测试数据创建新的网站和文件夹，则在创建将使用该种子数据的 trainable 分类程序之前，至少要为该位置编制索引一个小时。</span><span class="sxs-lookup"><span data-stu-id="13d62-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="13d62-178">选择 `Add items to test` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="13d62-179">从步骤12中选择测试内容网站的 SharePoint Online 网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="13d62-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="13d62-180">选择 `Add` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-180">Choose `Add`.</span></span>

15. <span data-ttu-id="13d62-181">通过选择完成向导 `Done` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="13d62-182">您的 trainable 分类器将需要一个小时来处理测试文件。</span><span class="sxs-lookup"><span data-stu-id="13d62-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="13d62-183">当 trainable 分类器处理完测试文件后，"详细信息" 页上的状态将更改为 `Ready to review` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="13d62-184">如果需要增加测试样本大小，请选择 `Add items to test` 并允许 trainable 分类器处理其他项。</span><span class="sxs-lookup"><span data-stu-id="13d62-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![准备查看屏幕截图](../media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="13d62-186">选择 `Tested items to review` "选项卡" 以查看项目。</span><span class="sxs-lookup"><span data-stu-id="13d62-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="13d62-187">Microsoft 365 将一次显示30个项目。</span><span class="sxs-lookup"><span data-stu-id="13d62-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="13d62-188">查看它们，然后在框中选择 "或" 或 "" 或 "" `We predict this item is "Relevant". Do you agree?` `Yes` `No` `Not sure, skip to next item` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="13d62-189">模型准确性在每30个项目后自动更新。</span><span class="sxs-lookup"><span data-stu-id="13d62-189">Model accuracy is automatically updated after every 30 items.</span></span>

!["查看项目" 框](../media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="13d62-191">查看 *至少200个* 项目。</span><span class="sxs-lookup"><span data-stu-id="13d62-191">Review *at least* 200 items.</span></span> <span data-ttu-id="13d62-192">在准确性得分稳定之后，" **发布** " 选项将变为可用，分类器状态将会 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="13d62-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

![准确性分数并准备好发布](../media/classifier-trainable-review-ready-to-publish.png)

20. <span data-ttu-id="13d62-194">发布分类器。</span><span class="sxs-lookup"><span data-stu-id="13d62-194">Publish the classifier.</span></span>

21. <span data-ttu-id="13d62-195">一旦发布了分类符，就可以[使用敏感度标签作为 Office 自动标记](apply-sensitivity-label-automatically.md)中的条件，根据条件和[通信合规性](communication-compliance.md)[自动应用保留标签策略](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="13d62-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>

## <a name="give-others-train-and-review-rights"></a><span data-ttu-id="13d62-196">向其他人授予培训和审核权限</span><span class="sxs-lookup"><span data-stu-id="13d62-196">Give others train and review rights</span></span>

<span data-ttu-id="13d62-197">使用此过程可向他人授予培训、审阅和调整自定义 trainable 分类器的权限。</span><span class="sxs-lookup"><span data-stu-id="13d62-197">Use this procedure to give others permissions to train, review and tune your custom trainable classifier.</span></span>  
 
1. <span data-ttu-id="13d62-198">作为分类器的创建者，全局管理员或电子数据展示管理员使用 [连接到安全 & 合规性中心 powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true)中的过程连接到合规中心（使用 PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="13d62-198">As the creator of the classifier, a global admin or eDiscovery admin connect to the Compliance center using PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span></span>
2. <span data-ttu-id="13d62-199">运行此命令：</span><span class="sxs-lookup"><span data-stu-id="13d62-199">Run this command:</span></span>
```powershell
Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
```
<span data-ttu-id="13d62-200">例如：`Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`</span><span class="sxs-lookup"><span data-stu-id="13d62-200">For example: `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`</span></span>

<span data-ttu-id="13d62-201">您可以多次运行此命令以添加多个用户。</span><span class="sxs-lookup"><span data-stu-id="13d62-201">You can run this command multiple times to add multiple users.</span></span> <span data-ttu-id="13d62-202">请注意，您只能将 Exchange Online Protection (EOP) 角色组和 Azure 角色组。</span><span class="sxs-lookup"><span data-stu-id="13d62-202">Note that you can only add Exchange Online Protection (EOP) Role Groups and not Azure Role Groups.</span></span>
