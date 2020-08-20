---
title: 记录管理
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 通过 Microsoft 365 中的记录管理，你可以将保留计划应用到文件计划中，以管理保留、记录声明和处置。
ms.openlocfilehash: c2ff344d22286fcd865aa08344389dad6334d48d
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778320"
---
# <a name="learn-about-records-management"></a><span data-ttu-id="fbc74-103">了解记录管理</span><span class="sxs-lookup"><span data-stu-id="fbc74-103">Learn about records management</span></span>

><span data-ttu-id="fbc74-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="fbc74-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="fbc74-105">所有类型的组织都需要一个记录管理解决方案跨公司数据管理法规、法律和业务关键记录。</span><span class="sxs-lookup"><span data-stu-id="fbc74-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="fbc74-106">Microsoft 365 中的记录管理有助于组织管理其法律义务，提供证明遵守法规的能力，并通过定期处置不再需要保留、不再具有价值或不再需要用于业务目的的项目来提高效率。</span><span class="sxs-lookup"><span data-stu-id="fbc74-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="fbc74-107">请使用以下功能支持 Microsoft 365 中的记录管理解决方案：</span><span class="sxs-lookup"><span data-stu-id="fbc74-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="fbc74-108">**将内容标记为记录**。</span><span class="sxs-lookup"><span data-stu-id="fbc74-108">**Label content as a record**.</span></span> <span data-ttu-id="fbc74-109">创建并配置将内容标记为[记录](#records)的保留标签，该类标签随后可由用户应用，或通过标识敏感信息、关键字或内容类型自动应用。</span><span class="sxs-lookup"><span data-stu-id="fbc74-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="fbc74-110">**使用文件计划迁移和管理保留要求**。</span><span class="sxs-lookup"><span data-stu-id="fbc74-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="fbc74-111">通过使用[文件计划](file-plan-manager.md)，可将现有保留计划引入 Microsoft 365，或者构建一个新的保留计划来增强管理功能。</span><span class="sxs-lookup"><span data-stu-id="fbc74-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="fbc74-112">**使用保留标签配置保留和删除设置**。</span><span class="sxs-lookup"><span data-stu-id="fbc74-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="fbc74-113">根据各种因素（包括上次修改日期或上次创建日期）配置有关保留期和操作的[保留标签](retention.md#retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="fbc74-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="fbc74-114">使用[基于事件的保留](event-driven-retention.md)，**在事件发生时启动不同的保留期**。</span><span class="sxs-lookup"><span data-stu-id="fbc74-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="fbc74-115">使用[处置评审](disposition.md#disposition-reviews)和[记录删除](disposition.md#disposition-of-records)证明**审核并验证处置**。</span><span class="sxs-lookup"><span data-stu-id="fbc74-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="fbc74-116">使用[导出选项](disposition.md#filter-and-export-the-views)**导出有关所有已处置项的信息**。</span><span class="sxs-lookup"><span data-stu-id="fbc74-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="fbc74-117">为组织中的记录管理器功能**设置特定权限**，以便[具有正确的访问权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fbc74-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="fbc74-118">借助这些功能，你可以将组织的保留计划和要求合并到用以管理保留、记录声明和处置的记录管理解决方案中，从而支持完整的内容生命周期。</span><span class="sxs-lookup"><span data-stu-id="fbc74-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="fbc74-119">除了阅读联机文档，你还可以收听有关记录管理的[网络研讨会录制内容](https://aka.ms/MIPC/Video-RecordsManagementWebinar)并下载随附的[常见问题幻灯片组](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)，这种方法可能也会非常有用。</span><span class="sxs-lookup"><span data-stu-id="fbc74-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="fbc74-120">记录</span><span class="sxs-lookup"><span data-stu-id="fbc74-120">Records</span></span>

<span data-ttu-id="fbc74-121">当内容被标记为记录时：</span><span class="sxs-lookup"><span data-stu-id="fbc74-121">When content is marked as a record:</span></span>

- <span data-ttu-id="fbc74-122">会针对[允许或阻止对记录项进行的操作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)施加限制。</span><span class="sxs-lookup"><span data-stu-id="fbc74-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="fbc74-123">记录了有关该项的其他活动。</span><span class="sxs-lookup"><span data-stu-id="fbc74-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="fbc74-124">保留期结束时将其删除时，拥有处置证明。</span><span class="sxs-lookup"><span data-stu-id="fbc74-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="fbc74-125">使用[保留标签](retention.md#retention-labels)将内容标记为记录。</span><span class="sxs-lookup"><span data-stu-id="fbc74-125">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="fbc74-126">你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="fbc74-126">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="fbc74-127">通过使用保留标签来将内容标记为记录，可在 Microsoft 365 环境中实现单一一致的记录管理策略。</span><span class="sxs-lookup"><span data-stu-id="fbc74-127">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="fbc74-128">比较对允许或阻止的操作的限制</span><span class="sxs-lookup"><span data-stu-id="fbc74-128">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="fbc74-129">使用以下表格识别应用标准保留标签和将内容标记为记录的保留标签后，对内容施加的限制。</span><span class="sxs-lookup"><span data-stu-id="fbc74-129">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="fbc74-130">标准保留标签具有保留设置和操作，但不会将内容标记为记录。</span><span class="sxs-lookup"><span data-stu-id="fbc74-130">A standard retention label has retention settings and actions but doesn't mark content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="fbc74-131">为确保完整性，表格包括已锁定和已解锁的记录列，适用于 SharePoint 和 OneDrive，但不适用于 Exchange。</span><span class="sxs-lookup"><span data-stu-id="fbc74-131">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="fbc74-132">锁定和解锁记录的功能使用 Exchange 项目不支持的[记录版本控制](record-versioning.md)功能。</span><span class="sxs-lookup"><span data-stu-id="fbc74-132">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="fbc74-133">因此，对于标记为记录的所有 Exchange 项目，该行为会映射到**记录 - 已锁定**列，而**记录 - 已解锁列**则不相关。</span><span class="sxs-lookup"><span data-stu-id="fbc74-133">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="fbc74-134">操作</span><span class="sxs-lookup"><span data-stu-id="fbc74-134">Action</span></span>| <span data-ttu-id="fbc74-135">保留标签</span><span class="sxs-lookup"><span data-stu-id="fbc74-135">Retention label</span></span> |<span data-ttu-id="fbc74-136">记录 - 已锁定</span><span class="sxs-lookup"><span data-stu-id="fbc74-136">Record - locked</span></span>| <span data-ttu-id="fbc74-137">记录 - 已解锁</span><span class="sxs-lookup"><span data-stu-id="fbc74-137">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fbc74-138">编辑内容</span><span class="sxs-lookup"><span data-stu-id="fbc74-138">Edit contents</span></span>|<span data-ttu-id="fbc74-139">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-139">Allowed</span></span> | <span data-ttu-id="fbc74-140">**阻止**</span><span class="sxs-lookup"><span data-stu-id="fbc74-140">**Blocked**</span></span> | <span data-ttu-id="fbc74-141">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-141">Allowed</span></span>|
|<span data-ttu-id="fbc74-142">编辑属性（包括重命名）</span><span class="sxs-lookup"><span data-stu-id="fbc74-142">Edit properties, including rename</span></span>|<span data-ttu-id="fbc74-143">Allowed</span><span class="sxs-lookup"><span data-stu-id="fbc74-143">Allowed</span></span> |<span data-ttu-id="fbc74-144">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-144">Allowed</span></span> | <span data-ttu-id="fbc74-145">Allowed</span><span class="sxs-lookup"><span data-stu-id="fbc74-145">Allowed</span></span>|
|<span data-ttu-id="fbc74-146">删除</span><span class="sxs-lookup"><span data-stu-id="fbc74-146">Delete</span></span>|<span data-ttu-id="fbc74-147">允许 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fbc74-147">Allowed <sup>1</sup></span></span> |<span data-ttu-id="fbc74-148">**阻止**</span><span class="sxs-lookup"><span data-stu-id="fbc74-148">**Blocked**</span></span> | <span data-ttu-id="fbc74-149">**阻止**</span><span class="sxs-lookup"><span data-stu-id="fbc74-149">**Blocked**</span></span>|
|<span data-ttu-id="fbc74-150">复制</span><span class="sxs-lookup"><span data-stu-id="fbc74-150">Copy</span></span>|<span data-ttu-id="fbc74-151">Allowed</span><span class="sxs-lookup"><span data-stu-id="fbc74-151">Allowed</span></span> |<span data-ttu-id="fbc74-152">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-152">Allowed</span></span> | <span data-ttu-id="fbc74-153">Allowed</span><span class="sxs-lookup"><span data-stu-id="fbc74-153">Allowed</span></span>|
|<span data-ttu-id="fbc74-154">在容器 <sup>2</sup> 中移动</span><span class="sxs-lookup"><span data-stu-id="fbc74-154">Move within container <sup>2</sup></span></span>|<span data-ttu-id="fbc74-155">Allowed</span><span class="sxs-lookup"><span data-stu-id="fbc74-155">Allowed</span></span> |<span data-ttu-id="fbc74-156">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-156">Allowed</span></span> | <span data-ttu-id="fbc74-157">Allowed</span><span class="sxs-lookup"><span data-stu-id="fbc74-157">Allowed</span></span>|
|<span data-ttu-id="fbc74-158">围绕容器 <sup>2</sup> 移动</span><span class="sxs-lookup"><span data-stu-id="fbc74-158">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="fbc74-159">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-159">Allowed</span></span> |<span data-ttu-id="fbc74-160">如果从未解锁，则允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-160">Allowed if never unlocked</span></span> | <span data-ttu-id="fbc74-161">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-161">Allowed</span></span>|
|<span data-ttu-id="fbc74-162">打开/读取</span><span class="sxs-lookup"><span data-stu-id="fbc74-162">Open/Read</span></span>|<span data-ttu-id="fbc74-163">Allowed</span><span class="sxs-lookup"><span data-stu-id="fbc74-163">Allowed</span></span> |<span data-ttu-id="fbc74-164">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-164">Allowed</span></span> | <span data-ttu-id="fbc74-165">Allowed</span><span class="sxs-lookup"><span data-stu-id="fbc74-165">Allowed</span></span>|
|<span data-ttu-id="fbc74-166">更改标签</span><span class="sxs-lookup"><span data-stu-id="fbc74-166">Change label</span></span>|<span data-ttu-id="fbc74-167">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-167">Allowed</span></span> |<span data-ttu-id="fbc74-168">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="fbc74-168">Allowed - container admin only</span></span> | <span data-ttu-id="fbc74-169">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="fbc74-169">Allowed - container admin only</span></span>|
|<span data-ttu-id="fbc74-170">删除标签</span><span class="sxs-lookup"><span data-stu-id="fbc74-170">Remove label</span></span>|<span data-ttu-id="fbc74-171">允许</span><span class="sxs-lookup"><span data-stu-id="fbc74-171">Allowed</span></span> |<span data-ttu-id="fbc74-172">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="fbc74-172">Allowed - container admin only</span></span> | <span data-ttu-id="fbc74-173">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="fbc74-173">Allowed - container admin only</span></span>|

<span data-ttu-id="fbc74-174">页脚：</span><span class="sxs-lookup"><span data-stu-id="fbc74-174">Footnotes:</span></span>

<span data-ttu-id="fbc74-175"><sup>1</sup>OneDrive 和 Exchange 支持此功能，方法是在安全位置保留一份副本，但 SharePoint 阻止此功能。</span><span class="sxs-lookup"><span data-stu-id="fbc74-175"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="fbc74-176">向用户发送一条消息，询问用户是否尝试删除 SharePoint 中带标记的文档：</span><span class="sxs-lookup"><span data-stu-id="fbc74-176">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![指明项未从 SharePoint 中删除的消息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="fbc74-178"><sup>2</sup>容器包括 SharePoint 文档库和 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="fbc74-178"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fbc74-179">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fbc74-179">Next steps</span></span>

<span data-ttu-id="fbc74-180">请参阅[记录管理入门](get-started-with-records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="fbc74-180">See [Get started with records management](get-started-with-records-management.md).</span></span>

<span data-ttu-id="fbc74-181">若要将内容标记为记录，请参阅[使用保留标签声明记录](declare-records.md)。</span><span class="sxs-lookup"><span data-stu-id="fbc74-181">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
