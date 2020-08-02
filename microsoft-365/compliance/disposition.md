---
title: 内容的处置
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 监视和管理内容的处置，无论您使用的是处置评审，还是根据您配置的设置自动删除内容。
ms.openlocfilehash: 55b57891732f50eba09425fce4d2be34c94740f3
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533819"
---
# <a name="disposition-of-content"></a><span data-ttu-id="6d024-103">内容的处置</span><span class="sxs-lookup"><span data-stu-id="6d024-103">Disposition of content</span></span>

><span data-ttu-id="6d024-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="6d024-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="6d024-105">使用 Microsoft 365 合规性中心中的**记录管理**中的 "**处置**" 选项卡来管理处置评审并查看保留期结束时自动删除的[记录](records.md)。</span><span class="sxs-lookup"><span data-stu-id="6d024-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="6d024-106">查看内容处置的先决条件</span><span class="sxs-lookup"><span data-stu-id="6d024-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="6d024-107">若要管理处置评审并确认已删除记录，您必须具有足够的权限，并且必须启用审核。</span><span class="sxs-lookup"><span data-stu-id="6d024-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="6d024-108">处置权限</span><span class="sxs-lookup"><span data-stu-id="6d024-108">Permissions for disposition</span></span>

<span data-ttu-id="6d024-109">若要成功访问 Microsoft 365 合规性中心中的 "**处置**" 选项卡，用户必须具有 "**处置管理**" 角色和 "**仅查看审核日志**" 角色。</span><span class="sxs-lookup"><span data-stu-id="6d024-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="6d024-110">虽然标准建议是将用户添加到默认角色组，在这种情况下，我们建议您创建一个名为 "**处置审阅者**" 的新角色组，该角色组具有这两个角色，并根据需要向该组添加用户。</span><span class="sxs-lookup"><span data-stu-id="6d024-110">Although the standard advice is to add users to the default role groups, in this case, we recommend you create a new role group called **Disposition Reviewers** that has these two roles and add users to this group as needed.</span></span> <span data-ttu-id="6d024-111">用于处置的单个角色组可减少管理开销，并使用户能够更轻松地拥有所需的组合权限。</span><span class="sxs-lookup"><span data-stu-id="6d024-111">A single role group for disposition reduces administration overheads and makes it easier for users have the combined permissions that they need.</span></span>

> [!NOTE]
> <span data-ttu-id="6d024-112">即使是全局管理员也需要授予**处置管理**角色。</span><span class="sxs-lookup"><span data-stu-id="6d024-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> <span data-ttu-id="6d024-113">因此，如果全局管理员需要访问 "处置审阅者" 角色组的成员，则将其作为 "处置**审阅者**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="6d024-113">So if global admins need to access the disposition tab, them as members of the **Disposition Reviewers** role group.</span></span> 

<span data-ttu-id="6d024-114">特定于**仅查看审核日志**角色：</span><span class="sxs-lookup"><span data-stu-id="6d024-114">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="6d024-115">由于用于搜索审核日志的基础 cmdlet 是 Exchange Online cmdlet，因此您必须使用 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)（而不是使用 Security & 合规性中心中的 "**权限**" 页）为用户分配此角色。</span><span class="sxs-lookup"><span data-stu-id="6d024-115">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="6d024-116">有关说明，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="6d024-116">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="6d024-117">此角色不支持 Microsoft 365 组（[以前称为 "Office 365 组](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)"）。</span><span class="sxs-lookup"><span data-stu-id="6d024-117">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="6d024-118">而是分配用户邮箱、邮件用户或启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="6d024-118">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="6d024-119">有关向用户授予**处置管理**角色和创建新的**处置审阅者**角色的说明，请参阅[向用户授予对 Office 365 安全 &amp; 合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6d024-119">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="6d024-120">启用审核</span><span class="sxs-lookup"><span data-stu-id="6d024-120">Enable auditing</span></span>

<span data-ttu-id="6d024-121">确保至少已在第一个处置操作之前的一天内启用审核。</span><span class="sxs-lookup"><span data-stu-id="6d024-121">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="6d024-122">有关详细信息，请参阅[在 Office 365 安全 &amp; 合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="6d024-122">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="6d024-123">处置评审</span><span class="sxs-lookup"><span data-stu-id="6d024-123">Disposition reviews</span></span>

<span data-ttu-id="6d024-124">当内容到达其保留期结束时，您可能需要查看内容以决定是否可以安全地删除（"已释放"），这有几个原因。</span><span class="sxs-lookup"><span data-stu-id="6d024-124">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="6d024-125">例如，您可能需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d024-125">For example, you might need to:</span></span>
  
- <span data-ttu-id="6d024-126">在诉讼或审核事件中，挂起对相关内容的删除。</span><span class="sxs-lookup"><span data-stu-id="6d024-126">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="6d024-127">如果内容具有信息检索或历史值，则从处置列表中移除要存储在存档中的内容。</span><span class="sxs-lookup"><span data-stu-id="6d024-127">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="6d024-128">为内容分配不同的保留期，可能是因为原始保留设置是临时或临时的解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d024-128">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="6d024-129">将内容返回给客户端或将其转移到其他组织。</span><span class="sxs-lookup"><span data-stu-id="6d024-129">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="6d024-130">在保留期结束时触发处置评审时：</span><span class="sxs-lookup"><span data-stu-id="6d024-130">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="6d024-131">您选择的人会收到一封电子邮件通知，告知他们有要审阅的内容。</span><span class="sxs-lookup"><span data-stu-id="6d024-131">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="6d024-132">这些审阅者可以是单独的用户、分发或安全组，也可以是 Microsoft 365 组（[以前称为 Office 365 组](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）。</span><span class="sxs-lookup"><span data-stu-id="6d024-132">These reviewers can be individual users, distribution or security groups, or Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span></span> <span data-ttu-id="6d024-133">请注意，每周会发送通知。</span><span class="sxs-lookup"><span data-stu-id="6d024-133">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="6d024-134">审阅者转到 Microsoft 365 合规性中心中的 "**处置**" 选项卡，以查看内容并决定是永久删除它、延长保留期还是应用不同的保留标签。</span><span class="sxs-lookup"><span data-stu-id="6d024-134">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="6d024-135">处置评审可以包含 Exchange 邮箱、SharePoint 网站、OneDrive 帐户和 Microsoft 365 组中的内容。</span><span class="sxs-lookup"><span data-stu-id="6d024-135">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="6d024-136">在这些位置中等待处置评审的内容仅在审阅者选择永久删除内容后才会被删除。</span><span class="sxs-lookup"><span data-stu-id="6d024-136">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="6d024-137">邮箱必须至少有 10 MB 数据才能支持处置评审。</span><span class="sxs-lookup"><span data-stu-id="6d024-137">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="6d024-138">您可以在 "**概述**" 选项卡中看到所有待处理的处置的概述。例如：</span><span class="sxs-lookup"><span data-stu-id="6d024-138">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![记录管理概述中的挂起的处置](../media/dispositions-overview.png)

<span data-ttu-id="6d024-140">当您选择 "**查看所有待处理的处理**" 时，您将转到 "**处置**" 页面。</span><span class="sxs-lookup"><span data-stu-id="6d024-140">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="6d024-141">例如：</span><span class="sxs-lookup"><span data-stu-id="6d024-141">For example:</span></span>

![Microsoft 365 合规性中心中的处置页](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="6d024-143">用于处置评审的工作流</span><span class="sxs-lookup"><span data-stu-id="6d024-143">Workflow for a disposition review</span></span>

<span data-ttu-id="6d024-144">下图显示了在发布保留标签并随后由用户手动应用时进行处置评审的基本工作流。</span><span class="sxs-lookup"><span data-stu-id="6d024-144">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="6d024-145">此外，还可以将为处置评审配置的保留标签自动应用于内容。</span><span class="sxs-lookup"><span data-stu-id="6d024-145">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![显示处置的工作流的图表](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="6d024-147">在保留期结束时触发处置评审是一个仅可用于保留标签的配置选项。</span><span class="sxs-lookup"><span data-stu-id="6d024-147">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="6d024-148">此选项不适用于保留策略。</span><span class="sxs-lookup"><span data-stu-id="6d024-148">This option is not available for a retention policy.</span></span> <span data-ttu-id="6d024-149">有关这两种保留解决方案的详细信息，请参阅[了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="6d024-149">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![标签的保留设置](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="6d024-151">当您选择 "**当有准备好查看的项目时通知这些人**" 选项时，请指定一个用户或已启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="6d024-151">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="6d024-152">此选项不支持 Microsoft 365 组（[以前称为 "Office 365 组](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)"）。</span><span class="sxs-lookup"><span data-stu-id="6d024-152">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="6d024-153">查看和处置内容</span><span class="sxs-lookup"><span data-stu-id="6d024-153">Viewing and disposing of content</span></span>

<span data-ttu-id="6d024-154">当通过电子邮件通知审阅者可以查看内容时，他们会从 Microsoft 365 合规性中心的**记录管理**转到 "**处置**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6d024-154">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6d024-155">审阅者可以查看每个保留标签的项目数正在等待处置，然后选择保留标签以查看具有该标签的所有内容。</span><span class="sxs-lookup"><span data-stu-id="6d024-155">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="6d024-156">选择保留标签后，您将看到 "**挂起处置**" 选项卡中该标签的所有待定的处置。选择一个或多个项目，您可以在其中选择操作并输入理由注释：</span><span class="sxs-lookup"><span data-stu-id="6d024-156">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![处置选项](../media/retention-disposition-options.png)

<span data-ttu-id="6d024-158">正如您可以从图片中看到的，受支持的操作是：</span><span class="sxs-lookup"><span data-stu-id="6d024-158">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="6d024-159">永久删除项目</span><span class="sxs-lookup"><span data-stu-id="6d024-159">Permanently delete the item</span></span>
- <span data-ttu-id="6d024-160">延长保留期</span><span class="sxs-lookup"><span data-stu-id="6d024-160">Extend the retention period</span></span>
- <span data-ttu-id="6d024-161">应用不同的保留标签</span><span class="sxs-lookup"><span data-stu-id="6d024-161">Apply a different retention label</span></span>

<span data-ttu-id="6d024-162">为您提供对位置和内容的权限，您可以使用**位置**列中的链接查看其原始位置中的文档。</span><span class="sxs-lookup"><span data-stu-id="6d024-162">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="6d024-163">在处置评审过程中，内容永远不会从其原始位置移动，并且在审阅者选择执行此操作之前永远不会删除。</span><span class="sxs-lookup"><span data-stu-id="6d024-163">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="6d024-164">电子邮件通知将在每周的基础上自动发送给审阅者。</span><span class="sxs-lookup"><span data-stu-id="6d024-164">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="6d024-165">此计划的过程意味着，当内容到达其保留期的末尾时，审阅者可能需要长达七天的时间，审阅者收到内容正在等待处置的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="6d024-165">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="6d024-166">可以审核所有处置操作，并将审阅者输入的调整文本保存并显示在 "已**释放项目**" 页上的 "**注释**" 列中。</span><span class="sxs-lookup"><span data-stu-id="6d024-166">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="6d024-167">在永久删除已释放内容之前的时间</span><span class="sxs-lookup"><span data-stu-id="6d024-167">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="6d024-168">等待处置评审的内容仅在审阅者选择永久删除内容后才会被删除。</span><span class="sxs-lookup"><span data-stu-id="6d024-168">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="6d024-169">当审阅者选择此选项时，SharePoint 网站或 OneDrive 帐户中的内容将成为符合[保留设置如何与内容配合](retention.md#how-retention-settings-work-with-content-in-place)使用的标准清理过程。</span><span class="sxs-lookup"><span data-stu-id="6d024-169">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="6d024-170">处置记录</span><span class="sxs-lookup"><span data-stu-id="6d024-170">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="6d024-171">为 SharePoint 和 OneDrive 中的记录提供处置证明的部署已完成。</span><span class="sxs-lookup"><span data-stu-id="6d024-171">The rollout for proof of disposal for records in SharePoint and OneDrive is complete.</span></span> <span data-ttu-id="6d024-172">您将在 Microsoft 365 合规性中心的 "记录管理" 页的 "处置" 部分中看到标记为 "内容为 SharePoint 和 OneDrive 的记录" 的保留标签列表。</span><span class="sxs-lookup"><span data-stu-id="6d024-172">You will see the list of retention labels that marked content as records for SharePoint and OneDrive in the Disposition section of the Records Management page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6d024-173">在这些标签下，您可以在 SharePoint 和 OneDrive 中查看已自动处置或在处置评审之后的项的列表。</span><span class="sxs-lookup"><span data-stu-id="6d024-173">Under these labels, you can see the list of items in SharePoint and OneDrive that were disposed automatically or after a disposition review.</span></span>
>
> <span data-ttu-id="6d024-174">Exchange 中的记录处置证明尚未激活。</span><span class="sxs-lookup"><span data-stu-id="6d024-174">Proof of disposal for records in Exchange is not yet active.</span></span> <span data-ttu-id="6d024-175">当此推出开始且完成时，我们将更新此注释。</span><span class="sxs-lookup"><span data-stu-id="6d024-175">When this rollout begins and when it is complete, we will update this note.</span></span>

<span data-ttu-id="6d024-176">使用 "**记录管理**" 页上的 "**处置**" 选项卡来标识自动删除的记录。</span><span class="sxs-lookup"><span data-stu-id="6d024-176">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="6d024-177">这些项目在 "**类型**" 列中显示已**处置的记录**。</span><span class="sxs-lookup"><span data-stu-id="6d024-177">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="6d024-178">例如：</span><span class="sxs-lookup"><span data-stu-id="6d024-178">For example:</span></span>

![在没有处置评审的情况下处置的项目](../media/records-disposed2.png)

<span data-ttu-id="6d024-180">记录标签的 "已**释放的项目**" 选项卡中显示的项目在项目被释放前最长保留7年，在该时间段内每条记录的项目数限制为1000000。</span><span class="sxs-lookup"><span data-stu-id="6d024-180">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="6d024-181">如果您看到 "**计数**数量" 接近此限制1000000，并且您需要对记录进行处置证明，请与[Microsoft 支持](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)部门联系。</span><span class="sxs-lookup"><span data-stu-id="6d024-181">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="6d024-182">此功能基于[统一审核日志](search-the-audit-log-in-security-and-compliance.md)中的信息，因此需要[启用和可搜索](turn-audit-log-search-on-or-off.md)审核，以便捕获相应的事件。</span><span class="sxs-lookup"><span data-stu-id="6d024-182">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="6d024-183">筛选和导出视图</span><span class="sxs-lookup"><span data-stu-id="6d024-183">Filter and export the views</span></span>

<span data-ttu-id="6d024-184">当您从 "**处置**" 页面中选择保留标签时，"**挂起的处置**" 选项卡（如果适用）和 "已**释放的项目**" 选项卡允许您筛选视图以帮助更轻松地查找项目。</span><span class="sxs-lookup"><span data-stu-id="6d024-184">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="6d024-185">对于挂起的处置，时间范围基于到期日期。</span><span class="sxs-lookup"><span data-stu-id="6d024-185">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="6d024-186">对于已释放的项目，时间范围基于删除日期。</span><span class="sxs-lookup"><span data-stu-id="6d024-186">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="6d024-187">您可以将任一视图中项目的相关信息导出为 .csv 文件，然后可以使用 Excel 进行排序和管理：</span><span class="sxs-lookup"><span data-stu-id="6d024-187">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![用于处置的导出选项](../media/retention-export-option.png)
  
![Excel 中的已导出处置数据](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


