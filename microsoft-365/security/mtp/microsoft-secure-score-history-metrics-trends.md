---
title: 跟踪 Microsoft 安全分数历史记录并实现目标
description: 深入了解影响 Microsoft 安全分数的活动。 发现趋势并设定目标。
keywords: microsoft 安全分数， 安全分数， office 365 安全分数， Microsoft 安全分数， microsoft 365 安全中心， 改进操作
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: c9af6a3ae6f461acfd2968897223446641d5cf09
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925668"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a><span data-ttu-id="67737-105">跟踪 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="67737-105">Track your Microsoft Secure Score history and meet goals</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="67737-106">[Microsoft 安全](microsoft-secure-score.md) 分数是组织安全状况的度量，较高的数字表示采取更多改进措施。</span><span class="sxs-lookup"><span data-stu-id="67737-106">[Microsoft Secure Score](microsoft-secure-score.md) is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="67737-107">可以在 https://security.microsoft.com/securescore [Microsoft 365 安全中心找到它](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="67737-107">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a><span data-ttu-id="67737-108">深入了解影响分数的活动</span><span class="sxs-lookup"><span data-stu-id="67737-108">Gain insights into activity that has affected your score</span></span>

<span data-ttu-id="67737-109">在"历史记录"选项卡中查看组织一段时间 **得分的图形。**</span><span class="sxs-lookup"><span data-stu-id="67737-109">View a graph of your organization's score over time in the **History** tab.</span></span>

<span data-ttu-id="67737-110">下图是选定时间范围内执行的所有操作及其属性的列表，如生成的点和类别。</span><span class="sxs-lookup"><span data-stu-id="67737-110">Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="67737-111">您可以自定义日期范围，并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="67737-111">You can customize a date range and filter by category.</span></span>

![活动历史记录](../../media/secure-score/secure-score-history-activity.png)

<span data-ttu-id="67737-113">如果选择与活动关联的改进操作，将显示完整的改进操作飞出图。</span><span class="sxs-lookup"><span data-stu-id="67737-113">If you select the improvement action associated with an activity, the full improvement action flyout will appear.</span></span>

<span data-ttu-id="67737-114">若要查看该特定改进操作的所有历史记录，请在飞出中选择历史记录链接。</span><span class="sxs-lookup"><span data-stu-id="67737-114">To view all history for that specific improvement action, select the history link in the flyout.</span></span>

![改进操作历史记录](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a><span data-ttu-id="67737-116">发现趋势并设定目标</span><span class="sxs-lookup"><span data-stu-id="67737-116">Discover trends and set goals</span></span>

<span data-ttu-id="67737-117">在 **"指标&** 趋势"选项卡中，有几个图表可让你进一步查看趋势和设定目标。</span><span class="sxs-lookup"><span data-stu-id="67737-117">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="67737-118">你可以为整个可视化页面设置日期范围。</span><span class="sxs-lookup"><span data-stu-id="67737-118">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="67737-119">可视化包括：</span><span class="sxs-lookup"><span data-stu-id="67737-119">The visualizations include:</span></span>

* <span data-ttu-id="67737-120">**安全分数区域** - 根据组织目标和良好、正常和差分范围的定义进行自定义。</span><span class="sxs-lookup"><span data-stu-id="67737-120">**Your Secure Score zone** - Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="67737-121">**回归趋势** - 由于配置、用户或设备更改而已回归的点的时间线。</span><span class="sxs-lookup"><span data-stu-id="67737-121">**Regression trend** - A timeline of points that have regressed because of configuration, user, or device changes.</span></span>  
* <span data-ttu-id="67737-122">**比较趋势** - 组织的安全分数如何与其他人的一段时间进行比较。</span><span class="sxs-lookup"><span data-stu-id="67737-122">**Comparison trend** - How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="67737-123">此视图可以包含表示具有相似席位计数的组织得分平均值的行和您可以设置的自定义比较视图。</span><span class="sxs-lookup"><span data-stu-id="67737-123">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="67737-124">**风险接受趋势** - 标记为"接受风险"的改进操作时间线。</span><span class="sxs-lookup"><span data-stu-id="67737-124">**Risk acceptance trend** - Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="67737-125">**分数更改** - 获得分数、已回归分数以及指定日期范围内分数的更改。</span><span class="sxs-lookup"><span data-stu-id="67737-125">**Score changes** - The number of points achieved, points regressed, and changes to your score in the specified date range.</span></span>

### <a name="compare-your-score-to-organizations-like-yours"></a><span data-ttu-id="67737-126">将你的分数与像你这样的组织进行比较</span><span class="sxs-lookup"><span data-stu-id="67737-126">Compare your score to organizations like yours</span></span>

<span data-ttu-id="67737-127">有两处可了解分数与你类似的组织的比较方式。</span><span class="sxs-lookup"><span data-stu-id="67737-127">There are two places to see how your score compares to organizations that are similar to you.</span></span> <span data-ttu-id="67737-128">在这两个图表中，都可以选择" **管理比较** "以查看和编辑组织的信息。</span><span class="sxs-lookup"><span data-stu-id="67737-128">In both charts, you can select **Manage comparisons** to view and edit your organization's information.</span></span> <span data-ttu-id="67737-129">您还可以根据行业、组织规模、许可证和地区创建自定义比较。</span><span class="sxs-lookup"><span data-stu-id="67737-129">You can also create a custom comparison based on industry, organization size, licenses, and regions.</span></span>

#### <a name="comparison-bar-chart"></a><span data-ttu-id="67737-130">比较条形图</span><span class="sxs-lookup"><span data-stu-id="67737-130">Comparison bar chart</span></span>

<span data-ttu-id="67737-131">比较条形图是"概述 **"** 选项卡。将鼠标悬停在图表上可查看得分和得分机会。</span><span class="sxs-lookup"><span data-stu-id="67737-131">The comparison bar chart is the **Overview** tab. Hover over the chart to view the score and score opportunity.</span></span> <span data-ttu-id="67737-132">对比较数据进行匿名处理，因此，我们完全不知道哪些其他租户位于混合中。</span><span class="sxs-lookup"><span data-stu-id="67737-132">The comparison data is anonymized so we don’t know exactly which others tenants are in the mix.</span></span>

![相似组织分数的条形图](../../media/secure-score/secure-score-comparison-bar.png)

- <span data-ttu-id="67737-134">**类似你的** 组织：如果我们至少有五个或五 (个租户来比较符合以下条件) 租户的平均得分：</span><span class="sxs-lookup"><span data-stu-id="67737-134">**Organizations like yours**: an average score of other tenants (provided we have at least five or more tenants to compare) that qualify with the following criteria:</span></span>
    1. <span data-ttu-id="67737-135">同一行业</span><span class="sxs-lookup"><span data-stu-id="67737-135">Same industry</span></span>
    2. <span data-ttu-id="67737-136">组织规模相同</span><span class="sxs-lookup"><span data-stu-id="67737-136">Same organization size</span></span>
    3. <span data-ttu-id="67737-137">所有区域</span><span class="sxs-lookup"><span data-stu-id="67737-137">All regions</span></span>
    4. <span data-ttu-id="67737-138">使用的 Microsoft 产品有 80% 相似</span><span class="sxs-lookup"><span data-stu-id="67737-138">Microsoft products used are 80% similar</span></span>
    5. <span data-ttu-id="67737-139">机会 (租户 20% 范围内的当前许可证) 达到的最大得分</span><span class="sxs-lookup"><span data-stu-id="67737-139">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

- <span data-ttu-id="67737-140">**自定义比较**：需要根据以下条件选择"管理 **比较"进行** 设置：</span><span class="sxs-lookup"><span data-stu-id="67737-140">**Custom Comparison**: needs to be set up by selecting **Manage Comparison** based on the following criteria:</span></span>
    1. <span data-ttu-id="67737-141">选定的行业 () </span><span class="sxs-lookup"><span data-stu-id="67737-141">Selected industry(s)</span></span>
    2. <span data-ttu-id="67737-142">所选组织规模 () </span><span class="sxs-lookup"><span data-stu-id="67737-142">Selected organization size(s)</span></span>
    3. <span data-ttu-id="67737-143">所选 (区域) </span><span class="sxs-lookup"><span data-stu-id="67737-143">Selected region(s)</span></span>
    4. <span data-ttu-id="67737-144">所选许可证 () </span><span class="sxs-lookup"><span data-stu-id="67737-144">Selected license(s)</span></span>
    5. <span data-ttu-id="67737-145">使用的 Microsoft 产品有 80% 相似</span><span class="sxs-lookup"><span data-stu-id="67737-145">Microsoft products used are 80% similar</span></span>
    6. <span data-ttu-id="67737-146">机会 (租户 20% 范围内的当前许可证) 可获取的最大得分</span><span class="sxs-lookup"><span data-stu-id="67737-146">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

<span data-ttu-id="67737-147">如果你已进行自定义选择，但结果少于五个我们可以与之比较的其他租户，你将看到"由于数据有限，不可用"。</span><span class="sxs-lookup"><span data-stu-id="67737-147">If you've made a custom selection but the results have less than five other tenants that we can compare against, you'll see “Not available due to limited data”.</span></span>

#### <a name="comparison-trend"></a><span data-ttu-id="67737-148">比较趋势</span><span class="sxs-lookup"><span data-stu-id="67737-148">Comparison trend</span></span>

<span data-ttu-id="67737-149">在 **"指标&** 趋势"选项卡中，查看组织的安全分数如何与其他人的一段时间进行比较。</span><span class="sxs-lookup"><span data-stu-id="67737-149">In the **Metrics & trends** tab, view how your organization's Secure Score compares to others' over time.</span></span>

![随着时间的推移，相似组织的分数的直线图](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="67737-151">欢迎提出宝贵意见</span><span class="sxs-lookup"><span data-stu-id="67737-151">We want to hear from you</span></span>

<span data-ttu-id="67737-152">如果有任何问题，请通过发布到安全、隐私和合规社区& [告知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 我们。</span><span class="sxs-lookup"><span data-stu-id="67737-152">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="67737-153">We're monitoring the community and will provide help.</span><span class="sxs-lookup"><span data-stu-id="67737-153">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="67737-154">相关资源</span><span class="sxs-lookup"><span data-stu-id="67737-154">Related resources</span></span>

- [<span data-ttu-id="67737-155">Microsoft 安全分数概述</span><span class="sxs-lookup"><span data-stu-id="67737-155">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="67737-156">评估你的安全状况</span><span class="sxs-lookup"><span data-stu-id="67737-156">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="67737-157">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="67737-157">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="67737-158">新增功能</span><span class="sxs-lookup"><span data-stu-id="67737-158">What's new</span></span>](microsoft-secure-score-whats-new.md)
