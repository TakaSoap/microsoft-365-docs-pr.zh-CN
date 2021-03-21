---
title: Microsoft 365 中的记录管理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 通过 Microsoft 365 中的记录管理，你可以将保留计划应用到文件计划中，以管理保留、记录声明和处置。
ms.openlocfilehash: 4f07732e403d711e2fa89bfb7c61c9eadfb2bd0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926180"
---
# <a name="learn-about-records-management-in-microsoft-365"></a><span data-ttu-id="ee5db-103">了解 Microsoft 365 中的记录管理</span><span class="sxs-lookup"><span data-stu-id="ee5db-103">Learn about records management in Microsoft 365</span></span>

><span data-ttu-id="ee5db-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="ee5db-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="ee5db-105">所有类型的组织都需要一个记录管理解决方案跨公司数据管理法规、法律和业务关键记录。</span><span class="sxs-lookup"><span data-stu-id="ee5db-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="ee5db-106">Microsoft 365 中的记录管理有助于组织管理其法律义务，提供证明遵守法规的能力，并通过定期处置不再需要保留、不再具有价值或不再需要用于业务目的的项目来提高效率。</span><span class="sxs-lookup"><span data-stu-id="ee5db-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="ee5db-107">请使用以下功能支持 Microsoft 365 中的记录管理解决方案：</span><span class="sxs-lookup"><span data-stu-id="ee5db-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="ee5db-108">**将内容标记为记录**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-108">**Label content as a record**.</span></span> <span data-ttu-id="ee5db-109">创建并配置将内容标记为[记录](#records)的保留标签，该类标签随后可由用户应用，或通过标识敏感信息、关键字或内容类型自动应用。</span><span class="sxs-lookup"><span data-stu-id="ee5db-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="ee5db-110">**使用文件计划迁移和管理保留要求**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="ee5db-111">通过使用[文件计划](file-plan-manager.md)，可将现有保留计划引入 Microsoft 365，或者构建一个新的保留计划来增强管理功能。</span><span class="sxs-lookup"><span data-stu-id="ee5db-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="ee5db-112">**使用保留标签配置保留和删除设置**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="ee5db-113">根据各种因素（包括上次修改日期或上次创建日期）配置有关保留期和操作的[保留标签](retention.md#retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="ee5db-114">使用 [基于事件的保留](event-driven-retention.md)，**在事件发生时启动不同的保留期**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="ee5db-115">使用 [处置评审](disposition.md#disposition-reviews)和 [记录删除](disposition.md#disposition-of-records)证明 **审核并验证处置**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="ee5db-116">使用 [导出选项](disposition.md#filter-and-export-the-views)**导出有关所有已处置项的信息**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="ee5db-117">为组织中的记录管理器功能 **设置特定权限**，以便 [具有正确的访问权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="ee5db-118">借助这些功能，你可以将组织的保留计划和要求合并到用以管理保留、记录声明和处置的记录管理解决方案中，从而支持完整的内容生命周期。</span><span class="sxs-lookup"><span data-stu-id="ee5db-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="ee5db-119">除了阅读联机文档，你还可以收听有关记录管理的[网络研讨会录制内容](https://aka.ms/MIPC/Video-RecordsManagementWebinar)并下载随附的[常见问题幻灯片组](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)，这种方法可能也会非常有用。</span><span class="sxs-lookup"><span data-stu-id="ee5db-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="ee5db-120">记录</span><span class="sxs-lookup"><span data-stu-id="ee5db-120">Records</span></span>

<span data-ttu-id="ee5db-121">将内容声明为记录时：</span><span class="sxs-lookup"><span data-stu-id="ee5db-121">When content is declared a record:</span></span>

- <span data-ttu-id="ee5db-122">会针对[允许或阻止对记录项进行的操作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)施加限制。</span><span class="sxs-lookup"><span data-stu-id="ee5db-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="ee5db-123">记录了有关该项的其他活动。</span><span class="sxs-lookup"><span data-stu-id="ee5db-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="ee5db-124">保留期结束时将其删除时，拥有处置证明。</span><span class="sxs-lookup"><span data-stu-id="ee5db-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="ee5db-125">使用 [保留标签](retention.md#retention-labels)将内容标记为 **记录** 或 **管理记录**。</span><span class="sxs-lookup"><span data-stu-id="ee5db-125">You use [retention labels](retention.md#retention-labels) to mark content as a **record**, or a **regulatory record**.</span></span> <span data-ttu-id="ee5db-126">这两者之间的差异将在下一节中介绍。</span><span class="sxs-lookup"><span data-stu-id="ee5db-126">The difference between these two are explained in the next section.</span></span> <span data-ttu-id="ee5db-127">你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录或合规性记录的内容。</span><span class="sxs-lookup"><span data-stu-id="ee5db-127">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record or a regulatory record.</span></span>

<span data-ttu-id="ee5db-128">通过使用保留标签来声明记录，可在 Microsoft 365 环境中实现单一一致的记录管理策略。</span><span class="sxs-lookup"><span data-stu-id="ee5db-128">By using retention labels to declare records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="ee5db-129">比较对允许或阻止的操作的限制</span><span class="sxs-lookup"><span data-stu-id="ee5db-129">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="ee5db-130">使用以下表格识别应用标准保留标签和将内容标记为记录或合规性记录的保留标签后，对内容施加的限制。</span><span class="sxs-lookup"><span data-stu-id="ee5db-130">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record or regulatory record.</span></span> 

<span data-ttu-id="ee5db-131">标准保留标签具有保留设置和操作，但不会将内容标记为记录或合规性记录。</span><span class="sxs-lookup"><span data-stu-id="ee5db-131">A standard retention label has retention settings and actions but doesn't mark content as a record or a regulatory record.</span></span>

>[!NOTE] 
> <span data-ttu-id="ee5db-132">为确保完整性，表格包括已锁定和已解锁的记录列，适用于 SharePoint 和 OneDrive，但不适用于 Exchange。</span><span class="sxs-lookup"><span data-stu-id="ee5db-132">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="ee5db-133">锁定和解锁记录的功能使用 Exchange 项目不支持的[记录版本控制](record-versioning.md)功能。</span><span class="sxs-lookup"><span data-stu-id="ee5db-133">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="ee5db-134">因此，对于标记为记录的所有 Exchange 项目，该行为会映射到 **记录 - 已锁定** 列，而 **记录 - 已解锁列** 则不相关。</span><span class="sxs-lookup"><span data-stu-id="ee5db-134">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="ee5db-135">操作</span><span class="sxs-lookup"><span data-stu-id="ee5db-135">Action</span></span>| <span data-ttu-id="ee5db-136">保留标签</span><span class="sxs-lookup"><span data-stu-id="ee5db-136">Retention label</span></span> |<span data-ttu-id="ee5db-137">记录 - 已锁定</span><span class="sxs-lookup"><span data-stu-id="ee5db-137">Record - locked</span></span>| <span data-ttu-id="ee5db-138">记录 - 已解锁</span><span class="sxs-lookup"><span data-stu-id="ee5db-138">Record - unlocked</span></span>| <span data-ttu-id="ee5db-139">合规性记录</span><span class="sxs-lookup"><span data-stu-id="ee5db-139">Regulatory record</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee5db-140">编辑内容</span><span class="sxs-lookup"><span data-stu-id="ee5db-140">Edit contents</span></span>|<span data-ttu-id="ee5db-141">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-141">Allowed</span></span> | <span data-ttu-id="ee5db-142">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-142">**Blocked**</span></span> | <span data-ttu-id="ee5db-143">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-143">Allowed</span></span> | <span data-ttu-id="ee5db-144">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-144">**Blocked**</span></span>|
|<span data-ttu-id="ee5db-145">编辑属性（包括重命名）</span><span class="sxs-lookup"><span data-stu-id="ee5db-145">Edit properties, including rename</span></span>|<span data-ttu-id="ee5db-146">Allowed</span><span class="sxs-lookup"><span data-stu-id="ee5db-146">Allowed</span></span> |<span data-ttu-id="ee5db-147">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-147">Allowed</span></span> | <span data-ttu-id="ee5db-148">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-148">Allowed</span></span>| <span data-ttu-id="ee5db-149">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-149">**Blocked**</span></span>|
|<span data-ttu-id="ee5db-150">删除</span><span class="sxs-lookup"><span data-stu-id="ee5db-150">Delete</span></span>|<span data-ttu-id="ee5db-151">允许 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ee5db-151">Allowed <sup>1</sup></span></span> |<span data-ttu-id="ee5db-152">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-152">**Blocked**</span></span> |<span data-ttu-id="ee5db-153">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-153">**Blocked**</span></span>| <span data-ttu-id="ee5db-154">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-154">**Blocked**</span></span>|
|<span data-ttu-id="ee5db-155">复制</span><span class="sxs-lookup"><span data-stu-id="ee5db-155">Copy</span></span>|<span data-ttu-id="ee5db-156">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-156">Allowed</span></span> |<span data-ttu-id="ee5db-157">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-157">Allowed</span></span> | <span data-ttu-id="ee5db-158">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-158">Allowed</span></span>| <span data-ttu-id="ee5db-159">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-159">Allowed</span></span>|
|<span data-ttu-id="ee5db-160">在容器 <sup>2</sup> 中移动</span><span class="sxs-lookup"><span data-stu-id="ee5db-160">Move within container <sup>2</sup></span></span>|<span data-ttu-id="ee5db-161">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-161">Allowed</span></span> |<span data-ttu-id="ee5db-162">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-162">Allowed</span></span> | <span data-ttu-id="ee5db-163">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-163">Allowed</span></span>| <span data-ttu-id="ee5db-164">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-164">Allowed</span></span>|
|<span data-ttu-id="ee5db-165">围绕容器 <sup>2</sup> 移动</span><span class="sxs-lookup"><span data-stu-id="ee5db-165">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="ee5db-166">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-166">Allowed</span></span> |<span data-ttu-id="ee5db-167">如果从未解锁，则允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-167">Allowed if never unlocked</span></span> | <span data-ttu-id="ee5db-168">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-168">**Blocked**</span></span> | <span data-ttu-id="ee5db-169">**阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-169">**Blocked**</span></span>|
|<span data-ttu-id="ee5db-170">打开/读取</span><span class="sxs-lookup"><span data-stu-id="ee5db-170">Open/Read</span></span>|<span data-ttu-id="ee5db-171">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-171">Allowed</span></span> |<span data-ttu-id="ee5db-172">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-172">Allowed</span></span> | <span data-ttu-id="ee5db-173">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-173">Allowed</span></span>| <span data-ttu-id="ee5db-174">Allowed</span><span class="sxs-lookup"><span data-stu-id="ee5db-174">Allowed</span></span>|
|<span data-ttu-id="ee5db-175">更改标签</span><span class="sxs-lookup"><span data-stu-id="ee5db-175">Change label</span></span>|<span data-ttu-id="ee5db-176">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-176">Allowed</span></span> |<span data-ttu-id="ee5db-177">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="ee5db-177">Allowed - container admin only</span></span> | <span data-ttu-id="ee5db-178">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="ee5db-178">Allowed - container admin only</span></span>| <span data-ttu-id="ee5db-179">**已阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-179">**Blocked**</span></span>
|<span data-ttu-id="ee5db-180">删除标签</span><span class="sxs-lookup"><span data-stu-id="ee5db-180">Remove label</span></span>|<span data-ttu-id="ee5db-181">允许</span><span class="sxs-lookup"><span data-stu-id="ee5db-181">Allowed</span></span> |<span data-ttu-id="ee5db-182">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="ee5db-182">Allowed - container admin only</span></span> | <span data-ttu-id="ee5db-183">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="ee5db-183">Allowed - container admin only</span></span>| <span data-ttu-id="ee5db-184">**已阻止**</span><span class="sxs-lookup"><span data-stu-id="ee5db-184">**Blocked**</span></span>

<span data-ttu-id="ee5db-185">页脚：</span><span class="sxs-lookup"><span data-stu-id="ee5db-185">Footnotes:</span></span>

<span data-ttu-id="ee5db-186"><sup>1</sup>OneDrive 和 Exchange 支持此功能，方法是在安全位置保留一份副本，但 SharePoint 阻止此功能。</span><span class="sxs-lookup"><span data-stu-id="ee5db-186"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="ee5db-187">当你将保留标签应用于具有文档附件的列表项时，该文档不会继承保留设置，因此可以从列表项中删除。</span><span class="sxs-lookup"><span data-stu-id="ee5db-187">When you apply a retention label to a list item that has a document attachment, that document doesn't inherit the retention settings and can be deleted from the list item.</span></span> <span data-ttu-id="ee5db-188">相比之下，如果该列表项被声明为带有保留标签的记录，则文档附件将继承保留设置，并且无法删除。</span><span class="sxs-lookup"><span data-stu-id="ee5db-188">In comparison, if that list item was declared a record with a retention label, the document attachment would inherit the retention settings and couldn't be deleted.</span></span> 

<span data-ttu-id="ee5db-189"><sup>2</sup> 个容器包括 SharePoint 文档库、OneDrive 帐户和 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="ee5db-189"><sup>2</sup> Containers include SharePoint document libraries, OneDrive accounts, and Exchange mailboxes.</span></span>

>[!IMPORTANT] 
> <span data-ttu-id="ee5db-190">合规性记录的最重要的差别是，在应用到内容后，任何人（哪怕是是全局管理员）都无法删除标签。</span><span class="sxs-lookup"><span data-stu-id="ee5db-190">The most important difference for a regulatory record is that after it is applied to content, nobody, not even a global administrator, can remove the label.</span></span> 
>
> <span data-ttu-id="ee5db-191">为合规性记录配置的保留标签还具有以下管理员限制：</span><span class="sxs-lookup"><span data-stu-id="ee5db-191">Retention labels configured for regulatory records also have the following admin restrictions:</span></span>
> - <span data-ttu-id="ee5db-192">保存标签后，不能缩短保留期，只能对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="ee5db-192">The retention period can't be made shorter after the label is saved, only extended.</span></span>
> - <span data-ttu-id="ee5db-193">自动标记策略不支持这些标签，必须使用[保留标签策略](create-apply-retention-labels.md)应用这些标签。</span><span class="sxs-lookup"><span data-stu-id="ee5db-193">These labels aren't supported by auto-labeling policies, and must be applied by using [retention label policies](create-apply-retention-labels.md).</span></span> 
>
> <span data-ttu-id="ee5db-194">此外，合规性标签无法应用于在 SharePoint 中签出的文档。</span><span class="sxs-lookup"><span data-stu-id="ee5db-194">In addition, a regulatory label can't be applied to a document that's checked out in SharePoint.</span></span>
> 
> <span data-ttu-id="ee5db-195">由于存在这些限制和不可逆操作，在针对保留标签选择此选项之前，请确保自己确实需要使用合规性记录。</span><span class="sxs-lookup"><span data-stu-id="ee5db-195">Because of the restrictions and irreversible actions, make sure you really do need to use regulatory records before you select this option for your retention labels.</span></span> <span data-ttu-id="ee5db-196">为帮助防止意外配置，默认情况下该选项不可用，但必须先使用 PowerShell 启用。</span><span class="sxs-lookup"><span data-stu-id="ee5db-196">To help prevent accidental configuration, this option is not available by default but must first be enabled by using PowerShell.</span></span> <span data-ttu-id="ee5db-197">有关说明，请参阅[使用保留标签 声明记录](declare-records.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-197">Instructions are included in [Declare records by using retention labels](declare-records.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="ee5db-198">配置指南</span><span class="sxs-lookup"><span data-stu-id="ee5db-198">Configuration guidance</span></span>

<span data-ttu-id="ee5db-199">请参阅[记录管理入门](get-started-with-records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-199">See [Get started with records management](get-started-with-records-management.md).</span></span>

<span data-ttu-id="ee5db-200">若要将内容标记为记录，请参阅[使用保留标签声明记录](declare-records.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5db-200">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>