---
title: 了解记录
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
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解有关记录的信息，以帮助您在 Microsoft 365 中实现记录管理解决方案。
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372517"
---
# <a name="learn-about-records"></a><span data-ttu-id="dbc8e-103">了解记录</span><span class="sxs-lookup"><span data-stu-id="dbc8e-103">Learn about records</span></span>

><span data-ttu-id="dbc8e-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="dbc8e-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dbc8e-105">在 Microsoft 365 中管理记录可帮助组织遵守公司策略、法律或法规义务，同时降低风险和法律责任。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="dbc8e-106">当内容被标记为记录时：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-106">When content is marked as a record:</span></span>

- <span data-ttu-id="dbc8e-107">会针对[允许或阻止对记录项进行的操作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)施加限制。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="dbc8e-108">记录了有关该项的其他活动。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="dbc8e-109">保留期结束时将其删除时，拥有处置证明。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="dbc8e-110">使用[保留标签](retention.md#retention-labels)将内容标记为记录。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="dbc8e-111">你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="dbc8e-112">通过使用保留标签来将内容标记为记录，可在 Microsoft 365 环境中实现单一一致的记录管理策略。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="dbc8e-113">比较对允许或阻止的操作的限制</span><span class="sxs-lookup"><span data-stu-id="dbc8e-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="dbc8e-114">使用以下表格识别应用标准保留标签和将内容标记为记录的保留标签后，对内容施加的限制。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="dbc8e-115">标准保留标签的配置为无需将内容标记为记录，即可保留数据。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="dbc8e-116">为确保完整性，表格包括已锁定和已解锁的记录列，适用于 SharePoint 和 OneDrive，但不适用于 Exchange。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="dbc8e-117">锁定和解锁记录的功能使用 Exchange 项目不支持的[记录版本控制](#record-versioning)功能。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="dbc8e-118">因此，对于标记为记录的所有 Exchange 项目，该行为会映射到**记录 - 已锁定**列，而**记录 - 已解锁列**则不相关。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="dbc8e-119">操作</span><span class="sxs-lookup"><span data-stu-id="dbc8e-119">Action</span></span>| <span data-ttu-id="dbc8e-120">保留标签</span><span class="sxs-lookup"><span data-stu-id="dbc8e-120">Retention label</span></span> |<span data-ttu-id="dbc8e-121">记录 - 已锁定</span><span class="sxs-lookup"><span data-stu-id="dbc8e-121">Record - locked</span></span>| <span data-ttu-id="dbc8e-122">记录 - 已解锁</span><span class="sxs-lookup"><span data-stu-id="dbc8e-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dbc8e-123">编辑内容</span><span class="sxs-lookup"><span data-stu-id="dbc8e-123">Edit contents</span></span>|<span data-ttu-id="dbc8e-124">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-124">Allowed</span></span> | <span data-ttu-id="dbc8e-125">**阻止**</span><span class="sxs-lookup"><span data-stu-id="dbc8e-125">**Blocked**</span></span> | <span data-ttu-id="dbc8e-126">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-126">Allowed</span></span>|
|<span data-ttu-id="dbc8e-127">编辑属性（包括重命名）</span><span class="sxs-lookup"><span data-stu-id="dbc8e-127">Edit properties, including rename</span></span>|<span data-ttu-id="dbc8e-128">Allowed</span><span class="sxs-lookup"><span data-stu-id="dbc8e-128">Allowed</span></span> |<span data-ttu-id="dbc8e-129">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-129">Allowed</span></span> | <span data-ttu-id="dbc8e-130">Allowed</span><span class="sxs-lookup"><span data-stu-id="dbc8e-130">Allowed</span></span>|
|<span data-ttu-id="dbc8e-131">删除</span><span class="sxs-lookup"><span data-stu-id="dbc8e-131">Delete</span></span>|<span data-ttu-id="dbc8e-132">允许 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dbc8e-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="dbc8e-133">**阻止**</span><span class="sxs-lookup"><span data-stu-id="dbc8e-133">**Blocked**</span></span> | <span data-ttu-id="dbc8e-134">**阻止**</span><span class="sxs-lookup"><span data-stu-id="dbc8e-134">**Blocked**</span></span>|
|<span data-ttu-id="dbc8e-135">复制</span><span class="sxs-lookup"><span data-stu-id="dbc8e-135">Copy</span></span>|<span data-ttu-id="dbc8e-136">Allowed</span><span class="sxs-lookup"><span data-stu-id="dbc8e-136">Allowed</span></span> |<span data-ttu-id="dbc8e-137">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-137">Allowed</span></span> | <span data-ttu-id="dbc8e-138">Allowed</span><span class="sxs-lookup"><span data-stu-id="dbc8e-138">Allowed</span></span>|
|<span data-ttu-id="dbc8e-139">在容器 <sup>2</sup> 中移动</span><span class="sxs-lookup"><span data-stu-id="dbc8e-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="dbc8e-140">Allowed</span><span class="sxs-lookup"><span data-stu-id="dbc8e-140">Allowed</span></span> |<span data-ttu-id="dbc8e-141">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-141">Allowed</span></span> | <span data-ttu-id="dbc8e-142">Allowed</span><span class="sxs-lookup"><span data-stu-id="dbc8e-142">Allowed</span></span>|
|<span data-ttu-id="dbc8e-143">围绕容器 <sup>2</sup> 移动</span><span class="sxs-lookup"><span data-stu-id="dbc8e-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="dbc8e-144">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-144">Allowed</span></span> |<span data-ttu-id="dbc8e-145">如果从未解锁，则允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-145">Allowed if never unlocked</span></span> | <span data-ttu-id="dbc8e-146">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-146">Allowed</span></span>|
|<span data-ttu-id="dbc8e-147">打开/读取</span><span class="sxs-lookup"><span data-stu-id="dbc8e-147">Open/Read</span></span>|<span data-ttu-id="dbc8e-148">Allowed</span><span class="sxs-lookup"><span data-stu-id="dbc8e-148">Allowed</span></span> |<span data-ttu-id="dbc8e-149">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-149">Allowed</span></span> | <span data-ttu-id="dbc8e-150">Allowed</span><span class="sxs-lookup"><span data-stu-id="dbc8e-150">Allowed</span></span>|
|<span data-ttu-id="dbc8e-151">更改标签</span><span class="sxs-lookup"><span data-stu-id="dbc8e-151">Change label</span></span>|<span data-ttu-id="dbc8e-152">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-152">Allowed</span></span> |<span data-ttu-id="dbc8e-153">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="dbc8e-153">Allowed - container admin only</span></span> | <span data-ttu-id="dbc8e-154">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="dbc8e-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="dbc8e-155">删除标签</span><span class="sxs-lookup"><span data-stu-id="dbc8e-155">Remove label</span></span>|<span data-ttu-id="dbc8e-156">允许</span><span class="sxs-lookup"><span data-stu-id="dbc8e-156">Allowed</span></span> |<span data-ttu-id="dbc8e-157">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="dbc8e-157">Allowed - container admin only</span></span> | <span data-ttu-id="dbc8e-158">允许 - 仅容器管理员</span><span class="sxs-lookup"><span data-stu-id="dbc8e-158">Allowed - container admin only</span></span>|

<span data-ttu-id="dbc8e-159">页脚：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-159">Footnotes:</span></span>

<span data-ttu-id="dbc8e-160"><sup>1</sup>OneDrive 和 Exchange 支持此功能，方法是在安全位置保留一份副本，但 SharePoint 阻止此功能。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="dbc8e-161">向用户发送一条消息，询问用户是否尝试删除 SharePoint 中带标记的文档：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![指明项未从 SharePoint 中删除的消息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="dbc8e-163"><sup>2</sup>容器包括 SharePoint 文档库和 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="dbc8e-164">使用保留标签声明记录</span><span class="sxs-lookup"><span data-stu-id="dbc8e-164">Using retention labels to declare records</span></span>

<span data-ttu-id="dbc8e-165">创建保留标签时，可视需要使用保留标签将内容标记为记录：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="dbc8e-166">在 Microsoft 365 合规性中心，转到“记录管理”\*\*\*\*\>“文件计划”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="dbc8e-167">在“文件计划”\*\*\*\* 页面上，选择“创建标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="dbc8e-168">在向导的“**标签设置**”页面上，选择将内容分类为记录的选项。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![选中“使用标签将内容分类为‘记录’”复选框](../media/recordversioning6.png)

3. <span data-ttu-id="dbc8e-170">根据需要，将保留标签应用于 SharePoint 或 OneDrive 文档和 Exchange 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="dbc8e-171">有关说明，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-171">For instructions:</span></span>
    
    - [<span data-ttu-id="dbc8e-172">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="dbc8e-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="dbc8e-173">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="dbc8e-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="dbc8e-174">对内容应用已配置保留标签</span><span class="sxs-lookup"><span data-stu-id="dbc8e-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="dbc8e-175">当用户可对应用中的内容应用将内容标记为记录的保留标签时：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="dbc8e-176">对于 Exchange，任何拥有邮箱写入权限的用户均可应用这些标签。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="dbc8e-177">对于 SharePoint 和 OneDrive，默认“成员”组（“参与”权限级别）中的任何用户均可应用这些标签。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="dbc8e-178">使用保留标签标记为记录的文档示例：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-178">Example of a document marked as record by using a retention label:</span></span>

![标记为记录的文档的详细信息窗格](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="dbc8e-180">记录版本控制</span><span class="sxs-lookup"><span data-stu-id="dbc8e-180">Record versioning</span></span>

<span data-ttu-id="dbc8e-181">将文档标记为记录并限制可对记录执行的操作是任何记录管理解决方案的重要目标。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="dbc8e-182">但是，用户创建后续版本时也可能需要开展协作。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="dbc8e-183">例如，你可以将销售合同标记为记录，但需要使用新条款更新合同，并将最新版本标记为新记录，同时保留先前的记录版本。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="dbc8e-184">对于这些类型的方案，SharePoint 和 OneDrive 现在支持*记录版本控制*。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="dbc8e-185">OneNote 笔记本文件夹不支持记录版本控制。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="dbc8e-186">若要使用记录版本控制，首先标记文档并将其标记为记录。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="dbc8e-187">完成此操作后，名为“*记录状态*”的文档属性将显示在保留标签旁边，初始记录状态为“**已锁定**”。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="dbc8e-188">现在，可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-188">You can now do the following things:</span></span>

  - <span data-ttu-id="dbc8e-189">**通过解锁和锁定记录状态属性，持续编辑文档的各个版本并将其保留为记录。**</span><span class="sxs-lookup"><span data-stu-id="dbc8e-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="dbc8e-190">只有当“**记录状态**”属性设置为“**已锁定**”时，才会保留新版本的记录。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="dbc8e-191">在已锁定和已解锁之间切换可降低保留不必要的文档版本和副本的风险。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="dbc8e-192">**将文档自动保存在位于网站集内的本地记录存储库中。**</span><span class="sxs-lookup"><span data-stu-id="dbc8e-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="dbc8e-193">SharePoint 和 OneDrive 中的每个网站集将内容保存在其保留库中。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="dbc8e-194">记录版本保存在此库中的“记录”文件夹内。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="dbc8e-195">**保存包含所有版本的始终更新的文档。**</span><span class="sxs-lookup"><span data-stu-id="dbc8e-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="dbc8e-196">默认情况下，每个 SharePoint 和 OneDrive 文档的项菜单上都有可用的版本历史记录。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="dbc8e-197">在此版本历史记录中，你可以轻松查看哪些版本是记录并查看这些文档。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="dbc8e-198">对于具有将项标记为记录的保留标签的任何文档，记录版本控制自动可用。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="dbc8e-199">当用户使用详细信息窗格查看文档属性时，可以将“**记录状态**”从“**已锁定**”切换为“**已解锁**”。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="dbc8e-200">执行此操作即可在保留库的“记录”文件夹中创建一个记录，该记录将在其中保存剩余的保留期。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="dbc8e-201">当文档处于已解锁状态时，拥有标准编辑权限的任何用户均可编辑此文件。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="dbc8e-202">但是，用户无法编辑此文件，因为它仍然是记录。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="dbc8e-203">完成编辑后，用户可再次将“**记录状态**”从“**已解锁**”切换回“**已锁定**”，此状态下可阻止用户进一步编辑该记录。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![标记为记录的文档上的记录状态属性](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="dbc8e-205">锁定和解锁记录</span><span class="sxs-lookup"><span data-stu-id="dbc8e-205">Locking and unlocking a record</span></span>

<span data-ttu-id="dbc8e-206">在向文档应用将内容标记为记录的保留标签后，任何拥有参与权限或更窄权限水平的用户可解锁记录或锁定未解锁的记录。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![记录状态显示记录文档已解锁](../media/recordversioning9.png)

<span data-ttu-id="dbc8e-208">当用户解锁记录时，将会发生以下操作：</span><span class="sxs-lookup"><span data-stu-id="dbc8e-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="dbc8e-209">如果当前网站集没有保留库，将会创建一个。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="dbc8e-210">如果保留库没有“记录”文件夹，将会创建一个。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="dbc8e-211">“复制到”\*\*\*\* 操作会将文档的最新版本复制到“记录”文件夹。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="dbc8e-212">“复制到”\*\*\*\* 操作仅包含最新版本，不包含先前版本。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="dbc8e-213">此复制的文档现在被视为文档的记录版本，其文件名格式为：\[标题 GUID 版本\#\]</span><span class="sxs-lookup"><span data-stu-id="dbc8e-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="dbc8e-214">在“记录”文件夹中创建的副本已添加到原始文档的版本历史记录中，此版本将在注释字段中显示“**记录**”一词。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="dbc8e-215">原始文档现已成为可编辑但不可删除的新版本。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="dbc8e-216">文档库列“**项为记录**”仍显示“**是**”值，因为文档仍是记录，即使它现在可以编辑。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="dbc8e-217">当用户锁定记录时，原始文档同样无法编辑。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="dbc8e-218">但是，是解锁记录的操作将版本复制到保留库中的“记录”文件夹。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="dbc8e-219">记录版本</span><span class="sxs-lookup"><span data-stu-id="dbc8e-219">Record versions</span></span>

<span data-ttu-id="dbc8e-220">每次用户解锁记录时，都会将最新版本复制到保留库的“记录”文件夹中，该版本在版本历史记录的“注释”\*\*\*\* 字段中的值为“记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![保留库中显示的记录](../media/recordversioning10.png)

<span data-ttu-id="dbc8e-222">要查看版本历史记录，请在文档库中选择一个文档，然后在项菜单中单击“版本历史记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="dbc8e-223">存储记录的位置。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-223">Where records are stored</span></span>

<span data-ttu-id="dbc8e-224">记录保存在网站集顶层站点的保留库内的“记录”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="dbc8e-225">在顶层站点的左侧导航中，选择“**网站内容**\>**”，“保留库”**。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![保留库](../media/recordversioning11.png)

<br/><br/>

![保留库中的“记录”文件夹](../media/recordversioning12.png)

<span data-ttu-id="dbc8e-228">保留库仅对网站集管理员可见。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="dbc8e-229">此外，默认情况下保留库不存在。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="dbc8e-230">仅当受保存标签影响的内容在网站集中第一次删除时才会创建。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="dbc8e-231">搜索记录版本控制事件的审核日志</span><span class="sxs-lookup"><span data-stu-id="dbc8e-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="dbc8e-232">锁定和解锁记录的操作会记录在审核日志中。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="dbc8e-233">你可以搜索特定活动“将记录状态更改为已锁定”\*\*\*\* 和“将记录状态更改为已解锁”\*\*\*\*，这些活动位于安全与合规性中心“审核日志搜索”\*\*\*\* 页面“活动”\*\*\*\* 下拉列表中的“文件和页面活动”\*\*\*\* 部分。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![在审核日志中搜索记录版本控制事件](../media/recordversioning13.png)

<span data-ttu-id="dbc8e-235">有关搜索这些事件的详细信息，请参阅[在安全与合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)的“文件和页面活动”部分。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="dbc8e-236">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dbc8e-236">Next steps</span></span>

<span data-ttu-id="dbc8e-237">如果还没有用于记录管理的保留标签，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="dbc8e-238">若要了解有关记录的处置，请参阅[处置内容](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="dbc8e-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
