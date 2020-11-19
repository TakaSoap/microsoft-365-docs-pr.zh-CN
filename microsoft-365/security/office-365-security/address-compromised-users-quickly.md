---
title: 使用自动调查和响应解决已损坏的用户帐户
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护、已泄露
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: 了解如何使用 Microsoft Defender for Office 365 计划2中的自动调查和响应功能，以加快检测和解决受危害的用户帐户的过程。
ms.openlocfilehash: 80e4529f864d83d2a1711007f0f095de39955e68
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357902"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="bfe45-104">使用自动调查和响应解决已损坏的用户帐户</span><span class="sxs-lookup"><span data-stu-id="bfe45-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bfe45-105">[Microsoft Defender For Office 365 计划 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 包括功能强大的 [自动调查和响应](office-365-air.md) (空中) 功能。</span><span class="sxs-lookup"><span data-stu-id="bfe45-105">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="bfe45-106">此类功能可以将安全操作团队保存大量时间和处理威胁的工作。</span><span class="sxs-lookup"><span data-stu-id="bfe45-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="bfe45-107">Microsoft 继续改进安全功能。</span><span class="sxs-lookup"><span data-stu-id="bfe45-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="bfe45-108">最近，空中功能已得到增强，可在当前预览) 中 (的用户安全行动手册。</span><span class="sxs-lookup"><span data-stu-id="bfe45-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="bfe45-109">阅读本文，了解有关已损坏用户安全行动手册的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bfe45-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="bfe45-110">通过 Microsoft Defender for Office 365，了解更多详细信息，了解博客文章 [加快了检查和响应用户泄露和限制泄露范围的时间](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) 。</span><span class="sxs-lookup"><span data-stu-id="bfe45-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![对受损用户的自动调查](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="bfe45-112">已损坏的用户安全行动手册使贵组织的安全团队能够：</span><span class="sxs-lookup"><span data-stu-id="bfe45-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="bfe45-113">加速对已泄露用户帐户的检测;</span><span class="sxs-lookup"><span data-stu-id="bfe45-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="bfe45-114">在帐户受到威胁时限制泄露的范围;并</span><span class="sxs-lookup"><span data-stu-id="bfe45-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="bfe45-115">更有效地响应已损坏的用户。</span><span class="sxs-lookup"><span data-stu-id="bfe45-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="bfe45-116">已损坏的用户通知</span><span class="sxs-lookup"><span data-stu-id="bfe45-116">Compromised user alerts</span></span>

<span data-ttu-id="bfe45-117">当用户帐户受到威胁时，将发生反常或反常行为。</span><span class="sxs-lookup"><span data-stu-id="bfe45-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="bfe45-118">例如，网络钓鱼和垃圾邮件可能会从受信任的用户帐户内部发送。</span><span class="sxs-lookup"><span data-stu-id="bfe45-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="bfe45-119">适用于 Office 的 Defender 365 可以检测到 Office 365 中的电子邮件模式和协作活动中的此类异常。</span><span class="sxs-lookup"><span data-stu-id="bfe45-119">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="bfe45-120">发生这种情况时，将触发警报，并开始威胁缓解过程。</span><span class="sxs-lookup"><span data-stu-id="bfe45-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="bfe45-121">例如，以下是由于可疑电子邮件发送而触发的警报：</span><span class="sxs-lookup"><span data-stu-id="bfe45-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![因可疑电子邮件发送而触发的警报](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="bfe45-123">下面的示例展示了用户达到发送限制时触发的警报：</span><span class="sxs-lookup"><span data-stu-id="bfe45-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![已达到发送限制触发的警报](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="bfe45-125">调查已损坏的用户并对其做出响应</span><span class="sxs-lookup"><span data-stu-id="bfe45-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="bfe45-126">当用户帐户受到威胁时，将触发警报。</span><span class="sxs-lookup"><span data-stu-id="bfe45-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="bfe45-127">在某些情况下，该用户帐户将被阻止，并阻止发送任何其他电子邮件，直到组织的安全操作团队解决该问题。</span><span class="sxs-lookup"><span data-stu-id="bfe45-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="bfe45-128">在其他情况下，自动调查开始时可能导致安全团队应采取的建议操作。</span><span class="sxs-lookup"><span data-stu-id="bfe45-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="bfe45-129">查看和调查受限制的用户</span><span class="sxs-lookup"><span data-stu-id="bfe45-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="bfe45-130">查看有关自动调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="bfe45-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="bfe45-131">您必须具有适当的权限才能执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="bfe45-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="bfe45-132">查看 [使用空中功能所需的权限](office-365-air.md#required-permissions-to-use-air-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="bfe45-132">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="bfe45-133">查看和调查受限制的用户</span><span class="sxs-lookup"><span data-stu-id="bfe45-133">View and investigate restricted users</span></span>

<span data-ttu-id="bfe45-134">有几个选项可用于导航到受限制的用户列表。</span><span class="sxs-lookup"><span data-stu-id="bfe45-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="bfe45-135">例如，在安全 & 合规性中心中，可以转到 "**威胁管理**"  >  **查看**  >  **受限制的用户**。</span><span class="sxs-lookup"><span data-stu-id="bfe45-135">For example, in the Security & Compliance Center, you can go to **Threat management** > **Review** > **Restricted Users**.</span></span> <span data-ttu-id="bfe45-136">下面的过程介绍了如何使用 " **通知** " 仪表板进行导航，这是查看可能已触发的各种警报的一种有效方式。</span><span class="sxs-lookup"><span data-stu-id="bfe45-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="bfe45-137">转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="bfe45-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="bfe45-138">在导航窗格中，选择 "**通知**  >  **仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="bfe45-138">In the navigation pane, choose **Alerts** > **Dashboard**.</span></span>

3. <span data-ttu-id="bfe45-139">在 " **其他通知** " 小组件中，选择 " **受限用户**"。</span><span class="sxs-lookup"><span data-stu-id="bfe45-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![其他通知小组件](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="bfe45-141">这将打开受限制的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="bfe45-141">This opens the list of restricted users.</span></span>

   ![Office 365 中的受限用户](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="bfe45-143">选择列表中的用户帐户以查看详细信息并执行操作，例如， [释放受限制的用户](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe45-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="bfe45-144">查看有关自动调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="bfe45-144">View details about automated investigations</span></span>

<span data-ttu-id="bfe45-145">自动调查开始后，您可以在安全 & 合规性中心中看到其详细信息和结果。</span><span class="sxs-lookup"><span data-stu-id="bfe45-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="bfe45-146">转到 "**威胁管理**  >  **调查**"，然后选择调查以查看其详细信息。</span><span class="sxs-lookup"><span data-stu-id="bfe45-146">Go to **Threat management** > **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="bfe45-147">若要了解详细信息，请参阅 [查看调查的详细信息](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe45-147">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="bfe45-148">请记住以下几点</span><span class="sxs-lookup"><span data-stu-id="bfe45-148">Keep the following points in mind</span></span>

- <span data-ttu-id="bfe45-149">**停留在通知的最前面**。</span><span class="sxs-lookup"><span data-stu-id="bfe45-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="bfe45-150">正如您所知，发现泄露的时间越长，组织、客户和合作伙伴可能会带来广泛的影响和成本。</span><span class="sxs-lookup"><span data-stu-id="bfe45-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="bfe45-151">早期检测和及时响应是缓解威胁的关键，尤其是在用户的帐户受到威胁时。</span><span class="sxs-lookup"><span data-stu-id="bfe45-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="bfe45-152">**自动化可协助您的安全操作团队，但不能取代**。</span><span class="sxs-lookup"><span data-stu-id="bfe45-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="bfe45-153">自动化调查和响应功能可以在早期检测到已损坏的用户，但您的安全操作团队可能需要参与并执行一些调查和修正。</span><span class="sxs-lookup"><span data-stu-id="bfe45-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="bfe45-154">需要有关这方面的一些帮助吗？</span><span class="sxs-lookup"><span data-stu-id="bfe45-154">Need some help with this?</span></span> <span data-ttu-id="bfe45-155">请参阅 [审阅和批准操作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe45-155">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="bfe45-156">**不要依赖可疑登录通知作为唯一的指示器**。</span><span class="sxs-lookup"><span data-stu-id="bfe45-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="bfe45-157">当用户帐户受到威胁时，它可能会（也可能不触发）可疑登录警报。</span><span class="sxs-lookup"><span data-stu-id="bfe45-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="bfe45-158">有时，它是在帐户泄露后发生的一系列活动，触发警报。</span><span class="sxs-lookup"><span data-stu-id="bfe45-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="bfe45-159">想要了解有关通知的详细信息吗？</span><span class="sxs-lookup"><span data-stu-id="bfe45-159">Want to know more about alerts?</span></span> <span data-ttu-id="bfe45-160">请参阅 [警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="bfe45-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bfe45-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bfe45-161">Next steps</span></span>

- [<span data-ttu-id="bfe45-162">查看使用 AIR 功能所需的权限</span><span class="sxs-lookup"><span data-stu-id="bfe45-162">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="bfe45-163">查找和调查 Office 365 中的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="bfe45-163">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="bfe45-164">了解 Microsoft Defender for Endpoint 中的空气</span><span class="sxs-lookup"><span data-stu-id="bfe45-164">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="bfe45-165">访问 Microsoft 365 路线图以了解即将推出和推出的内容</span><span class="sxs-lookup"><span data-stu-id="bfe45-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
