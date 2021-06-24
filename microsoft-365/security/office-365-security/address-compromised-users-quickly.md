---
title: 通过自动调查和响应处理遭到入侵的用户帐户
keywords: AIR， autoIR， Microsoft Defender for Endpoint， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护， 受到威胁
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 06/10/2021
description: 了解如何通过 Microsoft Defender for Office 365 计划 2 中的自动调查和响应功能来加快检测和解决遭到入侵的用户帐户的过程。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd1ad6f52114340153f3958441bfb9500db67215
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108569"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="c25b2-104">通过自动调查和响应处理遭到入侵的用户帐户</span><span class="sxs-lookup"><span data-stu-id="c25b2-104">Address compromised user accounts with automated investigation and response</span></span>

<span data-ttu-id="c25b2-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="c25b2-105">**Applies to**</span></span>
- [<span data-ttu-id="c25b2-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c25b2-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c25b2-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="c25b2-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c25b2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c25b2-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="c25b2-109">[Microsoft Defender for Office 365 计划 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)包括强大的自动调查和响应 (AIR) 功能。 [](office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="c25b2-109">[Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="c25b2-110">此类功能可以节省安全运营团队处理威胁的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="c25b2-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="c25b2-111">Microsoft 继续改进安全性功能。</span><span class="sxs-lookup"><span data-stu-id="c25b2-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="c25b2-112">最近，AIR 功能得到增强，包括当前处于预览版 (用户安全) 。</span><span class="sxs-lookup"><span data-stu-id="c25b2-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="c25b2-113">阅读本文，详细了解遭到入侵的用户安全手册。</span><span class="sxs-lookup"><span data-stu-id="c25b2-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="c25b2-114">有关其他详细信息，请参阅博客文章使用[Microsoft Defender](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) Office 365检测并响应用户泄露并限制泄露范围。</span><span class="sxs-lookup"><span data-stu-id="c25b2-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![针对受损用户的自动调查](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="c25b2-116">利用受损的用户安全手册，组织的安全团队可以：</span><span class="sxs-lookup"><span data-stu-id="c25b2-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="c25b2-117">加快检测遭到入侵的用户帐户;</span><span class="sxs-lookup"><span data-stu-id="c25b2-117">Speed up detection of compromised user accounts;</span></span>
- <span data-ttu-id="c25b2-118">在帐户泄露时限制泄露范围;和</span><span class="sxs-lookup"><span data-stu-id="c25b2-118">Limit the scope of a breach when an account is compromised; and</span></span>
- <span data-ttu-id="c25b2-119">更有效地响应受损用户。</span><span class="sxs-lookup"><span data-stu-id="c25b2-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="c25b2-120">遭到入侵的用户警报</span><span class="sxs-lookup"><span data-stu-id="c25b2-120">Compromised user alerts</span></span>

<span data-ttu-id="c25b2-121">当用户帐户受到威胁时，会发生异常或异常行为。</span><span class="sxs-lookup"><span data-stu-id="c25b2-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="c25b2-122">例如，网络钓鱼和垃圾邮件可能从受信任的用户帐户内部发送。</span><span class="sxs-lookup"><span data-stu-id="c25b2-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="c25b2-123">Defender for Office 365 可以检测电子邮件模式和内部协作活动中的Office 365。</span><span class="sxs-lookup"><span data-stu-id="c25b2-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="c25b2-124">发生这种情况时，将触发警报，并开始威胁缓解过程。</span><span class="sxs-lookup"><span data-stu-id="c25b2-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="c25b2-125">例如，下面是由于可疑电子邮件发送而触发的警报：</span><span class="sxs-lookup"><span data-stu-id="c25b2-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![由于可疑电子邮件发送而触发的警报](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="c25b2-127">下面是在达到用户的发送限制时触发的警报示例：</span><span class="sxs-lookup"><span data-stu-id="c25b2-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![通过达到发送限制触发的警报](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="c25b2-129">调查和响应遭到入侵的用户</span><span class="sxs-lookup"><span data-stu-id="c25b2-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="c25b2-130">用户帐户泄露时，将触发警报。</span><span class="sxs-lookup"><span data-stu-id="c25b2-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="c25b2-131">在某些情况下，该用户帐户将被阻止并阻止发送任何进一步的电子邮件，直到组织的安全运营团队解决该问题为止。</span><span class="sxs-lookup"><span data-stu-id="c25b2-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="c25b2-132">在其他情况下，将开始自动调查，这可能会导致安全团队采取建议的操作。</span><span class="sxs-lookup"><span data-stu-id="c25b2-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="c25b2-133">查看和调查受限用户</span><span class="sxs-lookup"><span data-stu-id="c25b2-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="c25b2-134">查看有关自动调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="c25b2-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="c25b2-135">您必须具有适当的权限才能执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="c25b2-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="c25b2-136">请参阅 [使用 AIR 功能所需的权限](office-365-air.md#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="c25b2-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="c25b2-137">查看和调查受限用户</span><span class="sxs-lookup"><span data-stu-id="c25b2-137">View and investigate restricted users</span></span>

<span data-ttu-id="c25b2-138">有几个选项可以导航到受限用户列表。</span><span class="sxs-lookup"><span data-stu-id="c25b2-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="c25b2-139">例如，在 Microsoft 365 Defender门户中，可以转到"电子邮件&**协作** \> **""** 审阅受限 \> **用户"。**</span><span class="sxs-lookup"><span data-stu-id="c25b2-139">For example, in the Microsoft 365 Defender portal, you can go to **Email & collaboration** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="c25b2-140">以下过程介绍使用 **警报** 仪表板的导航，这是查看可能触发的各种警报的一个好方法。</span><span class="sxs-lookup"><span data-stu-id="c25b2-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="c25b2-141">打开Microsoft 365 Defender门户 <https://security.microsoft.com> () 转到"事件&**警报** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="c25b2-141">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Incidents & alerts** \> **Alerts**.</span></span> <span data-ttu-id="c25b2-142">或者，若要直接转到 **警报** 页面，请使用 <https://security.microsoft.com/alerts> 。</span><span class="sxs-lookup"><span data-stu-id="c25b2-142">Or, to go directly to the **Alerts** page, use <https://security.microsoft.com/alerts>.</span></span>

2. <span data-ttu-id="c25b2-143">在" **通知"** 页上，按时间段筛选结果，并筛选名为"用户 **限制发送电子邮件"的策略**。</span><span class="sxs-lookup"><span data-stu-id="c25b2-143">On the **Alerts** page, filter the results by time period and the policy named **User restricted from sending email**.</span></span>

   ![已针对受限用户Microsoft 365 Defender通知门户中的"通知"页](../../media/m365-sc-alerts-page-with-restricted-user.png)

3. <span data-ttu-id="c25b2-145">If you select the entry by clicking on the name， a **User restricted from sending email** page opens with additional details for you to review.</span><span class="sxs-lookup"><span data-stu-id="c25b2-145">If you select the entry by clicking on the name, a **User restricted from sending email** page opens with additional details for you to review.</span></span> <span data-ttu-id="c25b2-146">在"**管理警报**"按钮旁边，可以单击"更多选项"图标"更多选项"，然后选择"查看受限用户详细信息"转到"受限用户"页面，可在其中释放 ![ ](../../media/m365-cc-sc-more-actions-icon.png) [受限用户](removing-user-from-restricted-users-portal-after-spam.md)。  </span><span class="sxs-lookup"><span data-stu-id="c25b2-146">Next to the **Manage alert** button, you can click ![More options icon](../../media/m365-cc-sc-more-actions-icon.png) **More options** and then select **View restricted user details** to go to the **Restricted users** page, where you can [release the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

   ![被限制从警报中心发送电子邮件的用户页面](../../media/m365-sc-alerts-user-restricted-from-sending-email-page.png)

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="c25b2-148">查看有关自动调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="c25b2-148">View details about automated investigations</span></span>

<span data-ttu-id="c25b2-149">开始自动调查后，可以在安全与合规中心内查看&结果。</span><span class="sxs-lookup"><span data-stu-id="c25b2-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="c25b2-150">转到 **"威胁管理** \> **调查"，** 然后选择调查以查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="c25b2-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="c25b2-151">若要了解详细信息，请参阅 [查看调查的详细信息](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="c25b2-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="c25b2-152">请记住以下几点</span><span class="sxs-lookup"><span data-stu-id="c25b2-152">Keep the following points in mind</span></span>

- <span data-ttu-id="c25b2-153">**随时了解警报**。</span><span class="sxs-lookup"><span data-stu-id="c25b2-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="c25b2-154">正如你所知，未发现泄露的时间越长，对组织、客户和合作伙伴造成广泛影响和成本的可能性越大。</span><span class="sxs-lookup"><span data-stu-id="c25b2-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="c25b2-155">提前检测和及时响应对于缓解威胁至关重要，尤其是在用户帐户受到威胁时。</span><span class="sxs-lookup"><span data-stu-id="c25b2-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="c25b2-156">**自动化可帮助（但不替换）安全运营团队**。</span><span class="sxs-lookup"><span data-stu-id="c25b2-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="c25b2-157">自动调查和响应功能可以尽早检测到受到威胁的用户，但安全运营团队可能需要参与并执行一些调查和修正。</span><span class="sxs-lookup"><span data-stu-id="c25b2-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="c25b2-158">需要一些帮助吗？</span><span class="sxs-lookup"><span data-stu-id="c25b2-158">Need some help with this?</span></span> <span data-ttu-id="c25b2-159">请参阅 [审阅和批准操作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="c25b2-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="c25b2-160">**不要依赖可疑登录警报作为唯一指示器**。</span><span class="sxs-lookup"><span data-stu-id="c25b2-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="c25b2-161">当用户帐户受到威胁时，它可能会或可能不会触发可疑的登录警报。</span><span class="sxs-lookup"><span data-stu-id="c25b2-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="c25b2-162">有时，是在帐户泄露后发生的一系列活动触发警报。</span><span class="sxs-lookup"><span data-stu-id="c25b2-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="c25b2-163">想要了解有关警报的更多信息？</span><span class="sxs-lookup"><span data-stu-id="c25b2-163">Want to know more about alerts?</span></span> <span data-ttu-id="c25b2-164">请参阅 [警报策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c25b2-164">See [Alert policies](../../compliance/alert-policies.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c25b2-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c25b2-165">Next steps</span></span>

- [<span data-ttu-id="c25b2-166">查看使用 AIR 功能所需的权限</span><span class="sxs-lookup"><span data-stu-id="c25b2-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="c25b2-167">在电子邮件中查找并调查恶意Office 365</span><span class="sxs-lookup"><span data-stu-id="c25b2-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="c25b2-168">了解 Microsoft Defender for Endpoint 中的 AIR</span><span class="sxs-lookup"><span data-stu-id="c25b2-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="c25b2-169">访问Microsoft 365路线图，了解即将推出和即将推出哪些功能</span><span class="sxs-lookup"><span data-stu-id="c25b2-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)