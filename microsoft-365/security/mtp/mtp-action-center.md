---
title: 转到操作中心以查看并批准自动调查和修正任务
description: 使用操作中心查看有关自动调查的详细信息并批准挂起的操作
keywords: 操作中心, 威胁防护, 调查, 警报, 挂起, 自动, 检测
search.appverid: met150
ms.prod: M365-security-compliance
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: a0b86240e09838ff290bb9c3b4b53f5cce3e2995
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600119"
---
# <a name="go-to-the-action-center-to-view-remediation-actions"></a><span data-ttu-id="6c28e-104">转到操作中心以查看修正操作</span><span class="sxs-lookup"><span data-stu-id="6c28e-104">Go to the Action center to view remediation actions</span></span>

<span data-ttu-id="6c28e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6c28e-105">**Applies to:**</span></span>
- <span data-ttu-id="6c28e-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6c28e-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="6c28e-107">“单窗格”体验</span><span class="sxs-lookup"><span data-stu-id="6c28e-107">A "single pane of glass" experience</span></span>

![操作中心](../images/air-actioncenter.png)

<span data-ttu-id="6c28e-109">使用操作中心查看组织设备和邮箱中的当前和过去调查的结果。</span><span class="sxs-lookup"><span data-stu-id="6c28e-109">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="6c28e-110">根据威胁的类型和[最终结论](mtp-autoir-results.md#remediation-actions-following-automated-investigation)，自动执行修正操作，或者在组织的安全运营团队批准后执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="6c28e-110">Depending on the type of threat and [resulting verdict](mtp-autoir-results.md#remediation-actions-following-automated-investigation), remediation actions occur automatically or upon approval by your organization’s security operations team.</span></span> <span data-ttu-id="6c28e-111">所有修正操作（无论是待批准还是已批准的操作）都合并在操作中心内。</span><span class="sxs-lookup"><span data-stu-id="6c28e-111">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

<span data-ttu-id="6c28e-112">操作中心提供任务的“单窗格”体验，例如：</span><span class="sxs-lookup"><span data-stu-id="6c28e-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="6c28e-113">批准挂起的修正操作；</span><span class="sxs-lookup"><span data-stu-id="6c28e-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="6c28e-114">查看已批准的修正操作的审核日志；以及</span><span class="sxs-lookup"><span data-stu-id="6c28e-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="6c28e-115">查看已完成的修正操作。</span><span class="sxs-lookup"><span data-stu-id="6c28e-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="6c28e-116">你的安全运营团队可以更有效地进行运营，因为操作中心提供了工作中的 Microsoft 威胁防护的全面视图。</span><span class="sxs-lookup"><span data-stu-id="6c28e-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft Threat Protection at work.</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="6c28e-117">修正操作</span><span class="sxs-lookup"><span data-stu-id="6c28e-117">Remediation actions</span></span>

<span data-ttu-id="6c28e-118">下表列出了操作中心当前支持的修正操作：</span><span class="sxs-lookup"><span data-stu-id="6c28e-118">The following table lists remediation actions that are currently supported in the Action center:</span></span> 

|<span data-ttu-id="6c28e-119">终结点修正操作</span><span class="sxs-lookup"><span data-stu-id="6c28e-119">Endpoints remediation actions</span></span>  |<span data-ttu-id="6c28e-120">电子邮件修正操作</span><span class="sxs-lookup"><span data-stu-id="6c28e-120">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="6c28e-121">隔离</span><span class="sxs-lookup"><span data-stu-id="6c28e-121">Quarantine file</span></span><br/><span data-ttu-id="6c28e-122">删除注册表项</span><span class="sxs-lookup"><span data-stu-id="6c28e-122">Remove registry key</span></span><br/><span data-ttu-id="6c28e-123">终止进程</span><span class="sxs-lookup"><span data-stu-id="6c28e-123">Kill process</span></span> <br/><span data-ttu-id="6c28e-124">停止服务</span><span class="sxs-lookup"><span data-stu-id="6c28e-124">Stop service</span></span> <br/><span data-ttu-id="6c28e-125">删除注册表项</span><span class="sxs-lookup"><span data-stu-id="6c28e-125">Remove registry key</span></span> <br/><span data-ttu-id="6c28e-126">禁用驱动程序</span><span class="sxs-lookup"><span data-stu-id="6c28e-126">Disable driver</span></span> <br/><span data-ttu-id="6c28e-127">删除计划任务</span><span class="sxs-lookup"><span data-stu-id="6c28e-127">Remove scheduled task</span></span>      |<span data-ttu-id="6c28e-128">软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="6c28e-128">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="6c28e-129">阻止 URL（单击时）</span><span class="sxs-lookup"><span data-stu-id="6c28e-129">Block URL (time-of-click)</span></span><br/><span data-ttu-id="6c28e-130">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="6c28e-130">Turn off external mail forwarding</span></span>          |

## <a name="go-to-the-action-center"></a><span data-ttu-id="6c28e-131">转到操作中心</span><span class="sxs-lookup"><span data-stu-id="6c28e-131">Go to the Action center</span></span>

1. <span data-ttu-id="6c28e-132">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="6c28e-132">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="6c28e-133">在导航窗格中，选择“**操作中心**”。</span><span class="sxs-lookup"><span data-stu-id="6c28e-133">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="6c28e-134">在操作中心，你将看到两个选项卡：“**挂起**”和 **“历史记录**”。</span><span class="sxs-lookup"><span data-stu-id="6c28e-134">In the Action center, you’ll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="6c28e-135">“**挂起**”选项卡列出了需要由安全运营团队中的人员进行审查和批准才能继续的调查。</span><span class="sxs-lookup"><span data-stu-id="6c28e-135">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="6c28e-136">确保对此处看到的挂起项目进行审查并采取操作。</span><span class="sxs-lookup"><span data-stu-id="6c28e-136">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="6c28e-137">“**历史记录**”选项卡列出了自动执行的过去调查和修正操作。</span><span class="sxs-lookup"><span data-stu-id="6c28e-137">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="6c28e-138">可查看过去一天、一周、一个月或六个月的数据。</span><span class="sxs-lookup"><span data-stu-id="6c28e-138">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="6c28e-139">若要仅显示想要查看的列，请选择“**自定义列**”。</span><span class="sxs-lookup"><span data-stu-id="6c28e-139">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="6c28e-140">![Microsoft 威胁防护中的操作中心](../images/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="6c28e-140">![Action Center in Microsoft Threat Protection](../images/mtp-action-center.png)</span></span>

5. <span data-ttu-id="6c28e-141">在列表中选择一个项目以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c28e-141">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="6c28e-142">此时将打开调查详细信息视图。</span><span class="sxs-lookup"><span data-stu-id="6c28e-142">The investigation details view opens.</span></span><br/>![调查详细信息](../images/mtp-air-investdetails.png)

    - <span data-ttu-id="6c28e-144">如果调查与电子邮件内容有关（例如，实体是邮箱），则将在 Office 365 安全与合规中心 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)) 中打开调查详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c28e-144">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Office 365 Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="6c28e-145">如果调查涉及设备，则将在安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 中打开调查详细信息。</span><span class="sxs-lookup"><span data-stu-id="6c28e-145">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 


> [!TIP]
> <span data-ttu-id="6c28e-146">如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="6c28e-146">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="6c28e-147">请参阅[如何在 Microsoft 威胁防护中报告误报/负面的自动调查和响应（空中）功能](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="6c28e-147">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="6c28e-148">操作中心任务所需的权限</span><span class="sxs-lookup"><span data-stu-id="6c28e-148">Required permissions for Action center tasks</span></span>

<span data-ttu-id="6c28e-149">若要批准或拒绝操作中心中挂起的操作，必须按下表所列的方式分配权限：</span><span class="sxs-lookup"><span data-stu-id="6c28e-149">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="6c28e-150">修正操作</span><span class="sxs-lookup"><span data-stu-id="6c28e-150">Remediation action</span></span> |<span data-ttu-id="6c28e-151">所需角色和权限</span><span class="sxs-lookup"><span data-stu-id="6c28e-151">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="6c28e-152">Microsoft Defender ATP 修正（设备）</span><span class="sxs-lookup"><span data-stu-id="6c28e-152">Microsoft Defender ATP remediation (devices)</span></span> |<span data-ttu-id="6c28e-153">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的**安全管理员**角色</span><span class="sxs-lookup"><span data-stu-id="6c28e-153">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="6c28e-154">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="6c28e-154">--- or ---</span></span><br/><span data-ttu-id="6c28e-155">在 Microsoft Defender ATP 中分配的**主动修正操作**角色</span><span class="sxs-lookup"><span data-stu-id="6c28e-155">**Active remediation actions** role assigned in Microsoft Defender ATP</span></span> <br/> <br/> <span data-ttu-id="6c28e-156">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="6c28e-156">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="6c28e-157">- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="6c28e-157">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="6c28e-158">- [为基于角色的访问控制创建和管理角色 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="6c28e-158">- [Create and manage roles for role-based access control (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="6c28e-159">Office 365 ATP 修正（Office 内容和电子邮件）</span><span class="sxs-lookup"><span data-stu-id="6c28e-159">Office 365 ATP remediation (Office content and email)</span></span>  |<span data-ttu-id="6c28e-160">在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中分配的**安全管理员**角色</span><span class="sxs-lookup"><span data-stu-id="6c28e-160">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="6c28e-161">--- 和 ---</span><span class="sxs-lookup"><span data-stu-id="6c28e-161">--- and ---</span></span> <br/><span data-ttu-id="6c28e-162">在 Office 365 安全与合规中心 ([https://protection.office.com](https://protection.office.com)) 中分配的**搜索和清除**角色</span><span class="sxs-lookup"><span data-stu-id="6c28e-162">**Search and Purge** role assigned the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="6c28e-163">**重要提示**：如果仅在 Office 365 安全与合规中心中分配了安全管理员角色，则将无法访问操作中心或 Microsoft 威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="6c28e-163">**IMPORTANT**: If you have the Security Administrator role assigned only in the Office 365 Security & Compliance Center, you will not be able to access the Action center or Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="6c28e-164">必须在 Azure Active Directory 或 Microsoft 365 管理中心中分配安全管理员角色。</span><span class="sxs-lookup"><span data-stu-id="6c28e-164">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="6c28e-165">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="6c28e-165">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="6c28e-166">- [Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="6c28e-166">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="6c28e-167">- [Office 365 安全与合规中心的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="6c28e-167">- [Permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="6c28e-168">在 Azure Active Directory 中分配了**全局管理员**角色的用户可以批准或拒绝操作中心中挂起的任何操作。</span><span class="sxs-lookup"><span data-stu-id="6c28e-168">Users who have the **Global Administrator** role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="6c28e-169">但是，作为最佳做法，你的组织应该限制分配全局管理员角色的人数。</span><span class="sxs-lookup"><span data-stu-id="6c28e-169">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="6c28e-170">对于操作中心权限，我们建议使用上面列出的**安全管理员**、**主动修正操作**以及**搜索和清除**角色。</span><span class="sxs-lookup"><span data-stu-id="6c28e-170">We recommend using the **Security Administrator**, **Active remediation actions**, and **Search and Purge** roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c28e-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6c28e-171">Next steps</span></span> 

- [<span data-ttu-id="6c28e-172">深入了解 Microsoft 威胁防护中的事件</span><span class="sxs-lookup"><span data-stu-id="6c28e-172">Learn more about incidents in Microsoft Threat Protection</span></span>](incidents-overview.md)
- [<span data-ttu-id="6c28e-173">查看自动调查的结果</span><span class="sxs-lookup"><span data-stu-id="6c28e-173">View the results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="6c28e-174">了解 Microsoft 威胁防护中的搜寻</span><span class="sxs-lookup"><span data-stu-id="6c28e-174">Learn about hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)

