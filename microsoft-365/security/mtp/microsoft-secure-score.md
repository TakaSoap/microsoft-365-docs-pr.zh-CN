---
title: Microsoft 安全功能分数
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 74afe39e78990d794368ed19aa5fd5116bee17bb
ms.sourcegitcommit: 0830be61e21570ee3a2589e35c21f358b52585c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "37774905"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="ce251-104">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="ce251-104">Microsoft Secure Score</span></span>

<span data-ttu-id="ce251-105">Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。</span><span class="sxs-lookup"><span data-stu-id="ce251-105">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="ce251-106">从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="ce251-106">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="ce251-107">安全分数可帮助组织：</span><span class="sxs-lookup"><span data-stu-id="ce251-107">Secure Score helps organizations:</span></span>

* <span data-ttu-id="ce251-108">报告组织安全状况的当前状态。</span><span class="sxs-lookup"><span data-stu-id="ce251-108">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="ce251-109">通过提供可发现性、可见性、指导和控制改进其安全状况。</span><span class="sxs-lookup"><span data-stu-id="ce251-109">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="ce251-110">与基准进行比较并建立关键绩效指标（Kpi）。</span><span class="sxs-lookup"><span data-stu-id="ce251-110">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="ce251-111">组织可以获得对指标和趋势的可靠可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较以及其他更多。</span><span class="sxs-lookup"><span data-stu-id="ce251-111">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="ce251-112">分数还可以反映第三方解决方案解决建议操作的时间。</span><span class="sxs-lookup"><span data-stu-id="ce251-112">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="ce251-113">此外，你还可以通过[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)访问你的建议和评分。</span><span class="sxs-lookup"><span data-stu-id="ce251-113">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="ce251-114">了解[安全分数资源类型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="ce251-114">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="ce251-115">运作方式</span><span class="sxs-lookup"><span data-stu-id="ce251-115">How it works</span></span>

<span data-ttu-id="ce251-116">为您提供配置推荐安全功能、执行与安全相关的任务（如查看报告）或使用第三方应用程序或软件解决改进操作的相关积分。</span><span class="sxs-lookup"><span data-stu-id="ce251-116">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="ce251-117">某些改进操作仅在完全完成时给出点，而有些改进操作在为某些设备或用户完成一些点时提供部分点。</span><span class="sxs-lookup"><span data-stu-id="ce251-117">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="ce251-118">安全性应与可用性平衡，而不是每个建议对您的环境都适用。</span><span class="sxs-lookup"><span data-stu-id="ce251-118">Security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="ce251-119">你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="ce251-119">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="ce251-120">安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。</span><span class="sxs-lookup"><span data-stu-id="ce251-120">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="ce251-121">如何对改进行动进行评分</span><span class="sxs-lookup"><span data-stu-id="ce251-121">How improvement actions are scored</span></span>

<span data-ttu-id="ce251-122">大多数都是以二进制方式进行评分—如果实现改进操作（如创建新策略或打开特定设置），则将获得100% 的点数。</span><span class="sxs-lookup"><span data-stu-id="ce251-122">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="ce251-123">对于其他改进操作，点作为总配置的百分比提供。</span><span class="sxs-lookup"><span data-stu-id="ce251-123">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="ce251-124">例如，如果通过使用多重身份验证保护您的所有用户，并且您只有5% 以上的用户都受到保护，则提高操作的状态为30点。在 2 100 个点的部分分数（5个受保护/100 总数 \* 30 个最大值 = 2 pt）中，可获得系数 部分分数）。</span><span class="sxs-lookup"><span data-stu-id="ce251-124">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="ce251-125">安全分数中包括的产品</span><span class="sxs-lookup"><span data-stu-id="ce251-125">Products included in Secure Score</span></span>

<span data-ttu-id="ce251-126">目前，我们提供了 Office 365 的一些建议（包括 SharePoint Online、Exchange Online、OneDrive for Business、Microsoft 信息保护等）、Azure AD、Intune 和云应用安全性。</span><span class="sxs-lookup"><span data-stu-id="ce251-126">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, Intune, and Cloud App Security.</span></span> <span data-ttu-id="ce251-127">对其他安全产品（如 Azure ATP 和 Microsoft Defender ATP）的建议即将推出。</span><span class="sxs-lookup"><span data-stu-id="ce251-127">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="ce251-128">这些建议不包含与每个产品相关联的所有攻击面，但都是一个很棒的基准。</span><span class="sxs-lookup"><span data-stu-id="ce251-128">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="ce251-129">您还可以将改进操作标记为第三方覆盖。</span><span class="sxs-lookup"><span data-stu-id="ce251-129">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="ce251-130">所需权限</span><span class="sxs-lookup"><span data-stu-id="ce251-130">Required permissions</span></span>

<span data-ttu-id="ce251-131">若要拥有访问 Microsoft 安全分数的权限，您必须在 Azure Active Directory 中为以下角色分配一个角色。</span><span class="sxs-lookup"><span data-stu-id="ce251-131">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="ce251-132">读取和写入角色</span><span class="sxs-lookup"><span data-stu-id="ce251-132">Read and write roles</span></span>

<span data-ttu-id="ce251-133">通过读取和写入访问权限，您可以进行更改，并直接与安全分数进行交互。</span><span class="sxs-lookup"><span data-stu-id="ce251-133">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="ce251-134">您还可以将只读访问权限分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="ce251-134">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="ce251-135">CompanyAdministrator</span><span class="sxs-lookup"><span data-stu-id="ce251-135">CompanyAdministrator</span></span>
* <span data-ttu-id="ce251-136">SecurityAdministrator</span><span class="sxs-lookup"><span data-stu-id="ce251-136">SecurityAdministrator</span></span>
* <span data-ttu-id="ce251-137">ExchangeAdmin</span><span class="sxs-lookup"><span data-stu-id="ce251-137">ExchangeAdmin</span></span>
* <span data-ttu-id="ce251-138">SharePointAdmin</span><span class="sxs-lookup"><span data-stu-id="ce251-138">SharePointAdmin</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="ce251-139">只读角色</span><span class="sxs-lookup"><span data-stu-id="ce251-139">Read-only roles</span></span>

<span data-ttu-id="ce251-140">如果具有只读访问权限，您将无法编辑 "改进" 操作的状态或注释、编辑分数区域或编辑自定义比较。</span><span class="sxs-lookup"><span data-stu-id="ce251-140">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="ce251-141">HelpdeskAdmin</span><span class="sxs-lookup"><span data-stu-id="ce251-141">HelpdeskAdmin</span></span>
* <span data-ttu-id="ce251-142">UserAccountAdmin</span><span class="sxs-lookup"><span data-stu-id="ce251-142">UserAccountAdmin</span></span>
* <span data-ttu-id="ce251-143">ServiceSupportAdmin</span><span class="sxs-lookup"><span data-stu-id="ce251-143">ServiceSupportAdmin</span></span>
* <span data-ttu-id="ce251-144">SecurityReader</span><span class="sxs-lookup"><span data-stu-id="ce251-144">SecurityReader</span></span>
* <span data-ttu-id="ce251-145">SecurityOperator</span><span class="sxs-lookup"><span data-stu-id="ce251-145">SecurityOperator</span></span>
* <span data-ttu-id="ce251-146">GlobalReader</span><span class="sxs-lookup"><span data-stu-id="ce251-146">GlobalReader</span></span>

### <a name="graph-api"></a><span data-ttu-id="ce251-147">Graph API</span><span class="sxs-lookup"><span data-stu-id="ce251-147">Graph API</span></span>

<span data-ttu-id="ce251-148">若要访问 Graph API，除了角色之外，还需要具有以下作用域之一：</span><span class="sxs-lookup"><span data-stu-id="ce251-148">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="ce251-149">Securityevents.readwrite.all （适用于只读角色）</span><span class="sxs-lookup"><span data-stu-id="ce251-149">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="ce251-150">Securityevents.readwrite.all （用于读取和写入角色）</span><span class="sxs-lookup"><span data-stu-id="ce251-150">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="ce251-151">深入了解你的安全状况</span><span class="sxs-lookup"><span data-stu-id="ce251-151">Gain visibility into your security posture</span></span>

<span data-ttu-id="ce251-152">为了帮助您更快地了解所需的信息，Microsoft 改善操作将组织成组：</span><span class="sxs-lookup"><span data-stu-id="ce251-152">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="ce251-153">Identity （Azure AD 帐户 & 角色，即将推出 Azure ATP）</span><span class="sxs-lookup"><span data-stu-id="ce251-153">Identity (Azure AD accounts & roles, with Azure ATP coming soon)</span></span>
* <span data-ttu-id="ce251-154">数据（Microsoft 信息保护）</span><span class="sxs-lookup"><span data-stu-id="ce251-154">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="ce251-155">设备（Microsoft Defender ATP 设备，即将推出）</span><span class="sxs-lookup"><span data-stu-id="ce251-155">Device (Microsoft Defender ATP devices, coming soon)</span></span>
* <span data-ttu-id="ce251-156">应用（电子邮件和云应用，包括 Office 365 和 Microsoft 云应用安全性）</span><span class="sxs-lookup"><span data-stu-id="ce251-156">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="ce251-157">基础结构（Azure 资源）</span><span class="sxs-lookup"><span data-stu-id="ce251-157">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="ce251-158">在 "Microsoft 安全分数概述" 页中，您可以看到在这些组之间如何拆分点以及哪些点可用。</span><span class="sxs-lookup"><span data-stu-id="ce251-158">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="ce251-159">[！注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置，以及可采取的优先改进措施以提高成绩。</span><span class="sxs-lookup"><span data-stu-id="ce251-159">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="ce251-160">![安全积分主页](../media/secure-score/homepage-original.png)
*图1： Microsoft 安全分数概述页面*</span><span class="sxs-lookup"><span data-stu-id="ce251-160">![Secure Score homepage](../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="ce251-161">采取行动以提高成绩</span><span class="sxs-lookup"><span data-stu-id="ce251-161">Take action to improve your score</span></span>

<span data-ttu-id="ce251-162">"改进操作" 选项卡列出了解决可能的攻击面的安全建议，以及它们的状态（已完成、未完成、已通过第三方解决和忽略）。</span><span class="sxs-lookup"><span data-stu-id="ce251-162">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="ce251-163">您可以搜索、筛选和分组所有改进操作。</span><span class="sxs-lookup"><span data-stu-id="ce251-163">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="ce251-164">排名</span><span class="sxs-lookup"><span data-stu-id="ce251-164">Ranking</span></span>

<span data-ttu-id="ce251-165">排名基于要达到的剩余点数、实现难度、用户影响和复杂性。</span><span class="sxs-lookup"><span data-stu-id="ce251-165">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="ce251-166">最高排名改进操作的剩余分数与较低的难度、用户影响和复杂性相同。</span><span class="sxs-lookup"><span data-stu-id="ce251-166">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="ce251-167">操作</span><span class="sxs-lookup"><span data-stu-id="ce251-167">Actions</span></span>

<span data-ttu-id="ce251-168">Microsoft 安全分数不会跟踪标记为 [未评分] 的操作。</span><span class="sxs-lookup"><span data-stu-id="ce251-168">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="ce251-169">你仍可以采取措施，但完成这些操作不会影响你的分数。</span><span class="sxs-lookup"><span data-stu-id="ce251-169">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="ce251-170">如果某个操作在将来被 Microsoft 安全得分跟踪，并且您已完成该操作，则安全得分将自动反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ce251-170">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="ce251-171">当您选择特定的 "改进" 操作时，将显示 "飞出"。</span><span class="sxs-lookup"><span data-stu-id="ce251-171">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="ce251-172">若要完成此操作，您有几个选项：</span><span class="sxs-lookup"><span data-stu-id="ce251-172">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="ce251-173">选择 "**查看设置**" 以转到配置屏幕并进行更改。</span><span class="sxs-lookup"><span data-stu-id="ce251-173">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="ce251-174">然后，您可以在飞出的顶部看到该操作值得的要点。点可能需要长达24小时才能更新。</span><span class="sxs-lookup"><span data-stu-id="ce251-174">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="ce251-175">选择 "**通过第三方解决**"，因为改进操作已由第三方应用程序或软件解决。</span><span class="sxs-lookup"><span data-stu-id="ce251-175">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="ce251-176">您可以获得该操作所需要的要点，这样您的安全分数就能更好地反映您的总体安全状况。</span><span class="sxs-lookup"><span data-stu-id="ce251-176">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="ce251-177">如果第三方不再涵盖该控件，则可以将 "改进" 操作标记为 "不完成"。</span><span class="sxs-lookup"><span data-stu-id="ce251-177">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="ce251-178">请注意，如果将改进操作标记为通过第三方解决，Microsoft 无法了解是否满足评分要求。</span><span class="sxs-lookup"><span data-stu-id="ce251-178">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="ce251-179">选择 "**忽略**"，因为您已决定接受风险而不执行改进操作。</span><span class="sxs-lookup"><span data-stu-id="ce251-179">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="ce251-180">忽略 "改进" 操作后，您可以实现的安全分数点总数将减少。</span><span class="sxs-lookup"><span data-stu-id="ce251-180">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="ce251-181">您可以在历史记录中查看此操作，也可以随时撤消。</span><span class="sxs-lookup"><span data-stu-id="ce251-181">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="ce251-182">选择 "**审阅**"，因为改进操作要求您定期查看环境的一部分以获取和保留点。</span><span class="sxs-lookup"><span data-stu-id="ce251-182">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="ce251-183">例如，应每周查看邮箱转发规则，以确保不会从您的网络中泄露数据。</span><span class="sxs-lookup"><span data-stu-id="ce251-183">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="ce251-184">您无需进行任何更改，但需要执行操作。</span><span class="sxs-lookup"><span data-stu-id="ce251-184">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="ce251-185">如果您定期查看规则，您将收到要点。</span><span class="sxs-lookup"><span data-stu-id="ce251-185">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="ce251-186">如果不是，则减少分数。</span><span class="sxs-lookup"><span data-stu-id="ce251-186">If not, the score is reduced.</span></span>

![安全分数提高操作示例](../media/secure-score/secure-score1x450.png) ![安全分数评审改进操作示例](../media/secure-score/secure-score2x450.png)

<span data-ttu-id="ce251-189">*图 2 & 3：改进操作 flyouts*</span><span class="sxs-lookup"><span data-stu-id="ce251-189">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="ce251-190">随着时间的推移监视改进</span><span class="sxs-lookup"><span data-stu-id="ce251-190">Monitor improvements over time</span></span>

<span data-ttu-id="ce251-191">您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。在图下方是在所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。</span><span class="sxs-lookup"><span data-stu-id="ce251-191">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="ce251-192">您可以自定义日期范围并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="ce251-192">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="ce251-193">风险感知</span><span class="sxs-lookup"><span data-stu-id="ce251-193">Risk awareness</span></span>

<span data-ttu-id="ce251-194">Microsoft 安全分数是基于系统配置、用户行为和其他与安全相关的度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="ce251-194">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="ce251-195">相反，它表示您在 Microsoft 环境中已采用安全控制的程度，这有助于抵消受到破坏的风险。</span><span class="sxs-lookup"><span data-stu-id="ce251-195">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="ce251-196">无在线服务完全不受安全破坏，并且安全分数不应以任何方式解释为保证安全。</span><span class="sxs-lookup"><span data-stu-id="ce251-196">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-coming"></a><span data-ttu-id="ce251-197">接下来是什么？</span><span class="sxs-lookup"><span data-stu-id="ce251-197">What's coming?</span></span>

<span data-ttu-id="ce251-198">为了使 Microsoft 安全得分更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="ce251-198">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="ce251-199">你的分数和可能的最大分数都将发生变化。</span><span class="sxs-lookup"><span data-stu-id="ce251-199">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="ce251-200">但是，这并不意味着您的安全状况发生了变化。</span><span class="sxs-lookup"><span data-stu-id="ce251-200">However, this does not imply a change in your security posture.</span></span>

### <a name="removing-not-scored-and-review-improvement-actions"></a><span data-ttu-id="ce251-201">删除 "未评分" 和 "审阅" 改进操作</span><span class="sxs-lookup"><span data-stu-id="ce251-201">Removing “not scored” and “review” improvement actions</span></span>

<span data-ttu-id="ce251-202">安全得分的原则之一是，分数应标准化且易于关联。</span><span class="sxs-lookup"><span data-stu-id="ce251-202">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="ce251-203">具有不可衡量或可操作的改进操作已导致混淆。</span><span class="sxs-lookup"><span data-stu-id="ce251-203">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="ce251-204">仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。</span><span class="sxs-lookup"><span data-stu-id="ce251-204">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="ce251-205">不计分的提高操作不可度量，并且与其他改进操作相比，不会将 "改进" 操作评估为与相同标准。</span><span class="sxs-lookup"><span data-stu-id="ce251-205">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="ce251-206">出于这些原因，所有未评分或要求的改进操作将暂时删除。</span><span class="sxs-lookup"><span data-stu-id="ce251-206">For these reasons, all improvement actions that were not scored or required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="ce251-207">您的部件不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="ce251-207">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="ce251-208">简化了点系统</span><span class="sxs-lookup"><span data-stu-id="ce251-208">Simplification of the point system</span></span>

<span data-ttu-id="ce251-209">若要在多个体验中标准化要点，每个安全分数改进操作点总数将更新为10磅或更少。</span><span class="sxs-lookup"><span data-stu-id="ce251-209">To standardize points across multiple experiences, each Secure Score improvement action point total will be updated to be worth 10 points or less.</span></span> <span data-ttu-id="ce251-210">在我们目前所拥有的安全控制的广泛 breather 和将来将添加的安全控制中，必须更加一致。</span><span class="sxs-lookup"><span data-stu-id="ce251-210">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="ce251-211">虽然这是一项重大更改，并且你将在点汇总中看到一个拖放，但你的安全状态不会有任何变化。</span><span class="sxs-lookup"><span data-stu-id="ce251-211">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>  

### <a name="preview-features"></a><span data-ttu-id="ce251-212">预览功能</span><span class="sxs-lookup"><span data-stu-id="ce251-212">Preview features</span></span>

<span data-ttu-id="ce251-213">预览版本中将包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="ce251-213">The following features will be included in the preview release:</span></span>

* <span data-ttu-id="ce251-214">CISO 和潜在客户级别讨论的所有新指标和趋势视图</span><span class="sxs-lookup"><span data-stu-id="ce251-214">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="ce251-215">跟踪和基准成绩的新方法</span><span class="sxs-lookup"><span data-stu-id="ce251-215">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="ce251-216">更好地跟踪和监控分数回归</span><span class="sxs-lookup"><span data-stu-id="ce251-216">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="ce251-217">筛选、标记、搜索和分组您的改进操作</span><span class="sxs-lookup"><span data-stu-id="ce251-217">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="ce251-218">使用分数预测和计划操作来管理未来目标</span><span class="sxs-lookup"><span data-stu-id="ce251-218">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="ce251-219">更多！</span><span class="sxs-lookup"><span data-stu-id="ce251-219">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="ce251-220">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="ce251-220">We want to hear from you</span></span>

<span data-ttu-id="ce251-221">如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="ce251-221">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="ce251-222">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="ce251-222">We're monitoring the community and will provide help.</span></span>
