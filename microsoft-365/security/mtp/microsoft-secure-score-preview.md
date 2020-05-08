---
title: Microsoft 安全评分（预览）
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员使用它的方式。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: w10
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
ms.openlocfilehash: 8277549c683da19dbbf915a7cf673fc731cb8803
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141402"
---
# <a name="microsoft-secure-score-preview"></a><span data-ttu-id="6ab76-104">Microsoft 安全评分（预览）</span><span class="sxs-lookup"><span data-stu-id="6ab76-104">Microsoft Secure Score (preview)</span></span>

>[!IMPORTANT]
><span data-ttu-id="6ab76-105">一些信息与 prereleased 产品相关，在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="6ab76-105">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6ab76-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6ab76-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6ab76-107">Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。</span><span class="sxs-lookup"><span data-stu-id="6ab76-107">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="6ab76-108">可在https://security.microsoft.com/securescore [Microsoft 365 安全中心](overview-security-center.md)中找到。</span><span class="sxs-lookup"><span data-stu-id="6ab76-108">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="6ab76-109">按照安全得分建议，可以保护您的组织免受威胁。</span><span class="sxs-lookup"><span data-stu-id="6ab76-109">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="6ab76-110">从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="6ab76-110">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="6ab76-111">安全分数可帮助组织：</span><span class="sxs-lookup"><span data-stu-id="6ab76-111">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="6ab76-112">报告组织安全状况的当前状态。</span><span class="sxs-lookup"><span data-stu-id="6ab76-112">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="6ab76-113">通过提供可发现性、可见性、指导和控制改进其安全状况。</span><span class="sxs-lookup"><span data-stu-id="6ab76-113">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="6ab76-114">与基准进行比较并建立关键绩效指标（Kpi）。</span><span class="sxs-lookup"><span data-stu-id="6ab76-114">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="6ab76-115">组织可以获得对指标和趋势的可靠可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较以及其他更多。</span><span class="sxs-lookup"><span data-stu-id="6ab76-115">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="6ab76-116">分数还可以反映第三方解决方案解决建议操作的时间。</span><span class="sxs-lookup"><span data-stu-id="6ab76-116">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="6ab76-117">此外，你还可以通过[Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)访问你的建议和评分。</span><span class="sxs-lookup"><span data-stu-id="6ab76-117">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="6ab76-118">了解[安全分数资源类型](https://go.microsoft.com/fwlink/?linkid=2092996)。</span><span class="sxs-lookup"><span data-stu-id="6ab76-118">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="6ab76-119">工作原理</span><span class="sxs-lookup"><span data-stu-id="6ab76-119">How it works</span></span>

<span data-ttu-id="6ab76-120">为您提供配置推荐安全功能、执行与安全相关的任务或使用第三方应用程序或软件解决改进操作的相关积分。</span><span class="sxs-lookup"><span data-stu-id="6ab76-120">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="6ab76-121">某些改进操作仅在完全完成时给出点，而有些改进操作在为某些设备或用户完成一些点时提供部分点。</span><span class="sxs-lookup"><span data-stu-id="6ab76-121">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="6ab76-122">如果不能或不希望执行其中一个改进操作，则可以选择接受风险或剩余风险。</span><span class="sxs-lookup"><span data-stu-id="6ab76-122">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="6ab76-123">我们为你展示了完整的一组可能的改进，而不考虑许可证，因此你可以了解安全最佳做法并提高你的成绩。</span><span class="sxs-lookup"><span data-stu-id="6ab76-123">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="6ab76-124">绝对安全状态由安全分数表示，无论贵组织拥有哪些产品许可证，这都保持不变。</span><span class="sxs-lookup"><span data-stu-id="6ab76-124">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="6ab76-125">请记住，安全应平衡可用性，而不是每个建议都适用于您的环境。</span><span class="sxs-lookup"><span data-stu-id="6ab76-125">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="6ab76-126">你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="6ab76-126">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="6ab76-127">安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。</span><span class="sxs-lookup"><span data-stu-id="6ab76-127">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="6ab76-128">如何对改进行动进行评分</span><span class="sxs-lookup"><span data-stu-id="6ab76-128">How improvement actions are scored</span></span>

<span data-ttu-id="6ab76-129">每个改进操作10磅或更少。</span><span class="sxs-lookup"><span data-stu-id="6ab76-129">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="6ab76-130">大多数都是以二进制方式进行评分—如果实现改进操作（如创建新策略或打开特定设置），则将获得100% 的点数。</span><span class="sxs-lookup"><span data-stu-id="6ab76-130">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="6ab76-131">对于其他改进操作，点作为总配置的百分比提供。</span><span class="sxs-lookup"><span data-stu-id="6ab76-131">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="6ab76-132">例如，如果使用多重身份验证保护您的所有用户，并且您仅有5% 以上100的用户受到保护，则 "改进" 操作将获得约30个点（共有2个分数，即5个 "受保护/100 总计 \* 30 个最大值 = 2 pt 部分分数"）。</span><span class="sxs-lookup"><span data-stu-id="6ab76-132">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="6ab76-133">安全分数中包括的产品</span><span class="sxs-lookup"><span data-stu-id="6ab76-133">Products included in Secure Score</span></span>

<span data-ttu-id="6ab76-134">目前有关于 Microsoft 365 （包括 Exchange Online）、Azure AD、Microsoft Defender ATP、Azure ATP 和云应用安全性的建议。</span><span class="sxs-lookup"><span data-stu-id="6ab76-134">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="6ab76-135">即将推出针对其他安全产品的建议。</span><span class="sxs-lookup"><span data-stu-id="6ab76-135">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="6ab76-136">这些建议不包含与每个产品相关联的所有攻击面，但都是一个很棒的基准。</span><span class="sxs-lookup"><span data-stu-id="6ab76-136">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="6ab76-137">您还可以将改进操作标记为第三方覆盖。</span><span class="sxs-lookup"><span data-stu-id="6ab76-137">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="6ab76-138">所需权限</span><span class="sxs-lookup"><span data-stu-id="6ab76-138">Required permissions</span></span>

<span data-ttu-id="6ab76-139">若要拥有访问 Microsoft 安全分数的权限，您必须在 Azure Active Directory 中为以下角色分配一个角色。</span><span class="sxs-lookup"><span data-stu-id="6ab76-139">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="6ab76-140">读取和写入角色</span><span class="sxs-lookup"><span data-stu-id="6ab76-140">Read and write roles</span></span>

<span data-ttu-id="6ab76-141">通过读取和写入访问权限，您可以进行更改，并直接与安全分数进行交互。</span><span class="sxs-lookup"><span data-stu-id="6ab76-141">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="6ab76-142">您还可以将只读访问权限分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="6ab76-142">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="6ab76-143">全局管理员</span><span class="sxs-lookup"><span data-stu-id="6ab76-143">Global administrator</span></span>
* <span data-ttu-id="6ab76-144">安全管理员</span><span class="sxs-lookup"><span data-stu-id="6ab76-144">Security administrator</span></span>
* <span data-ttu-id="6ab76-145">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="6ab76-145">Exchange administrator</span></span>
* <span data-ttu-id="6ab76-146">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="6ab76-146">SharePoint administrator</span></span>
* <span data-ttu-id="6ab76-147">帐户管理员</span><span class="sxs-lookup"><span data-stu-id="6ab76-147">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="6ab76-148">只读角色</span><span class="sxs-lookup"><span data-stu-id="6ab76-148">Read-only roles</span></span>

<span data-ttu-id="6ab76-149">如果具有只读访问权限，您将无法编辑 "改进" 操作的状态或注释、编辑分数区域或编辑自定义比较。</span><span class="sxs-lookup"><span data-stu-id="6ab76-149">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="6ab76-150">帮助台管理员</span><span class="sxs-lookup"><span data-stu-id="6ab76-150">Helpdesk administrator</span></span>
* <span data-ttu-id="6ab76-151">用户管理员</span><span class="sxs-lookup"><span data-stu-id="6ab76-151">User administrator</span></span>
* <span data-ttu-id="6ab76-152">服务管理员</span><span class="sxs-lookup"><span data-stu-id="6ab76-152">Service administrator</span></span>
* <span data-ttu-id="6ab76-153">安全读取者</span><span class="sxs-lookup"><span data-stu-id="6ab76-153">Security reader</span></span>
* <span data-ttu-id="6ab76-154">安全操作员</span><span class="sxs-lookup"><span data-stu-id="6ab76-154">Security operator</span></span>
* <span data-ttu-id="6ab76-155">全局读取者</span><span class="sxs-lookup"><span data-stu-id="6ab76-155">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="6ab76-156">Graph API</span><span class="sxs-lookup"><span data-stu-id="6ab76-156">Graph API</span></span>

<span data-ttu-id="6ab76-157">若要访问 Graph API，除了角色之外，还需要具有以下作用域之一：</span><span class="sxs-lookup"><span data-stu-id="6ab76-157">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="6ab76-158">Securityevents.readwrite.all （适用于只读角色）</span><span class="sxs-lookup"><span data-stu-id="6ab76-158">SecurityEvents.Read.All (for read-only roles)</span></span>
* <span data-ttu-id="6ab76-159">Securityevents.readwrite.all （用于读取和写入角色）</span><span class="sxs-lookup"><span data-stu-id="6ab76-159">SecurityEvents.ReadWrite.All (for read and write roles)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="6ab76-160">深入了解你的安全状况</span><span class="sxs-lookup"><span data-stu-id="6ab76-160">Gain visibility into your security posture</span></span>

<span data-ttu-id="6ab76-161">为了帮助您更快地了解所需的信息，Microsoft 改善操作将组织成组：</span><span class="sxs-lookup"><span data-stu-id="6ab76-161">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="6ab76-162">Identity （Azure AD 帐户 & 角色）</span><span class="sxs-lookup"><span data-stu-id="6ab76-162">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="6ab76-163">数据（Microsoft 信息保护）</span><span class="sxs-lookup"><span data-stu-id="6ab76-163">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="6ab76-164">设备（Microsoft Defender ATP）</span><span class="sxs-lookup"><span data-stu-id="6ab76-164">Device (Microsoft Defender ATP)</span></span>
* <span data-ttu-id="6ab76-165">应用（电子邮件和云应用，包括 Office 365 和 Microsoft 云应用安全性）</span><span class="sxs-lookup"><span data-stu-id="6ab76-165">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="6ab76-166">基础结构（暂时不提供改进操作）</span><span class="sxs-lookup"><span data-stu-id="6ab76-166">Infrastructure (no improvement actions for now)</span></span>

<span data-ttu-id="6ab76-167">在 "Microsoft 安全分数概述" 页中，您可以看到在这些组之间如何拆分点以及哪些点可用。</span><span class="sxs-lookup"><span data-stu-id="6ab76-167">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="6ab76-168">[！注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置，以及可采取的优先改进措施以提高成绩。</span><span class="sxs-lookup"><span data-stu-id="6ab76-168">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="6ab76-169">![安全积分主页](../../media/secure-score/secure-score-homepage.png)
*图1： Microsoft 安全分数概述页面*</span><span class="sxs-lookup"><span data-stu-id="6ab76-169">![Secure Score homepage](../../media/secure-score/secure-score-homepage.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="6ab76-170">采取行动以提高成绩</span><span class="sxs-lookup"><span data-stu-id="6ab76-170">Take action to improve your score</span></span>

<span data-ttu-id="6ab76-171">"**改进操作**" 选项卡列出了解决可能的攻击面的安全建议，以及它们的状态（若要解决、规划、接受风险，请通过第三方解决这些问题，通过替代的缓解措施进行解决，并完成）。</span><span class="sxs-lookup"><span data-stu-id="6ab76-171">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces, along with their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="6ab76-172">您可以搜索、筛选和分组所有改进操作。</span><span class="sxs-lookup"><span data-stu-id="6ab76-172">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="6ab76-173">排名</span><span class="sxs-lookup"><span data-stu-id="6ab76-173">Ranking</span></span>

<span data-ttu-id="6ab76-174">排名基于要达到的剩余点数、实现难度、用户影响和复杂性。</span><span class="sxs-lookup"><span data-stu-id="6ab76-174">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="6ab76-175">最高排名改进操作的剩余分数与较低的难度、用户影响和复杂性相同。</span><span class="sxs-lookup"><span data-stu-id="6ab76-175">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="6ab76-176">查看改进操作详细信息</span><span class="sxs-lookup"><span data-stu-id="6ab76-176">View improvement action details</span></span>

<span data-ttu-id="6ab76-177">选择特定的 "改进" 操作时，将显示完整的 "页面" 飞出控件。</span><span class="sxs-lookup"><span data-stu-id="6ab76-177">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="6ab76-178">![改进操作浮出](../../media/secure-score/secure-score-improvement-action-details.png)
控件示例*图2：改进操作浮出控件示例*</span><span class="sxs-lookup"><span data-stu-id="6ab76-178">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="6ab76-179">若要完成此操作，您有几个选项：</span><span class="sxs-lookup"><span data-stu-id="6ab76-179">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="6ab76-180">选择 "**管理**" 以转到配置屏幕并进行更改。</span><span class="sxs-lookup"><span data-stu-id="6ab76-180">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="6ab76-181">然后，您将获得该操作所需要的要点，在飞出中可见。点通常需要大约24小时才能更新。</span><span class="sxs-lookup"><span data-stu-id="6ab76-181">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="6ab76-182">选择 "**共享**" 将直接链接复制到 "改进" 操作，或选择用于共享链接（如电子邮件、microsoft 团队、microsoft Planner 或 ServiceNow）的平台。</span><span class="sxs-lookup"><span data-stu-id="6ab76-182">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="6ab76-183">选择 ServiceNow 将允许你创建将在 ServiceNow 和 Microsoft 365 安全中心主页中可见的更改票证。</span><span class="sxs-lookup"><span data-stu-id="6ab76-183">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="6ab76-184">若要了解详细信息，请参阅[Microsoft 365 安全中心和 ServiceNow 集成](tickets.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab76-184">To learn more, see [Microsoft 365 Security Center and ServiceNow integration](tickets.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="6ab76-185">选择改进操作状态</span><span class="sxs-lookup"><span data-stu-id="6ab76-185">Choose an improvement action status</span></span>

<span data-ttu-id="6ab76-186">选择特定于 "改进" 操作的任何状态和记录笔记。</span><span class="sxs-lookup"><span data-stu-id="6ab76-186">Choose any statuses and record notes specific to the improvement action.</span></span> <span data-ttu-id="6ab76-187">您可以选择的 statues 如下所示：</span><span class="sxs-lookup"><span data-stu-id="6ab76-187">The statues you can select are the following:</span></span>

* <span data-ttu-id="6ab76-188">**若要解决**此需要，您可以认识到改进操作是必需的，并计划在将来某一时间解决此操作。</span><span class="sxs-lookup"><span data-stu-id="6ab76-188">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="6ab76-189">此状态也适用于检测为部分但未完全完成的操作。</span><span class="sxs-lookup"><span data-stu-id="6ab76-189">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
* <span data-ttu-id="6ab76-190">**规划**—完成改进操作有一些具体的规划。</span><span class="sxs-lookup"><span data-stu-id="6ab76-190">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
* <span data-ttu-id="6ab76-191">**接受风险**—安全性应始终与可用性平衡，而不是每个建议对您的环境都适用。</span><span class="sxs-lookup"><span data-stu-id="6ab76-191">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="6ab76-192">在这种情况下，您可以选择接受风险或剩余风险，而不是执行改进操作。</span><span class="sxs-lookup"><span data-stu-id="6ab76-192">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="6ab76-193">不会向你提供任何点，但操作将不再显示在改进操作列表中。</span><span class="sxs-lookup"><span data-stu-id="6ab76-193">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="6ab76-194">您可以在历史记录中查看此操作，也可以随时撤消。</span><span class="sxs-lookup"><span data-stu-id="6ab76-194">You can view this action in history or undo it at any time.</span></span>
* <span data-ttu-id="6ab76-195">**通过第三方解决**，并**通过备用的缓解措施解决**—改进操作已由第三方应用程序或软件或内部工具解决。</span><span class="sxs-lookup"><span data-stu-id="6ab76-195">**Resolved through third party** and **Resolved through alternate mitigation** — The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="6ab76-196">你将获得该操作所需要的要点，因此你的得分更好地反映了你的总体安全状况。</span><span class="sxs-lookup"><span data-stu-id="6ab76-196">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="6ab76-197">如果第三方或内部工具不再涵盖该控件，您可以选择另一个状态。</span><span class="sxs-lookup"><span data-stu-id="6ab76-197">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="6ab76-198">请注意，如果将改进操作标记为这些状态之一，Microsoft 将无法深入了解实施的完整性。</span><span class="sxs-lookup"><span data-stu-id="6ab76-198">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="6ab76-199">威胁 & 漏洞管理改进操作</span><span class="sxs-lookup"><span data-stu-id="6ab76-199">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="6ab76-200">对于 "设备" 类别中的改进操作，你将无法选择状态。</span><span class="sxs-lookup"><span data-stu-id="6ab76-200">For improvement actions in the "Device" category, you will not be able to choose statuses.</span></span> <span data-ttu-id="6ab76-201">相反，你将被定向到[Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)的关联[威胁 & 漏洞管理（TVM）安全建议](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)，以采取措施。</span><span class="sxs-lookup"><span data-stu-id="6ab76-201">Instead, you will be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="6ab76-202">您选择的异常和您编写的理由将特定于该门户，而不会出现在 Microsoft 安全分数门户中。</span><span class="sxs-lookup"><span data-stu-id="6ab76-202">The exception you choose and justification you write will specific to that portal, and will not be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="6ab76-203">已完成的改进操作</span><span class="sxs-lookup"><span data-stu-id="6ab76-203">Completed improvement actions</span></span>

<span data-ttu-id="6ab76-204">一旦完成了改进操作的所有可能的点，改进操作将为 "已完成" 状态。</span><span class="sxs-lookup"><span data-stu-id="6ab76-204">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="6ab76-205">已完成的改进操作通过 Microsoft 数据进行确认，并且你将无法更改状态。</span><span class="sxs-lookup"><span data-stu-id="6ab76-205">Completed improvement actions are confirmed though Microsoft data, and you will not be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="6ab76-206">评估信息并查看用户影响</span><span class="sxs-lookup"><span data-stu-id="6ab76-206">Assess information and review user impact</span></span>

<span data-ttu-id="6ab76-207">**概览**部分将向您告知类别、它可以保护的攻击和产品。</span><span class="sxs-lookup"><span data-stu-id="6ab76-207">The **At a glance** section will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="6ab76-208">**用户影响**显示了在制定改进操作后用户将会遇到的情况，并且**受影响的用户**将会看到他们会遇到的情况。</span><span class="sxs-lookup"><span data-stu-id="6ab76-208">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="6ab76-209">实施改进操作</span><span class="sxs-lookup"><span data-stu-id="6ab76-209">Implement the improvement action</span></span>

<span data-ttu-id="6ab76-210">"**实现**" 部分显示了所有先决条件、分步完成改进操作的后续步骤、改进操作的当前实现状态以及任何 "了解更多" 链接。</span><span class="sxs-lookup"><span data-stu-id="6ab76-210">The **Implementation** section shows any prerequisites, step by step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="6ab76-211">先决条件将是在解决改进措施之前需要获取的任何许可证或需要完成的操作。</span><span class="sxs-lookup"><span data-stu-id="6ab76-211">Prerequisites will be any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="6ab76-212">请确保你的许可证中有足够的座位来完成改进操作，并且这些许可证适用于所需的用户。</span><span class="sxs-lookup"><span data-stu-id="6ab76-212">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="track-your-score-history-and-meet-goals"></a><span data-ttu-id="6ab76-213">跟踪分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="6ab76-213">Track your score history and meet goals</span></span>

<span data-ttu-id="6ab76-214">您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。在图下方是在所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。</span><span class="sxs-lookup"><span data-stu-id="6ab76-214">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="6ab76-215">您可以自定义日期范围并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="6ab76-215">You can customize a date range and filter by category.</span></span>

<span data-ttu-id="6ab76-216">在 "**指标 & 趋势**" 选项卡中，有几个图表和图表可让您更好地了解趋势和设置目标。</span><span class="sxs-lookup"><span data-stu-id="6ab76-216">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="6ab76-217">您可以为整个可视化页设置日期范围。</span><span class="sxs-lookup"><span data-stu-id="6ab76-217">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="6ab76-218">可视化效果包括：</span><span class="sxs-lookup"><span data-stu-id="6ab76-218">The visualizations include:</span></span>

* <span data-ttu-id="6ab76-219">**安全分数区域**—根据组织的目标和 "好"、"好" 和 "差" 得分范围的定义自定义。</span><span class="sxs-lookup"><span data-stu-id="6ab76-219">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="6ab76-220">**回归趋势**-由于配置、用户或设备更改而 regressed 的点的时间线。</span><span class="sxs-lookup"><span data-stu-id="6ab76-220">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="6ab76-221">**比较趋势**—组织的安全分数与其他人的对比情况。</span><span class="sxs-lookup"><span data-stu-id="6ab76-221">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="6ab76-222">此视图可包含表示具有类似座位计数的组织的平均分数和可设置的自定义比较视图的行。</span><span class="sxs-lookup"><span data-stu-id="6ab76-222">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="6ab76-223">**风险接受趋势**-标记为 "风险已接受" 的 "改进" 操作的时间线。</span><span class="sxs-lookup"><span data-stu-id="6ab76-223">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="6ab76-224">**得分变化**—指定的日期范围内的积分数、regressed 和后续得分的变化。</span><span class="sxs-lookup"><span data-stu-id="6ab76-224">**Score changes** — The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="6ab76-225">风险感知</span><span class="sxs-lookup"><span data-stu-id="6ab76-225">Risk awareness</span></span>

<span data-ttu-id="6ab76-226">Microsoft 安全分数是基于系统配置、用户行为和其他安全相关度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="6ab76-226">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="6ab76-227">相反，它表示您在 Microsoft 环境中已采用安全控制的程度，这有助于抵消受到破坏的风险。</span><span class="sxs-lookup"><span data-stu-id="6ab76-227">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="6ab76-228">无在线服务完全不受安全破坏，并且安全分数不应以任何方式解释为保证安全。</span><span class="sxs-lookup"><span data-stu-id="6ab76-228">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="6ab76-229">新变化？</span><span class="sxs-lookup"><span data-stu-id="6ab76-229">What's new?</span></span> 

<span data-ttu-id="6ab76-230">若要使 Microsoft 安全得分更好地代表安全状态，我们做了一些更改。</span><span class="sxs-lookup"><span data-stu-id="6ab76-230">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="6ab76-231">若要了解计划的更改，请参阅[Microsoft Secure 评分中的内容？](microsoft-secure-score-whats-coming.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab76-231">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

### <a name="april-2020"></a><span data-ttu-id="6ab76-232">2020 年 4 月</span><span class="sxs-lookup"><span data-stu-id="6ab76-232">April 2020</span></span>

#### <a name="added-azure-active-directory-improvement-action"></a><span data-ttu-id="6ab76-233">添加了 Azure Active Directory 提高操作</span><span class="sxs-lookup"><span data-stu-id="6ab76-233">Added Azure Active Directory improvement action</span></span>

- <span data-ttu-id="6ab76-234">不允许用户向非托管应用程序授予许可（当前在已发布版本中可用）</span><span class="sxs-lookup"><span data-stu-id="6ab76-234">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="added-azure-advanced-threat-protection-improvement-actions"></a><span data-ttu-id="6ab76-235">添加了 Azure 高级威胁防护改进操作</span><span class="sxs-lookup"><span data-stu-id="6ab76-235">Added Azure Advanced Threat Protection improvement actions</span></span>

- <span data-ttu-id="6ab76-236">在域控制器上禁用打印后台处理程序服务</span><span class="sxs-lookup"><span data-stu-id="6ab76-236">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="6ab76-237">修改不安全的 Kerberos 委派以阻止模拟</span><span class="sxs-lookup"><span data-stu-id="6ab76-237">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="6ab76-238">使用 Microsoft LAPS 保护和管理本地管理员密码</span><span class="sxs-lookup"><span data-stu-id="6ab76-238">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="6ab76-239">降低横向移动路径对敏感实体的风险</span><span class="sxs-lookup"><span data-stu-id="6ab76-239">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="6ab76-240">删除敏感组中的非活动帐户</span><span class="sxs-lookup"><span data-stu-id="6ab76-240">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="6ab76-241">从实体中删除不安全的 SID 历史记录属性</span><span class="sxs-lookup"><span data-stu-id="6ab76-241">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="6ab76-242">解决不安全帐户属性</span><span class="sxs-lookup"><span data-stu-id="6ab76-242">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="6ab76-243">停止明文凭据公开</span><span class="sxs-lookup"><span data-stu-id="6ab76-243">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="6ab76-244">停止旧协议通信</span><span class="sxs-lookup"><span data-stu-id="6ab76-244">Stop legacy protocols communication</span></span>
- <span data-ttu-id="6ab76-245">停止弱密码使用</span><span class="sxs-lookup"><span data-stu-id="6ab76-245">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="6ab76-246">对 Microsoft Defender ATP 威胁的支持 & 漏洞管理（TVM）安全建议</span><span class="sxs-lookup"><span data-stu-id="6ab76-246">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>

<span data-ttu-id="6ab76-247">现已提供 TVM 提供的所有已发布的安全建议。</span><span class="sxs-lookup"><span data-stu-id="6ab76-247">All released security recommendations supplied by TVM are now available.</span></span>

### <a name="january---march-2020"></a><span data-ttu-id="6ab76-248">1月-2020 年3月</span><span class="sxs-lookup"><span data-stu-id="6ab76-248">January - March 2020</span></span>

#### <a name="updated-interface-and-functionality"></a><span data-ttu-id="6ab76-249">更新的界面和功能</span><span class="sxs-lookup"><span data-stu-id="6ab76-249">Updated interface and functionality</span></span>

* <span data-ttu-id="6ab76-250">CISO 和潜在客户级别讨论的所有新指标和趋势视图</span><span class="sxs-lookup"><span data-stu-id="6ab76-250">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="6ab76-251">跟踪和基准成绩的新方法</span><span class="sxs-lookup"><span data-stu-id="6ab76-251">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="6ab76-252">更好地跟踪和理解分数回归</span><span class="sxs-lookup"><span data-stu-id="6ab76-252">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="6ab76-253">筛选、标记、搜索和分组您的改进操作</span><span class="sxs-lookup"><span data-stu-id="6ab76-253">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="6ab76-254">使用分数预测和计划操作来管理未来目标</span><span class="sxs-lookup"><span data-stu-id="6ab76-254">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="6ab76-255">更多！</span><span class="sxs-lookup"><span data-stu-id="6ab76-255">And more!</span></span>

#### <a name="removed-not-scored-and-review-improvement-actions"></a><span data-ttu-id="6ab76-256">删除 "未评分" 和 "审阅" 改进操作</span><span class="sxs-lookup"><span data-stu-id="6ab76-256">Removed "not scored" and "review" improvement actions</span></span>

<span data-ttu-id="6ab76-257">安全得分的原则之一是，分数应标准化且易于关联。</span><span class="sxs-lookup"><span data-stu-id="6ab76-257">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="6ab76-258">具有不可衡量或可操作的改进操作已导致混淆。</span><span class="sxs-lookup"><span data-stu-id="6ab76-258">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="6ab76-259">仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。</span><span class="sxs-lookup"><span data-stu-id="6ab76-259">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="6ab76-260">不计分的提高操作不可度量，并且与其他改进操作相比，不会将 "改进" 操作评估为与相同标准。</span><span class="sxs-lookup"><span data-stu-id="6ab76-260">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>

<span data-ttu-id="6ab76-261">出于这些原因，所有未评分或要求的改进操作都暂时删除了审阅节奏。</span><span class="sxs-lookup"><span data-stu-id="6ab76-261">For these reasons, all improvement actions that were not scored or required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="6ab76-262">您的部件不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="6ab76-262">No action is needed on your part.</span></span>

#### <a name="simplification-of-the-point-system"></a><span data-ttu-id="6ab76-263">简化了点系统</span><span class="sxs-lookup"><span data-stu-id="6ab76-263">Simplification of the point system</span></span>

<span data-ttu-id="6ab76-264">若要在多个体验中标准化点，每个安全分数改进操作点总数已更新为10磅或更少。</span><span class="sxs-lookup"><span data-stu-id="6ab76-264">To standardize points across multiple experiences, each Secure Score improvement action point total has been updated to be worth 10 points or less.</span></span> <span data-ttu-id="6ab76-265">在我们目前所拥有的安全控制的广泛 breather 和将来将添加的安全控制中，必须更加一致。</span><span class="sxs-lookup"><span data-stu-id="6ab76-265">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="6ab76-266">虽然这是一项重大更改，并且你将在点汇总中看到一个拖放，但你的安全状态不会有任何变化。</span><span class="sxs-lookup"><span data-stu-id="6ab76-266">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="6ab76-267">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="6ab76-267">We want to hear from you</span></span>

<span data-ttu-id="6ab76-268">如果你有任何问题，请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="6ab76-268">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="6ab76-269">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="6ab76-269">We're monitoring the community and will provide help.</span></span>
