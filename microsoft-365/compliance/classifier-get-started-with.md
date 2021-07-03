---
title: 可训练的分类器入门
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 一Microsoft 365分类器是一种工具，你可以训练它，通过提供要查看的示例来识别各种类型的内容。 本文演示如何创建和训练自定义分类器以及如何重新设置它们以提高准确性。
ms.openlocfilehash: 3053e5154fb4e1ff39ce7db366ce4679bbb8911d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286629"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="4401d-104">可训练的分类器入门</span><span class="sxs-lookup"><span data-stu-id="4401d-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="4401d-105">可Microsoft 365分类器是一种工具，你可以训练它，通过提供要查看的示例来识别各种类型的内容。</span><span class="sxs-lookup"><span data-stu-id="4401d-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="4401d-106">接受培训后，可用于标识用于应用敏感度Office、通信合规性策略和保留标签策略的项目。</span><span class="sxs-lookup"><span data-stu-id="4401d-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="4401d-107">首先，创建自定义可训练分类器涉及为分类器提供人工选取且与类别积极匹配的示例。</span><span class="sxs-lookup"><span data-stu-id="4401d-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="4401d-108">然后，处理完这些样本后，通过向分类器提供正样本和负样本的组合来测试分类器预测的能力。</span><span class="sxs-lookup"><span data-stu-id="4401d-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="4401d-109">本文介绍了如何创建和训练自定义分类器，以及如何在自定义可训练分类器及其生存期内通过重新培训提高这些分类器的性能。</span><span class="sxs-lookup"><span data-stu-id="4401d-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="4401d-110">若要详细了解不同类型的分类器，请参阅 [了解可训练分类器](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="4401d-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="4401d-111">观看此视频，了解创建可训练分类器的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="4401d-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="4401d-112">你仍然需要阅读此完整文章才能获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="4401d-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="4401d-113">必备条件</span><span class="sxs-lookup"><span data-stu-id="4401d-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="4401d-114">许可要求</span><span class="sxs-lookup"><span data-stu-id="4401d-114">Licensing requirements</span></span>

<span data-ttu-id="4401d-115">分类器是Microsoft 365 E5 E5 合规性功能。</span><span class="sxs-lookup"><span data-stu-id="4401d-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="4401d-116">你必须拥有其中一个订阅，以使用这些订阅。</span><span class="sxs-lookup"><span data-stu-id="4401d-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="4401d-117">权限</span><span class="sxs-lookup"><span data-stu-id="4401d-117">Permissions</span></span>

<span data-ttu-id="4401d-118">若要访问 UI 中的分类器：：</span><span class="sxs-lookup"><span data-stu-id="4401d-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="4401d-119">全局管理员需要选择租户来创建自定义分类器。</span><span class="sxs-lookup"><span data-stu-id="4401d-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="4401d-120">要训练分类器，需要合规性管理员角色。</span><span class="sxs-lookup"><span data-stu-id="4401d-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="4401d-121">在这些情况下，你需要具有这些权限的帐户才能使用分类器：</span><span class="sxs-lookup"><span data-stu-id="4401d-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="4401d-122">保留标签策略方案：记录管理和保留管理角色</span><span class="sxs-lookup"><span data-stu-id="4401d-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="4401d-123">敏感度标签策略方案：安全管理员、合规性管理员、合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="4401d-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="4401d-124">通信合规性策略方案：内部风险管理管理员、监管审核管理员</span><span class="sxs-lookup"><span data-stu-id="4401d-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4401d-125">默认情况下，只有创建自定义分类器的用户才能训练和查看该分类器做出预测。</span><span class="sxs-lookup"><span data-stu-id="4401d-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="4401d-126">准备自定义可训练分类器</span><span class="sxs-lookup"><span data-stu-id="4401d-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="4401d-127">在深入探讨之前，了解创建自定义可训练分类器所涉及的操作会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="4401d-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="4401d-128">日程表</span><span class="sxs-lookup"><span data-stu-id="4401d-128">Timeline</span></span>

<span data-ttu-id="4401d-129">此时间线反映了可训练分类器的示例部署。</span><span class="sxs-lookup"><span data-stu-id="4401d-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="4401d-131">可训练分类器首次需要选择加入。</span><span class="sxs-lookup"><span data-stu-id="4401d-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="4401d-132">完成组织内容的Microsoft 365评估需要 12 天。</span><span class="sxs-lookup"><span data-stu-id="4401d-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="4401d-133">请与全局管理员联系以启动选择加入过程。</span><span class="sxs-lookup"><span data-stu-id="4401d-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="4401d-134">总体工作流</span><span class="sxs-lookup"><span data-stu-id="4401d-134">Overall workflow</span></span>

<span data-ttu-id="4401d-135">若要了解有关创建自定义可训练分类器的整体工作流的更多信息，请参阅用于创建客户可训练分类 [器的流程](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="4401d-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="4401d-136">种子内容</span><span class="sxs-lookup"><span data-stu-id="4401d-136">Seed content</span></span>

<span data-ttu-id="4401d-137">当希望可训练分类器独立准确地将某个项目标识为特定内容类别时，首先必须向该项目显示该类别中的内容类型的许多示例。</span><span class="sxs-lookup"><span data-stu-id="4401d-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="4401d-138">将样本馈送到可训练分类器称为"种子 *设定"。*</span><span class="sxs-lookup"><span data-stu-id="4401d-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="4401d-139">种子内容由用户选择，并判断为表示内容类别。</span><span class="sxs-lookup"><span data-stu-id="4401d-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="4401d-140">你需要至少具有 50 个正样本和 500 个样本。</span><span class="sxs-lookup"><span data-stu-id="4401d-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="4401d-141">可训练分类器将处理多达 500 个最新创建的示例 (文件创建的日期/时间戳) 。</span><span class="sxs-lookup"><span data-stu-id="4401d-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="4401d-142">提供的样本数越多，分类器预测的精度就越准确。</span><span class="sxs-lookup"><span data-stu-id="4401d-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="4401d-143">测试内容</span><span class="sxs-lookup"><span data-stu-id="4401d-143">Testing content</span></span>

<span data-ttu-id="4401d-144">一旦可训练分类器处理了足够的正样本以构建预测模型，则需要测试它进行预测，以查看分类器能否正确区分与类别匹配的项和不匹配的项。</span><span class="sxs-lookup"><span data-stu-id="4401d-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="4401d-145">为此，选择另一组人工选取的内容（希望更大一些）包含应属于类别的样本和不应包含的示例。</span><span class="sxs-lookup"><span data-stu-id="4401d-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="4401d-146">你应该使用与首次提供的初始种子数据不同的数据进行测试。</span><span class="sxs-lookup"><span data-stu-id="4401d-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="4401d-147">处理这些错误后，你手动浏览结果并验证每个预测是否正确，或者你不确定。</span><span class="sxs-lookup"><span data-stu-id="4401d-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="4401d-148">可训练分类器使用此反馈来改进其预测模型。</span><span class="sxs-lookup"><span data-stu-id="4401d-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="4401d-149">为了获得最佳结果，在测试示例集内至少具有 200 个项目，并均匀分布正匹配和负匹配。</span><span class="sxs-lookup"><span data-stu-id="4401d-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="4401d-150">如何创建可训练分类器</span><span class="sxs-lookup"><span data-stu-id="4401d-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="4401d-151">收集 50-500 个种子内容项。</span><span class="sxs-lookup"><span data-stu-id="4401d-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="4401d-152">这些必须只是强烈表示您希望可训练分类器积极标识为分类类别的内容类型的示例。</span><span class="sxs-lookup"><span data-stu-id="4401d-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="4401d-153">有关受支持的[文件类型](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)，请参阅 SharePoint Server 中的默认已爬网文件扩展名和分析文件类型。</span><span class="sxs-lookup"><span data-stu-id="4401d-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4401d-154">种子和测试示例项不得加密，并且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="4401d-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4401d-155">请确保种子集内的项目是 **类别的** 强示例。</span><span class="sxs-lookup"><span data-stu-id="4401d-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="4401d-156">可训练分类器最初基于你为它设定种子的模型构建模型。</span><span class="sxs-lookup"><span data-stu-id="4401d-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="4401d-157">分类器假定所有种子样本都是强正数，并且无法知道样本是该类别的弱匹配还是负匹配。</span><span class="sxs-lookup"><span data-stu-id="4401d-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="4401d-158">将种子内容放在专用于SharePoint种子内容的联机 *文件夹中*。</span><span class="sxs-lookup"><span data-stu-id="4401d-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="4401d-159">记下网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="4401d-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="4401d-160">如果为种子数据创建新的站点和文件夹，请至少允许一小时对位置编制索引，然后再创建使用该种子数据的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="4401d-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="4401d-161">登录以使用Microsoft 365 合规中心管理员或安全管理员角色访问权限登录，然后打开Microsoft 365 合规中心或Microsoft 365 **安全中心**  >  **数据分类"**。</span><span class="sxs-lookup"><span data-stu-id="4401d-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="4401d-162">选择" **可训练分类器"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4401d-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="4401d-163">选择 **"创建可训练分类器"。**</span><span class="sxs-lookup"><span data-stu-id="4401d-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="4401d-164">为希望此可训练分类器标识的项目类别的 和 字段填写相应的 `Name` `Description` 值。</span><span class="sxs-lookup"><span data-stu-id="4401d-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="4401d-165">从SharePoint 2 中为种子内容网站选择"联机网站、库和文件夹 URL"。</span><span class="sxs-lookup"><span data-stu-id="4401d-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="4401d-166">选择 `Add` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-166">Choose `Add`.</span></span>

8. <span data-ttu-id="4401d-167">查看设置并选择 `Create trainable classifier` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="4401d-168">可训练分类器将在 24 小时内处理种子数据并生成预测模型。</span><span class="sxs-lookup"><span data-stu-id="4401d-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="4401d-169">分类器状态为 `In progress` 处理种子数据时的状态。</span><span class="sxs-lookup"><span data-stu-id="4401d-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="4401d-170">分类器处理完种子数据后，状态将更改为 `Need test items` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="4401d-171">现在，可以通过选择分类器来查看详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="4401d-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4401d-172">![可供测试的可训练分类器](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="4401d-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="4401d-173">收集至少 200 个最大 (10，000) 测试内容项，以获得最佳结果。</span><span class="sxs-lookup"><span data-stu-id="4401d-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="4401d-174">它们应该是强正值、强负和一些本质上不太明显的项目的组合。</span><span class="sxs-lookup"><span data-stu-id="4401d-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="4401d-175">有关受支持的[文件类型](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)，请参阅 SharePoint Server 中的默认已爬网文件扩展名和分析文件类型。</span><span class="sxs-lookup"><span data-stu-id="4401d-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4401d-176">示例项目不得加密，并且必须为英语。</span><span class="sxs-lookup"><span data-stu-id="4401d-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="4401d-177">将测试内容放在专用于SharePoint测试内容的联机 *文件夹中*。</span><span class="sxs-lookup"><span data-stu-id="4401d-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="4401d-178">记下联机SharePoint库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="4401d-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="4401d-179">如果为测试数据创建新的站点和文件夹，请至少允许一小时对位置编制索引，然后再创建使用该种子数据的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="4401d-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="4401d-180">选择 `Add items to test` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="4401d-181">从SharePoint 12 中选取测试内容网站的联机网站、库和文件夹 URL。</span><span class="sxs-lookup"><span data-stu-id="4401d-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="4401d-182">选择 `Add` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-182">Choose `Add`.</span></span>

15. <span data-ttu-id="4401d-183">通过选择 完成向导 `Done` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="4401d-184">可训练分类器最多需要一小时处理测试文件。</span><span class="sxs-lookup"><span data-stu-id="4401d-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="4401d-185">当可训练分类器处理完测试文件时，详细信息页面上的状态将更改为 `Ready to review` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="4401d-186">如果需要增加测试样本大小，请选择并允许可训练分类器 `Add items to test` 处理其他项目。</span><span class="sxs-lookup"><span data-stu-id="4401d-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4401d-187">![准备查看屏幕截图](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="4401d-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="4401d-188">选择 `Tested items to review` 选项卡查看项目。</span><span class="sxs-lookup"><span data-stu-id="4401d-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="4401d-189">Microsoft 365一次显示 30 个项目。</span><span class="sxs-lookup"><span data-stu-id="4401d-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="4401d-190">查看它们，在 `We predict this item is "Relevant". Do you agree?` 框中选择 或 `Yes` `No` 或 `Not sure, skip to next item` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="4401d-191">模型准确性每 30 个项目自动更新一次。</span><span class="sxs-lookup"><span data-stu-id="4401d-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4401d-192">!["审阅项目"框](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="4401d-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="4401d-193">查看 *至少* 200 个项目。</span><span class="sxs-lookup"><span data-stu-id="4401d-193">Review *at least* 200 items.</span></span> <span data-ttu-id="4401d-194">一旦精度分数稳定下来， **发布选项将** 变为可用，分类器状态将显示 `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="4401d-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4401d-195">![精度分数和准备发布](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="4401d-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="4401d-196">发布分类器。</span><span class="sxs-lookup"><span data-stu-id="4401d-196">Publish the classifier.</span></span>

21. <span data-ttu-id="4401d-197">发布分类器后，将用作使用敏感度标签Office自动[](apply-sensitivity-label-automatically.md)标记的条件，根据条件和通信合规性自动应用保留[标签策略](communication-compliance.md)。 [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)</span><span class="sxs-lookup"><span data-stu-id="4401d-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
