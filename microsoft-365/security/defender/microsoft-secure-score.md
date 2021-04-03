---
title: Microsoft 安全功能分数
description: 介绍 Microsoft 365 安全中心中的 Microsoft 安全分数、如何改善安全状况以及管理员期望的安全状态。
keywords: microsoft 安全分数， 安全分数， office 365 安全分数， Microsoft 安全分数， microsoft 365 安全中心， 改进操作
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 19b83fe7dd733bb8a0668039d4df2b692a398ad4
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570459"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="296fb-104">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="296fb-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="296fb-105">Microsoft 安全功能分数是衡量组织安全状况的指标，数字越高表示采取的改进措施越多。</span><span class="sxs-lookup"><span data-stu-id="296fb-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="296fb-106">可以在 Microsoft https://security.microsoft.com/securescore [365 安全中心 找到它](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="296fb-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="296fb-107">执行安全功能分数建议可保护组织免遭威胁。</span><span class="sxs-lookup"><span data-stu-id="296fb-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="296fb-108">在 Microsoft 365 安全中心的集中式仪表板中，组织可以监视并处理其 Microsoft 365 标识、应用和设备的安全性。</span><span class="sxs-lookup"><span data-stu-id="296fb-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="296fb-109">安全功能分数可帮助组织：</span><span class="sxs-lookup"><span data-stu-id="296fb-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="296fb-110">报告组织安全状况的当前状态。</span><span class="sxs-lookup"><span data-stu-id="296fb-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="296fb-111">通过提供可发现性、可见性、指导和控制来提升安全性。</span><span class="sxs-lookup"><span data-stu-id="296fb-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="296fb-112">与基准进行比较，并建立关键绩效指标 (KPI)。</span><span class="sxs-lookup"><span data-stu-id="296fb-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="296fb-113">组织可以访问指标和趋势的稳固可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较等。</span><span class="sxs-lookup"><span data-stu-id="296fb-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="296fb-114">该分数还可以反映第三方解决方案何时解决了建议的操作。</span><span class="sxs-lookup"><span data-stu-id="296fb-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![安全分数主页](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="296fb-116">运作方式</span><span class="sxs-lookup"><span data-stu-id="296fb-116">How it works</span></span>

<span data-ttu-id="296fb-117">你获得以下操作点数：</span><span class="sxs-lookup"><span data-stu-id="296fb-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="296fb-118">配置建议的安全功能</span><span class="sxs-lookup"><span data-stu-id="296fb-118">Configuring recommended security features</span></span>
- <span data-ttu-id="296fb-119">执行与安全相关的任务</span><span class="sxs-lookup"><span data-stu-id="296fb-119">Doing security-related tasks</span></span>
- <span data-ttu-id="296fb-120">使用第三方应用程序或软件或备用缓解解决改进操作</span><span class="sxs-lookup"><span data-stu-id="296fb-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="296fb-121">有些改进操作仅在完全完成时提供分数。</span><span class="sxs-lookup"><span data-stu-id="296fb-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="296fb-122">如果为某些设备或用户完成了这些操作，一些会提供部分分数。</span><span class="sxs-lookup"><span data-stu-id="296fb-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="296fb-123">如果无法或不希望评估其中一项改进操作，可以选择接受风险或剩余风险。</span><span class="sxs-lookup"><span data-stu-id="296fb-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="296fb-124">如果你有受支持的 Microsoft 产品之一的许可证，你将看到这些产品的建议。</span><span class="sxs-lookup"><span data-stu-id="296fb-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="296fb-125">我们将向您展示产品的完整可能改进集，而不考虑许可证版本、订阅或计划。</span><span class="sxs-lookup"><span data-stu-id="296fb-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="296fb-126">这样，你可以了解安全性最佳实践并提升分数。</span><span class="sxs-lookup"><span data-stu-id="296fb-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="296fb-127">无论组织拥有特定产品的许可证是什么，你的绝对安全状况（以安全分数表示）都保持不变。</span><span class="sxs-lookup"><span data-stu-id="296fb-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="296fb-128">请记住，安全性应该与可用性相平衡，同时请注意不是每个建议都适合您的环境。</span><span class="sxs-lookup"><span data-stu-id="296fb-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="296fb-129">你的分数会实时更新，以反映可视化和改进操作页面中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="296fb-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="296fb-130">安全分数还会每天同步一次，以接收有关每个操作所得分的系统数据。</span><span class="sxs-lookup"><span data-stu-id="296fb-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="296fb-131">关键方案</span><span class="sxs-lookup"><span data-stu-id="296fb-131">Key scenarios</span></span>

- [<span data-ttu-id="296fb-132">检查当前分数</span><span class="sxs-lookup"><span data-stu-id="296fb-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="296fb-133">将分数与类似你的组织的分数进行比较</span><span class="sxs-lookup"><span data-stu-id="296fb-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="296fb-134">查看改进操作并决定行动计划</span><span class="sxs-lookup"><span data-stu-id="296fb-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="296fb-135">启动要调查或实施的工作流</span><span class="sxs-lookup"><span data-stu-id="296fb-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="296fb-136">如何对改进操作进行评分</span><span class="sxs-lookup"><span data-stu-id="296fb-136">How improvement actions are scored</span></span>

<span data-ttu-id="296fb-137">每个改进操作都值 10 分或更少，大多数改进操作都以二进制方式进行评分。</span><span class="sxs-lookup"><span data-stu-id="296fb-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="296fb-138">如果实施改进操作（如创建新策略或启用特定设置），则获得 100% 的分数。</span><span class="sxs-lookup"><span data-stu-id="296fb-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="296fb-139">对于其他改进操作，分数以总配置百分比表示。</span><span class="sxs-lookup"><span data-stu-id="296fb-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="296fb-140">例如，改进操作通过多重身份验证保护所有用户而获得 10 分。</span><span class="sxs-lookup"><span data-stu-id="296fb-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="296fb-141">你只有 50 个保护的用户（共 100 个）中，因此你获得的部分分数为 5 分 (50 分/共 100 分 \* 10 最大 pts = 5 pts) 。</span><span class="sxs-lookup"><span data-stu-id="296fb-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="296fb-142">安全分数中包含的产品</span><span class="sxs-lookup"><span data-stu-id="296fb-142">Products included in Secure Score</span></span>

<span data-ttu-id="296fb-143">目前，有针对以下产品的建议：</span><span class="sxs-lookup"><span data-stu-id="296fb-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="296fb-144">Microsoft 365 (包括 Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="296fb-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="296fb-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="296fb-145">Azure Active Directory</span></span>
- <span data-ttu-id="296fb-146">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="296fb-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="296fb-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="296fb-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="296fb-148">云应用安全</span><span class="sxs-lookup"><span data-stu-id="296fb-148">Cloud App Security</span></span>
- <span data-ttu-id="296fb-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="296fb-149">Microsoft Teams</span></span>

<span data-ttu-id="296fb-150">即将推出针对其他安全产品的建议。</span><span class="sxs-lookup"><span data-stu-id="296fb-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="296fb-151">建议不会涵盖与每个产品关联的所有攻击面，但它们是一个很好的基线。</span><span class="sxs-lookup"><span data-stu-id="296fb-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="296fb-152">还可以将改进操作标记为第三方或备用缓解涵盖。</span><span class="sxs-lookup"><span data-stu-id="296fb-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="296fb-153">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="296fb-153">Security defaults</span></span>

<span data-ttu-id="296fb-154">Microsoft 安全分数已更新了改进操作以支持 [Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)中的安全默认值，从而可以更轻松地使用针对常见攻击的预配置安全设置来帮助保护组织。</span><span class="sxs-lookup"><span data-stu-id="296fb-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="296fb-155">如果启用安全默认值，将被授予以下改进操作的完整分数：</span><span class="sxs-lookup"><span data-stu-id="296fb-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="296fb-156">确保所有用户都可以在 9 个点 (安全访问) </span><span class="sxs-lookup"><span data-stu-id="296fb-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="296fb-157">管理角色需要 MFA (10) </span><span class="sxs-lookup"><span data-stu-id="296fb-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="296fb-158">启用策略以阻止 7 (旧身份验证) </span><span class="sxs-lookup"><span data-stu-id="296fb-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="296fb-159">安全默认值包括提供与"登录风险策略"和"用户风险策略"改进操作类似的安全性的安全功能。</span><span class="sxs-lookup"><span data-stu-id="296fb-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="296fb-160">建议不要根据安全默认值设置这些策略，而应更新其状态为"通过替代缓解解决"。</span><span class="sxs-lookup"><span data-stu-id="296fb-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="296fb-161">所需权限</span><span class="sxs-lookup"><span data-stu-id="296fb-161">Required permissions</span></span>

<span data-ttu-id="296fb-162">若要有权访问 Microsoft 安全分数，必须在 Azure Active Directory 中分配以下角色之一。</span><span class="sxs-lookup"><span data-stu-id="296fb-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="296fb-163">读取和写入角色</span><span class="sxs-lookup"><span data-stu-id="296fb-163">Read and write roles</span></span>

<span data-ttu-id="296fb-164">通过读取和写入访问权限，你可以进行更改并直接与安全分数进行交互。</span><span class="sxs-lookup"><span data-stu-id="296fb-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="296fb-165">您还可以向其他用户分配只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="296fb-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="296fb-166">全局管理员</span><span class="sxs-lookup"><span data-stu-id="296fb-166">Global administrator</span></span>
* <span data-ttu-id="296fb-167">安全管理员</span><span class="sxs-lookup"><span data-stu-id="296fb-167">Security administrator</span></span>
* <span data-ttu-id="296fb-168">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="296fb-168">Exchange administrator</span></span>
* <span data-ttu-id="296fb-169">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="296fb-169">SharePoint administrator</span></span>
* <span data-ttu-id="296fb-170">帐户管理员</span><span class="sxs-lookup"><span data-stu-id="296fb-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="296fb-171">只读角色</span><span class="sxs-lookup"><span data-stu-id="296fb-171">Read-only roles</span></span>

<span data-ttu-id="296fb-172">使用只读访问权限，你无法编辑改进操作的状态或备注、编辑分数区域或编辑自定义比较。</span><span class="sxs-lookup"><span data-stu-id="296fb-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="296fb-173">支持人员管理员</span><span class="sxs-lookup"><span data-stu-id="296fb-173">Helpdesk administrator</span></span>
* <span data-ttu-id="296fb-174">用户管理员</span><span class="sxs-lookup"><span data-stu-id="296fb-174">User administrator</span></span>
* <span data-ttu-id="296fb-175">服务管理员</span><span class="sxs-lookup"><span data-stu-id="296fb-175">Service administrator</span></span>
* <span data-ttu-id="296fb-176">安全读者</span><span class="sxs-lookup"><span data-stu-id="296fb-176">Security reader</span></span>
* <span data-ttu-id="296fb-177">安全操作员</span><span class="sxs-lookup"><span data-stu-id="296fb-177">Security operator</span></span>
* <span data-ttu-id="296fb-178">全局读取者</span><span class="sxs-lookup"><span data-stu-id="296fb-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="296fb-179">风险感知</span><span class="sxs-lookup"><span data-stu-id="296fb-179">Risk awareness</span></span>

<span data-ttu-id="296fb-180">Microsoft 安全分数是安全状态的数字摘要，基于系统配置、用户行为和其他与安全相关的度量。</span><span class="sxs-lookup"><span data-stu-id="296fb-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="296fb-181">它不是系统或数据泄露的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="296fb-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="296fb-182">而是表示在 Microsoft 环境中采用安全控件的程度，可帮助消除泄露风险。</span><span class="sxs-lookup"><span data-stu-id="296fb-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="296fb-183">任何联机服务都不应受到安全漏洞的影响，安全分数不应被解释为防止以任何方式出现安全漏洞的保证。</span><span class="sxs-lookup"><span data-stu-id="296fb-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="296fb-184">欢迎提出宝贵意见</span><span class="sxs-lookup"><span data-stu-id="296fb-184">We want to hear from you</span></span>

<span data-ttu-id="296fb-185">如果有任何问题，请通过发布到安全、隐私和合规性社区 [&告知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 我们。</span><span class="sxs-lookup"><span data-stu-id="296fb-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="296fb-186">We're monitoring the community and will provide help.</span><span class="sxs-lookup"><span data-stu-id="296fb-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="296fb-187">相关资源</span><span class="sxs-lookup"><span data-stu-id="296fb-187">Related resources</span></span>

- [<span data-ttu-id="296fb-188">评估安全状况</span><span class="sxs-lookup"><span data-stu-id="296fb-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="296fb-189">跟踪 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="296fb-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="296fb-190">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="296fb-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="296fb-191">新增功能</span><span class="sxs-lookup"><span data-stu-id="296fb-191">What's new</span></span>](microsoft-secure-score-whats-new.md)