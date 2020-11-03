---
title: 转到操作中心以查看并批准自动调查和修正任务
description: 使用操作中心查看有关自动调查的详细信息并批准挂起的操作
keywords: 操作中心, 威胁防护, 调查, 警报, 挂起, 自动, 检测
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 3ec17204903f3e83f3fbfd126d57d0b9ca5d56f7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843788"
---
# <a name="the-action-center"></a><span data-ttu-id="bfd64-104">操作中心</span><span class="sxs-lookup"><span data-stu-id="bfd64-104">The Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bfd64-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bfd64-105">**Applies to:**</span></span>
- <span data-ttu-id="bfd64-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfd64-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bfd64-107">使用操作中心查看组织设备和邮箱中的当前和过去调查的结果。</span><span class="sxs-lookup"><span data-stu-id="bfd64-107">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="bfd64-108">根据威胁的类型和得到的结论，将自动执行 [更正操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) ，或在组织的安全操作团队批准时执行。</span><span class="sxs-lookup"><span data-stu-id="bfd64-108">Depending on the type of threat and resulting verdict, [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="bfd64-109">所有修正操作（无论是待批准还是已批准的操作）都合并在操作中心内。</span><span class="sxs-lookup"><span data-stu-id="bfd64-109">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

![操作中心](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="bfd64-111">“单窗格”体验</span><span class="sxs-lookup"><span data-stu-id="bfd64-111">A "single pane of glass" experience</span></span>

<span data-ttu-id="bfd64-112">操作中心提供任务的“单窗格”体验，例如：</span><span class="sxs-lookup"><span data-stu-id="bfd64-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="bfd64-113">批准挂起的修正操作；</span><span class="sxs-lookup"><span data-stu-id="bfd64-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="bfd64-114">查看已批准的修正操作的审核日志；以及</span><span class="sxs-lookup"><span data-stu-id="bfd64-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="bfd64-115">查看已完成的修正操作。</span><span class="sxs-lookup"><span data-stu-id="bfd64-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="bfd64-116">您的安全操作团队可以更有效地运营，因为操作中心提供了 Microsoft 365 Defender 在工作中的全面视图。</span><span class="sxs-lookup"><span data-stu-id="bfd64-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft 365 Defender at work.</span></span>

## <a name="go-to-the-action-center"></a><span data-ttu-id="bfd64-117">转到操作中心</span><span class="sxs-lookup"><span data-stu-id="bfd64-117">Go to the Action center</span></span>

1. <span data-ttu-id="bfd64-118">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="bfd64-118">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="bfd64-119">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="bfd64-119">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="bfd64-120">在操作中心中，您将看到两个选项卡： **挂起** 和 **历史记录** 。</span><span class="sxs-lookup"><span data-stu-id="bfd64-120">In the Action center, you'll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="bfd64-121">“ **挂起** ”选项卡列出了需要由安全运营团队中的人员进行审查和批准才能继续的调查。</span><span class="sxs-lookup"><span data-stu-id="bfd64-121">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="bfd64-122">确保对此处看到的挂起项目进行审查并采取操作。</span><span class="sxs-lookup"><span data-stu-id="bfd64-122">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="bfd64-123">“ **历史记录** ”选项卡列出了自动执行的过去调查和修正操作。</span><span class="sxs-lookup"><span data-stu-id="bfd64-123">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="bfd64-124">可查看过去一天、一周、一个月或六个月的数据。</span><span class="sxs-lookup"><span data-stu-id="bfd64-124">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="bfd64-125">若要仅显示想要查看的列，请选择“ **自定义列** ”。</span><span class="sxs-lookup"><span data-stu-id="bfd64-125">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="bfd64-126">![Microsoft 365 Defender 中的操作中心](../../media/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="bfd64-126">![Action Center in Microsoft 365 Defender](../../media/mtp-action-center.png)</span></span>

5. <span data-ttu-id="bfd64-127">在列表中选择一个项目以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="bfd64-127">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="bfd64-128">此时将打开调查详细信息视图。</span><span class="sxs-lookup"><span data-stu-id="bfd64-128">The investigation details view opens.</span></span><br/>![调查详细信息](../../media/mtp-air-investdetails.png)

    - <span data-ttu-id="bfd64-130">如果调查与电子邮件内容有关 (例如，实体是邮箱) ，请在安全 & 合规性中心中打开调查详细信息 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) 。</span><span class="sxs-lookup"><span data-stu-id="bfd64-130">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="bfd64-131">如果调查涉及设备，则将在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 中打开调查详细信息。</span><span class="sxs-lookup"><span data-stu-id="bfd64-131">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

> [!TIP]
> <span data-ttu-id="bfd64-132">如果你认为在 Microsoft 365 Defender 中，自动调查和响应功能中缺少或错误地检测到了某些内容，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="bfd64-132">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="bfd64-133">请参阅 [如何在自动调查和响应中报告误报/负面 (在 Microsoft 365 Defender 中的空中) 功能](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="bfd64-133">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="available-actions"></a><span data-ttu-id="bfd64-134">可用操作</span><span class="sxs-lookup"><span data-stu-id="bfd64-134">Available actions</span></span>

<span data-ttu-id="bfd64-135">在采取补救措施时，它们将在操作中心的 "历史记录" 选项卡上列出。</span><span class="sxs-lookup"><span data-stu-id="bfd64-135">As remediation actions are taken, they're listed on the History tab in the Action center.</span></span> <span data-ttu-id="bfd64-136">此类操作包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="bfd64-136">Such actions include the following:</span></span>

- <span data-ttu-id="bfd64-137">收集调查包</span><span class="sxs-lookup"><span data-stu-id="bfd64-137">Collect investigation package</span></span> 
- <span data-ttu-id="bfd64-138">隔离设备 (可以撤消此操作) </span><span class="sxs-lookup"><span data-stu-id="bfd64-138">Isolate device (this action can be undone)</span></span> 
- <span data-ttu-id="bfd64-139">分离计算机</span><span class="sxs-lookup"><span data-stu-id="bfd64-139">Offboard machine</span></span> 
- <span data-ttu-id="bfd64-140">释放代码执行</span><span class="sxs-lookup"><span data-stu-id="bfd64-140">Release code execution</span></span> 
- <span data-ttu-id="bfd64-141">从隔离区发布</span><span class="sxs-lookup"><span data-stu-id="bfd64-141">Release from quarantine</span></span> 
- <span data-ttu-id="bfd64-142">请求示例</span><span class="sxs-lookup"><span data-stu-id="bfd64-142">Request sample</span></span> 
- <span data-ttu-id="bfd64-143">限制代码执行 (可以撤消此操作) </span><span class="sxs-lookup"><span data-stu-id="bfd64-143">Restrict code execution (this action can be undone)</span></span> 
- <span data-ttu-id="bfd64-144">运行防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="bfd64-144">Run antivirus scan</span></span> 
- <span data-ttu-id="bfd64-145">停止和隔离</span><span class="sxs-lookup"><span data-stu-id="bfd64-145">Stop and quarantine</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="bfd64-146">操作中心任务所需的权限</span><span class="sxs-lookup"><span data-stu-id="bfd64-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="bfd64-147">若要批准或拒绝操作中心中挂起的操作，必须按下表所列的方式分配权限：</span><span class="sxs-lookup"><span data-stu-id="bfd64-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="bfd64-148">修正操作</span><span class="sxs-lookup"><span data-stu-id="bfd64-148">Remediation action</span></span> |<span data-ttu-id="bfd64-149">所需角色和权限</span><span class="sxs-lookup"><span data-stu-id="bfd64-149">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="bfd64-150">Microsoft Defender for Endpoint 补救 (设备) </span><span class="sxs-lookup"><span data-stu-id="bfd64-150">Microsoft Defender for Endpoint remediation (devices)</span></span> |<span data-ttu-id="bfd64-151">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="bfd64-151">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="bfd64-152">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="bfd64-152">--- or ---</span></span><br/><span data-ttu-id="bfd64-153">在 Microsoft Defender for Endpoint 中分配的活动修正操作角色</span><span class="sxs-lookup"><span data-stu-id="bfd64-153">Active remediation actions role assigned in Microsoft Defender for Endpoint</span></span> <br/> <br/> <span data-ttu-id="bfd64-154">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="bfd64-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="bfd64-155">- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="bfd64-155">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="bfd64-156">- [为基于角色的访问控制创建和管理角色 (Microsoft Defender for Endpoint) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="bfd64-156">- [Create and manage roles for role-based access control (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="bfd64-157">Microsoft Defender for Office 365 更新 (Office 内容和电子邮件) </span><span class="sxs-lookup"><span data-stu-id="bfd64-157">Microsoft Defender for Office 365 remediation (Office content and email)</span></span>  |<span data-ttu-id="bfd64-158">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="bfd64-158">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="bfd64-159">--- 和 ---</span><span class="sxs-lookup"><span data-stu-id="bfd64-159">--- and ---</span></span> <br/><span data-ttu-id="bfd64-160">搜索和清除为安全 & 合规性中心 () 分配的角色 [https://protection.office.com](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="bfd64-160">Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="bfd64-161">**重要说明** ：如果您仅在安全 & 合规中心中分配安全管理员角色，您将无法访问操作中心或 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="bfd64-161">**IMPORTANT** : If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="bfd64-162">必须在 Azure Active Directory 或 Microsoft 365 管理中心中分配安全管理员角色。</span><span class="sxs-lookup"><span data-stu-id="bfd64-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="bfd64-163">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="bfd64-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="bfd64-164">- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="bfd64-164">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="bfd64-165">- [安全 & 合规中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="bfd64-165">- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="bfd64-166">在 Azure Active Directory 中分配了全局管理员角色的用户可以批准或拒绝操作中心中挂起的任何操作。</span><span class="sxs-lookup"><span data-stu-id="bfd64-166">Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="bfd64-167">但是，作为最佳做法，你的组织应该限制分配全局管理员角色的人数。</span><span class="sxs-lookup"><span data-stu-id="bfd64-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="bfd64-168">对于操作中心权限，我们建议使用上面列出的安全管理员、主动修正操作以及搜索和清除角色。</span><span class="sxs-lookup"><span data-stu-id="bfd64-168">We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bfd64-169">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bfd64-169">Next steps</span></span> 

- [<span data-ttu-id="bfd64-170">在自动调查后批准或拒绝待处理的操作</span><span class="sxs-lookup"><span data-stu-id="bfd64-170">Approve or reject pending actions following an automated investigation</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="bfd64-171">查看自动调查的结果</span><span class="sxs-lookup"><span data-stu-id="bfd64-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)

