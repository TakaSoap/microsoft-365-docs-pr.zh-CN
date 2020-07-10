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
ms.openlocfilehash: 35d1becad78cdb01402ba50ba44b277f8c511567
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080099"
---
# <a name="learn-about-records"></a><span data-ttu-id="0c870-103">了解记录</span><span class="sxs-lookup"><span data-stu-id="0c870-103">Learn about records</span></span>

><span data-ttu-id="0c870-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="0c870-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0c870-105">在 Microsoft 365 中管理记录可帮助组织遵守公司策略、法律或法规义务，同时降低风险和法律责任。</span><span class="sxs-lookup"><span data-stu-id="0c870-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="0c870-106">将内容标记为记录时：</span><span class="sxs-lookup"><span data-stu-id="0c870-106">When content is marked as an record:</span></span>

- <span data-ttu-id="0c870-107">该项变为不可变，即记录无法修改或删除。</span><span class="sxs-lookup"><span data-stu-id="0c870-107">The item becomes immutable, which means that it can't be modified or deleted.</span></span>

- <span data-ttu-id="0c870-108">记录了有关该项的其他活动。</span><span class="sxs-lookup"><span data-stu-id="0c870-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="0c870-109">保留期结束时将其删除时，拥有处置证明。</span><span class="sxs-lookup"><span data-stu-id="0c870-109">You have proof of disposition when they are deleted at the end of their retention period.</span></span>

<span data-ttu-id="0c870-110">使用[保留标签](labels.md)将内容标记为记录。</span><span class="sxs-lookup"><span data-stu-id="0c870-110">You use [retention labels](labels.md) to mark content as a record.</span></span> <span data-ttu-id="0c870-111">创建声明记录的保留标签后，你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="0c870-111">After you create retention labels that declare records, you can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span> <span data-ttu-id="0c870-112">有关说明，请参阅 [创建、发布和自动应用保留标签](create-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="0c870-112">For instructions, see [Create, publish, and auto-apply retention labels ](create-retention-labels.md).</span></span>

<span data-ttu-id="0c870-113">通过使用保留标签来声明记录，可在 Microsoft 365 环境中实现单一一致的记录管理策略。</span><span class="sxs-lookup"><span data-stu-id="0c870-113">By using retention labels to declare records, you can implement a single, consistent records-management strategy across your Microsoft 365 environment.</span></span>

<span data-ttu-id="0c870-114">请记住下列有关记录的事项：</span><span class="sxs-lookup"><span data-stu-id="0c870-114">Keep the following things in mind about records:</span></span>

  - <span data-ttu-id="0c870-115">**记录是不可变的。**</span><span class="sxs-lookup"><span data-stu-id="0c870-115">**Records are immutable.**</span></span> <span data-ttu-id="0c870-116">除了 SharePoint 和 OneDrive 以外，将内容标记为记录的保留标签还可以应用到 Exchange 内容。</span><span class="sxs-lookup"><span data-stu-id="0c870-116">A retention label that marks content as a record can be applied to content in Exchange, in addition to SharePoint and OneDrive.</span></span> <span data-ttu-id="0c870-117">但是，[记录版本控制](#record-versioning)仅在 SharePoint 和 OneDrive 中可用，对 Exchange 不可用。</span><span class="sxs-lookup"><span data-stu-id="0c870-117">However, [record versioning](#record-versioning) is available only in SharePoint and OneDrive, and not for Exchange.</span></span>

    <span data-ttu-id="0c870-118">在 Exchange 中，标记为记录的内容不可变，直到其最终删除。</span><span class="sxs-lookup"><span data-stu-id="0c870-118">In Exchange, content labeled as a record is immutable until its final deletion.</span></span> <span data-ttu-id="0c870-119">将 Exchange 项标记为记录后，会发生下述四项事件：</span><span class="sxs-lookup"><span data-stu-id="0c870-119">When an Exchange item is labeled as a record, four things happen:</span></span>

    - <span data-ttu-id="0c870-120">无法永久删除项。</span><span class="sxs-lookup"><span data-stu-id="0c870-120">The item can't be permanently deleted.</span></span>

    - <span data-ttu-id="0c870-121">无法编辑项。</span><span class="sxs-lookup"><span data-stu-id="0c870-121">The item can't be edited.</span></span>

    - <span data-ttu-id="0c870-122">无法更改标签。</span><span class="sxs-lookup"><span data-stu-id="0c870-122">The label can't be changed.</span></span>

    - <span data-ttu-id="0c870-123">无法删除标签。</span><span class="sxs-lookup"><span data-stu-id="0c870-123">The label can't be removed.</span></span>

  - <span data-ttu-id="0c870-124">**记录和文件夹。**</span><span class="sxs-lookup"><span data-stu-id="0c870-124">**Records and folders.**</span></span> <span data-ttu-id="0c870-125">可将保留标签应用于 Exchange、SharePoint 和 OneDrive 中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c870-125">You can apply a retention label to a folder in Exchange, SharePoint, and OneDrive.</span></span> <span data-ttu-id="0c870-126">如果某文件夹被标记为记录，且将某项移到此文件夹中，则该项被标记为记录。</span><span class="sxs-lookup"><span data-stu-id="0c870-126">If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record.</span></span> <span data-ttu-id="0c870-127">将该项移出文件夹后，该项将仍被标记为记录。</span><span class="sxs-lookup"><span data-stu-id="0c870-127">When you move the item out of the folder, the item remains labeled as a record.</span></span>

    <span data-ttu-id="0c870-128">此外，如果将应用于某个文件夹（在 SharePoint 和 OneDrive 中）的记录标签更改为不将内容声明为记录的保留标签，则该文件夹中的各项将保留其现有的记录标签。</span><span class="sxs-lookup"><span data-stu-id="0c870-128">Also, if you change the record label that's applied to a folder (in SharePoint and OneDrive) to a retention label that does not declare content as a record, items in the folder keep their existing record label.</span></span>

    <span data-ttu-id="0c870-129">有关将保留标签应用于 SharePoint 和 OneDrive 文件夹的详细信息，请参阅[将默认保留标签应用于 SharePoint 库、文件夹或文档集中的所有内容](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。</span><span class="sxs-lookup"><span data-stu-id="0c870-129">For more information about applying retention labels to SharePoint and OneDrive folders, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>

  - <span data-ttu-id="0c870-130">**记录无法删除。**</span><span class="sxs-lookup"><span data-stu-id="0c870-130">**Records can't be deleted**.</span></span> <span data-ttu-id="0c870-131">如果用户尝试删除 Exchange 中的记录，相应项会移至“可恢复的项目”文件夹中，如[保留策略如何作用于 Exchange](retention-policies-exchange.md#how-a-retention-policy-works-with-exchange) 中所述。</span><span class="sxs-lookup"><span data-stu-id="0c870-131">If a user attempts to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How a retention policy works with Exchange](retention-policies-exchange.md#how-a-retention-policy-works-with-exchange).</span></span>

    <span data-ttu-id="0c870-132">如果用户尝试删除 SharePoint 中的记录，将会显示错误，提醒你注意项未删除，仍留在库中。</span><span class="sxs-lookup"><span data-stu-id="0c870-132">If a user attempts to delete a record in a SharePoint, an error is displayed say that the item wasn't deleted, and remains in the library.</span></span>

    ![指明项未从 SharePoint 中删除的消息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    <span data-ttu-id="0c870-134">如果用户尝试删除 OneDrive 中的记录，相应项会移至保留库中，如[如何使用SharePoint 和 OneDrive 的保留策略](retention-policies-sharepoint.md#how-a-retention-policy-works-with-sharepoint-and-onedrive)中所述。</span><span class="sxs-lookup"><span data-stu-id="0c870-134">If a user attempts to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How a retention policy works with SharePoint and OneDrive](retention-policies-sharepoint.md#how-a-retention-policy-works-with-sharepoint-and-onedrive).</span></span>

  - <span data-ttu-id="0c870-135">**记录标签无法移除。**</span><span class="sxs-lookup"><span data-stu-id="0c870-135">**Records labels can't be removed.**</span></span> <span data-ttu-id="0c870-136">对项应用记录标签后，仅该位置（例如 SharePoint 网站的网站集管理员）的管理员可以移除该记录标签。</span><span class="sxs-lookup"><span data-stu-id="0c870-136">After a record label has been applied to an item, only the admin of that location (for example, a site collection admin of a SharePoint site) can remove that record label.</span></span>

## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="0c870-137">使用保留标签声明记录</span><span class="sxs-lookup"><span data-stu-id="0c870-137">Using retention labels to declare records</span></span>

<span data-ttu-id="0c870-138">创建保留标签时，可视需要使用保留标签将内容标记为记录：</span><span class="sxs-lookup"><span data-stu-id="0c870-138">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="0c870-139">在 Microsoft 365 合规性中心，转到“记录管理”\*\*\*\*\>“文件计划”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c870-139">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="0c870-140">在“文件计划”\*\*\*\* 页面上，选择“创建标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c870-140">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="0c870-141">在向导的“标签设置”\*\*\*\* 页面上，选择将保留标签设置为“将内容声明为记录”的选项。</span><span class="sxs-lookup"><span data-stu-id="0c870-141">On the **Label settings** page in the wizard, choose the option to set the retention label to declare content as a record.</span></span>
    
   ![选中“使用标签将内容分类为‘记录’”复选框](../media/recordversioning6.png)

3. <span data-ttu-id="0c870-143">将保留标签[发布](labels.md#how-retention-labels-work-with-retention-label-policies)或[自动应用](labels.md#applying-a-retention-label-automatically-based-on-conditions)到 SharePoint 网站和/或 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="0c870-143">[Publish](labels.md#how-retention-labels-work-with-retention-label-policies) or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) the retention label to SharePoint sites and/or OneDrive accounts.</span></span>


### <a name="applying-a-retention-label-to-content"></a><span data-ttu-id="0c870-144">对内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="0c870-144">Applying a retention label to content</span></span>

<span data-ttu-id="0c870-145">对于 Exchange，任何具有邮箱写入权限的用户均可对电子邮件应用记录标签。</span><span class="sxs-lookup"><span data-stu-id="0c870-145">For Exchange, any user with write-access to the mailbox can apply a record label to an email message.</span></span> <span data-ttu-id="0c870-146">对于 SharePoint 和 OneDrive 内容，默认“成员”组（“参与”权限级别）中的任何用户均可将记录标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="0c870-146">For content in SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply a record label to content.</span></span> <span data-ttu-id="0c870-147">应用后，仅网站集管理员可删除或更改该记录标签。</span><span class="sxs-lookup"><span data-stu-id="0c870-147">Only a site collection admin can remove or change that record label after it's been applied.</span></span> <span data-ttu-id="0c870-148">如前所述，可以对内容自动应用将内容分类为记录的保留标签。</span><span class="sxs-lookup"><span data-stu-id="0c870-148">As previously explained, a retention label that classifies content as a record can be auto-applied to content.</span></span>

<span data-ttu-id="0c870-149">此处为记录标签应用到 SharePoint 网站或 OneDrive 帐户上的文档的情况。</span><span class="sxs-lookup"><span data-stu-id="0c870-149">Here's what this looks like when a record label is applied to a document on a SharePoint site or OneDrive account.</span></span>
<br/><br/>

![标记为记录的文档的详细信息窗格](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="0c870-151">记录版本控制</span><span class="sxs-lookup"><span data-stu-id="0c870-151">Record versioning</span></span>

<span data-ttu-id="0c870-152">记录管理的重要组成部分是能够将文档声明为记录并且使该记录不可变。</span><span class="sxs-lookup"><span data-stu-id="0c870-152">An essential part of records management is the ability to declare a document as a record and have that record be immutable.</span></span> <span data-ttu-id="0c870-153">同时，如果用户需要创建后续版本，记录不可变性可阻止文档的协作性。</span><span class="sxs-lookup"><span data-stu-id="0c870-153">At the same time, record immutability prevents collaboration on the document if people need to create subsequent versions.</span></span> <span data-ttu-id="0c870-154">例如，你可以将销售合同声明为记录，但需要使用新条款更新合同，并将最新版本声明为新记录，同时保留先前的记录版本。</span><span class="sxs-lookup"><span data-stu-id="0c870-154">For example, you might declare a sales contract as a record, but then need to update the contract with new terms and declare the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="0c870-155">对于这些类型的方案，SharePoint 和 OneDrive 现在支持*记录版本控制*。</span><span class="sxs-lookup"><span data-stu-id="0c870-155">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="0c870-156">OneNote 笔记本文件夹不支持记录版本控制。</span><span class="sxs-lookup"><span data-stu-id="0c870-156">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="0c870-157">要使用记录版本控制，第一步是使用 Microsoft 365 合规性中心创建声明记录的保留标签，并将其发布到所有 SharePoint 网站和 OneDrive 帐户，或者将其发布到特定的 SharePoint 网站或 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="0c870-157">To use record versioning, the first step is to use the Microsoft 365 compliance center to create retention labels that declare records and and publish them to all SharePoint sites and OneDrive accounts, or publish them to specific SharePoint sites or OneDrive accounts.</span></span> <span data-ttu-id="0c870-158">下一步是将发布的保留记录标签应用到文档。</span><span class="sxs-lookup"><span data-stu-id="0c870-158">The next step is to apply a published retention record label to a document.</span></span> <span data-ttu-id="0c870-159">如果发生这种情况，名为“*记录状态*”的文档属性将显示在保留标签旁边，初始记录状态将为“**已锁定**”。</span><span class="sxs-lookup"><span data-stu-id="0c870-159">When this happens, a document property, called *Record status* is displayed next to the retention label, and the initial record status will be **Locked**.</span></span> <span data-ttu-id="0c870-160">此时，你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c870-160">At this point, you can do the following things:</span></span>

  - <span data-ttu-id="0c870-161">**通过解锁和锁定记录状态属性，持续编辑文档的各个版本并将其声明为记录。**</span><span class="sxs-lookup"><span data-stu-id="0c870-161">**Continually edit and declare individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="0c870-162">当“记录状态”\*\*\*\* 属性设置为“已锁定”\*\*\*\* 时，仅保留声明为记录的版本。</span><span class="sxs-lookup"><span data-stu-id="0c870-162">Only the versions declared as records are retained when the **Record status** property is set to **Locked**.</span></span> <span data-ttu-id="0c870-163">这将降低保留不必要的文档版本和副本的风险。</span><span class="sxs-lookup"><span data-stu-id="0c870-163">This reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="0c870-164">**将文档自动保存在位于网站集内的本地记录存储库中。**</span><span class="sxs-lookup"><span data-stu-id="0c870-164">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="0c870-165">SharePoint 和 OneDrive 中的每个网站集将内容保存在其保留库中。</span><span class="sxs-lookup"><span data-stu-id="0c870-165">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="0c870-166">记录版本保存在此库中的“记录”文件夹内。</span><span class="sxs-lookup"><span data-stu-id="0c870-166">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="0c870-167">**保存包含所有版本的始终更新的文档。**</span><span class="sxs-lookup"><span data-stu-id="0c870-167">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="0c870-168">默认情况下，每个 SharePoint 和 OneDrive 文档的项菜单上都有可用的版本历史记录。</span><span class="sxs-lookup"><span data-stu-id="0c870-168">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="0c870-169">在此版本历史记录中，你可以轻松查看哪些版本是记录并查看这些文档。</span><span class="sxs-lookup"><span data-stu-id="0c870-169">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="0c870-170">对于具有将项声明为记录的保留标签的任何文档，记录版本控制自动可用。</span><span class="sxs-lookup"><span data-stu-id="0c870-170">Record versioning is automatically available for any document that has a retention label that declares the item as a record.</span></span> <span data-ttu-id="0c870-171">当用户通过详细信息窗格查看文档属性时，他们会将“记录状态”\*\*\*\* 从“已锁定”\*\*\*\* 切换为“已解锁”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c870-171">When a user views the document properties through the details pane, they toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="0c870-172">单击一下，即可在保留库的“记录”文件夹中创建一个记录，该记录将在其中保存剩余的保留期。</span><span class="sxs-lookup"><span data-stu-id="0c870-172">This single click creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="0c870-173">当文档处于解锁状态时，具有权限的任何用户均可编辑此文件。</span><span class="sxs-lookup"><span data-stu-id="0c870-173">While the document is unlocked, any user with permissions can edit the file.</span></span> <span data-ttu-id="0c870-174">但是，用户无法编辑此文件，因为它被视为记录。</span><span class="sxs-lookup"><span data-stu-id="0c870-174">However, users can't delete the file, because it's considered a record.</span></span> <span data-ttu-id="0c870-175">进行必要的更改后，用户可以将“记录状态”\*\*\*\* 从“已解锁”\*\*\*\* 切换为“已锁定”\*\*\*\*，因此文档会再次声明为记录并且无法编辑。</span><span class="sxs-lookup"><span data-stu-id="0c870-175">After the necessary changes are made, the user can then toggle the **Record status** from **Unlocked** to **Locked**, so that the document is again declared a record and can't be edited.</span></span>
<br/><br/>

![标记为记录的文档上的记录状态属性](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="0c870-177">锁定和解锁记录</span><span class="sxs-lookup"><span data-stu-id="0c870-177">Locking and unlocking a record</span></span>

<span data-ttu-id="0c870-178">记录标签分配到文档后，任何有参与权限或更窄权限水平的用户可解锁记录或锁定未解锁的记录。</span><span class="sxs-lookup"><span data-stu-id="0c870-178">After a record label is assigned to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![记录状态显示记录文档已解锁](../media/recordversioning9.png)

<span data-ttu-id="0c870-180">当用户解锁记录时，将会发生以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c870-180">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="0c870-181">如果当前网站集没有保留库，将会创建一个。</span><span class="sxs-lookup"><span data-stu-id="0c870-181">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="0c870-182">如果保留库没有“记录”文件夹，将会创建一个。</span><span class="sxs-lookup"><span data-stu-id="0c870-182">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="0c870-183">“复制到”\*\*\*\* 操作会将文档的最新版本复制到“记录”文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c870-183">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="0c870-184">“复制到”\*\*\*\* 操作仅包含最新版本，不包含先前版本。</span><span class="sxs-lookup"><span data-stu-id="0c870-184">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="0c870-185">此复制的文档现在被视为文档的记录版本，其文件名格式为：\[标题 GUID 版本\#\]</span><span class="sxs-lookup"><span data-stu-id="0c870-185">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="0c870-186">在“记录”文件夹中创建的副本已添加到原始文档的版本历史记录中，此版本将在注释字段中显示“记录”\*\*\*\* 一词。</span><span class="sxs-lookup"><span data-stu-id="0c870-186">The copy created in the Records folder added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="0c870-187">原始文档现已成为可编辑（但不可删除）的新版本。</span><span class="sxs-lookup"><span data-stu-id="0c870-187">The original document is a new version that can be edited (but not deleted).</span></span> <span data-ttu-id="0c870-188">文档库列“项为记录”\*\*\*\* 仍显示“是”\*\*\*\* 值，因为文档仍被视为记录，即使它现在可以编辑。</span><span class="sxs-lookup"><span data-stu-id="0c870-188">The document library column **Item is a Record** still shows the **Yes** value because the document is still considered a record, even if it can now be edited.</span></span>

<span data-ttu-id="0c870-189">当用户锁定记录时，原始文档同样无法编辑。</span><span class="sxs-lookup"><span data-stu-id="0c870-189">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="0c870-190">但是，是解锁记录的操作将版本复制到保留库中的“记录”文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c870-190">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="0c870-191">记录版本</span><span class="sxs-lookup"><span data-stu-id="0c870-191">Record versions</span></span>

<span data-ttu-id="0c870-192">每次用户解锁记录时，都会将最新版本复制到保留库的“记录”文件夹中，该版本在版本历史记录的“注释”\*\*\*\* 字段中的值为“记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c870-192">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![保留库中显示的记录](../media/recordversioning10.png)

<span data-ttu-id="0c870-194">要查看版本历史记录，请在文档库中选择一个文档，然后在项菜单中单击“版本历史记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c870-194">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="0c870-195">存储记录的位置。</span><span class="sxs-lookup"><span data-stu-id="0c870-195">Where records are stored</span></span>

<span data-ttu-id="0c870-196">记录保存在网站集顶层站点的保留库内的“记录”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0c870-196">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="0c870-197">在顶层站点的左侧导航中，选择“网站内容”\*\*\*\*\>保留库”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c870-197">In the left nav on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![保留库](../media/recordversioning11.png)

<br/><br/>

![保留库中的“记录”文件夹](../media/recordversioning12.png)

<span data-ttu-id="0c870-200">保留库仅对网站集管理员可见。</span><span class="sxs-lookup"><span data-stu-id="0c870-200">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="0c870-201">此外，默认情况下保留库不存在。</span><span class="sxs-lookup"><span data-stu-id="0c870-201">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="0c870-202">仅当受保存标签影响的内容在网站集中第一次删除时才会创建。</span><span class="sxs-lookup"><span data-stu-id="0c870-202">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="0c870-203">搜索记录版本控制事件的审核日志</span><span class="sxs-lookup"><span data-stu-id="0c870-203">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="0c870-204">锁定和解锁记录的操作会记录在审核日志中。</span><span class="sxs-lookup"><span data-stu-id="0c870-204">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="0c870-205">你可以搜索特定活动“将记录状态更改为已锁定”\*\*\*\* 和“将记录状态更改为已解锁”\*\*\*\*，这些活动位于安全与合规性中心“审核日志搜索”\*\*\*\* 页面“活动”\*\*\*\* 下拉列表中的“文件和页面活动”\*\*\*\* 部分。</span><span class="sxs-lookup"><span data-stu-id="0c870-205">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![在审核日志中搜索记录版本控制事件](../media/recordversioning13.png)

<span data-ttu-id="0c870-207">有关搜索这些事件的详细信息，请参阅[在安全与合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)的“文件和页面活动”部分。</span><span class="sxs-lookup"><span data-stu-id="0c870-207">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c870-208">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0c870-208">Next steps</span></span>

<span data-ttu-id="0c870-209">有关如何创建和发布包含将内容标记为记录的设置的保留标签的说明，请参阅[创建、发布和自动应用保留标签](create-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="0c870-209">For instructions how to create and publish the retention labels that contain the setting to mark content as a record, see [Create, publish, and auto-apply retention labels](create-retention-labels.md).</span></span>
