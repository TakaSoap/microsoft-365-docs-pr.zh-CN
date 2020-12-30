---
title: 通过 Microsoft 安全分数评估安全状况
description: 介绍如何采取措施改进 Microsoft 365 安全中心中的 Microsoft 安全分数。
keywords: microsoft 安全分数， 安全分数， office 365 安全分数， Microsoft 安全分数， microsoft 365 安全中心， 改进操作
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
ms.openlocfilehash: c463e375594b3581486cb8d4bdd380412e195b2e
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738007"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="7aa0b-104">使用 Microsoft 安全分数评估安全状态</span><span class="sxs-lookup"><span data-stu-id="7aa0b-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7aa0b-105">Microsoft 安全分数是组织安全状况的度量，数字越高，表示采取的改进操作就越高。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="7aa0b-106">可以在 https://security.microsoft.com/securescore [Microsoft 365 安全中心找到它](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="7aa0b-107">为了帮助您更快获得所需的信息，Microsoft 改进操作分为多个组：</span><span class="sxs-lookup"><span data-stu-id="7aa0b-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="7aa0b-108">Azure (Directory 帐户的标识&角色) </span><span class="sxs-lookup"><span data-stu-id="7aa0b-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="7aa0b-109">Device (For Endpoint 的 Microsoft Defender，称为 [适用于终结点的 Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices) 安全) </span><span class="sxs-lookup"><span data-stu-id="7aa0b-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="7aa0b-110">应用 (电子邮件和云应用，包括 Office 365 和 Microsoft Cloud App Security) </span><span class="sxs-lookup"><span data-stu-id="7aa0b-110">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="7aa0b-111">在 Microsoft 安全分数的最近版本中，已发布了改进的评分模型，使 Microsoft 安全分数暂时与标识安全分数和 Graph API 不兼容。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="7aa0b-112">查看详细信息</span><span class="sxs-lookup"><span data-stu-id="7aa0b-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="7aa0b-113">在"Microsoft 安全分数概述"页中，查看如何在这些组之间拆分分数以及可用分数。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="7aa0b-114">通过基准比较，还可以全面查看总分、安全分数的历史趋势，以及可用于提高分数的优先级改进操作。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![安全分数主页](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="7aa0b-116">检查当前分数</span><span class="sxs-lookup"><span data-stu-id="7aa0b-116">Check your current score</span></span>

<span data-ttu-id="7aa0b-117">若要检查当前分数，请转到 Microsoft 安全分数概述页面，并查找显示安全分数 **的磁贴**。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="7aa0b-118">你的分数将显示为百分比，以及你从可能的总分数中实现的点数。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="7aa0b-119">此外，如果你选择分数旁边的" **包含** "按钮，你可以选择你的分数的不同视图。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="7aa0b-120">这些不同的分数视图将在分数磁贴和点细分图表的图形中显示。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="7aa0b-121">以下是你可以添加到总体分数视图的分数，以便更完整地了解总体分数：</span><span class="sxs-lookup"><span data-stu-id="7aa0b-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="7aa0b-122">**计划分数**：在计划操作完成时显示计划分数</span><span class="sxs-lookup"><span data-stu-id="7aa0b-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="7aa0b-123">**当前许可证分数**：显示可以使用当前 Microsoft 许可证实现的分数</span><span class="sxs-lookup"><span data-stu-id="7aa0b-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="7aa0b-124">**可得分**：显示可通过 Microsoft 许可证和当前风险接受实现的分数</span><span class="sxs-lookup"><span data-stu-id="7aa0b-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="7aa0b-125">如果已包含所有可能的得分视图，则此视图的外观将如下所示：</span><span class="sxs-lookup"><span data-stu-id="7aa0b-125">This view is what it will look like if you've included all possible score views:</span></span>

![你的安全分数，包括计划分数、当前许可证分数和可得分](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="7aa0b-127">采取措施提高分数</span><span class="sxs-lookup"><span data-stu-id="7aa0b-127">Take action to improve your score</span></span>

<span data-ttu-id="7aa0b-128">" **改进操作** "选项卡列出了解决可能的攻击面的安全建议。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="7aa0b-129">它还包括其状态 (解决、计划、接受的风险、通过第三方解决、通过备用缓解解决和已完成) 。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="7aa0b-130">可以搜索、筛选和分组所有改进操作。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="7aa0b-131">排名</span><span class="sxs-lookup"><span data-stu-id="7aa0b-131">Ranking</span></span>

<span data-ttu-id="7aa0b-132">排名基于要实现的分数数、实现难度、用户影响和复杂性。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="7aa0b-133">排名最高的改进操作仍具有大量分数，但难度、用户影响和复杂性较低。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="7aa0b-134">查看改进操作详细信息</span><span class="sxs-lookup"><span data-stu-id="7aa0b-134">View improvement action details</span></span>

<span data-ttu-id="7aa0b-135">选择特定改进操作时，将出现一个整页的飞出图。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![改进操作飞出示例](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="7aa0b-137">若要完成该操作，有几个选项：</span><span class="sxs-lookup"><span data-stu-id="7aa0b-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="7aa0b-138">选择 **"** 管理"转到配置屏幕并做出更改。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="7aa0b-139">然后，你将获得操作有价值的点，在飞出时可见。点通常需要大约 24 小时才能更新。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="7aa0b-140">选择 **"** 共享"以复制指向改进操作的直接链接。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="7aa0b-141">还可以选择共享链接的平台，如电子邮件、Microsoft Teams、Microsoft Planner 或 ServiceNow。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-141">You can also choose the platform to share the link, such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="7aa0b-142">选择 ServiceNow 将让你创建将在 ServiceNow 和 Microsoft 365 安全中心主页中可见的更改票证。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-142">Selecting ServiceNow will let you create a change ticket that will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="7aa0b-143">若要了解更多信息，请参阅 [Microsoft 365 安全中心和 ServiceNow 集成](tickets-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-143">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

<span data-ttu-id="7aa0b-144">添加 **注释** 以跟踪进度或要注释的任何内容。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-144">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="7aa0b-145">如果向改进操作 **添加** 自己的标记，可以按这些标记进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-145">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="7aa0b-146">选择改进操作状态</span><span class="sxs-lookup"><span data-stu-id="7aa0b-146">Choose an improvement action status</span></span>

<span data-ttu-id="7aa0b-147">选择任何状态并记录特定于改进操作的记录。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-147">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="7aa0b-148">**要** 解决 - 您意识到改进操作是必需的，并计划在将来的某一时间点处理改进操作。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-148">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="7aa0b-149">此状态还适用于被检测为部分但未完成的操作。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-149">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="7aa0b-150">**已计划** - 已制定具体计划来完成改进操作。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-150">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="7aa0b-151">**接受** 风险 - 安全性应始终与可用性进行平衡，并且并不是每个建议都适用于你的环境。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-151">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="7aa0b-152">在这种情况下，你可以选择接受风险或剩余风险，而不是强调改进操作。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-152">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="7aa0b-153">你将不会获得任何分数，但该操作将不再显示在改进操作列表中。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-153">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="7aa0b-154">可以在历史记录中查看此操作，也可以随时撤消此操作。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-154">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="7aa0b-155">**通过第三方解决** ， **通过** 备用缓解解决 - 改进操作已由第三方应用程序或软件或内部工具解决。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-155">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="7aa0b-156">你将获得操作有价值的分数，以便你的分数更好地反映你的整体安全状况。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-156">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="7aa0b-157">如果第三方或内部工具不再涵盖该控件，可以选择其他状态。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-157">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="7aa0b-158">请记住，如果改进操作被标记为这些状态之一，Microsoft 将不能了解实现的完整性。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-158">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="7aa0b-159">威胁&漏洞管理改进操作</span><span class="sxs-lookup"><span data-stu-id="7aa0b-159">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="7aa0b-160">对于"设备"类别中的改进操作，你无法选择状态。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-160">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="7aa0b-161">相反，你将被定向到[Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)安全中心中的关联威胁和漏洞管理安全建议以采取措施。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-161">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="7aa0b-162">你选择的例外以及你编写的理由将特定于该门户。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-162">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="7aa0b-163">它不会在 Microsoft 安全分数门户中显示。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-163">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="7aa0b-164">已完成的改进操作</span><span class="sxs-lookup"><span data-stu-id="7aa0b-164">Completed improvement actions</span></span>

<span data-ttu-id="7aa0b-165">一旦达到改进操作的所有可能点，改进操作就具有"已完成"状态。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-165">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="7aa0b-166">已完成的改进操作通过 Microsoft 数据进行确认，你无法更改状态。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-166">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="7aa0b-167">评估信息并查看用户影响</span><span class="sxs-lookup"><span data-stu-id="7aa0b-167">Assess information and review user impact</span></span>

<span data-ttu-id="7aa0b-168">名为 **"概览"的部分** 将告诉您类别、可抵御的攻击和产品。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-168">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="7aa0b-169">**用户** 影响是实施改进措施时用户将遇到的问题，受影响用户是将受到影响的用户。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-169">**User impact** is what the users will experience if the improvement action is enacted, and **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="7aa0b-170">实施改进操作</span><span class="sxs-lookup"><span data-stu-id="7aa0b-170">Implement the improvement action</span></span>

<span data-ttu-id="7aa0b-171">" **实现** "部分显示了任何先决条件、完成改进操作所需的分步步骤、改进操作的当前实现状态以及任何了解更多链接。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-171">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="7aa0b-172">先决条件包括解决改进操作之前需要的任何许可证或要完成的操作。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-172">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="7aa0b-173">请确保许可证中有足够的座位来完成改进操作，并且这些许可证适用于必要的用户。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-173">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="7aa0b-174">欢迎提出宝贵意见</span><span class="sxs-lookup"><span data-stu-id="7aa0b-174">We want to hear from you</span></span>

<span data-ttu-id="7aa0b-175">如果有任何问题，请通过发布到安全、隐私和合规社区& [告知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 我们。</span><span class="sxs-lookup"><span data-stu-id="7aa0b-175">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="7aa0b-176">We're monitoring the community and will provide help.</span><span class="sxs-lookup"><span data-stu-id="7aa0b-176">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="7aa0b-177">相关资源</span><span class="sxs-lookup"><span data-stu-id="7aa0b-177">Related resources</span></span>

- [<span data-ttu-id="7aa0b-178">Microsoft 安全分数概述</span><span class="sxs-lookup"><span data-stu-id="7aa0b-178">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="7aa0b-179">跟踪 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="7aa0b-179">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="7aa0b-180">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="7aa0b-180">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="7aa0b-181">新增功能</span><span class="sxs-lookup"><span data-stu-id="7aa0b-181">What's new</span></span>](microsoft-secure-score-whats-new.md)
