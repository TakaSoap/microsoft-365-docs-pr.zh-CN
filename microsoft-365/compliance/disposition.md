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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 监控和管理当你使用处置评审时或者根据配置的设置自动删除标记为记录的项目时的内容处置。
ms.openlocfilehash: 99ab789b99385af9ad2677995606d21ece54705c
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594069"
---
# <a name="disposition-of-content"></a><span data-ttu-id="996be-103">内容的处置</span><span class="sxs-lookup"><span data-stu-id="996be-103">Disposition of content</span></span>

><span data-ttu-id="996be-104">*[Microsoft 365 安全性与合规性的许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="996be-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="996be-105">使用 Microsoft 365 合规中心“**记录管理**”中的“**处置**”页面来管理处置评审，并查看在保持期结束时自动删除的 [记录](records-management.md#records)的元数据。</span><span class="sxs-lookup"><span data-stu-id="996be-105">Use the **Disposition** page from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view the metadata of [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span>

> [!NOTE]
> <span data-ttu-id="996be-106">预览版：**多阶段处置评审**</span><span class="sxs-lookup"><span data-stu-id="996be-106">In preview: **multi-stage disposition review**</span></span>
> 
> <span data-ttu-id="996be-107">现在，管理员可以在保留标签中添加最多五个连续的处置评审阶段，而审阅者可以将其他用户添加到其处置评审阶段。</span><span class="sxs-lookup"><span data-stu-id="996be-107">An administrator can now add up to five consecutive stages of disposition review in a retention label, and reviewers can add others users to their disposition review stage.</span></span> <span data-ttu-id="996be-108">你还可以自定义电子邮件通知和提醒。</span><span class="sxs-lookup"><span data-stu-id="996be-108">You can also customize the email notifications and reminders.</span></span> <span data-ttu-id="996be-109">下面的章节提供了有关此预览版中所做的更改的详细信息。</span><span class="sxs-lookup"><span data-stu-id="996be-109">The following sections have more information about the changes in this preview.</span></span>
>
> <span data-ttu-id="996be-110">要阅读发布公告，请参阅 [Microsoft 记录管理中多阶段处置公告](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-multi-stage-disposition-in-microsoft-records/ba-p/2361849)发布的博文。</span><span class="sxs-lookup"><span data-stu-id="996be-110">To read the release announcement, see the blog post [Announcing Multi-Stage Disposition in Microsoft Records Management](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-multi-stage-disposition-in-microsoft-records/ba-p/2361849).</span></span>

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="996be-111">查看内容处置的前提条件</span><span class="sxs-lookup"><span data-stu-id="996be-111">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="996be-112">若要管理处置评审并确认已删除记录，必须具有足够的权限，并且必须启用审核。</span><span class="sxs-lookup"><span data-stu-id="996be-112">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="996be-113">处置权限</span><span class="sxs-lookup"><span data-stu-id="996be-113">Permissions for disposition</span></span>

<span data-ttu-id="996be-114">若要成功访问 Microsoft 365 合规中心中的“**处置**”选项卡，用户必须拥有“**处置管理**”角色。</span><span class="sxs-lookup"><span data-stu-id="996be-114">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** role.</span></span> <span data-ttu-id="996be-115">从 2020 年 12 月起，此角色现已纳入“**记录管理**”默认角色组中。</span><span class="sxs-lookup"><span data-stu-id="996be-115">From December 2020, this role is now included in the **Records Management** default role group.</span></span>

> [!NOTE]
> <span data-ttu-id="996be-116">默认情况下，不向全局管理员授予“**处置管理**”角色。</span><span class="sxs-lookup"><span data-stu-id="996be-116">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="996be-117">若要仅为用户授予处置评审所需的权限，而不授予他们查看和配置保留和记录管理其他功能的权限，请创建一个自定义角色组（例如，命名为“处置审阅者”），并授予此组“**处置管理**”角色。</span><span class="sxs-lookup"><span data-stu-id="996be-117">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the **Disposition Management** role.</span></span>

<span data-ttu-id="996be-118">有关配置这些权限的说明，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="996be-118">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="996be-119">另外：</span><span class="sxs-lookup"><span data-stu-id="996be-119">Additionally:</span></span>

- <span data-ttu-id="996be-120">若要在处置过程中查看项目的内容，请将用户添加到“**内容资源管理器内容查看者**”角色组。</span><span class="sxs-lookup"><span data-stu-id="996be-120">To view the contents of items during the disposition process, add users to the **Content Explorer Content Viewer** role group.</span></span> <span data-ttu-id="996be-121">如果用户没有此角色组的权限，他们仍可选择一个处置评审操作来完成处置评审，但是执行此操作时无法在合规中心的迷你预览窗格中查看项目的内容。</span><span class="sxs-lookup"><span data-stu-id="996be-121">If users don't have the permissions from this role group, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the mini-preview pane in the compliance center.</span></span>

- <span data-ttu-id="996be-122">处于预览阶段：默认情况下，访问“**处置**”页面的每个人只能看到分配给他们进行审阅的项目。</span><span class="sxs-lookup"><span data-stu-id="996be-122">In preview: By default, each person that accesses the **Disposition** page sees only items that they are assigned to review.</span></span> <span data-ttu-id="996be-123">为使记录管理管理员能够查看分配给所有用户的所有项目以及配置用于处置评审的所有保留标签：导航到“**记录管理设置**” > “**常规**” > “**记录管理员安全组**”，选择并启用包含管理员帐户的已启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="996be-123">For a records management administrator to see all items assigned to all users, and all retention labels that are configured for disposition review: Navigate to **Records management settings** > **General** > **Security group for records manager** to select and then enable a mail-enabled security group that contains the administrator accounts.</span></span>
    
    <span data-ttu-id="996be-124">未启用邮件的 Microsoft 365 组和安全组不支持此功能，也不会显示在列表中供选择。</span><span class="sxs-lookup"><span data-stu-id="996be-124">Microsoft 365 groups and security groups that aren't mail-enabled doesn't support this feature and wouldn't be displayed in the list to select.</span></span> <span data-ttu-id="996be-125">如果需要创建新的启用邮件的安全组，请使用 Microsoft 365 管理中心的链接创建新组。</span><span class="sxs-lookup"><span data-stu-id="996be-125">If you need to create a new mail-enabled security group, use the link to the Microsoft 365 admin center to create the new group.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="996be-126">启用组后，你无法在合规中心更改组。</span><span class="sxs-lookup"><span data-stu-id="996be-126">After you have enabled the group, you can't change it in the compliance center.</span></span> <span data-ttu-id="996be-127">请参阅下一部分，了解如何使用 PowerShell 启用其他组。</span><span class="sxs-lookup"><span data-stu-id="996be-127">See the next section for how to enable a different group by using PowerShell.</span></span>

- <span data-ttu-id="996be-128">处于预览阶段：“**记录管理设置**”选项仅对记录管理管理员可见。</span><span class="sxs-lookup"><span data-stu-id="996be-128">In preview: The **Records management settings** option is visible only to record management administrators.</span></span> 

#### <a name="enabling-another-security-group-for-disposition"></a><span data-ttu-id="996be-129">启用另一个安全组用于处置</span><span class="sxs-lookup"><span data-stu-id="996be-129">Enabling another security group for disposition</span></span>

<span data-ttu-id="996be-130">在 Microsoft 365 合规中心的“**记录管理设置**”中启用了安全组用于处置后，你将无法对该组禁用此权限，也不能在合规中心中替换选定的组。</span><span class="sxs-lookup"><span data-stu-id="996be-130">After you have enabled a security group for disposition from the **Records management settings** in the Microsoft 365 compliance center, you can't disable this permission for the group or replace the selected group in the compliance center.</span></span> <span data-ttu-id="996be-131">但是，可使用 [Enable-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) cmdlet 启用其他启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="996be-131">However, you can enable another mail-enabled security group by using the [Enable-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) cmdlet.</span></span>

<span data-ttu-id="996be-132">例如：</span><span class="sxs-lookup"><span data-stu-id="996be-132">For example:</span></span> 

```PowerShell
Enable-ComplianceTagStorage -RecordsManagementSecurityGroupEmail dispositionreviewers@contosoi.com
````

### <a name="enable-auditing"></a><span data-ttu-id="996be-133">启用审核</span><span class="sxs-lookup"><span data-stu-id="996be-133">Enable auditing</span></span>

<span data-ttu-id="996be-134">确保至少在第一次处置操作之前一天已启用审核。</span><span class="sxs-lookup"><span data-stu-id="996be-134">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="996be-135">有关详细信息，请参阅[在 Office 365 安全&amp;合规中心](search-the-audit-log-in-security-and-compliance.md)内搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="996be-135">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="996be-136">处置评审</span><span class="sxs-lookup"><span data-stu-id="996be-136">Disposition reviews</span></span>

<span data-ttu-id="996be-p109">当内容的保持期结束时，这里有几个可能使人想审查其内容并确认它是否可以永久删除 (“处置”) 的原因。例如，若不删除其内容，可能需要:</span><span class="sxs-lookup"><span data-stu-id="996be-p109">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed"). For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="996be-139">暂停删除诉讼或审核相关的内容。</span><span class="sxs-lookup"><span data-stu-id="996be-139">Suspend the deletion of relevant content for litigation or an audit.</span></span>

- <span data-ttu-id="996be-140">为内容指定不同的保留期，可能是因为原始保留设置是临时或暂时的解决方案。</span><span class="sxs-lookup"><span data-stu-id="996be-140">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="996be-141">将内容从现有位置移动到存档位置，例如当内容具有研究或历史价值时。</span><span class="sxs-lookup"><span data-stu-id="996be-141">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="996be-142">在保持期结束时触发处置评审时：</span><span class="sxs-lookup"><span data-stu-id="996be-142">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="996be-143">你选择的审阅者将收到一封电子邮件通知，告知他们有内容需要审阅。</span><span class="sxs-lookup"><span data-stu-id="996be-143">The reviewers you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="996be-144">这些审阅者可以是单个用户或启用了邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="996be-144">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="996be-145">预览版中的新增功能：</span><span class="sxs-lookup"><span data-stu-id="996be-145">New in preview:</span></span>
   - <span data-ttu-id="996be-146">你可以自定义他们收到的电子邮件，包括不同语言的说明。</span><span class="sxs-lookup"><span data-stu-id="996be-146">You can customize the email that they receive, including instructions in different languages.</span></span> <span data-ttu-id="996be-147">若要获得多语言支持，你必须自己指定翻译，此自定义文本将显示给所有审阅者，无论其区域设置如何都是如此。</span><span class="sxs-lookup"><span data-stu-id="996be-147">For multi-language support, you must specify the translations yourself and this custom text is displayed to all reviewers irrespective of their locale.</span></span>
   - <span data-ttu-id="996be-148">在项目的保持期结束时，用户将收到每个标签的初始电子邮件通知，对于分配给他们的所有处置评审的每个标签，每周将收到一条提醒。</span><span class="sxs-lookup"><span data-stu-id="996be-148">Users receive an initial email notification per label at the end of the item's retention period, with a reminder per label once a week of all disposition reviews that they are assigned.</span></span> <span data-ttu-id="996be-149">他们可以单击通知和提醒电子邮件中的链接，转到 Microsoft 365 合规中心中的“**处置**”页面以查看该内容并执行操作。</span><span class="sxs-lookup"><span data-stu-id="996be-149">They can click the link in the notification and reminder emails to go to the **Disposition** page in the Microsoft 365 compliance center to review the content and take an action.</span></span> <span data-ttu-id="996be-150">或者，审阅者可以直接转到合规中心中的“**处置**”页面。</span><span class="sxs-lookup"><span data-stu-id="996be-150">Alternately, the reviewers can go directly to the **Disposition** page in the compliance center.</span></span>
   - <span data-ttu-id="996be-151">审阅者只能看到分配给他们的处置评审，而添加到所选“记录管理员安全组”的管理员将看到所有处置评审。</span><span class="sxs-lookup"><span data-stu-id="996be-151">Reviewers see only the disposition reviews that are assigned to them, whereas administrators who are added to the selected security group for records manager see all disposition reviews.</span></span>
   - <span data-ttu-id="996be-152">审阅者可以将新用户添加到同一处置评审中。</span><span class="sxs-lookup"><span data-stu-id="996be-152">Reviewers can add new users to the same disposition review.</span></span> <span data-ttu-id="996be-153">当前，此操作不会自动向添加的这些用户授予[所需权限](#permissions-for-disposition)。</span><span class="sxs-lookup"><span data-stu-id="996be-153">Currently, this action doesn't automatically grant these added users the [required permissions](#permissions-for-disposition).</span></span>
   - <span data-ttu-id="996be-154">对于处置评审过程，每个项目的迷你审阅窗格会显示内容预览（如果他们有权查看该内容）。</span><span class="sxs-lookup"><span data-stu-id="996be-154">For the disposition review process, a mini-review pane for each item shows a preview of the content if they have permissions to see it.</span></span> <span data-ttu-id="996be-155">如果他们没有权限，则可以选择内容链接并请求权限。</span><span class="sxs-lookup"><span data-stu-id="996be-155">If they don't have permissions, they can select the content link and request permissions.</span></span> <span data-ttu-id="996be-156">此迷你审阅窗格还包括有关内容的其他信息的选项卡：</span><span class="sxs-lookup"><span data-stu-id="996be-156">This mini-review pane also has tabs for additional information about the content:</span></span>
       - <span data-ttu-id="996be-157">**详细信息**，显示索引属性、其所在位置、创建者、创建时间和上次修改者以及上次修改时间。</span><span class="sxs-lookup"><span data-stu-id="996be-157">**Details** to display indexed properties, where it's located, who created it and when, and who last modified it and when.</span></span>
       - <span data-ttu-id="996be-158">**历史记录**，显示迄今为止任何处置评审操作的历史记录，以及审阅者备注（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="996be-158">**History** that shows the history of any disposition review actions to date, with reviewer comments if available.</span></span>

<span data-ttu-id="996be-159">处置评审可以包括 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户中的内容。</span><span class="sxs-lookup"><span data-stu-id="996be-159">A disposition review can include content in Exchange mailboxes, SharePoint sites, and OneDrive accounts.</span></span> <span data-ttu-id="996be-160">只有在处置的最终阶段，审阅者选择永久删除内容后，这些位置中等待处置评审的内容才会被永久删除。</span><span class="sxs-lookup"><span data-stu-id="996be-160">Content pending a disposition review in those locations is permanently deleted only after a reviewer for the final stage of disposition chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="996be-161">邮箱必须至少有 10 MB 数据才能支持处置评审。</span><span class="sxs-lookup"><span data-stu-id="996be-161">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="996be-162">管理员可以在“**概览**”选项卡中查看所有挂起的处置的概述。审阅者只会看到其项目挂起的处置。</span><span class="sxs-lookup"><span data-stu-id="996be-162">Administrators can see an overview of all pending dispositions in the **Overview** tab. Reviewers see only their items pending disposition.</span></span> <span data-ttu-id="996be-163">例如：</span><span class="sxs-lookup"><span data-stu-id="996be-163">For example:</span></span>

![记录管理概述中的待处置](../media/dispositions-overview.png)

<span data-ttu-id="996be-165">选择 **查看所有待处置** 后，则转到 **处置** 页面。</span><span class="sxs-lookup"><span data-stu-id="996be-165">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="996be-166">例如：</span><span class="sxs-lookup"><span data-stu-id="996be-166">For example:</span></span>

![Microsoft 365 合规中心内的策略页面](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="996be-168">处置评审的工作流</span><span class="sxs-lookup"><span data-stu-id="996be-168">Workflow for a disposition review</span></span>

<span data-ttu-id="996be-169">下图显示了发布保留标签后再由用户手动应用时处置评审的基本工作流。</span><span class="sxs-lookup"><span data-stu-id="996be-169">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="996be-170">此外，为处置评审配置的保留标签可自动应用于内容。</span><span class="sxs-lookup"><span data-stu-id="996be-170">Alternatively, a retention label configured for a disposition review can be automatically applied to content.</span></span>
  
![图表显示处置的工作流程](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)

### <a name="how-to-configure-a-retention-label-for-disposition-review"></a><span data-ttu-id="996be-172">如何配置处置评审的保留标签</span><span class="sxs-lookup"><span data-stu-id="996be-172">How to configure a retention label for disposition review</span></span>

<span data-ttu-id="996be-173">保持期结束时触发处置评审是一个配置选项，仅保留标签才能使用。</span><span class="sxs-lookup"><span data-stu-id="996be-173">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="996be-174">处置评审不适用于保留策略。</span><span class="sxs-lookup"><span data-stu-id="996be-174">Disposition review is not available for a retention policy.</span></span> <span data-ttu-id="996be-175">有关这两种保留解决方案的详细信息，请参阅[了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="996be-175">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="996be-176">来自 **定义保留标签的保留设置** 页面：</span><span class="sxs-lookup"><span data-stu-id="996be-176">From the **Define retention settings** page for a retention label:</span></span>

![标签的保留设置](../media/disposition-review-option.png)
 
<span data-ttu-id="996be-178">选择此“**触发处置评审**”选项后，在向导的下一页上，指定所需的处置连续阶段数以及每个阶段的处置评审：</span><span class="sxs-lookup"><span data-stu-id="996be-178">After you select this **Trigger a disposition review** option, on the next page of the wizard, you specify how many consecutive stages of disposition you want and the disposition reviewers for each stage:</span></span>

![指定处置审阅者](../media/disposition-reviewers.png) 

<span data-ttu-id="996be-180">选择“**添加阶段**”，并对阶段进行命名以方便识别。</span><span class="sxs-lookup"><span data-stu-id="996be-180">Select **Add a stage**, and name your stage for identification purposes.</span></span> <span data-ttu-id="996be-181">然后指定该阶段的审阅者。</span><span class="sxs-lookup"><span data-stu-id="996be-181">Then specify the reviewers for that stage.</span></span>

<span data-ttu-id="996be-182">对于审阅者，请指定用户或启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="996be-182">For the reviewers, specify a user or a mail-enabled security group.</span></span> <span data-ttu-id="996be-183">此选项当前不支持 Microsoft 365 组（[以前为 Office 365 组](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）。</span><span class="sxs-lookup"><span data-stu-id="996be-183">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are currently not supported for this option.</span></span>

<span data-ttu-id="996be-184">如果你需要多人在保持期结束后审阅某个项目，请再次选择“**添加阶段**”，并针对所需的阶段数重复配置过程，最多五个阶段。</span><span class="sxs-lookup"><span data-stu-id="996be-184">If you need more than one person to review an item at the end of its retention period, select **Add a stage** again and repeat the configuration process for the number of stages that you need, with a maximum of five stages.</span></span> 

<span data-ttu-id="996be-p122">在处置的每个阶段，你为该阶段指定的任何用户都有权在保持期结束后对该项目执行下一个操作。这些用户还可以将其他用户添加到其处置审核阶段。</span><span class="sxs-lookup"><span data-stu-id="996be-p122">Within each individual stage of disposition, any of the users you specify for that stage are authorized to take the next action for the item at the end of its retention period. These users can also add other users to their disposition review stage.</span></span>

> [!NOTE]
> <span data-ttu-id="996be-187">通过配置标签，可以将配置用于处置评审的现有保留标签升级为使用多阶段处置评审。</span><span class="sxs-lookup"><span data-stu-id="996be-187">Existing retention labels that are configured for disposition review can be upgraded to use multi-staged disposition review by configuring the label.</span></span> <span data-ttu-id="996be-188">在标签向导中，选择“**添加阶段**”，或者编辑现有审阅者或添加新的审阅者。</span><span class="sxs-lookup"><span data-stu-id="996be-188">In the label wizard, select **Add a stage**, or edit the existing reviewers or add new reviewers.</span></span>

<span data-ttu-id="996be-189">在配置阶段，对于指定的每个阶段，可以通过选择阶段操作选项 (**...**) 来对其重命名、重新排序或将其删除：</span><span class="sxs-lookup"><span data-stu-id="996be-189">During the configuration phase, for each stage specified, you can rename it, reorder it, or remove it by selecting the Stage actions option (**...**):</span></span> 

![处置评审的阶段操作](../media/stage-actions-disposition-review.png)

<span data-ttu-id="996be-191">但是，在创建保留标签后，你无法重新排序或删除阶段。</span><span class="sxs-lookup"><span data-stu-id="996be-191">However, you can't reorder or remove a stage after you have created the retention label.</span></span>

<span data-ttu-id="996be-192">指定审阅者后，请记得授予他们“**处置管理**”角色权限。</span><span class="sxs-lookup"><span data-stu-id="996be-192">After you have specified your reviewers, remember to grant them the **Disposition Management** role permission.</span></span> <span data-ttu-id="996be-193">有关详细信息，请参阅本页上的“[处置权限](#permissions-for-disposition)”部分。</span><span class="sxs-lookup"><span data-stu-id="996be-193">For more information, see the [Permissions for disposition](#permissions-for-disposition) section on this page.</span></span>

### <a name="how-to-customize-email-messages-for-disposition-review"></a><span data-ttu-id="996be-194">如何自定义处置评审的电子邮件</span><span class="sxs-lookup"><span data-stu-id="996be-194">How to customize email messages for disposition review</span></span>

<span data-ttu-id="996be-195">发送给审阅者的默认电子邮件通知示例：</span><span class="sxs-lookup"><span data-stu-id="996be-195">Example default email notification sent to a reviewer:</span></span>

![项目准备好进行处置审阅时包含默认文本的电子邮件通知示例](../media/disposition-review-email.png)

<span data-ttu-id="996be-197">另外在预览阶段，你还可以自定义发送给处置审阅者的电子邮件，以用于初始通知和提醒。</span><span class="sxs-lookup"><span data-stu-id="996be-197">Also in preview, you can customize the email messages that are sent to disposition reviewers for the initial notification and then reminders.</span></span>

<span data-ttu-id="996be-198">从合规中心的任意处置页面中，选择“**记录管理设置**”：</span><span class="sxs-lookup"><span data-stu-id="996be-198">From any of the Disposition pages in the compliance center, select **Records management settings**:</span></span>  

![记录管理设置](../media/record-management-settings.png)

<span data-ttu-id="996be-200">然后选择“**处置通知**”选项卡，并指定是仅使用默认电子邮件模板，还是将你自己的文本添加到默认模板。</span><span class="sxs-lookup"><span data-stu-id="996be-200">Then select the **Disposition notifications** tab, and specify whether you want to use just the default email message, or add your own text to the default message.</span></span> <span data-ttu-id="996be-201">你的自定义文本将添加到保留标签相关信息之后和后续步骤说明之前的电子邮件说明中。</span><span class="sxs-lookup"><span data-stu-id="996be-201">Your custom text is added to the email instructions after the information about the retention label and before the next steps instructions.</span></span>

<span data-ttu-id="996be-202">可添加所有语言的文本，但当前不支持格式和图像。</span><span class="sxs-lookup"><span data-stu-id="996be-202">Text for all languages can be added, but formatting and images are currently unsupported.</span></span> <span data-ttu-id="996be-203">URL 和电子邮件地址可以文本格式输入，根据电子邮件客户端在自定义电子邮件中显示为超链接或不设置格式的文本。</span><span class="sxs-lookup"><span data-stu-id="996be-203">URLs and email addresses can be entered as text and depending on the email client, display as hyperlinks or unformatted text in the customized email.</span></span>

<span data-ttu-id="996be-204">要附加的示例文本：</span><span class="sxs-lookup"><span data-stu-id="996be-204">Example text to add:</span></span>

```console
If you need additional information, visit the helpdesk website (https://support.contoso.com) or send them an email (helpdesk@contoso.com).
```

<span data-ttu-id="996be-205">选择“**保存**”以保存任何更改。</span><span class="sxs-lookup"><span data-stu-id="996be-205">Select **Save** to save any changes.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="996be-206">查看和处置内容</span><span class="sxs-lookup"><span data-stu-id="996be-206">Viewing and disposing of content</span></span>

<span data-ttu-id="996be-207">通过电子邮件通知审阅者已准备好需评审的内容，他们将单击邮件中的链接，转到 Microsoft 365 合规中心内“**记录管理**”中的“**处置**”页面。</span><span class="sxs-lookup"><span data-stu-id="996be-207">When a reviewer is notified by email that content is ready to review, they can click a link in the email that takes them directly to the **Disposition** page from **Records management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="996be-208">在这个页面中，审阅者可以查看每个保留标签有多少个项目正在等待处置，“**类型**”显示为“**挂起的处置**”。</span><span class="sxs-lookup"><span data-stu-id="996be-208">There, the reviewers can see how many items for each retention label are waiting disposition with the **Type** displaying **Pending disposition**.</span></span> <span data-ttu-id="996be-209">然后，他们选择一个保留标签并 **在新窗口中打开** 以查看带有该标签的所有内容：</span><span class="sxs-lookup"><span data-stu-id="996be-209">They then select a retention label, and **Open in new window** to see all content with that label:</span></span>

![在新窗口中打开以进行处置评审](../media/open-in-new-window.png)

<span data-ttu-id="996be-211">在“**挂起的处置**”页面上，他们会看到该标签的所有挂起的处置。</span><span class="sxs-lookup"><span data-stu-id="996be-211">From the **Pending dispositions** page, they see all pending dispositions for that label.</span></span> <span data-ttu-id="996be-212">选择一个或多个项目后，他们可以使用迷你预览窗格以及“**来源**”、“**详细信息**”和“**历史记录**”选项卡来检查内容，然后再对其执行操作：</span><span class="sxs-lookup"><span data-stu-id="996be-212">When one or more items are selected, they can use the mini-preview pane and the **Source**, **Details**, and **History** tab to inspect the content before taking action on it:</span></span>

![处置选项](../media/retention-disposition-options.png)

<span data-ttu-id="996be-214">如果你使用水平滚动条，或关闭迷你审阅窗格，则会看到更多列，其包括到期日期和处置评审阶段的名称。</span><span class="sxs-lookup"><span data-stu-id="996be-214">If you use the horizontal scroll bar, or close the min-review pane, you see more columns that include the expiry date and the name of the disposition review stage.</span></span>

<span data-ttu-id="996be-215">从所示的示例中可以看出，支持的操作包括：</span><span class="sxs-lookup"><span data-stu-id="996be-215">As you can see from the example shown, the actions supported are:</span></span> 
  
- <span data-ttu-id="996be-216">**批准处置**：</span><span class="sxs-lookup"><span data-stu-id="996be-216">**Approve disposal**:</span></span>
    - <span data-ttu-id="996be-217">当为处置评审的过渡阶段选择此操作（你已配置多个阶段）时：项目将移至下一处置阶段。</span><span class="sxs-lookup"><span data-stu-id="996be-217">When this action is selected for an interim stage of disposition review (you have configured multiple stages): The item moves to the next disposition stage.</span></span>
    - <span data-ttu-id="996be-218">如果对处置评审的最后阶段选择此操作，或者只有一个处置阶段：项目被标记为有资格永久删除。</span><span class="sxs-lookup"><span data-stu-id="996be-218">When this action is selected for the final stage of disposition review, or there is only one stage of disposition: The item is marked as eligible for permanent deletion.</span></span> <span data-ttu-id="996be-219">该删除的确切时间取决于工作量。</span><span class="sxs-lookup"><span data-stu-id="996be-219">The exact timing for that deletion depends on the workload.</span></span> <span data-ttu-id="996be-220">有关详细信息，请参阅[保留设置如何就地处理内容](retention.md#how-retention-settings-work-with-content-in-place)。</span><span class="sxs-lookup"><span data-stu-id="996be-220">For more information, see [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>
- <span data-ttu-id="996be-221">**重新标记**：</span><span class="sxs-lookup"><span data-stu-id="996be-221">**Relabel**:</span></span>
    - <span data-ttu-id="996be-222">选择此操作时，项目将退出原始标签的处置评审过程。</span><span class="sxs-lookup"><span data-stu-id="996be-222">When this action is selected, the item exits the disposition review process for the original label.</span></span> <span data-ttu-id="996be-223">然后，该项目受新选择的保留标签的保留设置所影响。</span><span class="sxs-lookup"><span data-stu-id="996be-223">The item is then subject to the retention settings of the newly selected retention label.</span></span>
- <span data-ttu-id="996be-224">**延期**：</span><span class="sxs-lookup"><span data-stu-id="996be-224">**Extend**:</span></span>
    - <span data-ttu-id="996be-225">选择此操作后，处置评审将有效暂停，直到延长期结束，然后从第一阶段开始再次触发处置评审。</span><span class="sxs-lookup"><span data-stu-id="996be-225">When this action is selected, disposition review is effectively suspended until the end of the extended period and then disposition review is triggered again from the first stage.</span></span>
- <span data-ttu-id="996be-226">**添加审阅者**：</span><span class="sxs-lookup"><span data-stu-id="996be-226">**Add reviewers**:</span></span>
    - <span data-ttu-id="996be-227">选择此操作后，系统将提示用户指定和添加其他用户以进行审阅。</span><span class="sxs-lookup"><span data-stu-id="996be-227">When this action is selected, the user is prompted to specify and add other users for review.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="996be-228">此操作不会自动向添加的用户授予[所需权限](#permissions-for-disposition)。</span><span class="sxs-lookup"><span data-stu-id="996be-228">This action doesn't automatically grant the [required permissions](#permissions-for-disposition) to the users who are added.</span></span> <span data-ttu-id="996be-229">如果他们没有这些权限，则将无法参与处置评审。</span><span class="sxs-lookup"><span data-stu-id="996be-229">If they don't have these permissions, they won't be able to participate in the disposition review.</span></span>

<span data-ttu-id="996be-230">尽管你尚无法在审核日志中搜索所采取的每项操作，但这些操作都将保存和存储下来。</span><span class="sxs-lookup"><span data-stu-id="996be-230">Each action taken is saved and stored although you can't yet search for them in the audit log.</span></span>

<span data-ttu-id="996be-231">在处置评审期间，内容从不会从原始位置移动，并且在审阅者为最终或唯一处置阶段选择此操作之前，该内容不会被标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="996be-231">During a disposition review, the content never moves from its original location, and it's not marked for permanent deletion until this action is selected by a reviewer for the final or only disposition stage.</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="996be-232">处置记录</span><span class="sxs-lookup"><span data-stu-id="996be-232">Disposition of records</span></span>

<span data-ttu-id="996be-233">使用“**记录管理**”页面的“**处置**”选项卡识别：</span><span class="sxs-lookup"><span data-stu-id="996be-233">Use the **Disposition** tab from the **Records management** page to identify:</span></span>

- <span data-ttu-id="996be-234">处置审阅后删除的项目。</span><span class="sxs-lookup"><span data-stu-id="996be-234">Items deleted as a result of a disposition review.</span></span>
- <span data-ttu-id="996be-235">标记为保留期限结束后自动删除的记录或法规记录的项目。</span><span class="sxs-lookup"><span data-stu-id="996be-235">Items marked as a record or regulatory record that were automatically deleted at the end of their retention period.</span></span>

<span data-ttu-id="996be-236">这些项目在 **类型** 列中的 **已处置记录** 里显示。</span><span class="sxs-lookup"><span data-stu-id="996be-236">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="996be-237">例如：</span><span class="sxs-lookup"><span data-stu-id="996be-237">For example:</span></span>

![未经处置评审即被处置的项目](../media/records-disposed2.png)

<span data-ttu-id="996be-239">在“**已处置项目**”选项卡中显示的项目将在处置后最多保留 7 年，在此期间，每条记录的上限为一百万个项目。</span><span class="sxs-lookup"><span data-stu-id="996be-239">Items that are shown in the **Disposed Items** tab are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="996be-240">如果看到 **计数** 数字接近一百万这一限制，并且需要对记录进行处置证明，请联系 [Microsoft 支持](../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="996be-240">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>

> [!NOTE]
> <span data-ttu-id="996be-241">此功能使用 [统一审核日志](search-the-audit-log-in-security-and-compliance.md) 中的信息，因此需要允许审核以使其 [启动且可搜索](turn-audit-log-search-on-or-off.md)，以便捕获相应的事件。</span><span class="sxs-lookup"><span data-stu-id="996be-241">This functionality uses information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="996be-242">要审核标记为记录或法规记录的已删除项目，请在“**文件和页面活动**”类别中搜索“**已删除的标记为记录的文件**”。</span><span class="sxs-lookup"><span data-stu-id="996be-242">For auditing of deleted items that were marked as records or regulatory records, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="996be-243">此审核事件适用于文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="996be-243">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="996be-244">筛选和导出视图</span><span class="sxs-lookup"><span data-stu-id="996be-244">Filter and export the views</span></span>

<span data-ttu-id="996be-245">从 **处置** 页面选择保留标签时，**待处置** 选项卡（如果适用）和 **已处置项目** 选项卡可用于筛选视图，帮助更轻松地查找项目。</span><span class="sxs-lookup"><span data-stu-id="996be-245">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span>

<span data-ttu-id="996be-246">对于待处置的，时间范围以终止日期为准。</span><span class="sxs-lookup"><span data-stu-id="996be-246">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="996be-247">对于已处置的项目，时间范围以删除日期为准。</span><span class="sxs-lookup"><span data-stu-id="996be-247">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="996be-248">可将任意视图中项目的相关信息导出为 .csv 文件，然后可使用 Excel 对其进行排序和管理。</span><span class="sxs-lookup"><span data-stu-id="996be-248">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel.</span></span>
