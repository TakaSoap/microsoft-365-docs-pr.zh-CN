---
title: 在审核日志中使用共享审核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 管理员可以了解如何在组织中使用共享审核Microsoft 365 审核日志标识与组织外部的用户共享的资源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 302ad7665c83ee9061b2e1965ef03ec25d0aab58
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341504"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a><span data-ttu-id="28b0e-103">在审核日志中使用共享审核</span><span class="sxs-lookup"><span data-stu-id="28b0e-103">Use sharing auditing in the audit log</span></span>

<span data-ttu-id="28b0e-104">共享是 SharePoint Online 和 OneDrive for Business中的一项关键活动，在组织中广泛使用。</span><span class="sxs-lookup"><span data-stu-id="28b0e-104">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in organizations.</span></span> <span data-ttu-id="28b0e-105">管理员可以使用共享审核功能审核日志确定如何在组织中使用共享。</span><span class="sxs-lookup"><span data-stu-id="28b0e-105">Administrators can use sharing auditing in the audit log to determine how sharing is used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="28b0e-106">共享SharePoint架构</span><span class="sxs-lookup"><span data-stu-id="28b0e-106">The SharePoint Sharing schema</span></span>

<span data-ttu-id="28b0e-107">共享事件 (不包括与共享策略和共享链接) 相关的事件，主要方式与文件和文件夹相关的事件不同：一个用户正在执行对其他用户有影响的操作。</span><span class="sxs-lookup"><span data-stu-id="28b0e-107">Sharing events (not including events related to sharing policy and sharing links) are different from file- and folder-related events in one primary way: one user is performing an action that has an effect on another user.</span></span> <span data-ttu-id="28b0e-108">例如，当资源用户 A 向用户 B 授予对文件的访问权限时。</span><span class="sxs-lookup"><span data-stu-id="28b0e-108">For example, when a resource User A gives User B access to a file.</span></span> <span data-ttu-id="28b0e-109">本示例中，用户 A 是  *操作用户，*  用户 B 是  *目标用户*。</span><span class="sxs-lookup"><span data-stu-id="28b0e-109">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="28b0e-110">在SharePoint文件架构中，操作用户的操作仅影响文件本身。</span><span class="sxs-lookup"><span data-stu-id="28b0e-110">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="28b0e-111">当用户 A 打开文件时 **，FileAccessed** 事件所需的唯一信息是操作用户。</span><span class="sxs-lookup"><span data-stu-id="28b0e-111">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="28b0e-112">为了消除此差异，有一个单独的架构，称为SharePoint *共享* 架构，用于捕获有关共享事件详细信息。</span><span class="sxs-lookup"><span data-stu-id="28b0e-112">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="28b0e-113">这将确保管理员能够查看共享资源的用户和共享资源的用户。</span><span class="sxs-lookup"><span data-stu-id="28b0e-113">This ensures that administrators have visibility into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="28b0e-114">共享架构在审核记录中提供两个与共享事件相关的其他字段：</span><span class="sxs-lookup"><span data-stu-id="28b0e-114">The Sharing schema provides two additional fields in an audit record related to sharing events:</span></span> 
  
- <span data-ttu-id="28b0e-115">**TargetUserOrGroupType：** 标识目标用户或组是成员、来宾、SharePointGroup、SecurityGroup 还是合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="28b0e-115">**TargetUserOrGroupType:** Identifies whether the target user or group is a Member, Guest, SharePointGroup, SecurityGroup, or Partner.</span></span>

- <span data-ttu-id="28b0e-116">**TargetUserOrGroupName：** 存储上一示例中与用户 B (共享资源的目标用户或组的 UPN 或) 。</span><span class="sxs-lookup"><span data-stu-id="28b0e-116">**TargetUserOrGroupName:** Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 

<span data-ttu-id="28b0e-117">这两个字段以及 审核日志 架构中的其他属性（如 User、Operation 和 Date）可以完整描述哪些用户与谁共享了哪个资源以及何时 *共享*。</span><span class="sxs-lookup"><span data-stu-id="28b0e-117">These two fields, in addition to other properties from the audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="28b0e-118">还有一个对共享情景非常重要的架构属性。</span><span class="sxs-lookup"><span data-stu-id="28b0e-118">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="28b0e-119">当您导出审核日志时，导出的 CSV 文件的 **AuditData** 列将存储有关共享事件的信息。</span><span class="sxs-lookup"><span data-stu-id="28b0e-119">When you export audit log search results, the **AuditData** column in the exported CSV file stores information about sharing events.</span></span> <span data-ttu-id="28b0e-120">例如，当用户与其他用户共享网站时，通过将目标用户添加到用户组SharePoint实现。</span><span class="sxs-lookup"><span data-stu-id="28b0e-120">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="28b0e-121">**AuditData** 列捕获此信息以向管理员提供上下文。</span><span class="sxs-lookup"><span data-stu-id="28b0e-121">The **AuditData** column captures this information to provide context for administrators.</span></span> <span data-ttu-id="28b0e-122">有关如何分析 **AuditData** 列中的信息的说明，请参阅步骤 [2。](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log)</span><span class="sxs-lookup"><span data-stu-id="28b0e-122">See [Step 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) for instructions on how to parse the information in the **AuditData** column.</span></span>

## <a name="sharepoint-sharing-events"></a><span data-ttu-id="28b0e-123">SharePoint共享事件</span><span class="sxs-lookup"><span data-stu-id="28b0e-123">SharePoint sharing events</span></span>

<span data-ttu-id="28b0e-124">共享的定义如下：当 (用户希望与) 用户共享资源时 (*用户* 共享) 。</span><span class="sxs-lookup"><span data-stu-id="28b0e-124">Sharing is defined by when a user (the *acting* user) wants to share a resource with another user (the *target* user).</span></span> <span data-ttu-id="28b0e-125">与与外部用户共享资源相关的审核记录 (组织外部且在组织的 Azure Active Directory) 中没有来宾帐户的用户由以下事件标识，这些事件记录在 审核日志：</span><span class="sxs-lookup"><span data-stu-id="28b0e-125">Audit records related to sharing a resource with an external user (a user who is outside of your organization and doesn't have a guest account in your organization's Azure Active Directory) are identified by the following events, which are logged in the audit log:</span></span>

- <span data-ttu-id="28b0e-126">**SharingInvitationCreated：** 您组织的用户尝试与外部用户 (网站) 共享资源。</span><span class="sxs-lookup"><span data-stu-id="28b0e-126">**SharingInvitationCreated:** A user in your organization tried to share a resource (likely a site) with an external user.</span></span> <span data-ttu-id="28b0e-127">这导致向目标用户发送外部共享邀请。</span><span class="sxs-lookup"><span data-stu-id="28b0e-127">This results in an external sharing invitation sent to the target user.</span></span> <span data-ttu-id="28b0e-128">此时，不授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="28b0e-128">No access to the resource is granted at this point.</span></span>

- <span data-ttu-id="28b0e-129">**SharingInvitationAccepted：** 外部用户已接受操作用户发送的共享邀请，现在可以访问资源。</span><span class="sxs-lookup"><span data-stu-id="28b0e-129">**SharingInvitationAccepted:** The external user has accepted the sharing invitation sent by the acting user and now has access to the resource.</span></span>

- <span data-ttu-id="28b0e-130">**AnonymousLinkCreated：** 为资源 (匿名链接或) "任何人"链接。</span><span class="sxs-lookup"><span data-stu-id="28b0e-130">**AnonymousLinkCreated:** An anonymous link (also called an "Anyone" link) is created for a resource.</span></span> <span data-ttu-id="28b0e-131">由于可创建并复制匿名链接，因此可以合理假定任何具有匿名链接的文档已与目标用户共享。</span><span class="sxs-lookup"><span data-stu-id="28b0e-131">Because an anonymous link can be created and then copied, it's reasonable to assume that any document that has an anonymous link has been shared with a target user.</span></span>

- <span data-ttu-id="28b0e-132">**AnonymousLinkUsed：** 如名称所示，使用匿名链接访问资源时将记录此事件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-132">**AnonymousLinkUsed:** As the name implies, this event is logged when an anonymous link is used to access a resource.</span></span> 

- <span data-ttu-id="28b0e-133">**SecureLinkCreated：** 用户已创建"特定人员链接"，以与特定人员共享资源。</span><span class="sxs-lookup"><span data-stu-id="28b0e-133">**SecureLinkCreated:** A user has created a "specific people link" to share a resource with a specific person.</span></span> <span data-ttu-id="28b0e-134">此目标用户可能是组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="28b0e-134">This target user may be someone who is external to your organization.</span></span> <span data-ttu-id="28b0e-135">与资源共享的人在 **AddedToSecureLink** 事件的审核记录中标识。</span><span class="sxs-lookup"><span data-stu-id="28b0e-135">The person that the resource is shared with is identified in the audit record for the **AddedToSecureLink** event.</span></span> <span data-ttu-id="28b0e-136">这两个事件的时间戳几乎完全相同。</span><span class="sxs-lookup"><span data-stu-id="28b0e-136">The time stamps for these two events are nearly identical.</span></span>

- <span data-ttu-id="28b0e-137">**AddedToSecureLink：** 用户已添加到特定人员链接。</span><span class="sxs-lookup"><span data-stu-id="28b0e-137">**AddedToSecureLink:** A user was added to a specific people link.</span></span> <span data-ttu-id="28b0e-138">使用 **此事件中的 TargetUserOrGroupName** 字段可标识添加到相应特定人员链接的用户。</span><span class="sxs-lookup"><span data-stu-id="28b0e-138">Use the **TargetUserOrGroupName** field in this event to identify the user added to the corresponding specific people link.</span></span> <span data-ttu-id="28b0e-139">此目标用户可能是组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="28b0e-139">This target user may be someone who is external to your organization.</span></span>

## <a name="sharing-auditing-work-flow"></a><span data-ttu-id="28b0e-140">共享审核工作流程</span><span class="sxs-lookup"><span data-stu-id="28b0e-140">Sharing auditing work flow</span></span>
  
<span data-ttu-id="28b0e-141">当用户 (代理用户) 想要与其他用户共享资源 (目标用户) 、SharePoint (或 OneDrive for Business) 将首先检查目标用户的电子邮件地址是否已与组织目录中的用户帐户关联。</span><span class="sxs-lookup"><span data-stu-id="28b0e-141">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="28b0e-142">如果目标用户位于目录 (并且具有相应的来宾用户帐户) ，SharePoint执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="28b0e-142">If the target user is in the directory (and has a corresponding guest user account), SharePoint does the following things:</span></span>
  
-  <span data-ttu-id="28b0e-143">通过将目标用户添加到相应的组，立即向目标用户分配访问资源SharePoint，并记录 **AddedToGroup** 事件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-143">Immediately assigns the target user permissions to access the resource by adding the target user to the appropriate SharePoint group, and logs an **AddedToGroup** event.</span></span> 
    
- <span data-ttu-id="28b0e-144">向目标用户的电子邮件地址发送共享通知。</span><span class="sxs-lookup"><span data-stu-id="28b0e-144">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="28b0e-145">记录 **SharingSet** 事件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-145">Logs a **SharingSet** event.</span></span> <span data-ttu-id="28b0e-146">此事件在搜索工具的活动选取器中的"共享和访问请求活动"下具有友好名称"共享文件、文件夹审核日志网站"。</span><span class="sxs-lookup"><span data-stu-id="28b0e-146">This event has a friendly name of "Shared file, folder, or site" under **Sharing and access request activities** in the activities picker of the audit log search tool.</span></span> <span data-ttu-id="28b0e-147">请参阅步骤 [1 中的屏幕截图](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)。</span><span class="sxs-lookup"><span data-stu-id="28b0e-147">See the screenshot in [Step 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file).</span></span> 
    
<span data-ttu-id="28b0e-148">如果目标用户的用户帐户不在目录中，SharePoint执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="28b0e-148">If a user account for the target user isn't in the directory, SharePoint does the following:</span></span> 
    
   - <span data-ttu-id="28b0e-149">根据资源的共享方法，记录以下事件之一：</span><span class="sxs-lookup"><span data-stu-id="28b0e-149">Logs one of the following events, based on how the resource is shared:</span></span>
   
      - <span data-ttu-id="28b0e-150">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="28b0e-150">**AnonymousLinkCreated**</span></span>
   
      - <span data-ttu-id="28b0e-151">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="28b0e-151">**SecureLinkCreated**</span></span>
   
      - <span data-ttu-id="28b0e-152">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="28b0e-152">**AddedToSecureLink**</span></span> 

      - <span data-ttu-id="28b0e-153">**SharingInvitationCreated** (仅在共享资源是网站集时记录) </span><span class="sxs-lookup"><span data-stu-id="28b0e-153">**SharingInvitationCreated** (this event is logged only when the shared resource is a site)</span></span>
    
   - <span data-ttu-id="28b0e-154">当目标用户通过单击邀请) 中的链接接受发送给 (的共享邀请时，SharePoint 将记录 **SharingInvitationAccepted** 事件并分配目标用户访问资源的权限。</span><span class="sxs-lookup"><span data-stu-id="28b0e-154">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="28b0e-155">如果向目标用户发送匿名链接，则目标用户使用该链接访问资源后，将记录 **AnonymousLinkUsed** 事件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-155">If the target user is sent an anonymous link, the **AnonymousLinkUsed** event is logged after the target user uses the link to access the resource.</span></span> <span data-ttu-id="28b0e-156">对于安全链接，当外部用户使用链接访问资源时，将记录 **FileAccessed** 事件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-156">For secure links, a **FileAccessed** event is logged when an external user uses the link to access the resource.</span></span>

<span data-ttu-id="28b0e-157">还会记录有关目标用户的其他信息，例如邀请的目标用户标识以及接受邀请的用户。</span><span class="sxs-lookup"><span data-stu-id="28b0e-157">Additional information about the target user is also logged, such as the identity of the user the invitation is to and the user who accepts the invitation.</span></span> <span data-ttu-id="28b0e-158">在某些情况下，这些用户 (电子邮件地址) 可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="28b0e-158">In some case, these users (or email addresses) can be different.</span></span> 

## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="28b0e-159">如何标识与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="28b0e-159">How to identify resources shared with external users</span></span>

<span data-ttu-id="28b0e-160">管理员的一个常见要求是创建已与组织外部的用户共享的所有资源的列表。</span><span class="sxs-lookup"><span data-stu-id="28b0e-160">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="28b0e-161">通过使用共享审核Office 365，管理员可以生成此列表。</span><span class="sxs-lookup"><span data-stu-id="28b0e-161">By using sharing auditing in Office 365, administrators can generate this list.</span></span> <span data-ttu-id="28b0e-162">方法如下：</span><span class="sxs-lookup"><span data-stu-id="28b0e-162">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="28b0e-163">步骤 1：搜索共享事件，将结果导出到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="28b0e-163">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="28b0e-164">第一步是搜索审核日志共享事件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-164">The first step is to search the audit log for sharing events.</span></span> <span data-ttu-id="28b0e-165">有关 (搜索) 所需的权限审核日志，请参阅Sing the 审核日志 in the Security & [Compliance Center。](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="28b0e-165">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="28b0e-166">转到 <https://compliance.microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="28b0e-166">Go to <https://compliance.microsoft.com>.</span></span>

2. <span data-ttu-id="28b0e-167">使用工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="28b0e-167">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="28b0e-168">在任务窗格的左Microsoft 365 合规中心，单击"审核 **"。**</span><span class="sxs-lookup"><span data-stu-id="28b0e-168">In the left pane of the Microsoft 365 compliance center, click **Audit**.</span></span>

    <span data-ttu-id="28b0e-169">将显示“**审核**”页。</span><span class="sxs-lookup"><span data-stu-id="28b0e-169">The **Audit** page is displayed.</span></span>

4. <span data-ttu-id="28b0e-170">在 **"活动**" **下，单击"共享和访问请求活动** "以搜索与共享相关的事件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-170">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 

    ![在"活动"下，选择"共享和访问请求活动"](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. <span data-ttu-id="28b0e-172">选择日期和时间范围以查找该时段内发生的共享事件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-172">Select a date and time range to find the sharing events that occurred within that period.</span></span> 

6. <span data-ttu-id="28b0e-173">单击 **"** 搜索"运行搜索。</span><span class="sxs-lookup"><span data-stu-id="28b0e-173">Click **Search** to run the search.</span></span> 

7. <span data-ttu-id="28b0e-174">运行完搜索并显示结果后，单击"**导出** 结果 \> **下载所有结果"。**</span><span class="sxs-lookup"><span data-stu-id="28b0e-174">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>

    <span data-ttu-id="28b0e-175">选择导出选项后，窗口底部会显示一条消息，提示您打开或保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-175">After you select the export option, a message at the bottom of the window prompts you to open or save the CSV file.</span></span>

8. <span data-ttu-id="28b0e-176">单击 **"** \> **另存为** "，将 CSV 文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="28b0e-176">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a><span data-ttu-id="28b0e-177">步骤 2：使用 PowerQuery 编辑器格式化导出审核日志</span><span class="sxs-lookup"><span data-stu-id="28b0e-177">Step 2: Use the PowerQuery Editor to format the exported audit log</span></span>

<span data-ttu-id="28b0e-178">下一步是使用 Excel 中 Power Query Editor 中的 JSON 转换功能将 **AuditData** 列 (（由多属性 JSON 对象) 组成）的每个属性拆分为其自己的列。</span><span class="sxs-lookup"><span data-stu-id="28b0e-178">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the **AuditData** column (which consists of a multi-property JSON object) into its own column.</span></span> <span data-ttu-id="28b0e-179">这允许您筛选列以查看与共享相关的记录</span><span class="sxs-lookup"><span data-stu-id="28b0e-179">This lets you filter columns to view records related to sharing</span></span>

<span data-ttu-id="28b0e-180">有关分步说明，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的“步骤 2：使用 Power Query 编辑器转换 JSON 对象”。</span><span class="sxs-lookup"><span data-stu-id="28b0e-180">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="28b0e-181">步骤 3：筛选 CSV 文件以搜索与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="28b0e-181">Step 3: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="28b0e-182">下一步是筛选 CSV，以筛选之前在"共享事件"部分SharePoint[与共享相关的事件](#sharepoint-sharing-events)。</span><span class="sxs-lookup"><span data-stu-id="28b0e-182">The next step is to filter the CSV for the different sharing-related events that were previously described in the [SharePoint sharing events](#sharepoint-sharing-events) section.</span></span> <span data-ttu-id="28b0e-183">或者，可以筛选 **TargetUserOrGroupType** 列以显示此属性的值为 Guest 的所有 **记录**。</span><span class="sxs-lookup"><span data-stu-id="28b0e-183">Alternatively, you can filter the **TargetUserOrGroupType** column to display all records where the value of this property is **Guest**.</span></span> 

<span data-ttu-id="28b0e-184">按照上一步中的说明使用 PowerQuery 编辑器准备 CSV 文件后，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="28b0e-184">After you've followed the instructions in the previous step to prepare the CSV file by using the PowerQuery editor, do the following:</span></span>
    
1. <span data-ttu-id="28b0e-185">打开Excel 2 中创建的配置文件。</span><span class="sxs-lookup"><span data-stu-id="28b0e-185">Open the Excel file that you created in Step 2.</span></span> 

2. <span data-ttu-id="28b0e-186">在"主页 **"** 选项卡上，单击"&**筛选器"，** 然后单击"筛选器 **"。**</span><span class="sxs-lookup"><span data-stu-id="28b0e-186">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="28b0e-187">在"**操作&** 上的"排序筛选器"下拉列表中，清除所有选择，然后选择一个或多个以下与共享相关的事件，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="28b0e-187">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select one or more the following sharing-related events and then click **Ok**.</span></span>
 
   - <span data-ttu-id="28b0e-188">**SharingInvitationCreated**</span><span class="sxs-lookup"><span data-stu-id="28b0e-188">**SharingInvitationCreated**</span></span>
   
   - <span data-ttu-id="28b0e-189">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="28b0e-189">**AnonymousLinkCreated**</span></span>
   
   - <span data-ttu-id="28b0e-190">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="28b0e-190">**SecureLinkCreated**</span></span>
   
   - <span data-ttu-id="28b0e-191">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="28b0e-191">**AddedToSecureLink**</span></span> 
    
    <span data-ttu-id="28b0e-192">Excel显示所选事件的行。</span><span class="sxs-lookup"><span data-stu-id="28b0e-192">Excel displays the rows for the events you selected.</span></span>
    
4. <span data-ttu-id="28b0e-193">转到名为 **TargetUserOrGroupType 的列** 并选择它。</span><span class="sxs-lookup"><span data-stu-id="28b0e-193">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="28b0e-194">在"**排序&筛选器**"下拉列表中，清除所有选择，然后选择 **"TargetUserOrGroupType：Guest"，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="28b0e-194">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **Ok**.</span></span>
    
    <span data-ttu-id="28b0e-195">现在Excel显示共享事件的行以及目标用户位于组织外部的行，因为外部用户由 **值 TargetUserOrGroupType：Guest 标识**。</span><span class="sxs-lookup"><span data-stu-id="28b0e-195">Now Excel displays the rows for sharing events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
  
> [!TIP]
> <span data-ttu-id="28b0e-196">对于显示的审核记录 **，ObjectId** 列标识与目标用户共享的资源;例如  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` 。</span><span class="sxs-lookup"><span data-stu-id="28b0e-196">For the audit records that are displayed, the **ObjectId** column identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
