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
description: 管理员可以了解如何在 Microsoft 365 审核日志中使用共享审核，以确定与组织外部的用户共享的资源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d26a8022f8d59aeb56a03c50ae546777c882ef7a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819292"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a><span data-ttu-id="c3ab6-103">在审核日志中使用共享审核</span><span class="sxs-lookup"><span data-stu-id="c3ab6-103">Use sharing auditing in the audit log</span></span>

<span data-ttu-id="c3ab6-104">共享是 SharePoint Online 和 OneDrive for business 中的关键活动，并在组织中广泛使用。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-104">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in organizations.</span></span> <span data-ttu-id="c3ab6-105">管理员可以使用审核日志中的共享审核来确定如何在组织中使用共享。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-105">Administrators can use sharing auditing in the audit log to determine how sharing is used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="c3ab6-106">SharePoint 共享架构</span><span class="sxs-lookup"><span data-stu-id="c3ab6-106">The SharePoint Sharing schema</span></span>

<span data-ttu-id="c3ab6-107">共享事件（不包括与共享策略和共享链接相关的事件）与文件和文件夹相关的事件有一个主要方式不同：一个用户执行的操作对另一个用户有影响。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-107">Sharing events (not including events related to sharing policy and sharing links) are different from file- and folder-related events in one primary way: one user is performing an action that has an effect on another user.</span></span> <span data-ttu-id="c3ab6-108">例如，当资源用户 A 向用户 B 授予对文件的访问权限时。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-108">For example, when a resource User A gives User B access to a file.</span></span> <span data-ttu-id="c3ab6-109">在此示例中，用户 A 是*作用用户*，而用户 B 是*目标用户*。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-109">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="c3ab6-110">在 SharePoint 文件架构中，作用用户的操作仅影响文件本身。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-110">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="c3ab6-111">当用户 A 打开文件时， **FileAccessed**事件中所需的唯一信息是操作用户。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-111">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="c3ab6-112">为了解决这种差异，有一个称为*SharePoint 共享架构*的单独架构，可捕获有关共享事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-112">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="c3ab6-113">这可确保管理员可以查看共享资源的人员以及共享资源的用户。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-113">This ensures that administrators have visibility into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="c3ab6-114">共享架构在与共享事件相关的审核记录中提供了两个附加字段：</span><span class="sxs-lookup"><span data-stu-id="c3ab6-114">The Sharing schema provides two additional fields in an audit record related to sharing events:</span></span> 
  
- <span data-ttu-id="c3ab6-115">**TargetUserOrGroupType：** 标识目标用户或组是成员、来宾、SharePointGroup、SecurityGroup 还是合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-115">**TargetUserOrGroupType:** Identifies whether the target user or group is a Member, Guest, SharePointGroup, SecurityGroup, or Partner.</span></span>

- <span data-ttu-id="c3ab6-116">**TargetUserOrGroupName：** 存储与之共享资源的目标用户或组的 UPN 或名称（上一示例中的用户 B）。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-116">**TargetUserOrGroupName:** Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 

<span data-ttu-id="c3ab6-117">除了审核日志架构中的其他属性（如用户、操作和日期）之外，这两个字段还可以详细说明*哪些*用户共享了哪些用户与*谁*共享了*哪些\*\*资源。*</span><span class="sxs-lookup"><span data-stu-id="c3ab6-117">These two fields, in addition to other properties from the audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="c3ab6-118">还有另一个架构属性，对共享情景很重要。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-118">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="c3ab6-119">当您导出审核日志搜索结果时，导出的 CSV 文件中的 " **AuditData** " 列存储有关共享事件的信息。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-119">When you export audit log search results, the **AuditData** column in the exported CSV file stores information about sharing events.</span></span> <span data-ttu-id="c3ab6-120">例如，当用户与其他用户共享网站时，可以通过将目标用户添加到 SharePoint 组来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-120">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="c3ab6-121">**AuditData**列捕获此信息，以便为管理员提供上下文。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-121">The **AuditData** column captures this information to provide context for administrators.</span></span> <span data-ttu-id="c3ab6-122">有关如何分析**AuditData**列中的信息的说明，请参阅[步骤 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) 。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-122">See [Step 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) for instructions on how to parse the information in the **AuditData** column.</span></span>

## <a name="sharepoint-sharing-events"></a><span data-ttu-id="c3ab6-123">SharePoint 共享事件</span><span class="sxs-lookup"><span data-stu-id="c3ab6-123">SharePoint sharing events</span></span>

<span data-ttu-id="c3ab6-124">当用户 *（用户）* 要与其他用户共享资源（*目标*用户）时，将定义共享。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-124">Sharing is defined by when a user (the *acting* user) wants to share a resource with another user (the *target* user).</span></span> <span data-ttu-id="c3ab6-125">与外部用户共享资源的审核记录（组织外部的用户，在组织的 Azure Active Directory 中没有来宾帐户）由以下事件标识，这些事件记录在审核日志中：</span><span class="sxs-lookup"><span data-stu-id="c3ab6-125">Audit records related to sharing a resource with an external user (a user who is outside of your organization and doesn't have a guest account in your organization's Azure Active Directory) are identified by the following events, which are logged in the audit log:</span></span>

- <span data-ttu-id="c3ab6-126">**SharingInvitationCreated：** 您的组织中的用户尝试与外部用户共享资源（可能是网站）。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-126">**SharingInvitationCreated:** A user in your organization tried to share a resource (likely a site) with an external user.</span></span> <span data-ttu-id="c3ab6-127">这将导致向目标用户发送外部共享邀请。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-127">This results in an external sharing invitation sent to the target user.</span></span> <span data-ttu-id="c3ab6-128">此时不授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-128">No access to the resource is granted at this point.</span></span>

- <span data-ttu-id="c3ab6-129">**SharingInvitationAccepted：** 外部用户接受了由操作用户发送的共享邀请，现在有权访问该资源。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-129">**SharingInvitationAccepted:** The external user has accepted the sharing invitation sent by the acting user and now has access to the resource.</span></span>

- <span data-ttu-id="c3ab6-130">**AnonymousLinkCreated：** 为资源创建匿名链接（也称为 "任何人" 链接）。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-130">**AnonymousLinkCreated:** An anonymous link (also called an "Anyone" link) is created for a resource.</span></span> <span data-ttu-id="c3ab6-131">由于可以创建匿名链接，然后复制它，因此假定具有匿名链接的任何文档已与目标用户共享，这是合理的。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-131">Because an anonymous link can be created and then copied, it's reasonable to assume that any document that has an anonymous link has been shared with a target user.</span></span>

- <span data-ttu-id="c3ab6-132">**AnonymousLinkUsed：** 顾名思义，当使用匿名链接访问资源时，将记录此事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-132">**AnonymousLinkUsed:** As the name implies, this event is logged when an anonymous link is used to access a resource.</span></span> 

- <span data-ttu-id="c3ab6-133">**SecureLinkCreated：** 用户已创建 "特定人员链接" 以与特定人员共享资源。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-133">**SecureLinkCreated:** A user has created a "specific people link" to share a resource with a specific person.</span></span> <span data-ttu-id="c3ab6-134">此目标用户可能是你的组织外部的人员。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-134">This target user may be someone who is external to your organization.</span></span> <span data-ttu-id="c3ab6-135">共享资源的人员在**AddedToSecureLink**事件的审核记录中标识。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-135">The person that the resource is shared with is identified in the audit record for the **AddedToSecureLink** event.</span></span> <span data-ttu-id="c3ab6-136">这两个事件的时间戳几乎完全相同。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-136">The time stamps for these two events are nearly identical.</span></span>

- <span data-ttu-id="c3ab6-137">**AddedToSecureLink：** 向特定人员链接添加了用户。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-137">**AddedToSecureLink:** A user was added to a specific people link.</span></span> <span data-ttu-id="c3ab6-138">使用此事件中的 " **TargetUserOrGroupName** " 字段可标识添加到相应的特定人员链接的用户。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-138">Use the **TargetUserOrGroupName** field in this event to identify the user added to the corresponding specific people link.</span></span> <span data-ttu-id="c3ab6-139">此目标用户可能是你的组织外部的人员。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-139">This target user may be someone who is external to your organization.</span></span>

## <a name="sharing-auditing-work-flow"></a><span data-ttu-id="c3ab6-140">共享审核工作流</span><span class="sxs-lookup"><span data-stu-id="c3ab6-140">Sharing auditing work flow</span></span>
  
<span data-ttu-id="c3ab6-141">当用户（用户）想要与其他用户（目标用户）共享资源时，SharePoint （或 OneDrive for Business）先检查目标用户的电子邮件地址是否已与组织目录中的用户帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-141">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="c3ab6-142">如果目标用户位于目录中（并具有相应的来宾用户帐户），SharePoint 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c3ab6-142">If the target user is in the directory (and has a corresponding guest user account), SharePoint does the following things:</span></span>
  
-  <span data-ttu-id="c3ab6-143">通过将目标用户添加到相应的 SharePoint 组，立即为目标用户分配访问资源的权限，并记录**AddedToGroup**事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-143">Immediately assigns the target user permissions to access the resource by adding the target user to the appropriate SharePoint group, and logs an **AddedToGroup** event.</span></span> 
    
- <span data-ttu-id="c3ab6-144">向目标用户的电子邮件地址发送共享通知。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-144">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="c3ab6-145">记录**SharingSet**事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-145">Logs a **SharingSet** event.</span></span> <span data-ttu-id="c3ab6-146">此事件在审核日志搜索工具的活动选取器中的 "共享**和访问请求" 活动**下有一个友好名称 "共享文件、文件夹或站点"。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-146">This event has a friendly name of "Shared file, folder, or site" under **Sharing and access request activities** in the activities picker of the audit log search tool.</span></span> <span data-ttu-id="c3ab6-147">请参阅[第1步](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)中的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-147">See the screenshot in [Step 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file).</span></span> 
    
<span data-ttu-id="c3ab6-148">如果目标用户的用户帐户不在目录中，则 SharePoint 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c3ab6-148">If a user account for the target user isn't in the directory, SharePoint does the following:</span></span> 
    
   - <span data-ttu-id="c3ab6-149">根据资源的共享方式，记录以下事件之一：</span><span class="sxs-lookup"><span data-stu-id="c3ab6-149">Logs one of the following events, based on how the resource is shared:</span></span>
   
      - <span data-ttu-id="c3ab6-150">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="c3ab6-150">**AnonymousLinkCreated**</span></span>
   
      - <span data-ttu-id="c3ab6-151">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="c3ab6-151">**SecureLinkCreated**</span></span>
   
      - <span data-ttu-id="c3ab6-152">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="c3ab6-152">**AddedToSecureLink**</span></span> 

      - <span data-ttu-id="c3ab6-153">**SharingInvitationCreated** （仅当共享资源是网站时，才会记录此事件）</span><span class="sxs-lookup"><span data-stu-id="c3ab6-153">**SharingInvitationCreated** (this event is logged only when the shared resource is a site)</span></span>
    
   - <span data-ttu-id="c3ab6-154">当目标用户接受发送给他们的共享邀请（通过单击邀请中的链接）时，SharePoint 会记录一个**SharingInvitationAccepted**事件并为目标用户分配访问资源的权限。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-154">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="c3ab6-155">如果向目标用户发送匿名链接，则在目标用户使用该链接访问资源后记录**AnonymousLinkUsed**事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-155">If the target user is sent an anonymous link, the **AnonymousLinkUsed** event is logged after the target user uses the link to access the resource.</span></span> <span data-ttu-id="c3ab6-156">对于安全链接，当外部用户使用链接访问资源时，将记录**FileAccessed**事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-156">For secure links, a **FileAccessed** event is logged when an external user uses the link to access the resource.</span></span>

<span data-ttu-id="c3ab6-157">还会记录有关目标用户的其他信息，如邀请的用户的标识和接受邀请的用户。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-157">Additional information about the target user is also logged, such as the identity of the user the invitation is to and the user who accepts the invitation.</span></span> <span data-ttu-id="c3ab6-158">在某些情况下，这些用户（或电子邮件地址）可以不同。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-158">In some case, these users (or email addresses) can be different.</span></span> 

## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="c3ab6-159">如何识别与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="c3ab6-159">How to identify resources shared with external users</span></span>

<span data-ttu-id="c3ab6-160">管理员的常见要求是创建已与组织外部的用户共享的所有资源的列表。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-160">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="c3ab6-161">通过使用 Office 365 中的共享审核，管理员可以生成此列表。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-161">By using sharing auditing in Office 365, administrators can generate this list.</span></span> <span data-ttu-id="c3ab6-162">方法如下：</span><span class="sxs-lookup"><span data-stu-id="c3ab6-162">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="c3ab6-163">步骤1：搜索共享事件并将结果导出到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="c3ab6-163">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="c3ab6-164">第一步是在审核日志中搜索共享事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-164">The first step is to search the audit log for sharing events.</span></span> <span data-ttu-id="c3ab6-165">有关搜索审核日志的详细信息（包括所需的权限），请参阅[在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-165">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="c3ab6-166">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-166">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c3ab6-167">使用工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-167">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="c3ab6-168">在安全与合规中心的左侧窗格中，单击“**搜索**”  > “**审核日志搜索**”。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-168">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="c3ab6-169">此时将显示“**审核日志搜索**”页面。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-169">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="c3ab6-170">在 "**活动**" 下，单击 "**共享和访问请求活动**" 以搜索与共享相关的事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-170">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 
    
    ![在 "活动" 下，选择 "共享和访问请求活动"](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="c3ab6-172">选择日期和时间范围以查找在该时间段内发生的共享事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-172">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="c3ab6-173">单击 "**搜索**" 以运行搜索。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-173">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="c3ab6-174">当搜索运行完成并显示结果后，单击 "**导出结果**" " \> **下载所有结果**"。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-174">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="c3ab6-175">选择 "导出" 选项后，窗口底部的一条消息将提示您打开或保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-175">After you select the export option, a message at the bottom of the window prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="c3ab6-176">单击 "**另**存 \> **为**"，然后将 CSV 文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-176">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a><span data-ttu-id="c3ab6-177">步骤2：使用 PowerQuery 编辑器设置导出的审核日志的格式</span><span class="sxs-lookup"><span data-stu-id="c3ab6-177">Step 2: Use the PowerQuery Editor to format the exported audit log</span></span>

<span data-ttu-id="c3ab6-178">下一步是在 Excel 的 Power Query 编辑器中使用 JSON 转换功能，以将**AuditData**列中的每个属性（由多属性 JSON 对象组成）拆分为自己的列。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-178">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the **AuditData** column (which consists of a multi-property JSON object) into its own column.</span></span> <span data-ttu-id="c3ab6-179">这样，您就可以筛选列以查看与共享相关的记录</span><span class="sxs-lookup"><span data-stu-id="c3ab6-179">This lets you filter columns to view records related to sharing</span></span>

<span data-ttu-id="c3ab6-180">有关分步说明，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的 "步骤2：使用 Power Query Editor 格式化导出的审核日志"。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-180">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="c3ab6-181">步骤3：筛选 CSV 文件，以获取与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="c3ab6-181">Step 3: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="c3ab6-182">下一步是筛选 CSV，以获取之前在 " [SharePoint 共享事件](#sharepoint-sharing-events)" 部分中描述的与共享相关的不同事件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-182">The next step is to filter the CSV for the different sharing-related events that were previously described in the [SharePoint sharing events](#sharepoint-sharing-events) section.</span></span> <span data-ttu-id="c3ab6-183">或者，可以筛选**TargetUserOrGroupType**列以显示此属性的值为 "**来宾**" 的所有记录。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-183">Alternatively, you can filter the **TargetUserOrGroupType** column to display all records where the value of this property is **Guest**.</span></span> 

<span data-ttu-id="c3ab6-184">按照上一步中的说明操作，使用 PowerQuery 编辑器准备 CSV 文件后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c3ab6-184">After you've followed the instructions in the previous step to prepare the CSV file by using the PowerQuery editor, do the following:</span></span>
    
1. <span data-ttu-id="c3ab6-185">打开您在步骤2中创建的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-185">Open the Excel file that you created in Step 2.</span></span> 

2. <span data-ttu-id="c3ab6-186">在 "**开始**" 选项卡上，单击 "**排序 & 筛选**"，然后单击 "**筛选**"。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-186">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="c3ab6-187">在 "**操作**" 列上的 "**排序 & 筛选**" 下拉列表中，清除所有选择，然后选择一个或多个以下与共享相关的事件，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-187">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select one or more the following sharing-related events and then click **Ok**.</span></span>
 
   - <span data-ttu-id="c3ab6-188">**SharingInvitationCreated**</span><span class="sxs-lookup"><span data-stu-id="c3ab6-188">**SharingInvitationCreated**</span></span>
   
   - <span data-ttu-id="c3ab6-189">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="c3ab6-189">**AnonymousLinkCreated**</span></span>
   
   - <span data-ttu-id="c3ab6-190">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="c3ab6-190">**SecureLinkCreated**</span></span>
   
   - <span data-ttu-id="c3ab6-191">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="c3ab6-191">**AddedToSecureLink**</span></span> 
    
    <span data-ttu-id="c3ab6-192">Excel 将显示所选事件的行。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-192">Excel displays the rows for the events you selected.</span></span>
    
4. <span data-ttu-id="c3ab6-193">转到名为**TargetUserOrGroupType**的列，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-193">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="c3ab6-194">在 "**排序 & 筛选**" 下拉列表中，清除 "所有选择"，然后选择 " **TargetUserOrGroupType： Guest**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-194">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **Ok**.</span></span>
    
    <span data-ttu-id="c3ab6-195">现在，Excel 将显示共享事件的行以及目标用户在组织外部的位置，因为外部用户由值**TargetUserOrGroupType： Guest**标识。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-195">Now Excel displays the rows for sharing events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
  
> [!TIP]
> <span data-ttu-id="c3ab6-196">对于显示的审核记录， **ObjectId**列标识与目标用户共享的资源;例如 `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` 。</span><span class="sxs-lookup"><span data-stu-id="c3ab6-196">For the audit records that are displayed, the **ObjectId** column identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
