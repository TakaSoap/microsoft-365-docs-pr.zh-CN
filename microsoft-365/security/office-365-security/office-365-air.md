---
title: 在 Microsoft Defender for Office 365 中开始进行自动调查和响应
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 开始在 Microsoft Defender for Office 365 中使用自动调查和响应功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925600"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a><span data-ttu-id="eab1c-104">开始在 Microsoft Defender for Office 365 中使用自动调查和响应 (AIR) </span><span class="sxs-lookup"><span data-stu-id="eab1c-104">Get started using automated investigation and response (AIR) in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eab1c-105">[Microsoft Defender For Office 365](office-365-atp.md) 包括功能强大的自动化调查和响应 (空中) 功能，可节省安全运营团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="eab1c-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="eab1c-106">随着警报的触发，安全操作团队可以对这些警报进行检查、设置优先级和响应。</span><span class="sxs-lookup"><span data-stu-id="eab1c-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="eab1c-107">跟上传入警报的数量的持续很大。</span><span class="sxs-lookup"><span data-stu-id="eab1c-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="eab1c-108">自动执行其中一些任务可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="eab1c-108">Automating some of those tasks can help.</span></span> <span data-ttu-id="eab1c-109">借助 AIR，安全操作团队可以将精力集中在优先级较高的任务上，而不会丢失触发的重要警报。</span><span class="sxs-lookup"><span data-stu-id="eab1c-109">With AIR, your security operations team can focus on higher-priority tasks without losing sight of important alerts that are triggered.</span></span>

<span data-ttu-id="eab1c-110">本文内容：</span><span class="sxs-lookup"><span data-stu-id="eab1c-110">This article describes:</span></span>
- <span data-ttu-id="eab1c-111">[空气的整体流量](#the-overall-flow-of-air);</span><span class="sxs-lookup"><span data-stu-id="eab1c-111">The [overall flow of AIR](#the-overall-flow-of-air);</span></span>
- <span data-ttu-id="eab1c-112">[如何获取空气](#how-to-get-air);并</span><span class="sxs-lookup"><span data-stu-id="eab1c-112">[How to get AIR](#how-to-get-air); and</span></span> 
- <span data-ttu-id="eab1c-113">配置或使用 AIR 功能 [所需的权限](#required-permissions-to-use-air-capabilities) 。</span><span class="sxs-lookup"><span data-stu-id="eab1c-113">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span> 

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="eab1c-114">空气的整体流动</span><span class="sxs-lookup"><span data-stu-id="eab1c-114">The overall flow of AIR</span></span>

<span data-ttu-id="eab1c-115">触发警报，安全行动手册开始进行自动调查，这将导致发现和推荐的操作。</span><span class="sxs-lookup"><span data-stu-id="eab1c-115">An alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommended actions.</span></span> <span data-ttu-id="eab1c-116">下面是空中的整体流，具体步骤如下：</span><span class="sxs-lookup"><span data-stu-id="eab1c-116">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="eab1c-117">可通过以下方式之一启动自动调查：</span><span class="sxs-lookup"><span data-stu-id="eab1c-117">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="eab1c-118">电子邮件中的某些可疑项（如邮件、附件或 URL) ）会触发 [警报](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) (。</span><span class="sxs-lookup"><span data-stu-id="eab1c-118">An [alert](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) is triggered by something suspicious in email (such as a message, attachment, or URL).</span></span> <span data-ttu-id="eab1c-119">创建一个事件。</span><span class="sxs-lookup"><span data-stu-id="eab1c-119">An incident is created.</span></span> <span data-ttu-id="eab1c-120">根据事件的类型， [安全行动手册](automated-investigation-response-office.md#security-playbooks) 运行，并开始进行自动调查。</span><span class="sxs-lookup"><span data-stu-id="eab1c-120">Depending on the type of incident, a [security playbook](automated-investigation-response-office.md#security-playbooks) runs, and an automated investigation begins.</span></span> 

     <span data-ttu-id="eab1c-121">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="eab1c-121">--- or ---</span></span>
   
   - <span data-ttu-id="eab1c-122">安全分析员在使用[威胁资源管理器](threat-explorer.md)时[开始进行自动调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="eab1c-122">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="eab1c-123">在自动调查运行过程中，它将收集有关与该电子邮件相关的相关电子邮件和实体的其他数据。</span><span class="sxs-lookup"><span data-stu-id="eab1c-123">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="eab1c-124">此类实体可以包括文件、Url 和收件人。</span><span class="sxs-lookup"><span data-stu-id="eab1c-124">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="eab1c-125">调查的范围可以随着新的和相关的警报的触发而增加。</span><span class="sxs-lookup"><span data-stu-id="eab1c-125">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="eab1c-126">在自动调查期间和之后，可以查看 [详细信息和结果](air-view-investigation-results.md) 。</span><span class="sxs-lookup"><span data-stu-id="eab1c-126">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="eab1c-127">结果包括 [建议的操作](air-remediation-actions.md) ，可采取这些操作来响应和修正发现的任何威胁。</span><span class="sxs-lookup"><span data-stu-id="eab1c-127">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond to and remediate any threats that were found.</span></span> <span data-ttu-id="eab1c-128">此外，还可以使用 [行动手册日志](air-view-investigation-results.md#playbook-log) 来跟踪所有调查活动。</span><span class="sxs-lookup"><span data-stu-id="eab1c-128">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>


4. <span data-ttu-id="eab1c-129">您的安全操作团队将检查 [调查结果和建议](air-view-investigation-results.md)，并 [批准或拒绝修正操作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="eab1c-129">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span> 

5. <span data-ttu-id="eab1c-130">由于已批准挂起的修正操作 (或拒绝) ，因此自动调查完成。</span><span class="sxs-lookup"><span data-stu-id="eab1c-130">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eab1c-131">在 Microsoft Defender for Office 365 中，不会自动执行任何修正操作。</span><span class="sxs-lookup"><span data-stu-id="eab1c-131">In Microsoft Defender for Office 365, no remediation actions are taken automatically.</span></span> <span data-ttu-id="eab1c-132">只有在组织的安全团队批准后，才会执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="eab1c-132">Remediation actions are taken only upon approval by your organization's security team.</span></span> <span data-ttu-id="eab1c-133">但是，空中功能通过确定纠正措施并提供做出明智决策所需的详细信息来节省安全运营团队的时间。</span><span class="sxs-lookup"><span data-stu-id="eab1c-133">However, AIR capabilities save your security operations team time by identifying remediation actions and providing the details needed to make an informed decision.</span></span>

<span data-ttu-id="eab1c-134">在每次自动调查期间和之后，安全操作团队可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eab1c-134">During and after each automated investigation, your security operations team can:</span></span>

- [<span data-ttu-id="eab1c-135">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="eab1c-135">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="eab1c-136">查看调查的结果详细信息</span><span class="sxs-lookup"><span data-stu-id="eab1c-136">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="eab1c-137">查看和批准作为调查结果的操作</span><span class="sxs-lookup"><span data-stu-id="eab1c-137">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="eab1c-138">有关更详细的概述，请参阅 [AIR 的工作原理](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)。</span><span class="sxs-lookup"><span data-stu-id="eab1c-138">For a more detailed overview, see [How AIR works](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="eab1c-139">如何获取空中</span><span class="sxs-lookup"><span data-stu-id="eab1c-139">How to get AIR</span></span>

<span data-ttu-id="eab1c-140">在 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)中包含空中功能，前提是你的策略和警报已配置。</span><span class="sxs-lookup"><span data-stu-id="eab1c-140">AIR capabilities are included in [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), provided your policies and alerts are configured.</span></span> <span data-ttu-id="eab1c-141">如果您想了解这方面的一些帮助，请按照 [针对威胁进行保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) 以设置或配置以下保护设置的指导：</span><span class="sxs-lookup"><span data-stu-id="eab1c-141">If you would like some help with this, follow the guidance in [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) to set up or configure the following protection settings:</span></span> 

1. <span data-ttu-id="eab1c-142">应启用[审核日志记录](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) () </span><span class="sxs-lookup"><span data-stu-id="eab1c-142">[Audit logging](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (should be turned on)</span></span>

2. [<span data-ttu-id="eab1c-143">反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="eab1c-143">Antimalware policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [<span data-ttu-id="eab1c-144">Antiphishing 保护</span><span class="sxs-lookup"><span data-stu-id="eab1c-144">Antiphishing protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. <span data-ttu-id="eab1c-145">[反垃圾邮件保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection)。</span><span class="sxs-lookup"><span data-stu-id="eab1c-145">[Antispam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).</span></span>
   
5. <span data-ttu-id="eab1c-146">[安全链接和安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="eab1c-146">[Safe Links and Safe Attachments](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).</span></span>
   
6. <span data-ttu-id="eab1c-147">[SharePoint、OneDrive 和 Microsoft 团队的安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)。</span><span class="sxs-lookup"><span data-stu-id="eab1c-147">[Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).</span></span>
   
7. <span data-ttu-id="eab1c-148">[电子邮件的零小时自动清除](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop)。</span><span class="sxs-lookup"><span data-stu-id="eab1c-148">[Zero-hour auto purge for email](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).</span></span>

<span data-ttu-id="eab1c-149">此外，请务必 [查看组织的通知策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)，尤其是 " [威胁管理" 类别中的默认策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="eab1c-149">In addition, make sure to [review your organization's alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), especially the [default policies in the Threat management category](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies).</span></span> 

## <a name="which-alert-policies-trigger-automated-investigations"></a><span data-ttu-id="eab1c-150">哪些警报策略会触发自动调查？</span><span class="sxs-lookup"><span data-stu-id="eab1c-150">Which alert policies trigger automated investigations?</span></span>

<span data-ttu-id="eab1c-151">Microsoft 365 提供了许多内置的警报策略，可帮助确定 Exchange 管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。</span><span class="sxs-lookup"><span data-stu-id="eab1c-151">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="eab1c-152">有几个 [默认的警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="eab1c-152">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="eab1c-153">其中包括以下项：</span><span class="sxs-lookup"><span data-stu-id="eab1c-153">These include the following:</span></span>

- <span data-ttu-id="eab1c-154">检测到潜在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="eab1c-154">A potentially malicious URL click is detected</span></span>
- <span data-ttu-id="eab1c-155">用户将电子邮件报告为网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="eab1c-155">An email message is reported by a user as phish</span></span>
- <span data-ttu-id="eab1c-156">传递后删除包含恶意软件的电子邮件</span><span class="sxs-lookup"><span data-stu-id="eab1c-156">Email messages containing malware are removed after delivery</span></span>
- <span data-ttu-id="eab1c-157">传递后删除包含网络钓鱼 Url 的电子邮件</span><span class="sxs-lookup"><span data-stu-id="eab1c-157">Email messages containing phish URLs are removed after delivery</span></span>
- <span data-ttu-id="eab1c-158">检测到可疑的电子邮件发送模式</span><span class="sxs-lookup"><span data-stu-id="eab1c-158">Suspicious email sending patterns are detected</span></span>
- <span data-ttu-id="eab1c-159">限制用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="eab1c-159">A user is restricted from sending email</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="eab1c-160">使用空中功能所需的权限</span><span class="sxs-lookup"><span data-stu-id="eab1c-160">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="eab1c-161">通过某些角色（如下表中所述的角色）授予权限：</span><span class="sxs-lookup"><span data-stu-id="eab1c-161">Permissions are granted through certain roles, such as those that are described in the following table:</span></span> 

|<span data-ttu-id="eab1c-162">任务</span><span class="sxs-lookup"><span data-stu-id="eab1c-162">Task</span></span> |<span data-ttu-id="eab1c-163">角色 (s) 必需</span><span class="sxs-lookup"><span data-stu-id="eab1c-163">Role(s) required</span></span> |
|--|--|
|<span data-ttu-id="eab1c-164">设置空中功能</span><span class="sxs-lookup"><span data-stu-id="eab1c-164">To set up AIR features</span></span> |<span data-ttu-id="eab1c-165">以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="eab1c-165">One of the following roles:</span></span> <br/><span data-ttu-id="eab1c-166">-全局管理员</span><span class="sxs-lookup"><span data-stu-id="eab1c-166">- Global Administrator</span></span><br/><span data-ttu-id="eab1c-167">-安全管理员</span><span class="sxs-lookup"><span data-stu-id="eab1c-167">- Security Administrator</span></span> <br/><span data-ttu-id="eab1c-168">可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合规性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)中分配这些角色。</span><span class="sxs-lookup"><span data-stu-id="eab1c-168">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> |
|<span data-ttu-id="eab1c-169">批准或拒绝建议的操作</span><span class="sxs-lookup"><span data-stu-id="eab1c-169">To approve or reject recommended actions</span></span>|<span data-ttu-id="eab1c-170">在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或 [Security & 合规性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) 中分配的以下角色之一) ：</span><span class="sxs-lookup"><span data-stu-id="eab1c-170">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):</span></span><br/><span data-ttu-id="eab1c-171">-全局管理员</span><span class="sxs-lookup"><span data-stu-id="eab1c-171">- Global Administrator</span></span> <br/><span data-ttu-id="eab1c-172">-安全管理员</span><span class="sxs-lookup"><span data-stu-id="eab1c-172">- Security Administrator</span></span><br/><span data-ttu-id="eab1c-173">-安全读者</span><span class="sxs-lookup"><span data-stu-id="eab1c-173">- Security Reader</span></span> <br/><span data-ttu-id="eab1c-174">--- 和 ---</span><span class="sxs-lookup"><span data-stu-id="eab1c-174">--- and ---</span></span><br/><span data-ttu-id="eab1c-175">-搜索和清除 (仅在 [安全 & 合规中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)中分配此角色。</span><span class="sxs-lookup"><span data-stu-id="eab1c-175">- Search and Purge (this role is assigned only in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span> <span data-ttu-id="eab1c-176">您可能需要在其中创建新的角色组，并将搜索和清除角色添加到该新角色组。 ) </span><span class="sxs-lookup"><span data-stu-id="eab1c-176">You might have to create a new role group there and add the Search and Purge role to that new role group.)</span></span>

## <a name="required-licenses"></a><span data-ttu-id="eab1c-177">必需的许可证</span><span class="sxs-lookup"><span data-stu-id="eab1c-177">Required licenses</span></span>

<span data-ttu-id="eab1c-178">应将[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)许可证分配给：</span><span class="sxs-lookup"><span data-stu-id="eab1c-178">[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenses should be assigned to:</span></span>
- <span data-ttu-id="eab1c-179">安全管理员 (包括全局管理员) </span><span class="sxs-lookup"><span data-stu-id="eab1c-179">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="eab1c-180">您的组织的安全操作团队 (包括安全读者和那些具有搜索和清除角色的读者) </span><span class="sxs-lookup"><span data-stu-id="eab1c-180">Your organization's security operations team (including security readers and those with the Search and Purge role)</span></span>
- <span data-ttu-id="eab1c-181">最终用户</span><span class="sxs-lookup"><span data-stu-id="eab1c-181">End users</span></span>


## <a name="next-steps"></a><span data-ttu-id="eab1c-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eab1c-182">Next steps</span></span>

- [<span data-ttu-id="eab1c-183">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="eab1c-183">See details and results of an automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [<span data-ttu-id="eab1c-184">查看和批准挂起的操作</span><span class="sxs-lookup"><span data-stu-id="eab1c-184">Review and approve pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a><span data-ttu-id="eab1c-185">相关文章</span><span class="sxs-lookup"><span data-stu-id="eab1c-185">Related articles</span></span>

- [<span data-ttu-id="eab1c-186">Microsoft Defender for Endpoint 中的自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="eab1c-186">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="eab1c-187">Microsoft 365 Defender 中的自动化调查和响应</span><span class="sxs-lookup"><span data-stu-id="eab1c-187">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
