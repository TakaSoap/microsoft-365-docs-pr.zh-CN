---
title: 记录概述
ms.author: laurawi
author: laurawi
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
description: 要在 Office 365 或 Microsoft 组织中实现记录管理策略，请使用将内容声明为记录的保留标签。 然后发布或自动应用保留记录标签。
ms.openlocfilehash: 37f23dcd9c2b94edce99fa55977cb26e1faa4d8e
ms.sourcegitcommit: 9a420b16aaa401a822ccfd9b133977ad8bd1024b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2019
ms.locfileid: "39637708"
---
# <a name="overview-of-records"></a><span data-ttu-id="8b157-104">记录概述</span><span class="sxs-lookup"><span data-stu-id="8b157-104">Overview of records management planning</span></span>

<span data-ttu-id="8b157-105">在 Microsoft 365 中管理记录可帮助组织遵守公司策略、法律和法规义务，同时降低风险和法律责任。</span><span class="sxs-lookup"><span data-stu-id="8b157-105">Managing records in Microsoft 365 helps an organization comply with their corporate policies, legal and regulatory obligations while reducing risk and legal liability.</span></span>

<span data-ttu-id="8b157-106">总体来说，将内容声明为记录意味着：</span><span class="sxs-lookup"><span data-stu-id="8b157-106">At a high level, declaring content as a record means that:</span></span>

- <span data-ttu-id="8b157-107">该项变为不可变（记录无法修改或删除）</span><span class="sxs-lookup"><span data-stu-id="8b157-107">The item becomes immutable (a record can't be modified or deleted)</span></span>

- <span data-ttu-id="8b157-108">记录了有关该项的其他活动</span><span class="sxs-lookup"><span data-stu-id="8b157-108">Additional activities about the item are logged</span></span>

- <span data-ttu-id="8b157-109">记录在声明的保留期结束后被处置</span><span class="sxs-lookup"><span data-stu-id="8b157-109">Records are finally disposed of after their stated lifetime is past.</span></span>

<span data-ttu-id="8b157-110">你可以使用[保留标签](labels.md)将内容分类为记录。</span><span class="sxs-lookup"><span data-stu-id="8b157-110">You can use retention labels to declare content as a record.</span></span> <span data-ttu-id="8b157-111">创建声明记录的保留标签后，可以将这些标签[发布](labels.md#how-retention-labels-work-with-retention-label-policies)（以便用户可以使用这些标签将内容分类为记录）或[自动应用](labels.md#applying-a-retention-label-automatically-based-on-conditions)到你想分类为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="8b157-111">After you create retention labels that declare records, you can either [publish](labels.md#how-retention-labels-work-with-retention-label-policies) those labels (so that users can use them to classify content as records) or [auto-apply those labels](labels.md#applying-a-retention-label-automatically-based-on-conditions) to content that you want to classify as a record.</span></span> <span data-ttu-id="8b157-112">通过使用保留标签声明记录，你可在 Office 365 中实施一致且单一的记录管理策略，而其他记录管理功能（如记录中心）仅适用于 SharePoint Online 内容。</span><span class="sxs-lookup"><span data-stu-id="8b157-112">By using retention labels to declare records, you can implement a single, consistent records-management strategy across all of Office 365, whereas other records-management features such as the Record Center apply only to content in SharePoint Online.</span></span>

<span data-ttu-id="8b157-113">请记住下列有关记录的事项：</span><span class="sxs-lookup"><span data-stu-id="8b157-113">Keep the following in mind about unindexed items:</span></span>

  - <span data-ttu-id="8b157-114">**记录是不可变的。**</span><span class="sxs-lookup"><span data-stu-id="8b157-114">**Records are immutable.**</span></span> <span data-ttu-id="8b157-115">除了 SharePoint 和 OneDrive for Business 以外，将内容声明为记录的保留标签还可以应用到 Exchange 内容。</span><span class="sxs-lookup"><span data-stu-id="8b157-115">A retention label that declares content as a record can be applied to content in Exchange, in addition to SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="8b157-116">但是，[记录版本控制](#record-versioning)仅在 SharePoint 和 OneDrive 中可用，对 Exchange 不可用。</span><span class="sxs-lookup"><span data-stu-id="8b157-116">However, [record versioning](#record-versioning) is available only in SharePoint and OneDrive, and not for Exchange.</span></span>

    <span data-ttu-id="8b157-117">在 Exchange 中，标记为记录的内容不可变，直到其最终删除。</span><span class="sxs-lookup"><span data-stu-id="8b157-117">In Exchange, content labeled as a record is immutable until its final deletion.</span></span> <span data-ttu-id="8b157-118">将 Exchange 项标记为记录后，会发生下述四项事件：</span><span class="sxs-lookup"><span data-stu-id="8b157-118">When an item is labeled as a record, four things happen:</span></span>

    - <span data-ttu-id="8b157-119">无法永久删除项。</span><span class="sxs-lookup"><span data-stu-id="8b157-119">The item can't be permanently deleted.</span></span>

    - <span data-ttu-id="8b157-120">无法编辑项。</span><span class="sxs-lookup"><span data-stu-id="8b157-120">The item can't be edited.</span></span>

    - <span data-ttu-id="8b157-121">无法更改标签。</span><span class="sxs-lookup"><span data-stu-id="8b157-121">The label can't be changed.</span></span>

    - <span data-ttu-id="8b157-122">无法删除标签。</span><span class="sxs-lookup"><span data-stu-id="8b157-122">The label can't be removed.</span></span>

  - <span data-ttu-id="8b157-123">**记录和文件夹。**</span><span class="sxs-lookup"><span data-stu-id="8b157-123">**Records and folders**</span></span> <span data-ttu-id="8b157-124">可将保留标签应用于 Exchange、SharePoint 和 OneDrive 中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b157-124">You can apply a retention label to a folder in Exchange, SharePoint, and OneDrive.</span></span> <span data-ttu-id="8b157-125">如果某文件夹被标记为记录，且将某项移到此文件夹中，则该项被标记为记录。</span><span class="sxs-lookup"><span data-stu-id="8b157-125">If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record.</span></span> <span data-ttu-id="8b157-126">将该项移出文件夹后，该项将仍被标记为记录。</span><span class="sxs-lookup"><span data-stu-id="8b157-126">When you move the item out of the folder, the item remains labeled as a record.</span></span>

    <span data-ttu-id="8b157-127">此外，如果将应用于某个文件夹（在 SharePoint 和 OneDrive 中）的记录标签更改为不将内容声明为记录的保留标签，则该文件夹中的各项将保留其现有的记录标签。</span><span class="sxs-lookup"><span data-stu-id="8b157-127">Also, if you change the record label that's applied to a folder (in SharePoint and OneDrive) to a retention label that does not declare content as a record, then items in the folder keep their existing  record label.</span></span>

    <span data-ttu-id="8b157-128">有关将保留标签应用于 SharePoint 和 OneDrive 文件夹的详细信息，请参阅[将默认保留标签应用于 SharePoint 库、文件夹或文档集中的所有内容](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。</span><span class="sxs-lookup"><span data-stu-id="8b157-128">For more information about applying retention labels to SharePoint and OneDrive folders, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>

  - <span data-ttu-id="8b157-129">**记录无法删除。**</span><span class="sxs-lookup"><span data-stu-id="8b157-129">Records can't be deleted</span></span> <span data-ttu-id="8b157-130">如果用户尝试删除 Exchange 中的记录，相应项会移至“可恢复项”文件夹中，如[保留策略如何处理留在原处的内容](retention-policies.md#content-in-mailboxes-and-public-folders)中所述。</span><span class="sxs-lookup"><span data-stu-id="8b157-130">If you attempt to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How a retention policy works with content in place](retention-policies.md#content-in-mailboxes-and-public-folders).</span></span>

    <span data-ttu-id="8b157-131">如果用户尝试删除 SharePoint 中的记录，将会显示错误，提醒你注意项未删除，仍留在库中。</span><span class="sxs-lookup"><span data-stu-id="8b157-131">If you attempt to delete a record in a SharePoint, you see an error that the item wasn't deleted, and the item remains in the library.</span></span>

    ![指明项未从 SharePoint 中删除的消息](media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    <span data-ttu-id="8b157-133">如果用户尝试删除 OneDrive 中的记录，相应项会移至保留库中，如 [保留策略如何处理留在原处的内容](retention-policies.md#content-in-onedrive-accounts-and-sharepoint-sites)中所述。</span><span class="sxs-lookup"><span data-stu-id="8b157-133">If you attempt to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in  [How a retention policy works with content in place](retention-policies.md#content-in-onedrive-accounts-and-sharepoint-sites).</span></span>

  - <span data-ttu-id="8b157-134">**记录标签无法移除。**</span><span class="sxs-lookup"><span data-stu-id="8b157-134">**Records labels can't be removed.**</span></span> <span data-ttu-id="8b157-135">对项应用记录标签后，仅该位置（例如 SharePoint 网站的网站集管理员）的管理员可以移除该记录标签。</span><span class="sxs-lookup"><span data-stu-id="8b157-135">Once a record label has been applied to an item, only the admin of that location (for example, a site collection admin of a SharePoint site) can remove that record label.</span></span>

## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="8b157-136">使用保留标签声明记录</span><span class="sxs-lookup"><span data-stu-id="8b157-136">Using retention labels to declare records</span></span>

<span data-ttu-id="8b157-137">创建保留标签时，可视需要使用保留标签将内容分类为记录。</span><span class="sxs-lookup"><span data-stu-id="8b157-137">When you create a retention label, you have the option to use the retention label to classify the content as a record.</span></span> <span data-ttu-id="8b157-138">要将内容声明为记录，你需要执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8b157-138">To declare content as a record, you need to do the following:</span></span>

1. <span data-ttu-id="8b157-139">创建保留标签。</span><span class="sxs-lookup"><span data-stu-id="8b157-139">Create a retention label and DLP policy.</span></span> <span data-ttu-id="8b157-140">在 Microsoft 365 合规性中心，转到“记录管理”\*\*\*\*\>“文件计划”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b157-140">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="8b157-141">在“文件计划”\*\*\*\* 页面上，单击“创建标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b157-141">On the **File plan** page, click  **Create a label**.</span></span>

2. <span data-ttu-id="8b157-142">在向导的“标签设置”\*\*\*\* 页面上，选择将保留标签设置为“将内容声明为记录”的选项。</span><span class="sxs-lookup"><span data-stu-id="8b157-142">On the **Label settings** page in the wizard, choose the option to set the retention label to declare content as a record.</span></span><br/>

   ![选中“使用标签将内容分类为‘记录’”复选框](media/recordversioning6.png)

3. <span data-ttu-id="8b157-144">将保留标签[发布](labels.md#how-retention-labels-work-with-retention-label-policies)或[自动应用](labels.md#applying-a-retention-label-automatically-based-on-conditions)到 SharePoint 网站和/或 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="8b157-144">[Publish](labels.md#how-retention-labels-work-with-retention-label-policies) or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) the retention label to SharePoint sites and/or OneDrive accounts.</span></span> 

### <a name="applying-a-retention-label-to-content"></a><span data-ttu-id="8b157-145">对内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="8b157-145">Applying a retention label to email by using rules</span></span>

<span data-ttu-id="8b157-146">对于 Exchange，任何具有邮箱写入权限的用户均可对电子邮件应用记录标签。</span><span class="sxs-lookup"><span data-stu-id="8b157-146">For Exchange, any user with write-access to the mailbox can apply a record label to an email message.</span></span> <span data-ttu-id="8b157-147">对于 SharePoint 和 OneDrive 内容，默认“成员”组（“参与”权限级别）中的任何用户均可将记录标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="8b157-147">For content in SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply a record label to content.</span></span> <span data-ttu-id="8b157-148">应用后，仅网站集管理员可删除或更改该记录标签。</span><span class="sxs-lookup"><span data-stu-id="8b157-148">Only a site collection admin can remove or change that record label after it's been applied.</span></span> <span data-ttu-id="8b157-149">如前所述，可以对内容自动应用将内容分类为记录的保留标签。</span><span class="sxs-lookup"><span data-stu-id="8b157-149">As previously explained, a retention label that classifies content as a record can be auto-applied to content.</span></span>

<span data-ttu-id="8b157-150">此处为记录标签应用到 SharePoint 网站或 OneDrive 帐户上的文档的情况。</span><span class="sxs-lookup"><span data-stu-id="8b157-150">Here's what this looks like when a record label is applied to a document on a SharePoint site or OneDrive account.</span></span>
<br/><br/>

<span data-ttu-id="8b157-151">:::image type="content" source="media/recordversioning7.png" alt-text="标记为记录的文档的详细信息窗格":::</span><span class="sxs-lookup"><span data-stu-id="8b157-151">:::image type="content" source="media/recordversioning7.png" alt-text="Details pane for document tagged as a record":::</span></span>

## <a name="record-versioning"></a><span data-ttu-id="8b157-152">记录版本控制</span><span class="sxs-lookup"><span data-stu-id="8b157-152">Record versioning</span></span>

<span data-ttu-id="8b157-153">记录管理的重要组成部分是能够将文档声明为记录并且使该记录不可变。</span><span class="sxs-lookup"><span data-stu-id="8b157-153">An essential part of records management is the ability to declare a document as a record and have that record be immutable.</span></span> <span data-ttu-id="8b157-154">同时，如果用户需要创建后续版本，记录不可变性可阻止文档的协作性。</span><span class="sxs-lookup"><span data-stu-id="8b157-154">At the same time, record immutability prevents collaboration on the document if people need to create subsequent versions.</span></span> <span data-ttu-id="8b157-155">例如，你可以将销售合同声明为记录，但需要使用新条款更新合同，并将最新版本声明为新记录，同时保留先前的记录版本。</span><span class="sxs-lookup"><span data-stu-id="8b157-155">For example, you might declare a sales contract as a record, but then need to update the contract with new terms and declare the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="8b157-156">对于这些类型的方案，SharePoint Online 和 OneDrive for Business 现在支持*记录版本控制*。</span><span class="sxs-lookup"><span data-stu-id="8b157-156">For these types of scenarios, SharePoint Online and OneDrive for Business now support *record versioning*.</span></span> <span data-ttu-id="8b157-157">不支持 OneNote 笔记本文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b157-157">OneNote notebook folders are not supported.</span></span>

<span data-ttu-id="8b157-158">要使用记录版本控制，第一步是使用 Microsoft 365 合规性中心创建声明记录的保留标签，并将其发布到所有 SharePoint 网站和/或 OneDrive 帐户，或者将其发布到特定的 SharePoint 网站和/或 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="8b157-158">To use record versioning, the first step is to use the Microsoft 365 compliance center to create and publish retention labels that declare records to all SharePoint sites and/or OneDrive accounts, or publish them to specific SharePoint sites and/or OneDrive accounts.</span></span> <span data-ttu-id="8b157-159">下一步是将发布的保留记录标签应用到文档。</span><span class="sxs-lookup"><span data-stu-id="8b157-159">The next step is to apply a published retention record label to a document.</span></span> <span data-ttu-id="8b157-160">完成此操作后，名为“记录状态”\*\* 的文档属性将显示在保留标签旁边，初始记录状态将为“已锁定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b157-160">When this is done, a document property, called *Record status* is displayed next to the retention label, and the initial record status will be **Locked**.</span></span> <span data-ttu-id="8b157-161">此时，你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b157-161">At this point, you can do the following things:</span></span>

  - <span data-ttu-id="8b157-162">**通过解锁和锁定记录状态属性，持续编辑文档的各个版本并将其声明为记录。**</span><span class="sxs-lookup"><span data-stu-id="8b157-162">**Continually edit and declare individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="8b157-163">当“记录状态”\*\*\*\* 属性设置为“已锁定”\*\*\*\* 时，仅保留声明为记录的版本。</span><span class="sxs-lookup"><span data-stu-id="8b157-163">Only the versions declared as records are retained when the **Record status** property is set to **Locked**.</span></span> <span data-ttu-id="8b157-164">这将降低保留不必要的文档版本和副本的风险。</span><span class="sxs-lookup"><span data-stu-id="8b157-164">This reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="8b157-165">**将文档自动保存在位于网站集内的本地记录存储库中。**</span><span class="sxs-lookup"><span data-stu-id="8b157-165">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="8b157-166">SharePoint 和 OneDrive 中的每个网站集将内容保存在其保留库中。</span><span class="sxs-lookup"><span data-stu-id="8b157-166">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="8b157-167">记录版本保存在此库中的“记录”文件夹内。</span><span class="sxs-lookup"><span data-stu-id="8b157-167">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="8b157-168">**保存包含所有版本的始终更新的文档。**</span><span class="sxs-lookup"><span data-stu-id="8b157-168">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="8b157-169">默认情况下，每个 SharePoint 和 OneDrive 文档的项菜单上都有可用的版本历史记录。</span><span class="sxs-lookup"><span data-stu-id="8b157-169">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="8b157-170">在此版本历史记录中，你可以轻松查看哪些版本是记录并查看这些文档。</span><span class="sxs-lookup"><span data-stu-id="8b157-170">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="8b157-171">对于具有将项声明为记录的保留标签的任何文档，记录版本控制自动可用。</span><span class="sxs-lookup"><span data-stu-id="8b157-171">Record versioning is automatically available for any document that has a retention label that declares the item as a record.</span></span> <span data-ttu-id="8b157-172">当用户通过详细信息窗格查看文档属性时，他们会将“记录状态”\*\*\*\* 从“已锁定”\*\*\*\* 切换为“已解锁”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b157-172">When a user views the document properties through the details pane, they toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="8b157-173">单击一下，即可在保留库的“记录”文件夹中创建一个记录，该记录将在其中保存剩余的保留期。</span><span class="sxs-lookup"><span data-stu-id="8b157-173">This single click creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> <span data-ttu-id="8b157-174">当文档处于解锁状态时，具有权限的任何用户均可编辑此文件。</span><span class="sxs-lookup"><span data-stu-id="8b157-174">While the document is unlocked, any user with permissions can edit the file.</span></span> <span data-ttu-id="8b157-175">但是，用户无法编辑此文件，因为它被视为声明的记录。</span><span class="sxs-lookup"><span data-stu-id="8b157-175">However, users can't delete the file, because it's considered a declared record.</span></span> <span data-ttu-id="8b157-176">进行必要的更改后，用户可以将“记录状态”\*\*\*\* 从“已解锁”\*\*\*\* 切换为“已锁定”\*\*\*\*，因此文档会再次声明为记录并且无法编辑。</span><span class="sxs-lookup"><span data-stu-id="8b157-176">After the necessary changes are made, the user can then toggle the **Record status** from **Unlocked** to **Locked**, so that the document is again declared a record and can't be edited.</span></span>
<br/><br/>

<span data-ttu-id="8b157-177">:::image type="content" source="media/recordversioning8.png" alt-text="文档上的记录状态属性标记为记录":::</span><span class="sxs-lookup"><span data-stu-id="8b157-177">:::image type="content" source="media/recordversioning8.png" alt-text="Record status property on document tagged as a record":::</span></span>

> [!NOTE]
> <span data-ttu-id="8b157-178">记录版本控制需要 Office 365 Enterprise E5 许可证，以便有权限的用户可以编辑无法在 SharePoint 网站或 OneDrive 帐户中声明为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="8b157-178">Record versioning requires an Office 365 Enterprise E5 license for each user who has permissions to edit content that's been declared a record in a SharePoint site or OneDrive account.</span></span> <span data-ttu-id="8b157-179">具有只读权限的用户不需要许可证。</span><span class="sxs-lookup"><span data-stu-id="8b157-179">Users who have read-only access don't require a license.</span></span>

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="8b157-180">锁定和解锁记录</span><span class="sxs-lookup"><span data-stu-id="8b157-180">Locking and unlocking a record</span></span>

<span data-ttu-id="8b157-181">记录标签分配到文档后，默认成员组（“参与”权限级别）中的任何用户均可将记录解锁或者锁定已解锁的记录。</span><span class="sxs-lookup"><span data-stu-id="8b157-181">After a record label is assigned to a document, any user in the default Members group (the Contribute permission level) can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

<span data-ttu-id="8b157-182">:::image type="content" source="media/recordversioning9.png" alt-text="记录状态显示记录文档已解锁":::</span><span class="sxs-lookup"><span data-stu-id="8b157-182">:::image type="content" source="media/recordversioning9.png" alt-text="Record status shows record document is unlocked":::</span></span>

<span data-ttu-id="8b157-183">当用户解锁记录时，将会发生以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b157-183">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="8b157-184">如果当前网站集没有保留库，将会创建一个。</span><span class="sxs-lookup"><span data-stu-id="8b157-184">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="8b157-185">如果保留库没有“记录”文件夹，将会创建一个。</span><span class="sxs-lookup"><span data-stu-id="8b157-185">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="8b157-186">“复制到”\*\*\*\* 操作会将文档的最新版本复制到“记录”文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b157-186">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="8b157-187">“复制到”\*\*\*\* 操作仅包含最新版本，不包含先前版本。</span><span class="sxs-lookup"><span data-stu-id="8b157-187">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="8b157-188">此复制的文档现在被视为文档的记录版本，其文件名格式为：\[标题 GUID 版本\#\]</span><span class="sxs-lookup"><span data-stu-id="8b157-188">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="8b157-189">在“记录”文件夹中创建的副本已添加到原始文档的版本历史记录中，此版本将在注释字段中显示“记录”\*\*\*\* 一词。</span><span class="sxs-lookup"><span data-stu-id="8b157-189">The copy created in the Records folder added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="8b157-190">原始文档现已成为可编辑（但不可删除）的新版本。</span><span class="sxs-lookup"><span data-stu-id="8b157-190">The original document is a new version that can be edited (but not deleted).</span></span> <span data-ttu-id="8b157-191">文档库列“项为记录”\*\*\*\* 仍显示“是”\*\*\*\* 值，因为文档仍被视为记录，即使它现在可以编辑。</span><span class="sxs-lookup"><span data-stu-id="8b157-191">The document library column **Item is a Record** still shows the **Yes** value because the document is still considered a record, even if it can now be edited.</span></span>

<span data-ttu-id="8b157-192">当用户锁定记录时，原始文档同样无法编辑。</span><span class="sxs-lookup"><span data-stu-id="8b157-192">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="8b157-193">但是，是解锁记录的操作将版本复制到保留库中的“记录”文件夹。</span><span class="sxs-lookup"><span data-stu-id="8b157-193">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="8b157-194">记录版本</span><span class="sxs-lookup"><span data-stu-id="8b157-194">Record versions</span></span>

<span data-ttu-id="8b157-195">每次用户解锁记录时，都会将最新版本复制到保留库的“记录”文件夹中，该版本在版本历史记录的“注释”\*\*\*\* 字段中的值为“记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b157-195">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

<span data-ttu-id="8b157-196">:::image type="content" source="media/recordversioning10.png" alt-text="保留库中显示的记录":::</span><span class="sxs-lookup"><span data-stu-id="8b157-196">:::image type="content" source="media/recordversioning10.png" alt-text="Record shown in the Preservation Hold library":::</span></span>

<span data-ttu-id="8b157-197">要查看版本历史记录，请在文档库中选择一个文档，然后在项菜单中单击“版本历史记录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b157-197">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="8b157-198">存储记录的位置。</span><span class="sxs-lookup"><span data-stu-id="8b157-198">Where rules are stored</span></span>

<span data-ttu-id="8b157-199">记录保存在网站集顶层站点的保留库内的“记录”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8b157-199">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="8b157-200">在顶层站点的左侧导航中，选择“网站内容”\*\*\*\*\>保留库”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b157-200">In the left nav on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

<span data-ttu-id="8b157-201">:::image type="content" source="media/recordversioning11.png" alt-text="保留库":::</span><span class="sxs-lookup"><span data-stu-id="8b157-201">:::image type="content" source="media/recordversioning11.png" alt-text="Preservation hold library":::</span></span>

<br/><br/>

<span data-ttu-id="8b157-202">:::image type="content" source="media/recordversioning12.png" alt-text="保留库中的“记录”文件夹":::</span><span class="sxs-lookup"><span data-stu-id="8b157-202">:::image type="content" source="media/recordversioning12.png" alt-text="The Records folder in the Preservation Hold library":::</span></span>

<span data-ttu-id="8b157-203">保留库仅对网站集管理员可见。</span><span class="sxs-lookup"><span data-stu-id="8b157-203">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="8b157-204">此外，默认情况下保留库不存在。</span><span class="sxs-lookup"><span data-stu-id="8b157-204">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="8b157-205">仅当受保存标签影响的内容在网站集中第一次删除时才会创建。</span><span class="sxs-lookup"><span data-stu-id="8b157-205">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="8b157-206">搜索记录版本控制事件的审核日志</span><span class="sxs-lookup"><span data-stu-id="8b157-206">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="8b157-207">锁定和解锁记录的操作会记录在 Office 365 审核日志中。</span><span class="sxs-lookup"><span data-stu-id="8b157-207">The actions of locking and unlocking records are logged in the Office 365 audit log.</span></span> <span data-ttu-id="8b157-208">你可以搜索特定活动“将记录状态更改为已锁定”\*\*\*\* 和“将记录状态更改为已解锁”\*\*\*\*，这些活动位于安全与合规性中心“审核日志搜索”\*\*\*\* 页面“活动”\*\*\*\* 下拉列表中的“文件和页面活动”\*\*\*\* 部分。</span><span class="sxs-lookup"><span data-stu-id="8b157-208">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

<span data-ttu-id="8b157-209">:::image type="content" source="media/recordversioning13.png" alt-text="搜索记录版本控制事件的审核日志":::</span><span class="sxs-lookup"><span data-stu-id="8b157-209">:::image type="content" source="media/recordversioning13.png" alt-text="Search the audit log for record versioning events":::</span></span>

<span data-ttu-id="8b157-210">有关搜索这些事件的详细信息，请参阅[在安全与合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)的“文件和页面活动”部分。</span><span class="sxs-lookup"><span data-stu-id="8b157-210">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>
