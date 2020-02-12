---
title: Microsoft 安全功能分数
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
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
ms.openlocfilehash: b37b8f0aaa225dec9e522964b59871047081be9d
ms.sourcegitcommit: e47694dedf7e213167d3d979a44c07c668bba543
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41932302"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="e6d05-104">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="e6d05-104">Microsoft Secure Score</span></span>

<span data-ttu-id="e6d05-105">Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。</span><span class="sxs-lookup"><span data-stu-id="e6d05-105">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="e6d05-106">按照安全得分建议，可以保护您的组织免受威胁。</span><span class="sxs-lookup"><span data-stu-id="e6d05-106">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="e6d05-107">从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="e6d05-107">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="e6d05-108">安全分数可帮助组织：</span><span class="sxs-lookup"><span data-stu-id="e6d05-108">Secure Score helps organizations:</span></span>

* <span data-ttu-id="e6d05-109">报告组织安全状况的当前状态。</span><span class="sxs-lookup"><span data-stu-id="e6d05-109">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="e6d05-110">通过提供可发现性、可见性、指导和控制改进其安全状况。</span><span class="sxs-lookup"><span data-stu-id="e6d05-110">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="e6d05-111">与基准进行比较并建立关键绩效指标（Kpi）。</span><span class="sxs-lookup"><span data-stu-id="e6d05-111">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="e6d05-112">组织可以获得对指标和趋势的可靠可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较以及其他更多。</span><span class="sxs-lookup"><span data-stu-id="e6d05-112">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="e6d05-113">分数还可以反映第三方解决方案解决建议操作的时间。</span><span class="sxs-lookup"><span data-stu-id="e6d05-113">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="e6d05-114">此外，你还可以通过[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)访问你的建议和评分。</span><span class="sxs-lookup"><span data-stu-id="e6d05-114">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="e6d05-115">了解[安全分数资源类型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="e6d05-115">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="e6d05-116">运作方式</span><span class="sxs-lookup"><span data-stu-id="e6d05-116">How it works</span></span>

<span data-ttu-id="e6d05-117">为您提供配置推荐安全功能、执行与安全相关的任务（如查看报告）或使用第三方应用程序或软件解决改进操作的相关积分。</span><span class="sxs-lookup"><span data-stu-id="e6d05-117">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="e6d05-118">某些改进操作仅在完全完成时给出点，而有些改进操作在为某些设备或用户完成一些点时提供部分点。</span><span class="sxs-lookup"><span data-stu-id="e6d05-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span>

<span data-ttu-id="e6d05-119">我们为你展示了完整的一组可能的改进，而不考虑许可证，因此你可以了解安全最佳做法并提高你的成绩。</span><span class="sxs-lookup"><span data-stu-id="e6d05-119">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="e6d05-120">绝对安全状态由安全分数表示，无论贵组织拥有哪些产品许可证，这都保持不变。</span><span class="sxs-lookup"><span data-stu-id="e6d05-120">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="e6d05-121">请记住，安全应平衡可用性，而不是每个建议都适用于您的环境。</span><span class="sxs-lookup"><span data-stu-id="e6d05-121">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="e6d05-122">你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="e6d05-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="e6d05-123">安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。</span><span class="sxs-lookup"><span data-stu-id="e6d05-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="e6d05-124">如何对改进行动进行评分</span><span class="sxs-lookup"><span data-stu-id="e6d05-124">How improvement actions are scored</span></span>

<span data-ttu-id="e6d05-125">大多数都是以二进制方式进行评分—如果实现改进操作（如创建新策略或打开特定设置），则将获得100% 的点数。</span><span class="sxs-lookup"><span data-stu-id="e6d05-125">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="e6d05-126">对于其他改进操作，点作为总配置的百分比提供。</span><span class="sxs-lookup"><span data-stu-id="e6d05-126">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="e6d05-127">例如，如果使用多重身份验证保护您的所有用户，并且您仅有5% 以上100的用户受到保护，则 "改进" 操作将获得约30个点（共有2个分数，即5个 "受保护/100 总计 \* 30 个最大值 = 2 pt 部分分数"）。</span><span class="sxs-lookup"><span data-stu-id="e6d05-127">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="e6d05-128">安全分数中包括的产品</span><span class="sxs-lookup"><span data-stu-id="e6d05-128">Products included in Secure Score</span></span>

<span data-ttu-id="e6d05-129">目前，我们提供了 Office 365 的一些建议（包括 SharePoint Online、Exchange Online、OneDrive for Business、Microsoft 信息保护等）、Azure AD 和云应用安全性。</span><span class="sxs-lookup"><span data-stu-id="e6d05-129">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, and Cloud App Security.</span></span> <span data-ttu-id="e6d05-130">对其他安全产品（如 Azure ATP 和 Microsoft Defender ATP）的建议即将推出。</span><span class="sxs-lookup"><span data-stu-id="e6d05-130">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="e6d05-131">这些建议不包含与每个产品相关联的所有攻击面，但都是一个很棒的基准。</span><span class="sxs-lookup"><span data-stu-id="e6d05-131">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="e6d05-132">您还可以将改进操作标记为第三方覆盖。</span><span class="sxs-lookup"><span data-stu-id="e6d05-132">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="e6d05-133">所需权限</span><span class="sxs-lookup"><span data-stu-id="e6d05-133">Required permissions</span></span>

<span data-ttu-id="e6d05-134">若要拥有访问 Microsoft 安全分数的权限，您必须在 Azure Active Directory 中为以下角色分配一个角色。</span><span class="sxs-lookup"><span data-stu-id="e6d05-134">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="e6d05-135">读取和写入角色</span><span class="sxs-lookup"><span data-stu-id="e6d05-135">Read and write roles</span></span>

<span data-ttu-id="e6d05-136">通过读取和写入访问权限，您可以进行更改，并直接与安全分数进行交互。</span><span class="sxs-lookup"><span data-stu-id="e6d05-136">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="e6d05-137">您还可以将只读访问权限分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="e6d05-137">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="e6d05-138">全局管理员</span><span class="sxs-lookup"><span data-stu-id="e6d05-138">Global administrator</span></span>
* <span data-ttu-id="e6d05-139">安全管理员</span><span class="sxs-lookup"><span data-stu-id="e6d05-139">Security administrator</span></span>
* <span data-ttu-id="e6d05-140">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="e6d05-140">Exchange administrator</span></span>
* <span data-ttu-id="e6d05-141">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="e6d05-141">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="e6d05-142">只读角色</span><span class="sxs-lookup"><span data-stu-id="e6d05-142">Read-only roles</span></span>

<span data-ttu-id="e6d05-143">如果具有只读访问权限，您将无法编辑 "改进" 操作的状态或注释、编辑分数区域或编辑自定义比较。</span><span class="sxs-lookup"><span data-stu-id="e6d05-143">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="e6d05-144">帮助台管理员</span><span class="sxs-lookup"><span data-stu-id="e6d05-144">Helpdesk administrator</span></span>
* <span data-ttu-id="e6d05-145">用户管理员</span><span class="sxs-lookup"><span data-stu-id="e6d05-145">User administrator</span></span>
* <span data-ttu-id="e6d05-146">服务管理员</span><span class="sxs-lookup"><span data-stu-id="e6d05-146">Service administrator</span></span>
* <span data-ttu-id="e6d05-147">安全读取者</span><span class="sxs-lookup"><span data-stu-id="e6d05-147">Security reader</span></span>
* <span data-ttu-id="e6d05-148">安全操作员</span><span class="sxs-lookup"><span data-stu-id="e6d05-148">Security operator</span></span>
* <span data-ttu-id="e6d05-149">全局读取者</span><span class="sxs-lookup"><span data-stu-id="e6d05-149">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="e6d05-150">Graph API</span><span class="sxs-lookup"><span data-stu-id="e6d05-150">Graph API</span></span>

<span data-ttu-id="e6d05-151">若要访问 Graph API，除了角色之外，还需要具有以下作用域之一：</span><span class="sxs-lookup"><span data-stu-id="e6d05-151">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="e6d05-152">Securityevents.readwrite.all （适用于只读角色）</span><span class="sxs-lookup"><span data-stu-id="e6d05-152">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="e6d05-153">Securityevents.readwrite.all （用于读取和写入角色）</span><span class="sxs-lookup"><span data-stu-id="e6d05-153">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="e6d05-154">深入了解你的安全状况</span><span class="sxs-lookup"><span data-stu-id="e6d05-154">Gain visibility into your security posture</span></span>

<span data-ttu-id="e6d05-155">为了帮助您更快地了解所需的信息，Microsoft 改善操作将组织成组：</span><span class="sxs-lookup"><span data-stu-id="e6d05-155">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="e6d05-156">Identity （Azure AD 帐户 & 角色，即将推出 Azure ATP）</span><span class="sxs-lookup"><span data-stu-id="e6d05-156">Identity (Azure AD accounts & roles, with Azure ATP coming soon)</span></span>
* <span data-ttu-id="e6d05-157">数据（Microsoft 信息保护）</span><span class="sxs-lookup"><span data-stu-id="e6d05-157">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="e6d05-158">设备（Microsoft Defender ATP 设备，即将推出）</span><span class="sxs-lookup"><span data-stu-id="e6d05-158">Device (Microsoft Defender ATP devices, coming soon)</span></span>
* <span data-ttu-id="e6d05-159">应用（电子邮件和云应用，包括 Office 365 和 Microsoft 云应用安全性）</span><span class="sxs-lookup"><span data-stu-id="e6d05-159">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="e6d05-160">基础结构（Azure 资源）</span><span class="sxs-lookup"><span data-stu-id="e6d05-160">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="e6d05-161">在 "Microsoft 安全分数概述" 页中，您可以看到在这些组之间如何拆分点以及哪些点可用。</span><span class="sxs-lookup"><span data-stu-id="e6d05-161">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="e6d05-162">[！注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置，以及可采取的优先改进措施以提高成绩。</span><span class="sxs-lookup"><span data-stu-id="e6d05-162">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="e6d05-163">![安全积分主页](../media/secure-score/homepage-original.png)
*图1： Microsoft 安全分数概述页面*</span><span class="sxs-lookup"><span data-stu-id="e6d05-163">![Secure Score homepage](../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="e6d05-164">采取行动以提高成绩</span><span class="sxs-lookup"><span data-stu-id="e6d05-164">Take action to improve your score</span></span>

<span data-ttu-id="e6d05-165">"改进操作" 选项卡列出了解决可能的攻击面的安全建议，以及它们的状态（已完成、未完成、已通过第三方解决和忽略）。</span><span class="sxs-lookup"><span data-stu-id="e6d05-165">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="e6d05-166">您可以搜索、筛选和分组所有改进操作。</span><span class="sxs-lookup"><span data-stu-id="e6d05-166">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="e6d05-167">排名</span><span class="sxs-lookup"><span data-stu-id="e6d05-167">Ranking</span></span>

<span data-ttu-id="e6d05-168">排名基于要达到的剩余点数、实现难度、用户影响和复杂性。</span><span class="sxs-lookup"><span data-stu-id="e6d05-168">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="e6d05-169">最高排名改进操作的剩余分数与较低的难度、用户影响和复杂性相同。</span><span class="sxs-lookup"><span data-stu-id="e6d05-169">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="e6d05-170">操作</span><span class="sxs-lookup"><span data-stu-id="e6d05-170">Actions</span></span>

<span data-ttu-id="e6d05-171">Microsoft 安全分数不会跟踪标记为 [未评分] 的操作。</span><span class="sxs-lookup"><span data-stu-id="e6d05-171">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="e6d05-172">你仍可以采取措施，但完成这些操作不会影响你的分数。</span><span class="sxs-lookup"><span data-stu-id="e6d05-172">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="e6d05-173">如果某个操作在将来被 Microsoft 安全得分跟踪，并且您已完成该操作，则安全得分将自动反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e6d05-173">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="e6d05-174">当您选择特定的 "改进" 操作时，将显示 "飞出"。</span><span class="sxs-lookup"><span data-stu-id="e6d05-174">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="e6d05-175">若要完成此操作，您有几个选项：</span><span class="sxs-lookup"><span data-stu-id="e6d05-175">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="e6d05-176">选择 "**查看设置**" 以转到配置屏幕并进行更改。</span><span class="sxs-lookup"><span data-stu-id="e6d05-176">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="e6d05-177">然后，您可以在飞出的顶部看到该操作值得的要点。点可能需要长达24小时才能更新。</span><span class="sxs-lookup"><span data-stu-id="e6d05-177">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="e6d05-178">选择 "**通过第三方解决**"，因为改进操作已由第三方应用程序或软件解决。</span><span class="sxs-lookup"><span data-stu-id="e6d05-178">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="e6d05-179">您可以获得该操作所需要的要点，这样您的安全分数就能更好地反映您的总体安全状况。</span><span class="sxs-lookup"><span data-stu-id="e6d05-179">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="e6d05-180">如果第三方不再涵盖该控件，则可以将 "改进" 操作标记为 "不完成"。</span><span class="sxs-lookup"><span data-stu-id="e6d05-180">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="e6d05-181">请注意，如果将改进操作标记为通过第三方解决，Microsoft 无法了解是否满足评分要求。</span><span class="sxs-lookup"><span data-stu-id="e6d05-181">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="e6d05-182">选择 "**忽略**"，因为您已决定接受风险而不执行改进操作。</span><span class="sxs-lookup"><span data-stu-id="e6d05-182">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="e6d05-183">忽略 "改进" 操作后，您可以实现的安全分数点总数将减少。</span><span class="sxs-lookup"><span data-stu-id="e6d05-183">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="e6d05-184">您可以在历史记录中查看此操作，也可以随时撤消。</span><span class="sxs-lookup"><span data-stu-id="e6d05-184">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="e6d05-185">选择 "**审阅**"，因为改进操作要求您定期查看环境的一部分以获取和保留点。</span><span class="sxs-lookup"><span data-stu-id="e6d05-185">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="e6d05-186">例如，应每周查看邮箱转发规则，以确保不会从您的网络中泄露数据。</span><span class="sxs-lookup"><span data-stu-id="e6d05-186">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="e6d05-187">您无需进行任何更改，但需要执行操作。</span><span class="sxs-lookup"><span data-stu-id="e6d05-187">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="e6d05-188">如果您定期查看规则，您将收到要点。</span><span class="sxs-lookup"><span data-stu-id="e6d05-188">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="e6d05-189">如果不是，则减少分数。</span><span class="sxs-lookup"><span data-stu-id="e6d05-189">If not, the score is reduced.</span></span>

![安全分数提高操作示例](../media/secure-score/secure-score1x450.png) ![安全分数评审改进操作示例](../media/secure-score/secure-score2x450.png)

<span data-ttu-id="e6d05-192">*图 2 & 3：改进操作 flyouts*</span><span class="sxs-lookup"><span data-stu-id="e6d05-192">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="e6d05-193">随着时间的推移监视改进</span><span class="sxs-lookup"><span data-stu-id="e6d05-193">Monitor improvements over time</span></span>

<span data-ttu-id="e6d05-194">您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。在图下方是在所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。</span><span class="sxs-lookup"><span data-stu-id="e6d05-194">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="e6d05-195">您可以自定义日期范围并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="e6d05-195">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="e6d05-196">风险感知</span><span class="sxs-lookup"><span data-stu-id="e6d05-196">Risk awareness</span></span>

<span data-ttu-id="e6d05-197">Microsoft 安全分数是基于系统配置、用户行为和其他与安全相关的度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="e6d05-197">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="e6d05-198">相反，它表示您在 Microsoft 环境中已采用安全控制的程度，这有助于抵消受到破坏的风险。</span><span class="sxs-lookup"><span data-stu-id="e6d05-198">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="e6d05-199">无在线服务完全不受安全破坏，并且安全分数不应以任何方式解释为保证安全。</span><span class="sxs-lookup"><span data-stu-id="e6d05-199">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="e6d05-200">新增功能</span><span class="sxs-lookup"><span data-stu-id="e6d05-200">What's new?</span></span>

<span data-ttu-id="e6d05-201">若要使 Microsoft 安全得分更好地代表安全状态，我们做出了一些更改。</span><span class="sxs-lookup"><span data-stu-id="e6d05-201">To make Microsoft Secure Score a better representative of your security posture we have made some changes.</span></span>

### <a name="removed-not-scored-improvement-actions"></a><span data-ttu-id="e6d05-202">删除了 "未评分" 的改进操作</span><span class="sxs-lookup"><span data-stu-id="e6d05-202">Removed “not scored” improvement actions</span></span>

<span data-ttu-id="e6d05-203">安全得分的原则之一是，分数应标准化且易于关联。</span><span class="sxs-lookup"><span data-stu-id="e6d05-203">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="e6d05-204">具有不可衡量或可操作的改进操作已导致混淆。</span><span class="sxs-lookup"><span data-stu-id="e6d05-204">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="e6d05-205">仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。</span><span class="sxs-lookup"><span data-stu-id="e6d05-205">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="e6d05-206">不计分的提高操作不可度量。</span><span class="sxs-lookup"><span data-stu-id="e6d05-206">Not scored improvement actions are not measurable.</span></span>  

<span data-ttu-id="e6d05-207">出于这些原因，未评分的所有改进操作均已删除。</span><span class="sxs-lookup"><span data-stu-id="e6d05-207">For these reasons, all improvement actions that were not scored have been removed.</span></span> <span data-ttu-id="e6d05-208">您的部件不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e6d05-208">No action is needed on your part.</span></span>

## <a name="whats-coming"></a><span data-ttu-id="e6d05-209">接下来是什么？</span><span class="sxs-lookup"><span data-stu-id="e6d05-209">What's coming?</span></span>

<span data-ttu-id="e6d05-210">为了使 Microsoft 安全得分更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="e6d05-210">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="e6d05-211">你的分数和可能的最大分数都将发生变化。</span><span class="sxs-lookup"><span data-stu-id="e6d05-211">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="e6d05-212">但是，这并不意味着您的安全状况发生了变化。</span><span class="sxs-lookup"><span data-stu-id="e6d05-212">However, this does not imply a change in your security posture.</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="e6d05-213">从 Intune 删除改进操作</span><span class="sxs-lookup"><span data-stu-id="e6d05-213">Removing improvement actions from Intune</span></span>

<span data-ttu-id="e6d05-214">评估了 Intune 提供的 Microsoft 安全得分改进操作后，它决定了它们不提供组织中设备的安全状态的有用表示形式。</span><span class="sxs-lookup"><span data-stu-id="e6d05-214">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="e6d05-215">我们正在努力引入可直接评估设备配置状态的安全控制，而不是重点关注策略。</span><span class="sxs-lookup"><span data-stu-id="e6d05-215">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="e6d05-216">将删除以下 Intune 改进操作：</span><span class="sxs-lookup"><span data-stu-id="e6d05-216">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="e6d05-217">启用 Microsoft Intune 移动设备管理</span><span class="sxs-lookup"><span data-stu-id="e6d05-217">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="e6d05-218">创建适用于 Android 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-218">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="e6d05-219">创建适用于 Android 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-219">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="e6d05-220">创建适用于 Android 的 Microsoft Intune 应用保护策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-220">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="e6d05-221">创建适用于 iOS 的 Microsoft Intune 应用保护策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-221">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="e6d05-222">标记不符合 Microsoft Intune 合规性策略的设备（未分配为不合规）</span><span class="sxs-lookup"><span data-stu-id="e6d05-222">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="e6d05-223">创建适用于 iOS 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-223">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="e6d05-224">为 macOS 创建 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-224">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="e6d05-225">创建适用于 Windows 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-225">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="e6d05-226">创建适用于 Android 的 Microsoft Intune 配置配置文件</span><span class="sxs-lookup"><span data-stu-id="e6d05-226">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="e6d05-227">为适用于 Android 的工作创建 Microsoft Intune 配置配置文件</span><span class="sxs-lookup"><span data-stu-id="e6d05-227">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="e6d05-228">为 macOS 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="e6d05-228">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="e6d05-229">为 iOS 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="e6d05-229">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="e6d05-230">为 Windows 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="e6d05-230">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="e6d05-231">在 Microsoft Intune 中启用增强型 jailbreak 检测</span><span class="sxs-lookup"><span data-stu-id="e6d05-231">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="e6d05-232">要求对所有设备进行修补，并启用防病毒和防火墙</span><span class="sxs-lookup"><span data-stu-id="e6d05-232">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="e6d05-233">启用 Microsoft Intune 中的 Windows Defender ATP 集成</span><span class="sxs-lookup"><span data-stu-id="e6d05-233">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="e6d05-234">创建 Microsoft Intune Windows 信息保护策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-234">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="e6d05-235">要求所有设备都具有高级安全配置</span><span class="sxs-lookup"><span data-stu-id="e6d05-235">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="e6d05-236">每周查看阻止的设备报告</span><span class="sxs-lookup"><span data-stu-id="e6d05-236">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="e6d05-237">删除不符合可靠测量预期的改进措施</span><span class="sxs-lookup"><span data-stu-id="e6d05-237">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="e6d05-238">为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。</span><span class="sxs-lookup"><span data-stu-id="e6d05-238">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="e6d05-239">启用审核数据记录</span><span class="sxs-lookup"><span data-stu-id="e6d05-239">Turn on audit data recording</span></span>
- <span data-ttu-id="e6d05-240">发现有风险和不兼容的卷影 IT 应用程序</span><span class="sxs-lookup"><span data-stu-id="e6d05-240">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="e6d05-241">查看权限 & 阻止连接到您的环境的有风险的 OAuth 应用程序</span><span class="sxs-lookup"><span data-stu-id="e6d05-241">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="e6d05-242">在 SharePoint online 文档库中设置版本控制</span><span class="sxs-lookup"><span data-stu-id="e6d05-242">Set up versioning on SharePoint online document libraries</span></span>
- <span data-ttu-id="e6d05-243">将用户文档存储在 OneDrive for Business 中</span><span class="sxs-lookup"><span data-stu-id="e6d05-243">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="e6d05-244">不允许邮箱委派</span><span class="sxs-lookup"><span data-stu-id="e6d05-244">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="e6d05-245">允许匿名来宾共享网站和文档的链接</span><span class="sxs-lookup"><span data-stu-id="e6d05-245">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="e6d05-246">设置 Office 365 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="e6d05-246">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="e6d05-247">设置 Office 365 安全链接以验证 Url</span><span class="sxs-lookup"><span data-stu-id="e6d05-247">Set up Office 365 Safe Links to verify URLs</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="e6d05-248">MFA 改进操作更新</span><span class="sxs-lookup"><span data-stu-id="e6d05-248">MFA improvement action updates</span></span>

<span data-ttu-id="e6d05-249">为了反映企业在应用使用其业务的策略时确保 upmost 安全性的需求，Microsoft 安全记分将删除围绕多重身份验证的三个改进操作，并添加两个。</span><span class="sxs-lookup"><span data-stu-id="e6d05-249">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="e6d05-250">将删除的三个：</span><span class="sxs-lookup"><span data-stu-id="e6d05-250">The three that will be removed:</span></span>

- <span data-ttu-id="e6d05-251">为多因素身份验证注册所有用户</span><span class="sxs-lookup"><span data-stu-id="e6d05-251">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="e6d05-252">要求对所有用户进行 MFA</span><span class="sxs-lookup"><span data-stu-id="e6d05-252">Require MFA for all users</span></span>
- <span data-ttu-id="e6d05-253">需要对 Azure AD 特权角色进行 MFA</span><span class="sxs-lookup"><span data-stu-id="e6d05-253">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="e6d05-254">添加了新的改进操作：</span><span class="sxs-lookup"><span data-stu-id="e6d05-254">New improvement actions added:</span></span>

- <span data-ttu-id="e6d05-255">确保所有用户都可以完成多重身份验证以实现安全访问</span><span class="sxs-lookup"><span data-stu-id="e6d05-255">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="e6d05-256">需要对管理角色进行 MFA</span><span class="sxs-lookup"><span data-stu-id="e6d05-256">Require MFA for administrative roles</span></span>

 <span data-ttu-id="e6d05-257">这些新的改进操作需要为你的用户或管理员在你的目录中注册多重身份验证（MFA），并建立符合你的组织需求的一组适当的策略。</span><span class="sxs-lookup"><span data-stu-id="e6d05-257">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="e6d05-258">主要目标具有灵活性，同时确保所有用户和管理员都可以通过多个因素或基于风险的身份验证提示进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e6d05-258">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="e6d05-259">这可以采用设置安全默认值的形式，让 Microsoft 决定何时对用户进行 MFA，或拥有多个应用范围决策的策略。</span><span class="sxs-lookup"><span data-stu-id="e6d05-259">That can take the form of setting security defaults that let Microsoft decide when to challenge users for MFA, or having multiple policies that apply scoped decisions.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="e6d05-260">删除 "审阅" 改进操作</span><span class="sxs-lookup"><span data-stu-id="e6d05-260">Removing “review” improvement actions</span></span>

<span data-ttu-id="e6d05-261">安全得分的原则之一是，分数应标准化且易于关联。</span><span class="sxs-lookup"><span data-stu-id="e6d05-261">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="e6d05-262">具有不可衡量或可操作的改进操作已导致混淆。</span><span class="sxs-lookup"><span data-stu-id="e6d05-262">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="e6d05-263">仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。</span><span class="sxs-lookup"><span data-stu-id="e6d05-263">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="e6d05-264">与其他改进操作相比，评审改进操作的计算方式不是相同标准。</span><span class="sxs-lookup"><span data-stu-id="e6d05-264">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="e6d05-265">出于这些原因，需要审阅节奏的所有改进操作都将暂时删除。</span><span class="sxs-lookup"><span data-stu-id="e6d05-265">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="e6d05-266">您的部件不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e6d05-266">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="e6d05-267">简化了点系统</span><span class="sxs-lookup"><span data-stu-id="e6d05-267">Simplification of the point system</span></span>

<span data-ttu-id="e6d05-268">若要在多个体验中标准化要点，每个安全分数改进操作点总数将更新为10磅或更少。</span><span class="sxs-lookup"><span data-stu-id="e6d05-268">To standardize points across multiple experiences, each Secure Score improvement action point total will be updated to be worth 10 points or less.</span></span> <span data-ttu-id="e6d05-269">在我们目前所拥有的安全控制的广泛 breather 和将来将添加的安全控制中，必须更加一致。</span><span class="sxs-lookup"><span data-stu-id="e6d05-269">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="e6d05-270">虽然这是一项重大更改，并且你将在点汇总中看到一个拖放，但你的安全状态不会有任何变化。</span><span class="sxs-lookup"><span data-stu-id="e6d05-270">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>  

### <a name="preview-features"></a><span data-ttu-id="e6d05-271">预览功能</span><span class="sxs-lookup"><span data-stu-id="e6d05-271">Preview features</span></span>

<span data-ttu-id="e6d05-272">[预览版本](microsoft-secure-score-preview.md)中将包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="e6d05-272">The following features will be included in the [preview release](microsoft-secure-score-preview.md):</span></span>

* <span data-ttu-id="e6d05-273">CISO 和潜在客户级别讨论的所有新指标和趋势视图</span><span class="sxs-lookup"><span data-stu-id="e6d05-273">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="e6d05-274">跟踪和基准成绩的新方法</span><span class="sxs-lookup"><span data-stu-id="e6d05-274">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="e6d05-275">更好地跟踪和监控分数回归</span><span class="sxs-lookup"><span data-stu-id="e6d05-275">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="e6d05-276">筛选、标记、搜索和分组您的改进操作</span><span class="sxs-lookup"><span data-stu-id="e6d05-276">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="e6d05-277">使用分数预测和计划操作来管理未来目标</span><span class="sxs-lookup"><span data-stu-id="e6d05-277">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="e6d05-278">更多！</span><span class="sxs-lookup"><span data-stu-id="e6d05-278">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="e6d05-279">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="e6d05-279">We want to hear from you</span></span>

<span data-ttu-id="e6d05-280">如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="e6d05-280">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="e6d05-281">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="e6d05-281">We're monitoring the community and will provide help.</span></span>