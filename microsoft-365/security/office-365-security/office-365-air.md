---
title: 自动调查和响应 (空中) -入门
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/29/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 开始在 Microsoft Defender for Office 365 中使用自动调查和响应功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: b844e4817bc77d7f6f4e99df53fc4b14c7e7110c
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308883"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="08da0-104">开始使用 Office 365 中的自动调查和响应 (AIR) </span><span class="sxs-lookup"><span data-stu-id="08da0-104">Get started using automated investigation and response (AIR) in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="08da0-105">[Microsoft Defender For Office 365](office-365-atp.md) 包括功能强大的自动化调查和响应 (空中) 功能，可节省安全运营团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="08da0-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="08da0-106">随着警报的触发，安全操作团队可以对这些警报进行检查、设置优先级和响应。</span><span class="sxs-lookup"><span data-stu-id="08da0-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="08da0-107">跟上传入警报的数量的持续很大。</span><span class="sxs-lookup"><span data-stu-id="08da0-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="08da0-108">自动执行其中一些可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="08da0-108">Automating some of this can help.</span></span> <span data-ttu-id="08da0-109">借助 AIR，安全操作团队可以将精力集中在优先级较高的任务上，而不会失去触发警报的可见性。</span><span class="sxs-lookup"><span data-stu-id="08da0-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of alerts that are triggered.</span></span>

<span data-ttu-id="08da0-110">本文包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="08da0-110">This article includes:</span></span>
- <span data-ttu-id="08da0-111">空气的 [整体流量](#the-overall-flow-of-air) ;</span><span class="sxs-lookup"><span data-stu-id="08da0-111">The [overall flow](#the-overall-flow-of-air) of AIR;</span></span>
- <span data-ttu-id="08da0-112">[如何获取空气](#how-to-get-air);并</span><span class="sxs-lookup"><span data-stu-id="08da0-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="08da0-113">配置或使用 AIR 功能 [所需的权限](#required-permissions-to-use-air-capabilities) 。</span><span class="sxs-lookup"><span data-stu-id="08da0-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="08da0-114">空气的整体流动</span><span class="sxs-lookup"><span data-stu-id="08da0-114">The overall flow of AIR</span></span>

<span data-ttu-id="08da0-115">在较高的级别，将触发警报，安全行动手册将开始进行自动调查，从而导致发现和建议。</span><span class="sxs-lookup"><span data-stu-id="08da0-115">At a high level, an alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommendations.</span></span> <span data-ttu-id="08da0-116">下面是空中的整体流，具体步骤如下：</span><span class="sxs-lookup"><span data-stu-id="08da0-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="08da0-117">可通过以下方式之一启动自动调查：</span><span class="sxs-lookup"><span data-stu-id="08da0-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="08da0-118">由负责创建事件的 Office 事件触发 [警报](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 。</span><span class="sxs-lookup"><span data-stu-id="08da0-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by an Office event, which creates an incident.</span></span> <span data-ttu-id="08da0-119">根据事件的类型， [安全行动手册](automated-investigation-response-office.md#security-playbooks) 会开始进行自动调查。</span><span class="sxs-lookup"><span data-stu-id="08da0-119">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) starts an automated investigation.</span></span> 

     <span data-ttu-id="08da0-120">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="08da0-120">--- or ---</span></span>
   
   - <span data-ttu-id="08da0-121">安全分析员在使用[威胁资源管理器](threat-explorer.md)时[开始进行自动调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="08da0-121">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="08da0-122">在自动调查运行过程中，它将收集有关与该电子邮件相关的相关电子邮件和实体的其他数据。</span><span class="sxs-lookup"><span data-stu-id="08da0-122">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="08da0-123">此类实体可以包括文件、Url 和收件人。</span><span class="sxs-lookup"><span data-stu-id="08da0-123">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="08da0-124">调查的范围可以随着新的和相关的警报的触发而增加。</span><span class="sxs-lookup"><span data-stu-id="08da0-124">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="08da0-125">在自动调查期间和之后，可以查看 [详细信息和结果](air-view-investigation-results.md) 。</span><span class="sxs-lookup"><span data-stu-id="08da0-125">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="08da0-126">结果包括 [建议的操作](air-remediation-actions.md) ，可采取这些操作来响应和修正发现的任何威胁。</span><span class="sxs-lookup"><span data-stu-id="08da0-126">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="08da0-127">此外，还可以使用 [行动手册日志](air-view-investigation-results.md#playbook-log) 来跟踪所有调查活动。</span><span class="sxs-lookup"><span data-stu-id="08da0-127">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

    <span data-ttu-id="08da0-128">如果您的组织使用的是自定义报告解决方案或第三方解决方案，则可以 [使用 Office 365 管理活动 API](air-custom-reporting.md) 来查看有关自动调查和威胁的信息。</span><span class="sxs-lookup"><span data-stu-id="08da0-128">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](air-custom-reporting.md) to view information about automated investigations and threats.</span></span>

4. <span data-ttu-id="08da0-129">您的安全操作团队将检查 [调查结果和建议](air-view-investigation-results.md)，并 [批准或拒绝修正操作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="08da0-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

    <span data-ttu-id="08da0-130">由于已批准挂起的修正操作 (或拒绝) ，因此自动调查完成。</span><span class="sxs-lookup"><span data-stu-id="08da0-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!NOTE]
> <span data-ttu-id="08da0-131">在 Office 365 ATP 中，不会自动执行任何修正操作。</span><span class="sxs-lookup"><span data-stu-id="08da0-131">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="08da0-132">只有在组织的安全团队批准后，才会执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="08da0-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

<span data-ttu-id="08da0-133">在自动调查过程期间和之后，安全团队可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="08da0-133">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="08da0-134">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="08da0-134">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="08da0-135">查看调查的结果详细信息</span><span class="sxs-lookup"><span data-stu-id="08da0-135">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="08da0-136">查看和批准作为调查结果的操作</span><span class="sxs-lookup"><span data-stu-id="08da0-136">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="08da0-137">有关更多详细信息，请参阅 [AIR 的工作原理](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。</span><span class="sxs-lookup"><span data-stu-id="08da0-137">For more details, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="08da0-138">如何获取空中</span><span class="sxs-lookup"><span data-stu-id="08da0-138">How to get AIR</span></span>

<span data-ttu-id="08da0-139">在 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)中包含空中功能。</span><span class="sxs-lookup"><span data-stu-id="08da0-139">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2).</span></span> <span data-ttu-id="08da0-140">但是， [必须配置](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 您的策略，以使空气按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="08da0-140">However, your [policies must be configured](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) in order for AIR to work as expected.</span></span> <span data-ttu-id="08da0-141">此外，请务必查看并可能配置组织的 [通知策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="08da0-141">In addition, make sure to review and potentially configure your organization's [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> 

<span data-ttu-id="08da0-142">Microsoft 365 提供了许多内置的警报策略，可帮助确定 Exchange 管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。</span><span class="sxs-lookup"><span data-stu-id="08da0-142">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="08da0-143">有几个 [默认的警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="08da0-143">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="08da0-144">其中包括以下项：</span><span class="sxs-lookup"><span data-stu-id="08da0-144">These include the following:</span></span>

- <span data-ttu-id="08da0-145">检测到潜在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="08da0-145">A potentially malicious URL click is detected</span></span>

- <span data-ttu-id="08da0-146">用户将电子邮件报告为网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="08da0-146">An email message is reported by a user as phish</span></span>

- <span data-ttu-id="08da0-147">传递后删除包含恶意软件的电子邮件</span><span class="sxs-lookup"><span data-stu-id="08da0-147">Email messages containing malware are removed after delivery</span></span>

- <span data-ttu-id="08da0-148">传递后删除包含网络钓鱼 Url 的电子邮件</span><span class="sxs-lookup"><span data-stu-id="08da0-148">Email messages containing phish URLs are removed after delivery</span></span>

- <span data-ttu-id="08da0-149">检测到可疑的电子邮件发送模式</span><span class="sxs-lookup"><span data-stu-id="08da0-149">Suspicious email sending patterns are detected</span></span>

- <span data-ttu-id="08da0-150">限制用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="08da0-150">A user is restricted from sending email</span></span>

<span data-ttu-id="08da0-151">[了解有关通知和空气的详细信息](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。</span><span class="sxs-lookup"><span data-stu-id="08da0-151">[Learn more about alerts and AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="08da0-152">使用空中功能所需的权限</span><span class="sxs-lookup"><span data-stu-id="08da0-152">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="08da0-153">通过某些角色（如下表中所述的角色）授予权限：</span><span class="sxs-lookup"><span data-stu-id="08da0-153">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="08da0-154">任务</span><span class="sxs-lookup"><span data-stu-id="08da0-154">Task</span></span> |<span data-ttu-id="08da0-155">角色 (s) 必需</span><span class="sxs-lookup"><span data-stu-id="08da0-155">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="08da0-156">设置空中功能</span><span class="sxs-lookup"><span data-stu-id="08da0-156">To set up AIR features</span></span> |<span data-ttu-id="08da0-157">以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="08da0-157">One of the following roles:</span></span> <br/><span data-ttu-id="08da0-158">-全局管理员</span><span class="sxs-lookup"><span data-stu-id="08da0-158">- Global Administrator</span></span><br/><span data-ttu-id="08da0-159">-安全管理员</span><span class="sxs-lookup"><span data-stu-id="08da0-159">- Security Administrator</span></span> <br/><span data-ttu-id="08da0-160">可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合规性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="08da0-160">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="08da0-161">批准或拒绝建议的操作</span><span class="sxs-lookup"><span data-stu-id="08da0-161">To approve or reject recommended actions</span></span>|<span data-ttu-id="08da0-162">在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合规性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) 中分配的以下角色之一) ：</span><span class="sxs-lookup"><span data-stu-id="08da0-162">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="08da0-163">-全局管理员</span><span class="sxs-lookup"><span data-stu-id="08da0-163">- Global Administrator</span></span> <br/><span data-ttu-id="08da0-164">-安全管理员</span><span class="sxs-lookup"><span data-stu-id="08da0-164">- Security Administrator</span></span><br/><span data-ttu-id="08da0-165">-安全读者</span><span class="sxs-lookup"><span data-stu-id="08da0-165">- Security Reader</span></span> <br/><span data-ttu-id="08da0-166">--- 和 ---</span><span class="sxs-lookup"><span data-stu-id="08da0-166">--- and ---</span></span><br/><span data-ttu-id="08da0-167">-搜索和清除 (仅在 [安全 & 合规中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)中分配此角色。</span><span class="sxs-lookup"><span data-stu-id="08da0-167">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="08da0-168">您可能需要在其中创建新的角色组，并将搜索和清除角色添加到该新角色组。 ) </span><span class="sxs-lookup"><span data-stu-id="08da0-168">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

<span data-ttu-id="08da0-169">应将[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)许可证分配给：</span><span class="sxs-lookup"><span data-stu-id="08da0-169">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="08da0-170">安全管理员 (包括全局管理员) </span><span class="sxs-lookup"><span data-stu-id="08da0-170">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="08da0-171">您的组织的安全操作团队 (包括安全读者和那些具有搜索和清除角色的读者) </span><span class="sxs-lookup"><span data-stu-id="08da0-171">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="08da0-172">最终用户</span><span class="sxs-lookup"><span data-stu-id="08da0-172">End users</span></span>

<span data-ttu-id="08da0-173">此外，还必须定义和应用 [Microsoft Defender For Office 365 策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) ，以便就地保护。</span><span class="sxs-lookup"><span data-stu-id="08da0-173">In addition, [Microsoft Defender for Office 365 policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) must be defined and applied in order for protection to be in place.</span></span>

## <a name="next-steps"></a><span data-ttu-id="08da0-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="08da0-174">Next steps</span></span>

- [<span data-ttu-id="08da0-175">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="08da0-175">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="08da0-176">查看和批准挂起的操作</span><span class="sxs-lookup"><span data-stu-id="08da0-176">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="08da0-177">相关文章</span><span class="sxs-lookup"><span data-stu-id="08da0-177">Related articles</span></span>

- [<span data-ttu-id="08da0-178">Microsoft Defender for Endpoint 中的自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="08da0-178">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="08da0-179">Microsoft 365 Defender 中的自动化调查和响应</span><span class="sxs-lookup"><span data-stu-id="08da0-179">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
