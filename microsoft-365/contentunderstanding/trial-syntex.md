---
title: 运行 Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: 了解如何在组织中计划和运行SharePoint Syntex试点计划。
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327077"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a><span data-ttu-id="bf42c-103">运行 Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="bf42c-103">Run a trial of Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="bf42c-104">本文介绍如何设置和运行试用计划，以在SharePoint Syntex部署部署。</span><span class="sxs-lookup"><span data-stu-id="bf42c-104">This article describes how to set up and run a trial pilot program to deploy SharePoint Syntex in your organization.</span></span> <span data-ttu-id="bf42c-105">它还建议试用的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="bf42c-105">It also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="bf42c-106">注册试用版</span><span class="sxs-lookup"><span data-stu-id="bf42c-106">Sign up for a trial</span></span>

<span data-ttu-id="bf42c-107">试用版SharePoint Syntex 300 个用户 30 天的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bf42c-107">The trial of SharePoint Syntex gives access to 300 users for 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="bf42c-108">试用版中最多包含 300 个用户，以确保自动添加 100 万个 AI Builder 信用额度。</span><span class="sxs-lookup"><span data-stu-id="bf42c-108">Up to 300 users are included in the trial to ensure the automatic addition of 1 million AI Builder credits.</span></span> <span data-ttu-id="bf42c-109">You do not have to include 300 users for a trial to succeed.</span><span class="sxs-lookup"><span data-stu-id="bf42c-109">You do not have to include 300 users for a trial to succeed.</span></span>

<span data-ttu-id="bf42c-110">可以从以下来源之一获取试用版：</span><span class="sxs-lookup"><span data-stu-id="bf42c-110">You can get the trial version from one of the following sources:</span></span>

- <span data-ttu-id="bf42c-111">产品[SharePoint Syntex页面](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="bf42c-111">The [SharePoint Syntex product page](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="bf42c-112">The [Microsoft 365 管理中心](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="bf42c-112">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="bf42c-113">登录到 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bf42c-113">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="bf42c-114">转到计费  >  **购买服务**。</span><span class="sxs-lookup"><span data-stu-id="bf42c-114">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="bf42c-115">向下滚动到“**加载项**”部分。</span><span class="sxs-lookup"><span data-stu-id="bf42c-115">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="bf42c-116">在"SharePoint Syntex磁贴上，选择"详细信息 **"。**</span><span class="sxs-lookup"><span data-stu-id="bf42c-116">On the SharePoint Syntex tile, select **Details**.</span></span>
    5.  <span data-ttu-id="bf42c-117">选择“**获取免费试用版**”。</span><span class="sxs-lookup"><span data-stu-id="bf42c-117">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="bf42c-118">若要确认试用版，请按照其余向导步骤操作。</span><span class="sxs-lookup"><span data-stu-id="bf42c-118">To confirm the trial, follow the remaining wizard steps.</span></span>

<span data-ttu-id="bf42c-119">你必须是全局Microsoft 365或帐单管理员才能激活试用版。</span><span class="sxs-lookup"><span data-stu-id="bf42c-119">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="bf42c-120">Who应涉及试用版</span><span class="sxs-lookup"><span data-stu-id="bf42c-120">Who should be involved in a trial</span></span>

|<span data-ttu-id="bf42c-121">角色</span><span class="sxs-lookup"><span data-stu-id="bf42c-121">Role</span></span>  |<span data-ttu-id="bf42c-122">活动</span><span class="sxs-lookup"><span data-stu-id="bf42c-122">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="bf42c-123">Microsoft 365全局管理员或帐单管理员</span><span class="sxs-lookup"><span data-stu-id="bf42c-123">Microsoft 365 global admin or billing admin</span></span>    |     <span data-ttu-id="bf42c-124">激活试用版并分配许可证</span><span class="sxs-lookup"><span data-stu-id="bf42c-124">Activate the trial and assign licenses</span></span>    |
|<span data-ttu-id="bf42c-125">Microsoft 365全局管理员或SharePoint管理员</span><span class="sxs-lookup"><span data-stu-id="bf42c-125">Microsoft 365 global admin or SharePoint admin</span></span>     |   <span data-ttu-id="bf42c-126">配置SharePoint Syntex和创建内容中心</span><span class="sxs-lookup"><span data-stu-id="bf42c-126">Configure SharePoint Syntex and create content centers</span></span>      |
|<span data-ttu-id="bf42c-127">业务用户</span><span class="sxs-lookup"><span data-stu-id="bf42c-127">Business users</span></span>     |    <span data-ttu-id="bf42c-128">模型生成和测试</span><span class="sxs-lookup"><span data-stu-id="bf42c-128">Model building and testing</span></span>     |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="bf42c-129">激活试用版之前</span><span class="sxs-lookup"><span data-stu-id="bf42c-129">Before you activate a trial</span></span>

<span data-ttu-id="bf42c-130">若要成功规划SharePoint Syntex，请考虑以下因素：</span><span class="sxs-lookup"><span data-stu-id="bf42c-130">To successfully plan a SharePoint Syntex trial, consider the following factors:</span></span>

- <span data-ttu-id="bf42c-131">最有意义的测试在"实际"方案和数据上完成。</span><span class="sxs-lookup"><span data-stu-id="bf42c-131">The most meaningful testing is completed on “real world” scenarios and data.</span></span>
- <span data-ttu-id="bf42c-132">每个租户只能SharePoint Syntex一次试用版。</span><span class="sxs-lookup"><span data-stu-id="bf42c-132">You can only activate a SharePoint Syntex trial once per tenant.</span></span>

<span data-ttu-id="bf42c-133">测试或演示租户可以用作"试运行"，以演练激活步骤和管理控制。</span><span class="sxs-lookup"><span data-stu-id="bf42c-133">A test or demo tenant can be used as a “dry run” to walk through the activation steps and administrative controls.</span></span> <span data-ttu-id="bf42c-134">但是，最好评估在生产租户上构建的模型。</span><span class="sxs-lookup"><span data-stu-id="bf42c-134">But it’s probably best to evaluate model building on a production tenant.</span></span>

<span data-ttu-id="bf42c-135">若要在生产租户上最大化试用版的价值，规划和业务参与至关重要。</span><span class="sxs-lookup"><span data-stu-id="bf42c-135">To maximize the value of a trial on a production tenant, planning and business engagement are essential.</span></span> <span data-ttu-id="bf42c-136">您应参与一个或多个业务领域，以确定三到六个用例，这些用例可能会由 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="bf42c-136">You should engage one or more business areas to identify three-to-six use cases that could potentially be addressed by SharePoint Syntex.</span></span> <span data-ttu-id="bf42c-137">这些用例应：</span><span class="sxs-lookup"><span data-stu-id="bf42c-137">These use cases should:</span></span>

- <span data-ttu-id="bf42c-138">包括可以通过表单处理或文档理解模型解决的方案。</span><span class="sxs-lookup"><span data-stu-id="bf42c-138">Include scenarios that could be solved by either the forms processing or document understanding model.</span></span>
- <span data-ttu-id="bf42c-139">明确了解任何提取的元数据的用途;例如，通过使用设置视图格式或实现Power Automate。</span><span class="sxs-lookup"><span data-stu-id="bf42c-139">Have a clear understanding of the purpose for any extracted metadata; for example, view formatting or automation by using Power Automate.</span></span> <span data-ttu-id="bf42c-140">尽管SharePoint Syntex文档分类和提取元数据，但要量化的值是此元数据所支持的值。</span><span class="sxs-lookup"><span data-stu-id="bf42c-140">While SharePoint Syntex is focused on classifying documents and extracting metadata, the value to quantify is what this metadata enables.</span></span>
- <span data-ttu-id="bf42c-141">基于定义的一组数据;例如，特定SharePoint或库。</span><span class="sxs-lookup"><span data-stu-id="bf42c-141">Be based on a defined set of data; for example, specific SharePoint sites or libraries.</span></span> <span data-ttu-id="bf42c-142">一个SharePoint Syntex一点就是，通用模型可以应用于所有组织内容。</span><span class="sxs-lookup"><span data-stu-id="bf42c-142">A common misconception of SharePoint Syntex is that general purpose models can be applied across all organization content.</span></span> <span data-ttu-id="bf42c-143">更准确的视图是构建模型以帮助解决目标位置的特定业务问题。</span><span class="sxs-lookup"><span data-stu-id="bf42c-143">A more accurate view is that models are built to help solve specific business problems in targeted locations.</span></span>

<span data-ttu-id="bf42c-144">所有这些用例可能不适合SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="bf42c-144">All of these use cases might not be a good fit for SharePoint Syntex.</span></span> <span data-ttu-id="bf42c-145">质量试用的目标并不证明SharePoint Syntex满足所有方案。</span><span class="sxs-lookup"><span data-stu-id="bf42c-145">The goal of a quality trial isn't to prove that SharePoint Syntex will fit all the scenarios.</span></span> <span data-ttu-id="bf42c-146">相反，该试用版应帮助你更好地了解产品的价值。</span><span class="sxs-lookup"><span data-stu-id="bf42c-146">Instead, the trial should help you better understand the value of product.</span></span>

<span data-ttu-id="bf42c-147">对于每个计划用例，确定作为相关内容或流程的主题专家的用户。</span><span class="sxs-lookup"><span data-stu-id="bf42c-147">For each of the planned use cases, identify users who are subject matter experts in the related content or process.</span></span> <span data-ttu-id="bf42c-148">创建SharePoint Syntex模型侧重于内容中的域专家，而不是 IT 专业人员或开发人员资源。</span><span class="sxs-lookup"><span data-stu-id="bf42c-148">The creation of SharePoint Syntex models is focused on domain experts in the content, rather than on IT professionals or developer resources.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="bf42c-149">激活试用版</span><span class="sxs-lookup"><span data-stu-id="bf42c-149">Activate a trial</span></span>

<span data-ttu-id="bf42c-150">启动试用版时，需要：</span><span class="sxs-lookup"><span data-stu-id="bf42c-150">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="bf42c-151">将许可证分配给相关用户。</span><span class="sxs-lookup"><span data-stu-id="bf42c-151">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="bf42c-152">执行[其他设置SharePoint Syntex。](set-up-content-understanding.md)</span><span class="sxs-lookup"><span data-stu-id="bf42c-152">Perform [additional setup of SharePoint Syntex](set-up-content-understanding.md).</span></span>
    - <span data-ttu-id="bf42c-153">您可能需要创建 [其他内容中心](create-a-content-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bf42c-153">You might want to [create additional content centers](create-a-content-center.md).</span></span>

<span data-ttu-id="bf42c-154">激活试用版后，可以创建模型并处理文件。</span><span class="sxs-lookup"><span data-stu-id="bf42c-154">After the trial is activated, you can create models and process files.</span></span> <span data-ttu-id="bf42c-155">请参阅 [模型创建指南](create-a-content-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bf42c-155">See [guidance for model creation](create-a-content-center.md).</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="bf42c-156">试用期间</span><span class="sxs-lookup"><span data-stu-id="bf42c-156">During a trial</span></span>

<span data-ttu-id="bf42c-157">试用期有限，因此最好首先关注一下SharePoint Syntex模型是否可以对文档进行分类，并提取定义的用例的元数据。</span><span class="sxs-lookup"><span data-stu-id="bf42c-157">Trial periods are limited, so it’s best to focus initially on whether SharePoint Syntex models can classify documents and extract metadata for the defined use cases.</span></span> <span data-ttu-id="bf42c-158">试用期结束后，可以评估元数据的利用方式。</span><span class="sxs-lookup"><span data-stu-id="bf42c-158">After the trial period is over, you can evaluate how the metadata can be exploited.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="bf42c-159">试用后</span><span class="sxs-lookup"><span data-stu-id="bf42c-159">After a trial</span></span>

<span data-ttu-id="bf42c-160">根据试验结果，可以决定是否继续生产SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="bf42c-160">Based on the outcome of the trial, you can decide whether to proceed to production use of SharePoint Syntex.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="bf42c-161">继续生产使用</span><span class="sxs-lookup"><span data-stu-id="bf42c-161">Proceed to production use</span></span>

<span data-ttu-id="bf42c-162">为了确保服务的连续性，需要购买所需数量的许可证，并将这些许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="bf42c-162">To ensure continuity of service, you need to purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="bf42c-163">在试用期结束时没有完整许可证的试用用户将无法充分利用SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="bf42c-163">Trial users who don’t have a full license at the end of the trial period won’t be able to fully utilize SharePoint Syntex.</span></span>

<span data-ttu-id="bf42c-164">你可能必须估计表单处理的预期使用，并规划预期 AI 生成器信用额度。</span><span class="sxs-lookup"><span data-stu-id="bf42c-164">You might have to estimate your projected use of forms processing and plan for the expected amount of AI Builder credits.</span></span> <span data-ttu-id="bf42c-165">有关帮助，请参阅 [估计适合你的 AI 生成器容量](https://powerapps.microsoft.com/ai-builder-calculator/)。</span><span class="sxs-lookup"><span data-stu-id="bf42c-165">For help, see [Estimate the AI Builder capacity that’s right for you](https://powerapps.microsoft.com/ai-builder-calculator/).</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="bf42c-166">请勿继续生产使用</span><span class="sxs-lookup"><span data-stu-id="bf42c-166">Don't proceed to production use</span></span>

<span data-ttu-id="bf42c-167">如果你在试用后不购买许可证：</span><span class="sxs-lookup"><span data-stu-id="bf42c-167">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="bf42c-168">无法创建新模型。</span><span class="sxs-lookup"><span data-stu-id="bf42c-168">You won’t be able to create new models.</span></span>
- <span data-ttu-id="bf42c-169">运行模型的库将不再自动对文件或提取模型进行分类。</span><span class="sxs-lookup"><span data-stu-id="bf42c-169">Libraries that were running models will no longer automatically classify files or extract models.</span></span>
- <span data-ttu-id="bf42c-170">任何以前已分类的文件或提取的元数据都不受影响。</span><span class="sxs-lookup"><span data-stu-id="bf42c-170">Any previously classified files or extracted metadata won’t be affected.</span></span> 
- <span data-ttu-id="bf42c-171">内容中心和任何文档理解模型不会自动删除。</span><span class="sxs-lookup"><span data-stu-id="bf42c-171">Content centers and any document-understanding models won’t be automatically deleted.</span></span> <span data-ttu-id="bf42c-172">如果你决定将来购买许可证，这些许可证将仍然可供使用。</span><span class="sxs-lookup"><span data-stu-id="bf42c-172">These will remain available for use if you decide to purchase licenses in the future.</span></span>
- <span data-ttu-id="bf42c-173">表单处理模型将存储在默认 Power Platform 环境的 common Data Services (CDS) 实例中。</span><span class="sxs-lookup"><span data-stu-id="bf42c-173">Forms-processing models will be stored in the Common Data Services (CDS) instance of the default Power Platform environment.</span></span> <span data-ttu-id="bf42c-174">这些可以与以后许可一SharePoint Syntex Power Platform 中的 AI 生成器功能一起使用。</span><span class="sxs-lookup"><span data-stu-id="bf42c-174">These could be used with future licensing for SharePoint Syntex or with AI Builder capabilities in the Power Platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf42c-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf42c-175">See also</span></span>

[<span data-ttu-id="bf42c-176">Microsoft SharePoint Syntex采用：入门</span><span class="sxs-lookup"><span data-stu-id="bf42c-176">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)
