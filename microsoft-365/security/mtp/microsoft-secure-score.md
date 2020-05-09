---
title: Microsoft 安全得分（以前的迭代）
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何提高安全状态以及安全管理员可预期的功能。
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
ms.openlocfilehash: 383ef5a0ff61b861bd72dc08d7b974ef98592fcc
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173388"
---
# <a name="microsoft-secure-score-previous-iteration"></a><span data-ttu-id="da7b5-104">Microsoft 安全得分（以前的迭代）</span><span class="sxs-lookup"><span data-stu-id="da7b5-104">Microsoft Secure Score (previous iteration)</span></span>

>[!IMPORTANT]
><span data-ttu-id="da7b5-105">在接下来的几个月中，这一小部分 Microsoft 安全分数将被替换为新的设计元素和功能。</span><span class="sxs-lookup"><span data-stu-id="da7b5-105">This iteration of Microsoft Secure Score is being replaced with new design elements and features over the next few months.</span></span> <span data-ttu-id="da7b5-106">如果您还没有看到最新小版本，很快就会完成。</span><span class="sxs-lookup"><span data-stu-id="da7b5-106">If you do not already see the newest iteration, you will soon.</span></span>
>
><span data-ttu-id="da7b5-107">如果您看到 "历史记录" 旁边的 "**指标 & 趋势**" 选项卡，则是在新的迭代中。</span><span class="sxs-lookup"><span data-stu-id="da7b5-107">If you see a **Metrics & trends** tab next to History, you are in the new iteration.</span></span> [<span data-ttu-id="da7b5-108">转到 Microsoft Secure 评分（新）</span><span class="sxs-lookup"><span data-stu-id="da7b5-108">Go to Microsoft Secure Score (new)</span></span>](microsoft-secure-score-new.md)

<span data-ttu-id="da7b5-109">Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。</span><span class="sxs-lookup"><span data-stu-id="da7b5-109">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="da7b5-110">按照安全得分建议，可以保护您的组织免受威胁。</span><span class="sxs-lookup"><span data-stu-id="da7b5-110">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="da7b5-111">从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="da7b5-111">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="da7b5-112">安全分数可帮助组织：</span><span class="sxs-lookup"><span data-stu-id="da7b5-112">Secure Score helps organizations:</span></span>

* <span data-ttu-id="da7b5-113">报告组织安全状况的当前状态。</span><span class="sxs-lookup"><span data-stu-id="da7b5-113">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="da7b5-114">通过提供可发现性、可见性、指导和控制改进其安全状况。</span><span class="sxs-lookup"><span data-stu-id="da7b5-114">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="da7b5-115">与基准进行比较并建立关键绩效指标（Kpi）。</span><span class="sxs-lookup"><span data-stu-id="da7b5-115">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="da7b5-116">组织可以获得对指标和趋势的可靠可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较以及其他更多。</span><span class="sxs-lookup"><span data-stu-id="da7b5-116">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="da7b5-117">分数还可以反映第三方解决方案解决建议操作的时间。</span><span class="sxs-lookup"><span data-stu-id="da7b5-117">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="da7b5-118">此外，你还可以通过[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)访问你的建议和评分。</span><span class="sxs-lookup"><span data-stu-id="da7b5-118">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="da7b5-119">了解[安全分数资源类型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="da7b5-119">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="da7b5-120">工作原理</span><span class="sxs-lookup"><span data-stu-id="da7b5-120">How it works</span></span>

<span data-ttu-id="da7b5-121">为您提供配置推荐安全功能、执行与安全相关的任务（如查看报告）或使用第三方应用程序或软件解决改进操作的相关积分。</span><span class="sxs-lookup"><span data-stu-id="da7b5-121">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="da7b5-122">某些改进操作仅在完全完成时给出点，而有些改进操作在为某些设备或用户完成一些点时提供部分点。</span><span class="sxs-lookup"><span data-stu-id="da7b5-122">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span>

<span data-ttu-id="da7b5-123">我们为你展示了完整的一组可能的改进，而不考虑许可证，因此你可以了解安全最佳做法并提高你的成绩。</span><span class="sxs-lookup"><span data-stu-id="da7b5-123">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="da7b5-124">绝对安全状态由安全分数表示，无论贵组织拥有哪些产品许可证，这都保持不变。</span><span class="sxs-lookup"><span data-stu-id="da7b5-124">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="da7b5-125">请记住，安全应平衡可用性，而不是每个建议都适用于您的环境。</span><span class="sxs-lookup"><span data-stu-id="da7b5-125">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="da7b5-126">你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="da7b5-126">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="da7b5-127">安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。</span><span class="sxs-lookup"><span data-stu-id="da7b5-127">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="da7b5-128">如何对改进行动进行评分</span><span class="sxs-lookup"><span data-stu-id="da7b5-128">How improvement actions are scored</span></span>

<span data-ttu-id="da7b5-129">大多数都是以二进制方式进行评分—如果实现改进操作（如创建新策略或打开特定设置），则将获得100% 的点数。</span><span class="sxs-lookup"><span data-stu-id="da7b5-129">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="da7b5-130">对于其他改进操作，点作为总配置的百分比提供。</span><span class="sxs-lookup"><span data-stu-id="da7b5-130">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="da7b5-131">例如，如果使用多重身份验证保护您的所有用户，并且您仅有5% 以上100的用户受到保护，则 "改进" 操作将获得约30个点（共有2个分数，即5个 "受保护/100 总计 \* 30 个最大值 = 2 pt 部分分数"）。</span><span class="sxs-lookup"><span data-stu-id="da7b5-131">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="da7b5-132">安全分数中包括的产品</span><span class="sxs-lookup"><span data-stu-id="da7b5-132">Products included in Secure Score</span></span>

<span data-ttu-id="da7b5-133">目前有关于 Microsoft 365 （包括 Exchange Online）、Azure AD、Microsoft Defender ATP、Azure ATP 和云应用安全性的建议。</span><span class="sxs-lookup"><span data-stu-id="da7b5-133">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="da7b5-134">即将推出针对其他安全产品的建议。</span><span class="sxs-lookup"><span data-stu-id="da7b5-134">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="da7b5-135">这些建议不包含与每个产品相关联的所有攻击面，但都是一个很棒的基准。</span><span class="sxs-lookup"><span data-stu-id="da7b5-135">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="da7b5-136">您还可以将改进操作标记为第三方覆盖。</span><span class="sxs-lookup"><span data-stu-id="da7b5-136">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="da7b5-137">所需权限</span><span class="sxs-lookup"><span data-stu-id="da7b5-137">Required permissions</span></span>

<span data-ttu-id="da7b5-138">若要拥有访问 Microsoft 安全分数的权限，您必须在 Azure Active Directory 中为以下角色分配一个角色。</span><span class="sxs-lookup"><span data-stu-id="da7b5-138">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="da7b5-139">读取和写入角色</span><span class="sxs-lookup"><span data-stu-id="da7b5-139">Read and write roles</span></span>

<span data-ttu-id="da7b5-140">通过读取和写入访问权限，您可以进行更改，并直接与安全分数进行交互。</span><span class="sxs-lookup"><span data-stu-id="da7b5-140">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="da7b5-141">您还可以将只读访问权限分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="da7b5-141">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="da7b5-142">全局管理员</span><span class="sxs-lookup"><span data-stu-id="da7b5-142">Global administrator</span></span>
* <span data-ttu-id="da7b5-143">安全管理员</span><span class="sxs-lookup"><span data-stu-id="da7b5-143">Security administrator</span></span>
* <span data-ttu-id="da7b5-144">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="da7b5-144">Exchange administrator</span></span>
* <span data-ttu-id="da7b5-145">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="da7b5-145">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="da7b5-146">只读角色</span><span class="sxs-lookup"><span data-stu-id="da7b5-146">Read-only roles</span></span>

<span data-ttu-id="da7b5-147">如果具有只读访问权限，您将无法编辑 "改进" 操作的状态或注释、编辑分数区域或编辑自定义比较。</span><span class="sxs-lookup"><span data-stu-id="da7b5-147">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="da7b5-148">帮助台管理员</span><span class="sxs-lookup"><span data-stu-id="da7b5-148">Helpdesk administrator</span></span>
* <span data-ttu-id="da7b5-149">用户管理员</span><span class="sxs-lookup"><span data-stu-id="da7b5-149">User administrator</span></span>
* <span data-ttu-id="da7b5-150">服务管理员</span><span class="sxs-lookup"><span data-stu-id="da7b5-150">Service administrator</span></span>
* <span data-ttu-id="da7b5-151">安全读取者</span><span class="sxs-lookup"><span data-stu-id="da7b5-151">Security reader</span></span>
* <span data-ttu-id="da7b5-152">安全操作员</span><span class="sxs-lookup"><span data-stu-id="da7b5-152">Security operator</span></span>
* <span data-ttu-id="da7b5-153">全局读取者</span><span class="sxs-lookup"><span data-stu-id="da7b5-153">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="da7b5-154">Graph API</span><span class="sxs-lookup"><span data-stu-id="da7b5-154">Graph API</span></span>

<span data-ttu-id="da7b5-155">若要访问 Graph API，除了角色之外，还需要具有以下作用域之一：</span><span class="sxs-lookup"><span data-stu-id="da7b5-155">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="da7b5-156">Securityevents.readwrite.all （适用于只读角色）</span><span class="sxs-lookup"><span data-stu-id="da7b5-156">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="da7b5-157">Securityevents.readwrite.all （用于读取和写入角色）</span><span class="sxs-lookup"><span data-stu-id="da7b5-157">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="da7b5-158">深入了解你的安全状况</span><span class="sxs-lookup"><span data-stu-id="da7b5-158">Gain visibility into your security posture</span></span>

<span data-ttu-id="da7b5-159">为了帮助您更快地了解所需的信息，Microsoft 改善操作将组织成组：</span><span class="sxs-lookup"><span data-stu-id="da7b5-159">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="da7b5-160">Identity （Azure AD 帐户 & 角色）</span><span class="sxs-lookup"><span data-stu-id="da7b5-160">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="da7b5-161">数据（Microsoft 信息保护）</span><span class="sxs-lookup"><span data-stu-id="da7b5-161">Data (Microsoft Information Protection)</span></span>
* <span data-ttu-id="da7b5-162">设备（现在无改进操作）</span><span class="sxs-lookup"><span data-stu-id="da7b5-162">Device (no improvement actions for now)</span></span>
* <span data-ttu-id="da7b5-163">应用（电子邮件和云应用，包括 Office 365 和 Microsoft 云应用安全性）</span><span class="sxs-lookup"><span data-stu-id="da7b5-163">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="da7b5-164">基础结构（暂时不提供改进操作）</span><span class="sxs-lookup"><span data-stu-id="da7b5-164">Infrastructure (no improvement actions for now)</span></span>

<span data-ttu-id="da7b5-165">在 "Microsoft 安全分数概述" 页中，您可以看到在这些组之间如何拆分点以及哪些点可用。</span><span class="sxs-lookup"><span data-stu-id="da7b5-165">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="da7b5-166">[！注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置，以及可采取的优先改进措施以提高成绩。</span><span class="sxs-lookup"><span data-stu-id="da7b5-166">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="da7b5-167">![安全积分主页](../../media/secure-score/homepage-original.png)
*图1： Microsoft 安全分数概述页面*</span><span class="sxs-lookup"><span data-stu-id="da7b5-167">![Secure Score homepage](../../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="da7b5-168">采取行动以提高成绩</span><span class="sxs-lookup"><span data-stu-id="da7b5-168">Take action to improve your score</span></span>

<span data-ttu-id="da7b5-169">"改进操作" 选项卡列出了解决可能的攻击面的安全建议，以及它们的状态（已完成、未完成、已通过第三方解决和忽略）。</span><span class="sxs-lookup"><span data-stu-id="da7b5-169">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="da7b5-170">您可以搜索、筛选和分组所有改进操作。</span><span class="sxs-lookup"><span data-stu-id="da7b5-170">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="da7b5-171">排名</span><span class="sxs-lookup"><span data-stu-id="da7b5-171">Ranking</span></span>

<span data-ttu-id="da7b5-172">排名基于要达到的剩余点数、实现难度、用户影响和复杂性。</span><span class="sxs-lookup"><span data-stu-id="da7b5-172">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="da7b5-173">最高排名改进操作的剩余分数与较低的难度、用户影响和复杂性相同。</span><span class="sxs-lookup"><span data-stu-id="da7b5-173">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="da7b5-174">操作</span><span class="sxs-lookup"><span data-stu-id="da7b5-174">Actions</span></span>

<span data-ttu-id="da7b5-175">当您选择特定的 "改进" 操作时，将显示 "飞出"。</span><span class="sxs-lookup"><span data-stu-id="da7b5-175">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="da7b5-176">若要完成此操作，您有几个选项：</span><span class="sxs-lookup"><span data-stu-id="da7b5-176">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="da7b5-177">选择 "**查看设置**" 以转到配置屏幕并进行更改。</span><span class="sxs-lookup"><span data-stu-id="da7b5-177">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="da7b5-178">然后，您可以在飞出的顶部看到该操作值得的要点。点可能需要长达24小时才能更新。</span><span class="sxs-lookup"><span data-stu-id="da7b5-178">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="da7b5-179">选择 "**通过第三方解决**"，因为改进操作已由第三方应用程序或软件解决。</span><span class="sxs-lookup"><span data-stu-id="da7b5-179">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="da7b5-180">您可以获得该操作所需要的要点，这样您的安全分数就能更好地反映您的总体安全状况。</span><span class="sxs-lookup"><span data-stu-id="da7b5-180">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="da7b5-181">如果第三方不再涵盖该控件，则可以将 "改进" 操作标记为 "不完成"。</span><span class="sxs-lookup"><span data-stu-id="da7b5-181">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="da7b5-182">请注意，如果将改进操作标记为通过第三方解决，Microsoft 无法了解是否满足评分要求。</span><span class="sxs-lookup"><span data-stu-id="da7b5-182">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="da7b5-183">选择 "**忽略**"，因为您已决定接受风险而不执行改进操作。</span><span class="sxs-lookup"><span data-stu-id="da7b5-183">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="da7b5-184">忽略 "改进" 操作后，您可以实现的安全分数点总数将减少。</span><span class="sxs-lookup"><span data-stu-id="da7b5-184">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="da7b5-185">您可以在历史记录中查看此操作，也可以随时撤消。</span><span class="sxs-lookup"><span data-stu-id="da7b5-185">You can view this action in history or undo it at any time.</span></span>

![安全分数提高操作示例](../../media/secure-score/secure-score1x450.png)

<span data-ttu-id="da7b5-187">*图2：改进操作浮出控件*</span><span class="sxs-lookup"><span data-stu-id="da7b5-187">*Figures 2: Improvement action flyout*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="da7b5-188">随着时间的推移监视改进</span><span class="sxs-lookup"><span data-stu-id="da7b5-188">Monitor improvements over time</span></span>

<span data-ttu-id="da7b5-189">您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。在图下方是在所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。</span><span class="sxs-lookup"><span data-stu-id="da7b5-189">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="da7b5-190">您可以自定义日期范围并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="da7b5-190">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="da7b5-191">风险感知</span><span class="sxs-lookup"><span data-stu-id="da7b5-191">Risk awareness</span></span>

<span data-ttu-id="da7b5-192">Microsoft 安全分数是基于系统配置、用户行为和其他与安全相关的度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="da7b5-192">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="da7b5-193">相反，它表示您在 Microsoft 环境中已采用安全控制的程度，这有助于抵消受到破坏的风险。</span><span class="sxs-lookup"><span data-stu-id="da7b5-193">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="da7b5-194">无在线服务完全不受安全破坏，并且安全分数不应以任何方式解释为保证安全。</span><span class="sxs-lookup"><span data-stu-id="da7b5-194">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="da7b5-195">新变化？</span><span class="sxs-lookup"><span data-stu-id="da7b5-195">What's new?</span></span>

<span data-ttu-id="da7b5-196">若要使 Microsoft 安全得分更好地代表安全状态，我们做出了一些更改。</span><span class="sxs-lookup"><span data-stu-id="da7b5-196">To make Microsoft Secure Score a better representative of your security posture we have made some changes.</span></span> <span data-ttu-id="da7b5-197">若要了解计划的更改，请参阅[Microsoft 安全分数中的内容？](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="da7b5-197">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

### <a name="april-21st-2020"></a><span data-ttu-id="da7b5-198">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="da7b5-198">April 21st 2020</span></span>

#### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="da7b5-199">删除不符合可靠测量预期的改进操作或不提供安全状态的有用表示形式</span><span class="sxs-lookup"><span data-stu-id="da7b5-199">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="da7b5-200">为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。</span><span class="sxs-lookup"><span data-stu-id="da7b5-200">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="da7b5-201">将 IRM 保护应用于文档</span><span class="sxs-lookup"><span data-stu-id="da7b5-201">Apply IRM protections to documents</span></span>
- <span data-ttu-id="da7b5-202">应用数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-202">Apply Data Loss Prevention policies</span></span>

### <a name="january---march-2020"></a><span data-ttu-id="da7b5-203">1月-2020 年3月</span><span class="sxs-lookup"><span data-stu-id="da7b5-203">January - March 2020</span></span>

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="da7b5-204">支持 Azure AD 改进操作的安全默认值</span><span class="sxs-lookup"><span data-stu-id="da7b5-204">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="da7b5-205">Microsoft 安全分数将更新改进操作以支持[AZURE AD 中的安全默认](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)设置，这使组织可以更轻松地使用预配置的常见攻击安全设置来保护组织。</span><span class="sxs-lookup"><span data-stu-id="da7b5-205">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="da7b5-206">这将影响以下改进操作：</span><span class="sxs-lookup"><span data-stu-id="da7b5-206">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="da7b5-207">确保所有用户都可以完成多重身份验证以实现安全访问</span><span class="sxs-lookup"><span data-stu-id="da7b5-207">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="da7b5-208">需要对管理角色进行 MFA</span><span class="sxs-lookup"><span data-stu-id="da7b5-208">Require MFA for administrative roles</span></span>
- <span data-ttu-id="da7b5-209">启用策略以阻止旧版身份验证</span><span class="sxs-lookup"><span data-stu-id="da7b5-209">Enable policy to block legacy authentication</span></span>

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="da7b5-210">删除了不符合可靠测量预期的改进操作，或者不提供安全状态的有用表示形式</span><span class="sxs-lookup"><span data-stu-id="da7b5-210">Removed improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="da7b5-211">为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。</span><span class="sxs-lookup"><span data-stu-id="da7b5-211">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="da7b5-212">将用户文档存储在 OneDrive for Business 中</span><span class="sxs-lookup"><span data-stu-id="da7b5-212">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="da7b5-213">设置 Office 365 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-213">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="da7b5-214">设置 Office 365 安全链接以验证 Url</span><span class="sxs-lookup"><span data-stu-id="da7b5-214">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="da7b5-215">不允许邮箱委派</span><span class="sxs-lookup"><span data-stu-id="da7b5-215">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="da7b5-216">允许匿名来宾共享网站和文档的链接</span><span class="sxs-lookup"><span data-stu-id="da7b5-216">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="da7b5-217">启用云应用安全控制台</span><span class="sxs-lookup"><span data-stu-id="da7b5-217">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="da7b5-218">为外部共享链接配置过期时间</span><span class="sxs-lookup"><span data-stu-id="da7b5-218">Configure expiration time for external sharing links</span></span>
- <span data-ttu-id="da7b5-219">启用审核数据记录</span><span class="sxs-lookup"><span data-stu-id="da7b5-219">Turn on audit data recording</span></span>
- <span data-ttu-id="da7b5-220">发现有风险和不兼容的卷影 IT 应用程序</span><span class="sxs-lookup"><span data-stu-id="da7b5-220">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="da7b5-221">查看权限 & 阻止连接到您的环境的有风险的 OAuth 应用程序</span><span class="sxs-lookup"><span data-stu-id="da7b5-221">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="da7b5-222">在 SharePoint online 文档库中设置版本控制</span><span class="sxs-lookup"><span data-stu-id="da7b5-222">Set up versioning on SharePoint online document libraries</span></span>
- <span data-ttu-id="da7b5-223">删除/阻止在过去30天内未使用的帐户</span><span class="sxs-lookup"><span data-stu-id="da7b5-223">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="da7b5-224">指定少于5个全局管理员</span><span class="sxs-lookup"><span data-stu-id="da7b5-224">Designate fewer than 5 global admins</span></span>

#### <a name="removed-not-scored-improvement-actions"></a><span data-ttu-id="da7b5-225">删除了 "未评分" 的改进操作</span><span class="sxs-lookup"><span data-stu-id="da7b5-225">Removed "not scored" improvement actions</span></span>

<span data-ttu-id="da7b5-226">安全得分的原则之一是，分数应标准化且易于关联。</span><span class="sxs-lookup"><span data-stu-id="da7b5-226">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="da7b5-227">具有不可衡量或可操作的改进操作已导致混淆。</span><span class="sxs-lookup"><span data-stu-id="da7b5-227">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="da7b5-228">仅当每个建议可能对分数有明显影响时，Microsoft 安全分数才有意义。</span><span class="sxs-lookup"><span data-stu-id="da7b5-228">Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="da7b5-229">不计分的提高操作不可度量。</span><span class="sxs-lookup"><span data-stu-id="da7b5-229">Not scored improvement actions are not measurable.</span></span>  

<span data-ttu-id="da7b5-230">出于这些原因，未评分的所有改进操作均已删除。</span><span class="sxs-lookup"><span data-stu-id="da7b5-230">For these reasons, all improvement actions that were not scored have been removed.</span></span> <span data-ttu-id="da7b5-231">您的部件不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="da7b5-231">No action is needed on your part.</span></span>

#### <a name="removed-device-improvement-actions"></a><span data-ttu-id="da7b5-232">删除了设备改进操作</span><span class="sxs-lookup"><span data-stu-id="da7b5-232">Removed device improvement actions</span></span>

<span data-ttu-id="da7b5-233">评估 Microsoft 安全得分设备类别的改进操作后，确定这些操作当前评估策略状态，而不是设备的配置状态。</span><span class="sxs-lookup"><span data-stu-id="da7b5-233">After an evaluation of the Microsoft Secure Score device category of improvement actions, it was determined that those actions currently assess the policy state and not the configuration state of devices.</span></span> <span data-ttu-id="da7b5-234">由于配置直接与安全状态相关联，因此已确定现有的设备操作未完全代表组织的状况。</span><span class="sxs-lookup"><span data-stu-id="da7b5-234">Since configuration is directly tied to security posture, the existing device actions were determined to not fully represent organizational posture.</span></span>  <span data-ttu-id="da7b5-235">我们将删除设备类别中的当前操作，因为我们将提供一组直接使用诊断数据以更完整地表示设备安全状态的建议。</span><span class="sxs-lookup"><span data-stu-id="da7b5-235">We will be removing the current actions in the device category as we work to provide a set of recommendations which directly use diagnostic data to more fully represent device security posture.</span></span>

<span data-ttu-id="da7b5-236">已删除以下改进操作：</span><span class="sxs-lookup"><span data-stu-id="da7b5-236">The following improvement actions have been removed:</span></span>

- <span data-ttu-id="da7b5-237">启用 Microsoft Intune 移动设备管理</span><span class="sxs-lookup"><span data-stu-id="da7b5-237">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="da7b5-238">创建适用于 Android 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-238">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="da7b5-239">创建适用于 Android 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-239">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="da7b5-240">创建适用于 Android 的 Microsoft Intune 应用保护策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-240">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="da7b5-241">创建适用于 iOS 的 Microsoft Intune 应用保护策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-241">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="da7b5-242">标记不符合 Microsoft Intune 合规性策略的设备（未分配为不合规）</span><span class="sxs-lookup"><span data-stu-id="da7b5-242">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="da7b5-243">创建适用于 iOS 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-243">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="da7b5-244">为 macOS 创建 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-244">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="da7b5-245">创建适用于 Windows 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-245">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="da7b5-246">创建适用于 Android 的 Microsoft Intune 配置配置文件</span><span class="sxs-lookup"><span data-stu-id="da7b5-246">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="da7b5-247">为适用于 Android 的工作创建 Microsoft Intune 配置配置文件</span><span class="sxs-lookup"><span data-stu-id="da7b5-247">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="da7b5-248">为 macOS 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="da7b5-248">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="da7b5-249">为 iOS 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="da7b5-249">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="da7b5-250">为 Windows 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="da7b5-250">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="da7b5-251">在 Microsoft Intune 中启用增强型 jailbreak 检测</span><span class="sxs-lookup"><span data-stu-id="da7b5-251">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="da7b5-252">要求对所有设备进行修补，并启用防病毒和防火墙</span><span class="sxs-lookup"><span data-stu-id="da7b5-252">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="da7b5-253">启用 Microsoft Intune 中的 Windows Defender ATP 集成</span><span class="sxs-lookup"><span data-stu-id="da7b5-253">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="da7b5-254">创建 Microsoft Intune Windows 信息保护策略</span><span class="sxs-lookup"><span data-stu-id="da7b5-254">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="da7b5-255">要求所有设备都具有高级安全配置</span><span class="sxs-lookup"><span data-stu-id="da7b5-255">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="da7b5-256">每周查看阻止的设备报告</span><span class="sxs-lookup"><span data-stu-id="da7b5-256">Review blocked devices report weekly</span></span>

#### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="da7b5-257">MFA 改进操作更新</span><span class="sxs-lookup"><span data-stu-id="da7b5-257">MFA improvement action updates</span></span>

<span data-ttu-id="da7b5-258">为了反映企业在应用使用其业务的策略时确保 upmost 安全性的需求，Microsoft 安全分数已删除了围绕多重身份验证的三个改进操作，并添加了两个操作。</span><span class="sxs-lookup"><span data-stu-id="da7b5-258">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score has removed three improvement actions centered around multi-factor authentication, and added two.</span></span>

<span data-ttu-id="da7b5-259">删除了改进操作：</span><span class="sxs-lookup"><span data-stu-id="da7b5-259">Removed improvement actions:</span></span>

- <span data-ttu-id="da7b5-260">为多因素身份验证注册所有用户</span><span class="sxs-lookup"><span data-stu-id="da7b5-260">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="da7b5-261">要求对所有用户执行 MFA</span><span class="sxs-lookup"><span data-stu-id="da7b5-261">Require MFA for all users</span></span>
- <span data-ttu-id="da7b5-262">需要对 Azure AD 特权角色进行 MFA</span><span class="sxs-lookup"><span data-stu-id="da7b5-262">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="da7b5-263">添加了改进操作：</span><span class="sxs-lookup"><span data-stu-id="da7b5-263">Added improvement actions:</span></span>

- <span data-ttu-id="da7b5-264">确保所有用户都可以完成多重身份验证以实现安全访问</span><span class="sxs-lookup"><span data-stu-id="da7b5-264">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="da7b5-265">需要对管理角色进行 MFA</span><span class="sxs-lookup"><span data-stu-id="da7b5-265">Require MFA for administrative roles</span></span>

 <span data-ttu-id="da7b5-266">这些新的改进操作需要为你的用户或管理员在你的目录中注册多重身份验证（MFA），并建立符合你的组织需求的一组适当的策略。</span><span class="sxs-lookup"><span data-stu-id="da7b5-266">These new improvement actions require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="da7b5-267">主要目标具有灵活性，同时确保所有用户和管理员都可以通过多个因素或基于风险的身份验证提示进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="da7b5-267">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="da7b5-268">这可以采用具有多个策略的形式，这些策略将应用范围决定，或者设置安全默认值（即将3月16日），让 Microsoft 决定何时对用户进行 MFA 质询。</span><span class="sxs-lookup"><span data-stu-id="da7b5-268">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

#### <a name="removed-review-improvement-actions"></a><span data-ttu-id="da7b5-269">删除了 "审阅" 改进操作</span><span class="sxs-lookup"><span data-stu-id="da7b5-269">Removed "review" improvement actions</span></span>

<span data-ttu-id="da7b5-270">安全得分的原则之一是，分数应标准化且易于关联。</span><span class="sxs-lookup"><span data-stu-id="da7b5-270">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="da7b5-271">具有不可衡量或可操作的改进操作已导致混淆。</span><span class="sxs-lookup"><span data-stu-id="da7b5-271">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="da7b5-272">仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。</span><span class="sxs-lookup"><span data-stu-id="da7b5-272">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="da7b5-273">与其他改进操作相比，评审改进操作的计算方式不是相同标准。</span><span class="sxs-lookup"><span data-stu-id="da7b5-273">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="da7b5-274">出于这些原因，需要审阅节奏的所有改进操作都已暂时删除。</span><span class="sxs-lookup"><span data-stu-id="da7b5-274">For these reasons, all improvement actions that required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="da7b5-275">您的部件不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="da7b5-275">No action is needed on your part.</span></span>

### <a name="preview-features"></a><span data-ttu-id="da7b5-276">预览功能</span><span class="sxs-lookup"><span data-stu-id="da7b5-276">Preview features</span></span>

<span data-ttu-id="da7b5-277">[预览版本](microsoft-secure-score-preview.md)中将包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="da7b5-277">The following features will be included in the [preview release](microsoft-secure-score-preview.md):</span></span>

* <span data-ttu-id="da7b5-278">CISO 和潜在客户级别讨论的所有新指标和趋势视图</span><span class="sxs-lookup"><span data-stu-id="da7b5-278">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="da7b5-279">跟踪和基准成绩的新方法</span><span class="sxs-lookup"><span data-stu-id="da7b5-279">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="da7b5-280">更好地跟踪和监控分数回归</span><span class="sxs-lookup"><span data-stu-id="da7b5-280">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="da7b5-281">筛选、标记、搜索和分组您的改进操作</span><span class="sxs-lookup"><span data-stu-id="da7b5-281">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="da7b5-282">使用分数预测和计划操作来管理未来目标</span><span class="sxs-lookup"><span data-stu-id="da7b5-282">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="da7b5-283">简化了要点系统</span><span class="sxs-lookup"><span data-stu-id="da7b5-283">Simplification of the points system</span></span>
* <span data-ttu-id="da7b5-284">更多！</span><span class="sxs-lookup"><span data-stu-id="da7b5-284">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="da7b5-285">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="da7b5-285">We want to hear from you</span></span>

<span data-ttu-id="da7b5-286">如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="da7b5-286">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="da7b5-287">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="da7b5-287">We're monitoring the community and will provide help.</span></span>
