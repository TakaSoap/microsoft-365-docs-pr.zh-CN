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
description: 无论是使用处置评审还是根据配置的设置自动删除内容，都可监视和管理内容的处置。
ms.openlocfilehash: a0fd71aa1eb7c0a7eff97e783f4b0dfb8a50a915
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262228"
---
# <a name="disposition-of-content"></a><span data-ttu-id="f906c-103">内容的处置</span><span class="sxs-lookup"><span data-stu-id="f906c-103">Disposition of content</span></span>

><span data-ttu-id="f906c-104">*[Microsoft 365 安全性与合规性的许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="f906c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f906c-105">使用 Microsoft 365 合规中心中 **记录管理** 中的 **处置** 选项卡来管理处置评审，并查看在保留期结束时自动删除 [记录](records-management.md#records)。</span><span class="sxs-lookup"><span data-stu-id="f906c-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="f906c-106">查看内容处置的前提条件</span><span class="sxs-lookup"><span data-stu-id="f906c-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="f906c-107">若要管理处置评审并确认已删除记录，必须具有足够的权限，并且必须启用审核。</span><span class="sxs-lookup"><span data-stu-id="f906c-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="f906c-108">处置权限</span><span class="sxs-lookup"><span data-stu-id="f906c-108">Permissions for disposition</span></span>

<span data-ttu-id="f906c-109">若要成功访问 Microsoft 365 合规中心中的 **处置** 选项卡，用户必须拥有 **处置管理** 管理员角色。</span><span class="sxs-lookup"><span data-stu-id="f906c-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="f906c-110">该角色包含在默认管理员角色组中， **合规性管理员**和 **合规性数据管理员**。</span><span class="sxs-lookup"><span data-stu-id="f906c-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="f906c-111">若要向用户授予所需的处置管理角色，可将其添加到这些默认角色组中，或创建自定义角色组（例如命名为 "处置审阅者"），并向此组授予处置管理角色。</span><span class="sxs-lookup"><span data-stu-id="f906c-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="f906c-112">即使是全局管理员也需要被授予**处置管理**角色。</span><span class="sxs-lookup"><span data-stu-id="f906c-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="f906c-113">有关说明，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f906c-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="f906c-114">启用审核</span><span class="sxs-lookup"><span data-stu-id="f906c-114">Enable auditing</span></span>

<span data-ttu-id="f906c-115">确保至少在第一次处置操作之前一天已启用审核。</span><span class="sxs-lookup"><span data-stu-id="f906c-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="f906c-116">有关详细信息，请参阅[在 Office 365 安全&amp;合规中心](search-the-audit-log-in-security-and-compliance.md)内搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="f906c-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="f906c-117">处置评审</span><span class="sxs-lookup"><span data-stu-id="f906c-117">Disposition reviews</span></span>

<span data-ttu-id="f906c-118">内容到达其保持期结束时，有几个原因可能会让你审查该内容来确定是否可以安全地删除（"已处置"）。</span><span class="sxs-lookup"><span data-stu-id="f906c-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="f906c-119">例如，你可能需要：</span><span class="sxs-lookup"><span data-stu-id="f906c-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="f906c-120">在诉讼或审计的事件中，暂停对相关内容的删除。</span><span class="sxs-lookup"><span data-stu-id="f906c-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="f906c-121">如果内容有研究或历史价值，则从处置列表中删除该内容存储至档案中。</span><span class="sxs-lookup"><span data-stu-id="f906c-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="f906c-122">为内容指定不同的保留期，可能是因为原始保留设置是临时或暂时的解决方案。</span><span class="sxs-lookup"><span data-stu-id="f906c-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="f906c-123">将内容返回至客户端，或将其转移到其他组织。</span><span class="sxs-lookup"><span data-stu-id="f906c-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="f906c-124">在保持期结束时触发处置评审时：</span><span class="sxs-lookup"><span data-stu-id="f906c-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="f906c-125">你选择的人员将收到一封电子邮件通知，告知他们有内容需要审查。</span><span class="sxs-lookup"><span data-stu-id="f906c-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="f906c-126">这些审阅者可以是单个用户或启用了邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="f906c-126">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="f906c-127">注意，通知是每周发送一次。</span><span class="sxs-lookup"><span data-stu-id="f906c-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="f906c-128">审阅者转到 Microsoft 365 合规中心的 **处置** 选项卡审查内容，并决定是否要将其永久删除、延长其保留期或应用不同的保留标签。</span><span class="sxs-lookup"><span data-stu-id="f906c-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="f906c-129">处置评审可以包括Exchange邮箱、SharePoint网站、OneDrive账户和Microsoft 365组中的内容。</span><span class="sxs-lookup"><span data-stu-id="f906c-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="f906c-130">仅在审阅者选择永久删除内容后，才会删除在这些位置等候处置审核的内容。</span><span class="sxs-lookup"><span data-stu-id="f906c-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="f906c-131">一个邮箱必须有至少10MB的数据来支持处置评审。</span><span class="sxs-lookup"><span data-stu-id="f906c-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="f906c-132">可在**概述**选项卡中查看所有待处置的概述。例如：</span><span class="sxs-lookup"><span data-stu-id="f906c-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![记录管理概述中的待处置](../media/dispositions-overview.png)

<span data-ttu-id="f906c-134">选择**查看所有待处置**后，则转到**处置**页面。</span><span class="sxs-lookup"><span data-stu-id="f906c-134">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="f906c-135">例如：</span><span class="sxs-lookup"><span data-stu-id="f906c-135">For example:</span></span>

![Microsoft 365 合规中心内的策略页面](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="f906c-137">处置评审的工作流</span><span class="sxs-lookup"><span data-stu-id="f906c-137">Workflow for a disposition review</span></span>

<span data-ttu-id="f906c-138">下图显示了发布保留标签后再由用户手动应用时处置评审的基本工作流。</span><span class="sxs-lookup"><span data-stu-id="f906c-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="f906c-139">此外，为处置评审配置的保留标签可自动运用于内容。</span><span class="sxs-lookup"><span data-stu-id="f906c-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![显示处置工作流的图表](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="f906c-141">保持期结束时触发处置评审是一个配置选项，仅保留标签才能使用。</span><span class="sxs-lookup"><span data-stu-id="f906c-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="f906c-142">此选项在保留策略中不可用。</span><span class="sxs-lookup"><span data-stu-id="f906c-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="f906c-143">有关这两种保留解决方案的详细信息，请参阅[了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="f906c-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="f906c-144">来自 **定义保留标签的保留设置** 页面：</span><span class="sxs-lookup"><span data-stu-id="f906c-144">From the **Define retention settings** page for a retention label:</span></span>

![标签的保留设置](../media/disposition-review-option.png)
 
<span data-ttu-id="f906c-146">选择此 **触发处置审核** 选项后，可在向导的下一页上指定处置审阅者：</span><span class="sxs-lookup"><span data-stu-id="f906c-146">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![指定处置审阅者](../media/disposition-reviewers.png)

<span data-ttu-id="f906c-148">对审阅者指定一个用户或邮件启用安全组。</span><span class="sxs-lookup"><span data-stu-id="f906c-148">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="f906c-149">此选项不支持 Microsoft 365 组（[原 Office 365 组](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）。</span><span class="sxs-lookup"><span data-stu-id="f906c-149">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="f906c-150">查看和处置内容</span><span class="sxs-lookup"><span data-stu-id="f906c-150">Viewing and disposing of content</span></span>

<span data-ttu-id="f906c-151">通过电子邮件通知审阅者已准备好所需评论的内容时，他们将转到 Microsoft 365 合规中心中 **记录管理** 中的 **处置** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f906c-151">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f906c-152">审阅者可以查看每个保留标签中有多少项正在等待处置，然后选择一个保留标签即可查看带有该标签的所有内容。</span><span class="sxs-lookup"><span data-stu-id="f906c-152">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="f906c-153">选择保留标签后，可在 **待处置** 选项卡中查看带有该标签的所有待处置。选择一个或多个项目，然后可以在其中选择一个操作并输入评论理由：</span><span class="sxs-lookup"><span data-stu-id="f906c-153">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![处置选项](../media/retention-disposition-options.png)

<span data-ttu-id="f906c-155">从图中可以看出，支持的操作如下：</span><span class="sxs-lookup"><span data-stu-id="f906c-155">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="f906c-156">永久删除项目</span><span class="sxs-lookup"><span data-stu-id="f906c-156">Permanently delete the item</span></span>
- <span data-ttu-id="f906c-157">延长保留期</span><span class="sxs-lookup"><span data-stu-id="f906c-157">Extend the retention period</span></span>
- <span data-ttu-id="f906c-158">应用不同的保留标签</span><span class="sxs-lookup"><span data-stu-id="f906c-158">Apply a different retention label</span></span>

<span data-ttu-id="f906c-159">提供对位置和内容的权限，可使用 **位置** 列中的链接查看原始位置中的文档。</span><span class="sxs-lookup"><span data-stu-id="f906c-159">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="f906c-160">在处置评审过程中，内容永远不会从其原始位置移动，并且在审阅者选择执行此操作之前，永远不会删除该内容。</span><span class="sxs-lookup"><span data-stu-id="f906c-160">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="f906c-161">每周都会自动向审核者发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="f906c-161">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="f906c-162">此计划流程表示当内容到达其保留期末尾时，审阅者可能需要长达7天的时间才能收到内容正在等待处置的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="f906c-162">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="f906c-163">可对所有处置操作进行审核，审阅者输入的理由文本将保存并显示在 **已处置项目** 页面上的 **评论** 列中。</span><span class="sxs-lookup"><span data-stu-id="f906c-163">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="f906c-164">永久删除处置的内容需要多长时间</span><span class="sxs-lookup"><span data-stu-id="f906c-164">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="f906c-165">仅在审阅者选择永久删除内容后，才会删除等候处置审核的内容。</span><span class="sxs-lookup"><span data-stu-id="f906c-165">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="f906c-166">审阅者选择此选项时，SharePoint 网站或 OneDrive 帐户中的内容将符合[保留设置如何与内容配合到位](retention.md#how-retention-settings-work-with-content-in-place)中所描述的标准清理流程的条件。</span><span class="sxs-lookup"><span data-stu-id="f906c-166">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="f906c-167">处置记录</span><span class="sxs-lookup"><span data-stu-id="f906c-167">Disposition of records</span></span>

<span data-ttu-id="f906c-168">使用 **记录管理** 页面中的 **处置** 选项卡来识别当前需删除的记录是自动删除，或是经过处置评审后删除。</span><span class="sxs-lookup"><span data-stu-id="f906c-168">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="f906c-169">这些项目在**类型**列中的**已处置记录**里显示。</span><span class="sxs-lookup"><span data-stu-id="f906c-169">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="f906c-170">例如：</span><span class="sxs-lookup"><span data-stu-id="f906c-170">For example:</span></span>

![未经处置评审即被处置的项目](../media/records-disposed2.png)

<span data-ttu-id="f906c-172">在记录标签的 **已处置项目** 选项卡中显示的项目，在该项目被处置后最多保留7年，在此期间，每条记录的上限为一百万项。</span><span class="sxs-lookup"><span data-stu-id="f906c-172">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="f906c-173">如果看到 **计数** 数字接近一百万这一限制，并且需要对记录进行处置证明，请联系 [Microsoft 支持](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="f906c-173">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="f906c-174">此功能基于 [统一审核日志](search-the-audit-log-in-security-and-compliance.md) 中的信息，因此需要[启动并可搜索](turn-audit-log-search-on-or-off.md)审核，以便捕获相应的事件。</span><span class="sxs-lookup"><span data-stu-id="f906c-174">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="f906c-175">筛选和导出视图</span><span class="sxs-lookup"><span data-stu-id="f906c-175">Filter and export the views</span></span>

<span data-ttu-id="f906c-176">从 **处置** 页面选择保留标签时，**待处置** 选项卡（如果适用）和 **已处置项目** 选项卡可用于筛选视图，帮助更轻松地查找项目。</span><span class="sxs-lookup"><span data-stu-id="f906c-176">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="f906c-177">对于待处置的，时间范围以终止日期为准。</span><span class="sxs-lookup"><span data-stu-id="f906c-177">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="f906c-178">对于已处置的项目，时间范围以删除日期为准。</span><span class="sxs-lookup"><span data-stu-id="f906c-178">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="f906c-179">可将任意视图中的项目的信息导出为 .csv 文件，然后即可使用 Excel 对其进行排序和管理：</span><span class="sxs-lookup"><span data-stu-id="f906c-179">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![处置的导出选项](../media/retention-export-option.png)

