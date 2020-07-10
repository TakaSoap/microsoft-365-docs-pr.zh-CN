---
title: 跟踪你的 Microsoft 安全分数历史记录并实现目标
description: 深入了解已影响安全分数的活动。 发现趋势并设置目标。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
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
ms.openlocfilehash: b99f927711ed1015b38d8020e287d76155ce706f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "45095018"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a><span data-ttu-id="4b190-105">跟踪你的 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="4b190-105">Track your Microsoft Secure Score history and meet goals</span></span>

<span data-ttu-id="4b190-106">[Microsoft 安全分数](microsoft-secure-score.md)是组织的安全状态的度量，数字越大，表明执行了更多改进操作。</span><span class="sxs-lookup"><span data-stu-id="4b190-106">[Microsoft Secure Score](microsoft-secure-score.md) is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="4b190-107">可在 https://security.microsoft.com/securescore [Microsoft 365 安全中心](overview-security-center.md)中找到。</span><span class="sxs-lookup"><span data-stu-id="4b190-107">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a><span data-ttu-id="4b190-108">深入了解已影响你得分的活动</span><span class="sxs-lookup"><span data-stu-id="4b190-108">Gain insights into activity that has affected your score</span></span>

<span data-ttu-id="4b190-109">在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。</span><span class="sxs-lookup"><span data-stu-id="4b190-109">View a graph of your organization's score over time in the **History** tab.</span></span>

<span data-ttu-id="4b190-110">图下方是所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。</span><span class="sxs-lookup"><span data-stu-id="4b190-110">Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="4b190-111">您可以自定义日期范围并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="4b190-111">You can customize a date range and filter by category.</span></span>

![活动历史记录](../../media/secure-score/secure-score-history-activity.png)

<span data-ttu-id="4b190-113">如果选择与某一活动相关联的 "改进" 操作，则将显示完整的 "改进操作" 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="4b190-113">If you select the improvement action associated with an activity, the full improvement action flyout will appear.</span></span>

<span data-ttu-id="4b190-114">若要查看该特定 "改进" 操作的所有历史记录，请在浮出控件中选择 "历史记录" 链接。</span><span class="sxs-lookup"><span data-stu-id="4b190-114">To view all history for that specific improvement action, select the history link in the flyout.</span></span>

![改进操作历史记录](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a><span data-ttu-id="4b190-116">发现趋势并设置目标</span><span class="sxs-lookup"><span data-stu-id="4b190-116">Discover trends and set goals</span></span>

<span data-ttu-id="4b190-117">在 "**指标 & 趋势**" 选项卡中，有几个图表和图表可让您更好地了解趋势和设置目标。</span><span class="sxs-lookup"><span data-stu-id="4b190-117">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="4b190-118">您可以为整个可视化页设置日期范围。</span><span class="sxs-lookup"><span data-stu-id="4b190-118">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="4b190-119">可视化效果包括：</span><span class="sxs-lookup"><span data-stu-id="4b190-119">The visualizations include:</span></span>

* <span data-ttu-id="4b190-120">**安全分数区域**—根据组织的目标和 "好"、"好" 和 "差" 得分范围的定义自定义。</span><span class="sxs-lookup"><span data-stu-id="4b190-120">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="4b190-121">**回归趋势**-由于配置、用户或设备更改而 regressed 的点的时间线。</span><span class="sxs-lookup"><span data-stu-id="4b190-121">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="4b190-122">**比较趋势**—组织的安全分数与其他人的对比情况。</span><span class="sxs-lookup"><span data-stu-id="4b190-122">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="4b190-123">此视图可包含表示具有类似座位计数的组织的平均分数和可设置的自定义比较视图的行。</span><span class="sxs-lookup"><span data-stu-id="4b190-123">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="4b190-124">**风险接受趋势**-标记为 "风险已接受" 的 "改进" 操作的时间线。</span><span class="sxs-lookup"><span data-stu-id="4b190-124">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="4b190-125">**得分变化**—指定的日期范围内的积分数、regressed 和后续得分的变化。</span><span class="sxs-lookup"><span data-stu-id="4b190-125">**Score changes** — The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

### <a name="compare-your-score-to-organizations-like-yours"></a><span data-ttu-id="4b190-126">比较你的成绩与你的组织（如你的组织）</span><span class="sxs-lookup"><span data-stu-id="4b190-126">Compare your score to organizations like yours</span></span>

<span data-ttu-id="4b190-127">你可以在两个位置查看你的成绩与类似于您的组织的对比情况。</span><span class="sxs-lookup"><span data-stu-id="4b190-127">There are two place to see how your score compares to organizations that are similar to you.</span></span>

<span data-ttu-id="4b190-128">第一个位置位于 "**概述**" 选项卡上，您可以在其中查看比较条形图。</span><span class="sxs-lookup"><span data-stu-id="4b190-128">The first place is in the **Overview** tab, where you will be able to see a comparison bar graph.</span></span> <span data-ttu-id="4b190-129">将鼠标悬停在图表上以查看分数和分数机会。</span><span class="sxs-lookup"><span data-stu-id="4b190-129">Hover over the chart to view the score and score opportunity.</span></span>

![相似组织分数的条形图](../../media/secure-score/secure-score-comparison-bar.png)

<span data-ttu-id="4b190-131">第二个位置是 "**指标" & 趋势**"选项卡，您可以在其中查看组织的安全分数与其他时间的对比情况。</span><span class="sxs-lookup"><span data-stu-id="4b190-131">The second place is in the **Metrics & trends** tab, where you can view how your organization's Secure Score compares to others' over time.</span></span>

![一段时间内相似组织分数的线形图](../../media/secure-score/secure-score-comparison-trend.png)

<span data-ttu-id="4b190-133">在这两个图表中，您可以选择 "**管理比较**" 以查看和编辑您的组织的信息。</span><span class="sxs-lookup"><span data-stu-id="4b190-133">In both charts, you can select **Manage comparisons** to view and edit your organization's information.</span></span> <span data-ttu-id="4b190-134">您还可以创建基于行业、组织规模、许可证和地区的自定义比较。</span><span class="sxs-lookup"><span data-stu-id="4b190-134">You can also create a custom comparison based on industry, organization size, licenses, and regions.</span></span> 

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="4b190-135">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="4b190-135">We want to hear from you</span></span>

<span data-ttu-id="4b190-136">如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="4b190-136">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="4b190-137">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="4b190-137">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="4b190-138">相关资源</span><span class="sxs-lookup"><span data-stu-id="4b190-138">Related resources</span></span>

- [<span data-ttu-id="4b190-139">Microsoft 安全评分概述</span><span class="sxs-lookup"><span data-stu-id="4b190-139">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="4b190-140">深入了解你的安全状况</span><span class="sxs-lookup"><span data-stu-id="4b190-140">Gain visibility into your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="4b190-141">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="4b190-141">What's coming</span></span>](microsoft-secure-score-whats-coming.md)