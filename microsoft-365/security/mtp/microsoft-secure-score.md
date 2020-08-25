---
title: Microsoft 安全功能分数
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 304967a06c1fec2df6968f12be30ef3001fdb762
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866867"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="36d10-104">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="36d10-104">Microsoft Secure Score</span></span>

<span data-ttu-id="36d10-105">Microsoft 安全分数是组织的安全状态的度量，数字越大，表明执行了更多改进操作。</span><span class="sxs-lookup"><span data-stu-id="36d10-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="36d10-106">可在 https://security.microsoft.com/securescore [Microsoft 365 安全中心](overview-security-center.md)中找到。</span><span class="sxs-lookup"><span data-stu-id="36d10-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="36d10-107">遵循安全得分建议可保护您的组织免受威胁。</span><span class="sxs-lookup"><span data-stu-id="36d10-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="36d10-108">从 Microsoft 365 安全中心的中央仪表板中，组织可以监视和使用其 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="36d10-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="36d10-109">安全分数可帮助组织：</span><span class="sxs-lookup"><span data-stu-id="36d10-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="36d10-110">报告组织安全状况的当前状态。</span><span class="sxs-lookup"><span data-stu-id="36d10-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="36d10-111">通过提供可发现性、可见性、指导和控制改进其安全状况。</span><span class="sxs-lookup"><span data-stu-id="36d10-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="36d10-112">与基准测试进行比较，并建立 (Kpi) 的关键绩效指标。</span><span class="sxs-lookup"><span data-stu-id="36d10-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="36d10-113">组织可以获得对指标和趋势的可靠可视化、与其他 Microsoft 产品的集成、与类似组织的分数比较以及其他更多。</span><span class="sxs-lookup"><span data-stu-id="36d10-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="36d10-114">分数还可以反映第三方解决方案解决建议操作的时间。</span><span class="sxs-lookup"><span data-stu-id="36d10-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![安全得分主页](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="36d10-116">运作方式</span><span class="sxs-lookup"><span data-stu-id="36d10-116">How it works</span></span>

<span data-ttu-id="36d10-117">为您提供了以下操作的要点：</span><span class="sxs-lookup"><span data-stu-id="36d10-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="36d10-118">配置建议的安全功能</span><span class="sxs-lookup"><span data-stu-id="36d10-118">Configuring recommended security features</span></span>
- <span data-ttu-id="36d10-119">执行与安全相关的任务</span><span class="sxs-lookup"><span data-stu-id="36d10-119">Performing security-related tasks</span></span>
- <span data-ttu-id="36d10-120">使用第三方应用程序或软件或其他缓解措施解决改进操作</span><span class="sxs-lookup"><span data-stu-id="36d10-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="36d10-121">某些改进操作仅在完全完成时提供积分。</span><span class="sxs-lookup"><span data-stu-id="36d10-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="36d10-122">某些设备或用户的已完成部分会提供一些要点。</span><span class="sxs-lookup"><span data-stu-id="36d10-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="36d10-123">如果您无法或不希望执行其中一个改进操作，则可以选择接受风险或剩余风险。</span><span class="sxs-lookup"><span data-stu-id="36d10-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="36d10-124">如果你拥有某个受支持的 Microsoft 产品的许可证，你将看到这些产品的建议。</span><span class="sxs-lookup"><span data-stu-id="36d10-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="36d10-125">我们将向您展示产品的全部可能改进，而不考虑许可证版本、订阅或计划。</span><span class="sxs-lookup"><span data-stu-id="36d10-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="36d10-126">通过这种方式，您可以了解安全最佳实践并提高成绩。</span><span class="sxs-lookup"><span data-stu-id="36d10-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="36d10-127">无论您的组织对特定产品拥有哪些许可证，绝对安全状态（按安全分数表示）保持不变。</span><span class="sxs-lookup"><span data-stu-id="36d10-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="36d10-128">请记住，安全应平衡可用性，而不是每个建议都适用于您的环境。</span><span class="sxs-lookup"><span data-stu-id="36d10-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="36d10-129">你的分数将实时更新，以反映可视化和改进操作页面中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="36d10-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="36d10-130">安全分数也会每天同步，以接收有关每个操作的已实现分数的系统数据。</span><span class="sxs-lookup"><span data-stu-id="36d10-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="36d10-131">关键方案</span><span class="sxs-lookup"><span data-stu-id="36d10-131">Key scenarios</span></span>

- [<span data-ttu-id="36d10-132">检查当前分数</span><span class="sxs-lookup"><span data-stu-id="36d10-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="36d10-133">比较你的成绩与你的组织（如你的组织）</span><span class="sxs-lookup"><span data-stu-id="36d10-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="36d10-134">查看改进操作并决定行动计划</span><span class="sxs-lookup"><span data-stu-id="36d10-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="36d10-135">启动工作流以进行调查或实施</span><span class="sxs-lookup"><span data-stu-id="36d10-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="36d10-136">Microsoft 365 安全中心和 ServiceNow 集成</span><span class="sxs-lookup"><span data-stu-id="36d10-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="36d10-137">如何对改进行动进行评分</span><span class="sxs-lookup"><span data-stu-id="36d10-137">How improvement actions are scored</span></span>

<span data-ttu-id="36d10-138">每个改进操作10磅或更少，并且都是以二进制方式进行评分。</span><span class="sxs-lookup"><span data-stu-id="36d10-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="36d10-139">如果实施改进操作（如创建新策略或打开特定设置），则将获得100% 的点数。</span><span class="sxs-lookup"><span data-stu-id="36d10-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="36d10-140">对于其他改进操作，点作为总配置的百分比提供。</span><span class="sxs-lookup"><span data-stu-id="36d10-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="36d10-141">例如，改进操作表明您通过使用多重身份验证来保护您的所有用户，从而获得10分。</span><span class="sxs-lookup"><span data-stu-id="36d10-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="36d10-142">您只有50的100个用户受保护，因此，您可以得到5分的部分分数 (50 受保护/100 总计 \* 10 max 磅 = 5 磅) 。</span><span class="sxs-lookup"><span data-stu-id="36d10-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="36d10-143">安全分数中包括的产品</span><span class="sxs-lookup"><span data-stu-id="36d10-143">Products included in Secure Score</span></span>

<span data-ttu-id="36d10-144">目前有关于 Microsoft 365 (的建议，其中包括 Exchange Online) 、Azure Active Directory、Microsoft Defender ATP、Azure ATP 和云应用安全性。</span><span class="sxs-lookup"><span data-stu-id="36d10-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="36d10-145">即将推出针对其他安全产品的建议。</span><span class="sxs-lookup"><span data-stu-id="36d10-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="36d10-146">这些建议不包含与每个产品相关联的所有攻击面，但它们是一个很棒的基准。</span><span class="sxs-lookup"><span data-stu-id="36d10-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="36d10-147">您还可以将改进操作标记为由第三方或备用缓解措施覆盖。</span><span class="sxs-lookup"><span data-stu-id="36d10-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="36d10-148">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="36d10-148">Security defaults</span></span>

<span data-ttu-id="36d10-149">Microsoft 安全评分已更新了 [在 Azure Active Directory 中支持安全默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)的改进操作，这使组织能够更轻松地使用预配置的安全设置进行常见攻击，从而帮助保护组织。</span><span class="sxs-lookup"><span data-stu-id="36d10-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="36d10-150">如果启用安全默认设置，你将获得以下改进操作的完整积分：</span><span class="sxs-lookup"><span data-stu-id="36d10-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="36d10-151">确保所有用户都可以完成多重身份验证以实现 (9 点的安全访问) </span><span class="sxs-lookup"><span data-stu-id="36d10-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="36d10-152">要求对管理角色进行 MFA (10 磅) </span><span class="sxs-lookup"><span data-stu-id="36d10-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="36d10-153">启用策略以阻止旧版身份验证 (7 点) </span><span class="sxs-lookup"><span data-stu-id="36d10-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="36d10-154">安全性默认值包括为 "登录风险策略" 和 "用户风险策略" 改进操作提供类似安全性的安全功能。</span><span class="sxs-lookup"><span data-stu-id="36d10-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="36d10-155">建议将这些策略的安全默认值更新为 "通过其他缓解措施进行解决"，而不是将这些策略设置为 "通过其他缓解措施"。</span><span class="sxs-lookup"><span data-stu-id="36d10-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="36d10-156">所需权限</span><span class="sxs-lookup"><span data-stu-id="36d10-156">Required permissions</span></span>

<span data-ttu-id="36d10-157">若要拥有访问 Microsoft 安全分数的权限，您必须在 Azure Active Directory 中为以下角色分配一个角色。</span><span class="sxs-lookup"><span data-stu-id="36d10-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="36d10-158">读取和写入角色</span><span class="sxs-lookup"><span data-stu-id="36d10-158">Read and write roles</span></span>

<span data-ttu-id="36d10-159">通过读取和写入访问权限，您可以进行更改，并直接与安全分数进行交互。</span><span class="sxs-lookup"><span data-stu-id="36d10-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="36d10-160">您还可以将只读访问权限分配给其他用户。</span><span class="sxs-lookup"><span data-stu-id="36d10-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="36d10-161">全局管理员</span><span class="sxs-lookup"><span data-stu-id="36d10-161">Global administrator</span></span>
* <span data-ttu-id="36d10-162">安全管理员</span><span class="sxs-lookup"><span data-stu-id="36d10-162">Security administrator</span></span>
* <span data-ttu-id="36d10-163">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="36d10-163">Exchange administrator</span></span>
* <span data-ttu-id="36d10-164">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="36d10-164">SharePoint administrator</span></span>
* <span data-ttu-id="36d10-165">帐户管理员</span><span class="sxs-lookup"><span data-stu-id="36d10-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="36d10-166">只读角色</span><span class="sxs-lookup"><span data-stu-id="36d10-166">Read-only roles</span></span>

<span data-ttu-id="36d10-167">如果具有只读访问权限，则无法编辑改进操作的状态或注释、编辑分数区域或编辑自定义比较。</span><span class="sxs-lookup"><span data-stu-id="36d10-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="36d10-168">支持人员管理员</span><span class="sxs-lookup"><span data-stu-id="36d10-168">Helpdesk administrator</span></span>
* <span data-ttu-id="36d10-169">用户管理员</span><span class="sxs-lookup"><span data-stu-id="36d10-169">User administrator</span></span>
* <span data-ttu-id="36d10-170">服务管理员</span><span class="sxs-lookup"><span data-stu-id="36d10-170">Service administrator</span></span>
* <span data-ttu-id="36d10-171">安全读者</span><span class="sxs-lookup"><span data-stu-id="36d10-171">Security reader</span></span>
* <span data-ttu-id="36d10-172">安全操作员</span><span class="sxs-lookup"><span data-stu-id="36d10-172">Security operator</span></span>
* <span data-ttu-id="36d10-173">全局读取者</span><span class="sxs-lookup"><span data-stu-id="36d10-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="36d10-174">风险感知</span><span class="sxs-lookup"><span data-stu-id="36d10-174">Risk awareness</span></span>

<span data-ttu-id="36d10-175">Microsoft 安全分数是基于系统配置、用户行为和其他与安全相关的度量的安全状态的数字摘要。</span><span class="sxs-lookup"><span data-stu-id="36d10-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="36d10-176">它并不是对系统或数据受到破坏的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="36d10-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="36d10-177">相反，它表示您在 Microsoft 环境中已采用安全控制的程度，可帮助弥补受到破坏的风险。</span><span class="sxs-lookup"><span data-stu-id="36d10-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="36d10-178">无在线服务完全不受安全破坏，安全分数不应以任何方式解释为保证安全违规。</span><span class="sxs-lookup"><span data-stu-id="36d10-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="36d10-179">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="36d10-179">We want to hear from you</span></span>

<span data-ttu-id="36d10-180">如果你有任何问题，请通过在 [安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="36d10-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="36d10-181">我们正在监视社区，并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="36d10-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="36d10-182">相关资源</span><span class="sxs-lookup"><span data-stu-id="36d10-182">Related resources</span></span>

- [<span data-ttu-id="36d10-183">评估你的安全状况</span><span class="sxs-lookup"><span data-stu-id="36d10-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="36d10-184">跟踪你的 Microsoft 安全分数历史记录并实现目标</span><span class="sxs-lookup"><span data-stu-id="36d10-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="36d10-185">即将推出的功能</span><span class="sxs-lookup"><span data-stu-id="36d10-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="36d10-186">新增功能</span><span class="sxs-lookup"><span data-stu-id="36d10-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
