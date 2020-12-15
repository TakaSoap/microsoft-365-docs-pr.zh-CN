---
title: Microsoft 安全功能分数
description: 介绍 Microsoft 365 安全中心中的 Microsoft 安全分数、如何改善安全状态以及管理员期望的安全。
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
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682567"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="da968-104">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="da968-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="da968-105">Microsoft 安全分数是组织安全状况的度量，数字越高，表示采取的改进操作就越高。</span><span class="sxs-lookup"><span data-stu-id="da968-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="da968-106">可以在 https://security.microsoft.com/securescore [Microsoft 365 安全中心找到它](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="da968-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="da968-107">遵循安全分数建议可保护组织免受威胁。</span><span class="sxs-lookup"><span data-stu-id="da968-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="da968-108">在 Microsoft 365 安全中心的集中式仪表板中，组织可以监视并处理其 Microsoft 365 标识、应用和设备的安全性。</span><span class="sxs-lookup"><span data-stu-id="da968-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="da968-109">安全分数可帮助组织：</span><span class="sxs-lookup"><span data-stu-id="da968-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="da968-110">有关组织安全状况的当前状态的报告。</span><span class="sxs-lookup"><span data-stu-id="da968-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="da968-111">通过提供可发现性、可见性、指导和控制，改进其安全状况。</span><span class="sxs-lookup"><span data-stu-id="da968-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="da968-112">与基准进行比较，并建立关键绩效指标 (KPI) 。</span><span class="sxs-lookup"><span data-stu-id="da968-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="da968-113">组织可以访问指标和趋势的稳固可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较等。</span><span class="sxs-lookup"><span data-stu-id="da968-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="da968-114">该分数还可以反映第三方解决方案何时解决了建议的操作。</span><span class="sxs-lookup"><span data-stu-id="da968-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![安全分数主页](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="da968-116">运作方式</span><span class="sxs-lookup"><span data-stu-id="da968-116">How it works</span></span>

<span data-ttu-id="da968-117">您将获得以下操作点数：</span><span class="sxs-lookup"><span data-stu-id="da968-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="da968-118">配置建议的安全功能</span><span class="sxs-lookup"><span data-stu-id="da968-118">Configuring recommended security features</span></span>
- <span data-ttu-id="da968-119">执行与安全相关的任务</span><span class="sxs-lookup"><span data-stu-id="da968-119">Performing security-related tasks</span></span>
- <span data-ttu-id="da968-120">使用第三方应用程序或软件或备用缓解解决改进操作</span><span class="sxs-lookup"><span data-stu-id="da968-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="da968-121">某些改进操作仅在完全完成时提供分数。</span><span class="sxs-lookup"><span data-stu-id="da968-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="da968-122">如果为某些设备或用户完成了这些操作，一些会提供部分分数。</span><span class="sxs-lookup"><span data-stu-id="da968-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="da968-123">如果无法或不希望对其中一项改进操作进行评估，可以选择接受风险或剩余风险。</span><span class="sxs-lookup"><span data-stu-id="da968-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="da968-124">如果你有受支持的 Microsoft 产品之一的许可证，你将看到这些产品的建议。</span><span class="sxs-lookup"><span data-stu-id="da968-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="da968-125">我们将向您展示产品的完整可能改进，无论许可证版本、订阅或计划如何。</span><span class="sxs-lookup"><span data-stu-id="da968-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="da968-126">这样，你可以了解安全最佳做法并提升分数。</span><span class="sxs-lookup"><span data-stu-id="da968-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="da968-127">无论组织为特定产品拥有哪些许可证，你的绝对安全状态（由安全分数表示）都保持不变。</span><span class="sxs-lookup"><span data-stu-id="da968-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="da968-128">请记住，安全性应该与可用性平衡，并且并不是每个建议都适用于你的环境。</span><span class="sxs-lookup"><span data-stu-id="da968-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="da968-129">你的分数会实时更新，以反映可视化和改进操作页面中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="da968-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="da968-130">安全分数还会每天同步，以接收有关每个操作所得分的系统数据。</span><span class="sxs-lookup"><span data-stu-id="da968-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="da968-131">关键方案</span><span class="sxs-lookup"><span data-stu-id="da968-131">Key scenarios</span></span>

- [<span data-ttu-id="da968-132">检查当前分数</span><span class="sxs-lookup"><span data-stu-id="da968-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="da968-133">将分数与组织（如组织）进行比较</span><span class="sxs-lookup"><span data-stu-id="da968-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="da968-134">查看改进操作并决定行动计划</span><span class="sxs-lookup"><span data-stu-id="da968-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="da968-135">启动要调查或实施的工作流</span><span class="sxs-lookup"><span data-stu-id="da968-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="da968-136">Microsoft 365 安全中心和 ServiceNow 集成</span><span class="sxs-lookup"><span data-stu-id="da968-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="da968-137">如何对改进操作进行评分</span><span class="sxs-lookup"><span data-stu-id="da968-137">How improvement actions are scored</span></span>

<span data-ttu-id="da968-138">每个改进操作都值 10 分或更少，大多数改进操作都以二进制方式进行评分。</span><span class="sxs-lookup"><span data-stu-id="da968-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="da968-139">如果实施改进操作（如创建新策略或打开特定设置），则获得 100% 的分数。</span><span class="sxs-lookup"><span data-stu-id="da968-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="da968-140">对于其他改进操作，分数以总配置的百分比表示。</span><span class="sxs-lookup"><span data-stu-id="da968-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="da968-141">例如，改进操作通过多重身份验证保护所有用户来表示你获得 10 分。</span><span class="sxs-lookup"><span data-stu-id="da968-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="da968-142">你只有 50 个保护的用户，共 100 个用户，因此你获得的部分分数为 5 分 (50 个受保护/ 100 个总计 \* 10 最大 pts = 5 pts) 。</span><span class="sxs-lookup"><span data-stu-id="da968-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="da968-143">安全分数中包含的产品</span><span class="sxs-lookup"><span data-stu-id="da968-143">Products included in Secure Score</span></span>

<span data-ttu-id="da968-144">目前，有针对 Microsoft 365 (的建议，包括 Exchange Online) 、Azure Active Directory、Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="da968-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Cloud App Security.</span></span> <span data-ttu-id="da968-145">即将推出针对其他安全产品的建议。</span><span class="sxs-lookup"><span data-stu-id="da968-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="da968-146">建议不会涵盖与每个产品关联的所有攻击面，但它们是一个很好的基线。</span><span class="sxs-lookup"><span data-stu-id="da968-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="da968-147">还可以将改进操作标记为第三方或备用缓解所涵盖。</span><span class="sxs-lookup"><span data-stu-id="da968-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="da968-148">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="da968-148">Security defaults</span></span>

<span data-ttu-id="da968-149">Microsoft 安全分数已更新了改进操作以支持 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)中的安全默认值，这便于使用常见攻击的预配置安全设置帮助保护组织。</span><span class="sxs-lookup"><span data-stu-id="da968-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="da968-150">如果启用安全默认值，将被授予以下改进操作的完整分数：</span><span class="sxs-lookup"><span data-stu-id="da968-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="da968-151">确保所有用户都可以完成多重身份验证，以便安全访问 (9) </span><span class="sxs-lookup"><span data-stu-id="da968-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="da968-152">管理角色需要 MFA (10 点) </span><span class="sxs-lookup"><span data-stu-id="da968-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="da968-153">启用策略以阻止旧式身份验证 (7 点) </span><span class="sxs-lookup"><span data-stu-id="da968-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="da968-154">安全默认值包括提供与"登录风险策略"和"用户风险策略"改进操作类似的安全性的安全功能。</span><span class="sxs-lookup"><span data-stu-id="da968-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="da968-155">建议将状态更新为"通过替代缓解解决"，而不是在安全默认值上设置这些策略。</span><span class="sxs-lookup"><span data-stu-id="da968-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="da968-156">所需权限</span><span class="sxs-lookup"><span data-stu-id="da968-156">Required permissions</span></span>

<span data-ttu-id="da968-157">若要有权访问 Microsoft 安全分数，必须在 Azure Active Directory 中分配以下角色之一。</span><span class="sxs-lookup"><span data-stu-id="da968-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="da968-158">读取和写入角色</span><span class="sxs-lookup"><span data-stu-id="da968-158">Read and write roles</span></span>

<span data-ttu-id="da968-159">通过读取和写入访问权限，你可以进行更改并直接与安全分数交互。</span><span class="sxs-lookup"><span data-stu-id="da968-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="da968-160">您还可以向其他用户分配只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="da968-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="da968-161">全局管理员</span><span class="sxs-lookup"><span data-stu-id="da968-161">Global administrator</span></span>
* <span data-ttu-id="da968-162">安全管理员</span><span class="sxs-lookup"><span data-stu-id="da968-162">Security administrator</span></span>
* <span data-ttu-id="da968-163">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="da968-163">Exchange administrator</span></span>
* <span data-ttu-id="da968-164">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="da968-164">SharePoint administrator</span></span>
* <span data-ttu-id="da968-165">帐户管理员</span><span class="sxs-lookup"><span data-stu-id="da968-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="da968-166">只读角色</span><span class="sxs-lookup"><span data-stu-id="da968-166">Read-only roles</span></span>

<span data-ttu-id="da968-167">使用只读访问权限，你无法编辑改进操作的状态或注释、编辑分数区域或编辑自定义比较。</span><span class="sxs-lookup"><span data-stu-id="da968-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="da968-168">支持人员管理员</span><span class="sxs-lookup"><span data-stu-id="da968-168">Helpdesk administrator</span></span>
* <span data-ttu-id="da968-169">用户管理员</span><span class="sxs-lookup"><span data-stu-id="da968-169">User administrator</span></span>
* <span data-ttu-id="da968-170">服务管理员</span><span class="sxs-lookup"><span data-stu-id="da968-170">Service administrator</span></span>
* <span data-ttu-id="da968-171">安全读者</span><span class="sxs-lookup"><span data-stu-id="da968-171">Security reader</span></span>
* <span data-ttu-id="da968-172">安全操作员</span><span class="sxs-lookup"><span data-stu-id="da968-172">Security operator</span></span>
* <span data-ttu-id="da968-173">全局读取者</span><span class="sxs-lookup"><span data-stu-id="da968-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="da968-174">风险感知</span><span class="sxs-lookup"><span data-stu-id="da968-174">Risk awareness</span></span>

<span data-ttu-id="da968-175">Microsoft 安全分数是基于系统配置、用户行为和其他与安全相关的度量的安全状况的数字摘要。</span><span class="sxs-lookup"><span data-stu-id="da968-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="da968-176">它不是系统或数据被泄露的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="da968-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="da968-177">相反，它表示在 Microsoft 环境中采用安全控件的程度，可帮助消除泄露风险。</span><span class="sxs-lookup"><span data-stu-id="da968-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="da968-178">任何联机服务都完全不受安全漏洞的影响，安全分数不应被解释为防止以任何方式出现安全漏洞的保证。</span><span class="sxs-lookup"><span data-stu-id="da968-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="da968-179">欢迎提出宝贵意见</span><span class="sxs-lookup"><span data-stu-id="da968-179">We want to hear from you</span></span>

<span data-ttu-id="da968-180">如果有任何问题，请通过发布到安全、隐私和合规社区& [告知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 我们。</span><span class="sxs-lookup"><span data-stu-id="da968-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="da968-181">We're monitoring the community and will provide help.</span><span class="sxs-lookup"><span data-stu-id="da968-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="da968-182">相关资源</span><span class="sxs-lookup"><span data-stu-id="da968-182">Related resources</span></span>

- [<span data-ttu-id="da968-183">评估你的安全状况</span><span class="sxs-lookup"><span data-stu-id="da968-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="da968-184">跟踪 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="da968-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="da968-185">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="da968-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="da968-186">新增功能</span><span class="sxs-lookup"><span data-stu-id="da968-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
