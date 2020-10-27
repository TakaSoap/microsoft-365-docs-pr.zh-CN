---
title: 跟踪你的 Microsoft 安全分数历史记录并实现目标
description: 深入了解已影响你的 Microsoft 安全分数的活动。 发现趋势并设置目标。
keywords: microsoft 安全分数，安全分数，office 365 安全分数，microsoft 安全分数，microsoft 365 安全中心，改进操作
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4dfe1c9595db869a59474a030a5dd8673cf7db24
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769240"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a><span data-ttu-id="c5e72-105">跟踪你的 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="c5e72-105">Track your Microsoft Secure Score history and meet goals</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5e72-106">[Microsoft 安全分数](microsoft-secure-score.md) 是组织的安全状态的度量，数字越大，表明执行了更多改进操作。</span><span class="sxs-lookup"><span data-stu-id="c5e72-106">[Microsoft Secure Score](microsoft-secure-score.md) is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="c5e72-107">可在 https://security.microsoft.com/securescore [Microsoft 365 安全中心](overview-security-center.md)中找到。</span><span class="sxs-lookup"><span data-stu-id="c5e72-107">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a><span data-ttu-id="c5e72-108">深入了解已影响你得分的活动</span><span class="sxs-lookup"><span data-stu-id="c5e72-108">Gain insights into activity that has affected your score</span></span>

<span data-ttu-id="c5e72-109">在 " **历史记录** " 选项卡中查看组织的分数在一段时间内的关系图。</span><span class="sxs-lookup"><span data-stu-id="c5e72-109">View a graph of your organization's score over time in the **History** tab.</span></span>

<span data-ttu-id="c5e72-110">图下方是所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。</span><span class="sxs-lookup"><span data-stu-id="c5e72-110">Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="c5e72-111">您可以自定义日期范围并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="c5e72-111">You can customize a date range and filter by category.</span></span>

![活动历史记录](../../media/secure-score/secure-score-history-activity.png)

<span data-ttu-id="c5e72-113">如果选择与某一活动相关联的 "改进" 操作，则将显示完整的 "改进操作" 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="c5e72-113">If you select the improvement action associated with an activity, the full improvement action flyout will appear.</span></span>

<span data-ttu-id="c5e72-114">若要查看该特定 "改进" 操作的所有历史记录，请在浮出控件中选择 "历史记录" 链接。</span><span class="sxs-lookup"><span data-stu-id="c5e72-114">To view all history for that specific improvement action, select the history link in the flyout.</span></span>

![改进操作历史记录](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a><span data-ttu-id="c5e72-116">发现趋势并设置目标</span><span class="sxs-lookup"><span data-stu-id="c5e72-116">Discover trends and set goals</span></span>

<span data-ttu-id="c5e72-117">在 " **指标 & 趋势** " 选项卡中，有几个图表和图表可让您更好地了解趋势和设置目标。</span><span class="sxs-lookup"><span data-stu-id="c5e72-117">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="c5e72-118">您可以为整个可视化页设置日期范围。</span><span class="sxs-lookup"><span data-stu-id="c5e72-118">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="c5e72-119">可视化效果包括：</span><span class="sxs-lookup"><span data-stu-id="c5e72-119">The visualizations include:</span></span>

* <span data-ttu-id="c5e72-120">**您的安全分数区域** -根据组织的目标和 "良好"、"好" 和 "差" 得分范围的定义进行自定义。</span><span class="sxs-lookup"><span data-stu-id="c5e72-120">**Your Secure Score zone** - Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="c5e72-121">**回归趋势** -由于配置、用户或设备更改而 regressed 的点的时间线。</span><span class="sxs-lookup"><span data-stu-id="c5e72-121">**Regression trend** - A timeline of points that have regressed because of configuration, user, or device changes.</span></span>  
* <span data-ttu-id="c5e72-122">**比较趋势** -组织的安全分数与其他人的对比情况。</span><span class="sxs-lookup"><span data-stu-id="c5e72-122">**Comparison trend** - How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="c5e72-123">此视图可包含表示具有类似座位计数的组织的平均分数和可设置的自定义比较视图的行。</span><span class="sxs-lookup"><span data-stu-id="c5e72-123">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="c5e72-124">**风险接受趋势** -标记为 "风险已接受" 的 "改进" 操作的时间线。</span><span class="sxs-lookup"><span data-stu-id="c5e72-124">**Risk acceptance trend** - Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="c5e72-125">**分数变化** -指定的日期范围内已实现的点数，点 regressed，以及后续得分的变化。</span><span class="sxs-lookup"><span data-stu-id="c5e72-125">**Score changes** - The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

### <a name="compare-your-score-to-organizations-like-yours"></a><span data-ttu-id="c5e72-126">比较你的成绩与你的组织（如你的组织）</span><span class="sxs-lookup"><span data-stu-id="c5e72-126">Compare your score to organizations like yours</span></span>

<span data-ttu-id="c5e72-127">有两个位置可查看您的分数如何与类似于您的组织进行比较。</span><span class="sxs-lookup"><span data-stu-id="c5e72-127">There are two places to see how your score compares to organizations that are similar to you.</span></span> <span data-ttu-id="c5e72-128">在这两个图表中，您可以选择 " **管理比较** " 以查看和编辑您的组织的信息。</span><span class="sxs-lookup"><span data-stu-id="c5e72-128">In both charts, you can select **Manage comparisons** to view and edit your organization's information.</span></span> <span data-ttu-id="c5e72-129">您还可以创建基于行业、组织规模、许可证和地区的自定义比较。</span><span class="sxs-lookup"><span data-stu-id="c5e72-129">You can also create a custom comparison based on industry, organization size, licenses, and regions.</span></span>

#### <a name="comparison-bar-chart"></a><span data-ttu-id="c5e72-130">比较条形图</span><span class="sxs-lookup"><span data-stu-id="c5e72-130">Comparison bar chart</span></span>

<span data-ttu-id="c5e72-131">比较条形图是 " **概述** " 选项卡。将鼠标悬停在图表上以查看分数和分数机会。</span><span class="sxs-lookup"><span data-stu-id="c5e72-131">The comparison bar chart is the **Overview** tab. Hover over the chart to view the score and score opportunity.</span></span> <span data-ttu-id="c5e72-132">比较数据是匿名，因此我们不知道组合中的其他租户。</span><span class="sxs-lookup"><span data-stu-id="c5e72-132">The comparison data is anonymized so we don’t know exactly which others tenant are in the mix.</span></span>

![相似组织分数的条形图](../../media/secure-score/secure-score-comparison-bar.png)

- <span data-ttu-id="c5e72-134">**像你这样的组织** ：我们为你提供了其他 (租户的平均分数，如果我们至少有5个或更多租户可用于比较符合以下条件的) ：</span><span class="sxs-lookup"><span data-stu-id="c5e72-134">**Organizations like yours** : we give you an average score of other tenants (provided we have at least 5 or more tenants to compare) that qualify with the following criteria:</span></span>
    1. <span data-ttu-id="c5e72-135">同一行业</span><span class="sxs-lookup"><span data-stu-id="c5e72-135">Same industry</span></span>
    2. <span data-ttu-id="c5e72-136">相同的组织规模</span><span class="sxs-lookup"><span data-stu-id="c5e72-136">Same organization size</span></span>
    3. <span data-ttu-id="c5e72-137">所有区域</span><span class="sxs-lookup"><span data-stu-id="c5e72-137">All regions</span></span>
    4. <span data-ttu-id="c5e72-138">使用的 Microsoft 产品是80% 相似的</span><span class="sxs-lookup"><span data-stu-id="c5e72-138">Microsoft products used are 80% similar</span></span>
    5. <span data-ttu-id="c5e72-139">在来自租户的20% 范围内，当前许可证) 可实现的商机 (最大分数</span><span class="sxs-lookup"><span data-stu-id="c5e72-139">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

- <span data-ttu-id="c5e72-140">**自定义比较** ：只有在找到5个或更多租户) 基于以下条件时，才需要先通过选择 " **管理比较** " (进行安装：</span><span class="sxs-lookup"><span data-stu-id="c5e72-140">**Custom Comparison** : needs to be setup up first by selecting **Manage Comparison** (only if we find 5 or more tenants) based on the following criteria:</span></span>
    1. <span data-ttu-id="c5e72-141">选定的行业 (s) </span><span class="sxs-lookup"><span data-stu-id="c5e72-141">Selected industry(s)</span></span>
    2. <span data-ttu-id="c5e72-142">选定的组织大小 (s) </span><span class="sxs-lookup"><span data-stu-id="c5e72-142">Selected organization size(s)</span></span>
    3. <span data-ttu-id="c5e72-143"> (s 的选定区域) </span><span class="sxs-lookup"><span data-stu-id="c5e72-143">Selected region(s)</span></span>
    4. <span data-ttu-id="c5e72-144">选定的许可证 (s) </span><span class="sxs-lookup"><span data-stu-id="c5e72-144">Selected license(s)</span></span>
    5. <span data-ttu-id="c5e72-145">使用的 Microsoft 产品是80% 相似的</span><span class="sxs-lookup"><span data-stu-id="c5e72-145">Microsoft products used are 80% similar</span></span>
    6. <span data-ttu-id="c5e72-146">在来自租户的20% 范围内，当前许可证) 可实现的商机 (最大分数</span><span class="sxs-lookup"><span data-stu-id="c5e72-146">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

<span data-ttu-id="c5e72-147">如果您未选择自定义选择结果导致的其他租户小于5个其他租户，则会看到 "由于数据有限而不可用"。</span><span class="sxs-lookup"><span data-stu-id="c5e72-147">If you have not made a selection for custom selection of the selection result in getting less than 5 other tenants that we can compare against, you will see “Not available due to limited data”.</span></span>

#### <a name="comparison-trend"></a><span data-ttu-id="c5e72-148">比较趋势</span><span class="sxs-lookup"><span data-stu-id="c5e72-148">Comparison trend</span></span>

<span data-ttu-id="c5e72-149">在 " **指标 & 趋势** " 选项卡中，查看组织的安全分数与其他时间的对比情况。</span><span class="sxs-lookup"><span data-stu-id="c5e72-149">In the **Metrics & trends** tab, view how your organization's Secure Score compares to others' over time.</span></span>

![一段时间内相似组织分数的线形图](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="c5e72-151">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="c5e72-151">We want to hear from you</span></span>

<span data-ttu-id="c5e72-152">如果你有任何问题，请通过在 [安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="c5e72-152">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="c5e72-153">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="c5e72-153">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="c5e72-154">相关资源</span><span class="sxs-lookup"><span data-stu-id="c5e72-154">Related resources</span></span>

- [<span data-ttu-id="c5e72-155">Microsoft 安全评分概述</span><span class="sxs-lookup"><span data-stu-id="c5e72-155">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="c5e72-156">评估你的安全状况</span><span class="sxs-lookup"><span data-stu-id="c5e72-156">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="c5e72-157">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="c5e72-157">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="c5e72-158">新增功能</span><span class="sxs-lookup"><span data-stu-id="c5e72-158">What's new</span></span>](microsoft-secure-score-whats-new.md)
