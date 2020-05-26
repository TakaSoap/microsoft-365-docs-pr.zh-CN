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
description: 了解记录 要在 Office 365 或 Microsoft 组织中实现记录管理策略，请使用将内容声明为记录的保留标签。 然后发布或自动应用保留记录标签。
ms.openlocfilehash: 8dcb3b03dcd908da2a3133d52c1a70ae197eee99
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "44231905"
---
# <a name="learn-about-records"></a><span data-ttu-id="55c90-104">了解记录</span><span class="sxs-lookup"><span data-stu-id="55c90-104">Learn about records</span></span>

><span data-ttu-id="55c90-105">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="55c90-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="55c90-106">在 Microsoft 365 中管理记录可帮助组织遵守公司策略、法律和法规义务，同时降低风险和法律责任。</span><span class="sxs-lookup"><span data-stu-id="55c90-106">Managing records in Microsoft 365 helps an organization comply with their corporate policies, legal and regulatory obligations while reducing risk and legal liability.</span></span>

<span data-ttu-id="55c90-107">总体来说，将内容声明为记录意味着：</span><span class="sxs-lookup"><span data-stu-id="55c90-107">At a high level, declaring content as a record means that:</span></span>

- <span data-ttu-id="55c90-108">该项变为不可变（记录无法修改或删除）</span><span class="sxs-lookup"><span data-stu-id="55c90-108">The item becomes immutable (a record can't be modified or deleted)</span></span>

- <span data-ttu-id="55c90-109">记录了有关该项的其他活动</span><span class="sxs-lookup"><span data-stu-id="55c90-109">Additional activities about the item are logged</span></span>

- <span data-ttu-id="55c90-110">记录在声明的保留期结束后被处置</span><span class="sxs-lookup"><span data-stu-id="55c90-110">Records are disposed of after their stated retention period is past</span></span>

<span data-ttu-id="55c90-111">使用[保留标签](labels.md)将内容分类为记录。</span><span class="sxs-lookup"><span data-stu-id="55c90-111">You use [retention labels](labels.md) to classify content as a record.</span></span> <span data-ttu-id="55c90-112">创建声明记录的保留标签后，你可以发布这些标签，以便用户可以将其应用于内容，或自动应用这些标签到你想分类为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="55c90-112">After you create retention labels that declare records, you can either publish those labels so that users can apply them to content, or auto-apply those labels to content that you want to classify as a record.</span></span> <span data-ttu-id="55c90-113">有关说明，请参阅 [创建、发布和自动应用保留标签](create-retention-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="55c90-113">For instructions, see [Create, publish, and auto-apply retention labels ](create-retention-labels.md).</span></span>

<span data-ttu-id="55c90-114">通过使用保留标签来声明记录，可在 Microsoft 365 环境中实现单一一致的记录管理策略。</span><span class="sxs-lookup"><span data-stu-id="55c90-114">By using retention labels to declare records, you can implement a single, consistent records-management strategy across your Microsoft 365 environment.</span></span>

<span data-ttu-id="55c90-115">请记住下列有关记录的事项：</span><span class="sxs-lookup"><span data-stu-id="55c90-115">Keep the following things in mind about records:</span></span>

  - <span data-ttu-id="55c90-116">**记录是不可变的。**</span><span class="sxs-lookup"><span data-stu-id="55c90-116">**Records are immutable.**</span></span> <span data-ttu-id="55c90-117">除了 SharePoint 和 OneDrive for Business 以外，将内容声明为记录的保留标签还可以应用到 Exchange 内容。</span><span class="sxs-lookup"><span data-stu-id="55c90-117">A retention label that declares content as a record can be applied to content in Exchange, in addition to SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="55c90-118">但是，[记录版本控制](#record-versioning)仅在 SharePoint 和 OneDrive 中可用，对 Exchange 不可用。</span><span class="sxs-lookup"><span data-stu-id="55c90-118">However, [record versioning](#record-versioning) is available only in SharePoint and OneDrive, and not for Exchange.</span></span>

    <span data-ttu-id="55c90-119">在 Exchange 中，标记为记录的内容不可变，直到其最终删除。</span><span class="sxs-lookup"><span data-stu-id="55c90-119">In Exchange, content labeled as a record is immutable until its final deletion.</span></span> <span data-ttu-id="55c90-120">将 Exchange 项标记为记录后，会发生下述四项事件：</span><span class="sxs-lookup"><span data-stu-id="55c90-120">When an Exchange item is labeled as a record, four things happen:</span></span>

    - <span data-ttu-id="55c90-121">无法永久删除项。</span><span class="sxs-lookup"><span data-stu-id="55c90-121">The item can't be permanently deleted.</span></span>

    - <span data-ttu-id="55c90-122">无法编辑项。</span><span class="sxs-lookup"><span data-stu-id="55c90-122">The item can't be edited.</span></span>

    - <span data-ttu-id="55c90-123">无法更改标签。</span><span class="sxs-lookup"><span data-stu-id="55c90-123">The label can't be changed.</span></span>

    - <span data-ttu-id="55c90-124">无法删除标签。</span><span class="sxs-lookup"><span data-stu-id="55c90-124">The label can't be removed.</span></span>

  - <span data-ttu-id="55c90-125">**记录和文件夹。**</span><span class="sxs-lookup"><span data-stu-id="55c90-125">**Records and folders.**</span></span> <span data-ttu-id="55c90-126">可将保留标签应用于 Exchange、SharePoint 和 OneDrive 中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="55c90-126">You can apply a retention label to a folder in Exchange, SharePoint, and OneDrive.</span></span> <span data-ttu-id="55c90-127">如果某文件夹被标记为记录，且将某项移到此文件夹中，则该项被标记为记录。</span><span class="sxs-lookup"><span data-stu-id="55c90-127">If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record.</span></span> <span data-ttu-id="55c90-128">将该项移出文件夹后，该项将仍被标记为记录。</span><span class="sxs-lookup"><span data-stu-id="55c90-128">When you move the item out of the folder, the item remains labeled as a record.</span></span>

    <span data-ttu-id="55c90-129">此外，如果将应用于某个文件夹（在 SharePoint 和 OneDrive 中）的记录标签更改为不将内容声明为记录的保留标签，则该文件夹中的各项将保留其现有的记录标签。</span><span class="sxs-lookup"><span data-stu-id="55c90-129">Also, if you change the record label that's applied to a folder (in SharePoint and OneDrive) to a retention label that does not declare content as a record, then items in the folder keep their existing  record label.</span></span>

    <span data-ttu-id="55c90-130">有关将保留标签应用于 SharePoint 和 OneDrive 文件夹的详细信息，请参阅[将默认保留标签应用于 SharePoint 库、文件夹或文档集中的所有内容](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。</span><span class="sxs-lookup"><span data-stu-id="55c90-130">For more information about applying retention labels to SharePoint and OneDrive folders, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>

  - <span data-ttu-id="55c90-131">**记录无法删除。**</span><span class="sxs-lookup"><span data-stu-id="55c90-131">**Records can't be deleted**.</span></span> <span data-ttu-id="55c90-132">如果用户尝试删除 Exchange 中的记录，相应项会移至“可恢复项”文件夹中，如[如何使用 Exchange 位置的保留策略](retention-policies-exchange.md#how-a-retention-policy-works-with-exchange-locations)中所述。</span><span class="sxs-lookup"><span data-stu-id="55c90-132">If a user attempts to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How a retention policy works with Exchange locations](retention-policies-exchange.md#how-a-retention-policy-works-with-exchange-locations).</span></span>

    <span data-ttu-id="55c90-133">如果用户尝试删除 SharePoint 中的记录，将会显示错误，提醒你注意项未删除，仍留在库中。</span><span class="sxs-lookup"><span data-stu-id="55c90-133">If a user attempts to delete a record in a SharePoint, an error is displayed say that the item wasn't deleted, and remains in the library.</span></span>

    ![指明项未从 SharePoint 中删除的消息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    <span data-ttu-id="55c90-135">如果用户尝试删除 OneDrive 中的记录，相应项会移至保留库中，如[如何使用SharePoint 和 OneDrive 的保留策略](retention-policies-sharepoint.md#how-a-retention-policy-works-with-sharepoint-and-onedrive)中所述。</span><span class="sxs-lookup"><span data-stu-id="55c90-135">If a user attempts to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How a retention policy works with SharePoint and OneDrive](retention-policies-sharepoint.md#how-a-retention-policy-works-with-sharepoint-and-onedrive).</span></span>

  - <span data-ttu-id="55c90-136">**记录标签无法移除。**</span><span class="sxs-lookup"><span data-stu-id="55c90-136">**Records labels can't be removed.**</span></span> <span data-ttu-id="55c90-137">对项应用记录标签后，仅该位置（例如 SharePoint 网站的网站集管理员）的管理员可以移除该记录标签。</span><span class="sxs-lookup"><span data-stu-id="55c90-137">Once a record label has been applied to an item, only the admin of that location (for example, a site collection admin of a SharePoint site) can remove that record label.</span></span>

## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="55c90-138">使用保留标签声明记录</span><span class="sxs-lookup"><span data-stu-id="55c90-138">Using retention labels to declare records</span></span>

<span data-ttu-id="55c90-139">创建保留标签时，可视需要使用保留标签将内容分类为记录：</span><span class="sxs-lookup"><span data-stu-id="55c90-139">When you create a retention label, you have the option to use the retention label to classify the content as a record:</span></span>

1. <span data-ttu-id="55c90-140">在 Microsoft 365 合规性中心，转到“记录管理”\*\*\*\*\>“文件计划”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55c90-140">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="55c90-141">在“文件计划”\*\*\*\* 页面上，选择“创建标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55c90-141">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="55c90-142">在向导的“标签设置”\*\*\*\* 页面上，选择将保留标签设置为“将内容声明为记录”的选项。</span><span class="sxs-lookup"><span data-stu-id="55c90-142">On the **Label settings** page in the wizard, choose the option to set the retention label to declare content as a record.</span></span>
    
   ![选中“使用标签将内容分类为‘记录’”复选框](../media/recordversioning6.png)

3. <span data-ttu-id="55c90-144">将保留标签[发布](labels.md#how-retention-labels-work-with-retention-label-policies)或[自动应用](labels.md#applying-a-retention-label-automatically-based-on-conditions)到 SharePoint 网站和/或 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="55c90-144">[Publish](labels.md#how-retention-labels-work-with-retention-label-policies) or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) the retention label to SharePoint sites and/or OneDrive accounts.</span></span>


### <a name="applying-a-retention-label-to-content"></a><span data-ttu-id="55c90-145">对内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="55c90-145">Applying a retention label to content</span></span>

<span data-ttu-id="55c90-146">对于 Exchange，任何具有邮箱写入权限的用户均可对电子邮件应用记录标签。</span><span class="sxs-lookup"><span data-stu-id="55c90-146">For Exchange, any user with write-access to the mailbox can apply a record label to an email message.</span></span> <span data-ttu-id="55c90-147">对于 SharePoint 和 OneDrive 内容，默认“成员”组（“参与”权限级别）中的任何用户均可将记录标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="55c90-147">For content in SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply a record label to content.</span></span> <span data-ttu-id="55c90-148">应用后，仅网站集管理员可删除或更改该记录标签。</span><span class="sxs-lookup"><span data-stu-id="55c90-148">Only a site collection admin can remove or change that record label after it's been applied.</span></span> <span data-ttu-id="55c90-149">如前所述，可以对内容自动应用将内容分类为记录的保留标签。</span><span class="sxs-lookup"><span data-stu-id="55c90-149">As previously explained, a retention label that classifies content as a record can be auto-applied to content.</span></span>

<span data-ttu-id="55c90-150">此处为记录标签应用到 SharePoint 网站或 OneDrive 帐户上的文档的情况。</span><span class="sxs-lookup"><span data-stu-id="55c90-150">Here's what this looks like when a record label is applied to a document on a SharePoint site or OneDrive account.</span></span>
<br/><br/>

![标记为记录的文档的详细信息窗格](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="55c90-152">记录版本控制</span><span class="sxs-lookup"><span data-stu-id="55c90-152">Record versioning</span></span>

<span data-ttu-id="55c90-153">记录管理的重要组成部分是能够将文档声明为记录并且使该记录不可变。</span><span class="sxs-lookup"><span data-stu-id="55c90-153">An essential part of records management is the ability to declare a document as a record and have that record be immutable.</span></span> <span data-ttu-id="55c90-154">同时，如果用户需要创建后续版本，记录不可变性可阻止文档的协作性。</span><span class="sxs-lookup"><span data-stu-id="55c90-154">At the same time, record immutability prevents collaboration on the document if people need to create subsequent versions.</span></span> <span data-ttu-id="55c90-155">例如，你可以将销售合同声明为记录，但需要使用新条款更新合同，并将最新版本声明为新记录，同时保留先前的记录版本。</span><span class="sxs-lookup"><span data-stu-id="55c90-155">For example, you might declare a sales contract as a record, but then need to update the contract with new terms and declare the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="55c90-156">对于这些类型的方案，SharePoint Online 和 OneDrive for Business 现在支持*记录版本控制*。</span><span class="sxs-lookup"><span data-stu-id="55c90-156">For these types of scenarios, SharePoint Online and OneDrive for Business now support *record versioning*.</span></span> <span data-ttu-id="55c90-157">不支持 OneNote 笔记本文件夹。</span><span class="sxs-lookup"><span data-stu-id="55c90-157">OneNote notebook folders are not supported.</span></span>

<span data-ttu-id="55c90-158">要使用记录版本控制，第一步是使用 Microsoft 365 合规性中心创建声明记录的保留标签，并将其发布到所有 SharePoint 网站和/或 OneDrive 帐户，或者将其发布到特定的 SharePoint 网站和/或 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="55c90-158">To use record versioning, the first step is to use the Microsoft 365 compliance center to create and publish retention labels that declare records to all SharePoint sites and/or OneDrive accounts, or publish them to specific SharePoint sites and/or OneDrive accounts.</span></span> <span data-ttu-id="55c90-159">下一步是将发布的保留记录标签应用到文档。</span><span class="sxs-lookup"><span data-stu-id="55c90-159">The next step is to apply a published retention record label to a document.</span></span> <span data-ttu-id="55c90-160">完成此操作后，名为“记录状态”\*\* 的文档属性将显示在保留标签旁边，初始记录状态将为“已锁定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55c90-160">When this is done, a document property, called *Record status* is displayed next to the retention label, and the initial record status will be **Locked**.</span></span> <span data-ttu-id="55c90-161">此时，你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="55c90-161">At this point, you can do the following things:</span></span>

  - <span data-ttu-id="55c90-162">**通过解锁和锁定记录状态属性，持续编辑文档的各个版本并将其声明为记录。**</span><span class="sxs-lookup"><span data-stu-id="55c90-162">**Continually edit and declare individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="55c90-163">当“记录状态”\*\*\*\* 属性设置为“已锁定”\*\*\*\* 时，仅保留声明为记录的版本。</span><span class="sxs-lookup"><span data-stu-id="55c90-163">Only the versions declared as records are retained when the **Record status** property is set to **Locked**.</span></span> <span data-ttu-id="55c90-164">这将降低保留不必要的文档版本和副本的风险。</span><span class="sxs-lookup"><span data-stu-id="55c90-164">This reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="55c90-165">**将文档自动保存在位于网站集内的本地记录存储库中。**</span><span class="sxs-lookup"><span data-stu-id="55c90-165">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="55c90-166">SharePoint 和 OneDrive 中的每个网站集将内容保存在其保留库中。</span><span class="sxs-lookup"><span data-stu-id="55c90-166">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="55c90-167">记录版本保存在此库中的“记录”文件夹内。</span><span class="sxs-lookup"><span data-stu-id="55c90-167">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="55c90-168">**保存包含所有版本的始终更新的文档。**</span><span class="sxs-lookup"><span data-stu-id="55c90-168">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="55c90-169">默认情况下，每个 SharePoint 和 OneDrive 文档的项菜单上都有可用的版本历史记录。</span><span class="sxs-lookup"><span data-stu-id="55c90-169">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="55c90-170">在此版本历史记录中，你可以轻松查看哪些版本是记录并查看这些文档。</span><span class="sxs-lookup"><span data-stu-id="55c90-170">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="55c90-171">对于具有将项声明为记录的保留标签的任何文档，记录版本控制自动可用。</span><span class="sxs-lookup"><span data-stu-id="55c90-171">Record versioning is automatically available for any document that has a retention label that declares the item as a record.</span></span> <span data-ttu-id="55c90-172">当用户通过详细信息窗格查看文档属性时，他们会将“记录状态”\*\*\*\* 从“已锁定”\*\*\*\* 切换为“已解锁”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55c90-172">When a user views the document properties through the details pane, they toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="55c90-173">单击一下，即可在保留库的“记录”文件夹中创建一个记录，该记录将在其中保存剩余的保留期。</span><span class="sxs-lookup"><span data-stu-id="55c90-173">This single click creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> <span data-ttu-id="55c90-174">当文档处于解锁状态时，具有权限的任何用户均可编辑此文件。</span><span class="sxs-lookup"><span data-stu-id="55c90-174">While the document is unlocked, any user with permissions can edit the file.</span></span> <span data-ttu-id="55c90-175">但是，用户无法编辑此文件，因为它被视为声明的记录。</span><span class="sxs-lookup"><span data-stu-id="55c90-175">However, users can't delete the file, because it's considered a declared record.</span></span> <span data-ttu-id="55c90-176">进行必要的更改后，用户可以将“记录状态”\*\*\*\* 从“已解锁”\*\*\*\* 切换为“已锁定”\*\*\*\*，因此文档会再次声明为记录并且无法编辑。</span><span class="sxs-lookup"><span data-stu-id="55c90-176">After the necessary changes are made, the user can then toggle the **Record status** from **Unlocked** to **Locked**, so that the document is again declared a record and can't be edited.</span></span>
<br/><br/>

![标记为记录的文档上的记录状态属性](../media/recordversioning8.png)

> [!NOTE]
> <span data-ttu-id="55c90-178">记录版本控制需要 Office 365 Enterprise E5 许可证，以便有权限的用户可以编辑无法在 SharePoint 网站或 OneDrive 帐户中声明为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="55c90-178">Record versioning requires an Office 365 Enterprise E5 license for each user who has permissions to edit content that's been declared a record in a SharePoint site or OneDrive account.</span></span> <span data-ttu-id="55c90-179">具有只读权限的用户不需要此许可证。</span><span class="sxs-lookup"><span data-stu-id="55c90-179">Users who have read-only access don't require this license.</span></span>

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="55c90-180">锁定和解锁记录</span><span class="sxs-lookup"><span data-stu-id="55c90-180">Locking and unlocking a record</span></span>

<span data-ttu-id="55c90-181">记录标签分配到文档后，任何有参与权限或更窄权限水平的用户可解锁记录或锁定未解锁的记录。</span><span class="sxs-lookup"><span data-stu-id="55c90-181">After a record label is assigned to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![记录状态显示记录文档已解锁](../media/recordversioning9.png)

<span data-ttu-id="55c90-183">当用户解锁记录时，将会发生以下操作：</span><span class="sxs-lookup"><span data-stu-id="55c90-183">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="55c90-184">如果当前网站集没有保留库，将会创建一个。</span><span class="sxs-lookup"><span data-stu-id="55c90-184">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="55c90-185">如果保留库没有“记录”文件夹，将会创建一个。</span><span class="sxs-lookup"><span data-stu-id="55c90-185">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="55c90-186">“复制到”\*\*\*\* 操作会将文档的最新版本复制到“记录”文件夹。</span><span class="sxs-lookup"><span data-stu-id="55c90-186">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="55c90-187">“复制到”\*\*\*\* 操作仅包含最新版本，不包含先前版本。</span><span class="sxs-lookup"><span data-stu-id="55c90-187">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="55c90-188">此复制的文档现在被视为文档的记录版本，其文件名格式为：\[标题 GUID 版本\#\]</span><span class="sxs-lookup"><span data-stu-id="55c90-188">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="55c90-189">在“记录”文件夹中创建的副本已添加到原始文档的版本历史记录中，此版本将在注释字段中显示“记录”\*\*\*\* 一词。</span><span class="sxs-lookup"><span data-stu-id="55c90-189">The copy created in the Records folder added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="55c90-190">原始文档现已成为可编辑（但不可删除）的新版本。</span><span class="sxs-lookup"><span data-stu-id="55c90-190">The original document is a new version that can be edited (but not deleted).</span></span> <span data-ttu-id="55c90-191">文档库列“项为记录”\*\*\*\* 仍显示“是”\*\*\*\* 值，因为文档仍被视为记录，即使它现在可以编辑。</span><span class="sxs-lookup"><span data-stu-id="55c90-191">The document library column **Item is a Record** still shows the **Yes** value because the document is still considered a record, even if it can now be edited.</span></span>

<span data-ttu-id="55c90-192">当用户锁定记录时，原始文档同样无法编辑。</span><span class="sxs-lookup"><span data-stu-id="55c90-192">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="55c90-193">但是，是解锁记录的操作将版本复制到保留库中的“记录”文件夹。</span><span class="sxs-lookup"><span data-stu-id="55c90-193">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="55c90-194">记录版本</span><span class="sxs-lookup"><span data-stu-id="55c90-194">Record versions</span></span>

<span data-ttu-id="55c90-195">每次用户解锁记录时，都会将最新版本复制到保留库的“记录”文件夹中，该版本在版本历史记录的“注释”\*\*\*\* 字段中的值为“记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55c90-195">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![保留库中显示的记录](../media/recordversioning10.png)

<span data-ttu-id="55c90-197">要查看版本历史记录，请在文档库中选择一个文档，然后在项菜单中单击“版本历史记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55c90-197">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="55c90-198">存储记录的位置。</span><span class="sxs-lookup"><span data-stu-id="55c90-198">Where records are stored</span></span>

<span data-ttu-id="55c90-199">记录保存在网站集顶层站点的保留库内的“记录”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55c90-199">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="55c90-200">在顶层站点的左侧导航中，选择“网站内容”\*\*\*\*\>保留库”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55c90-200">In the left nav on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![保留库](../media/recordversioning11.png)

<br/><br/>

![保留库中的“记录”文件夹](../media/recordversioning12.png)

<span data-ttu-id="55c90-203">保留库仅对网站集管理员可见。</span><span class="sxs-lookup"><span data-stu-id="55c90-203">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="55c90-204">此外，默认情况下保留库不存在。</span><span class="sxs-lookup"><span data-stu-id="55c90-204">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="55c90-205">仅当受保存标签影响的内容在网站集中第一次删除时才会创建。</span><span class="sxs-lookup"><span data-stu-id="55c90-205">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="55c90-206">搜索记录版本控制事件的审核日志</span><span class="sxs-lookup"><span data-stu-id="55c90-206">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="55c90-207">锁定和解锁记录的操作会记录在审核日志中。</span><span class="sxs-lookup"><span data-stu-id="55c90-207">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="55c90-208">你可以搜索特定活动“将记录状态更改为已锁定”\*\*\*\* 和“将记录状态更改为已解锁”\*\*\*\*，这些活动位于安全与合规性中心“审核日志搜索”\*\*\*\* 页面“活动”\*\*\*\* 下拉列表中的“文件和页面活动”\*\*\*\* 部分。</span><span class="sxs-lookup"><span data-stu-id="55c90-208">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![在审核日志中搜索记录版本控制事件](../media/recordversioning13.png)

<span data-ttu-id="55c90-210">有关搜索这些事件的详细信息，请参阅[在安全与合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)的“文件和页面活动”部分。</span><span class="sxs-lookup"><span data-stu-id="55c90-210">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>
