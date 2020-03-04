---
title: 删除保留的基于云的邮箱的 "可恢复的项目" 文件夹中的项目-管理员帮助
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: "对于管理员：删除中的项目 \n\nExchange Online 邮箱的 er 的 \"可恢复的项目\" 文件夹，即使该邮箱位于 \"合法保留\" 中也是如此。 这是一种删除意外溅入 Office 365 中的数据的有效方法。"
ms.openlocfilehash: 5c8614c0faf8ea0f807b09cb24ccd3409dd7facb
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409647"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="6ae25-105">删除保留的基于云的邮箱的 "可恢复的项目" 文件夹中的项目-管理员帮助</span><span class="sxs-lookup"><span data-stu-id="6ae25-105">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="6ae25-106">Exchange Online 邮箱的 "可恢复的项目" 文件夹存在，以防止意外或恶意删除。</span><span class="sxs-lookup"><span data-stu-id="6ae25-106">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="6ae25-107">它还用于存储由 Office 365 合规性功能（如保留和电子数据展示搜索）保留和访问的项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-107">It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="6ae25-108">但是，在某些情况下，组织可能会在必须删除的 "可恢复的项目" 文件夹中包含意外保留的数据。</span><span class="sxs-lookup"><span data-stu-id="6ae25-108">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="6ae25-109">例如，用户可能在不知情的情况下发送或转发包含敏感信息的电子邮件或可能有严重业务后果的信息。</span><span class="sxs-lookup"><span data-stu-id="6ae25-109">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="6ae25-110">即使邮件永久删除，它仍可能会无限期保留，因为邮箱中已设置了合法保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-110">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="6ae25-111">此方案称为数据外泄，因为数据被意外地溅入 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="6ae25-111">This scenario is known as data spillage because data has been unintentionally spilled into Office 365.</span></span> <span data-ttu-id="6ae25-112">在这些情况下，您可以删除 Exchange Online 邮箱的用户的 "可恢复的项目" 文件夹中的项目，即使该邮箱是使用 Office 365 中的一种不同的保留功能来保留的。</span><span class="sxs-lookup"><span data-stu-id="6ae25-112">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="6ae25-113">这些保留类型包括诉讼保留、就地保留、电子数据展示保留和 Office 365 保留策略（在 Office 365 或 Microsoft 365 的安全与合规中心中创建）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-113">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="6ae25-114">本文介绍如何从处于保留状态的基于云的邮箱的 "可恢复的项目" 文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-114">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="6ae25-115">此过程涉及到禁用对邮箱的访问和禁用单个项目恢复，禁用托管文件夹助理处理邮箱，暂时删除保留，从 "可恢复的项目" 文件夹中删除项目，然后还原邮箱设置为其以前的配置。</span><span class="sxs-lookup"><span data-stu-id="6ae25-115">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="6ae25-116">过程如下：</span><span class="sxs-lookup"><span data-stu-id="6ae25-116">Here's the process:</span></span> 
  
[<span data-ttu-id="6ae25-117">步骤1：收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="6ae25-117">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="6ae25-118">步骤2：准备邮箱</span><span class="sxs-lookup"><span data-stu-id="6ae25-118">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="6ae25-119">步骤3：从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-119">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="6ae25-120">步骤4：从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-120">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="6ae25-121">步骤5：删除 "可恢复的项目" 文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="6ae25-121">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="6ae25-122">步骤6：将邮箱还原到其以前的状态</span><span class="sxs-lookup"><span data-stu-id="6ae25-122">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="6ae25-123">本文中所述的过程将导致从 Exchange Online 邮箱永久删除（清除）的数据。</span><span class="sxs-lookup"><span data-stu-id="6ae25-123">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="6ae25-124">这意味着无法恢复从 "可恢复的项目" 文件夹中删除的邮件，也不会提供用于法律查询或其他合规性的邮件。</span><span class="sxs-lookup"><span data-stu-id="6ae25-124">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="6ae25-125">如果要从作为诉讼保留的一部分的邮箱中删除邮件，请在 "安全与合规中心" 中创建的 "就地保留"、"电子数据展示保留" 或 "Office 365 保留策略" 中，与您的记录管理或法律部门进行核实在删除保留之前。</span><span class="sxs-lookup"><span data-stu-id="6ae25-125">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="6ae25-126">您的组织可能有定义邮箱处于保留状态或 data 外泄事件是否优先的策略。</span><span class="sxs-lookup"><span data-stu-id="6ae25-126">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="6ae25-127">开始之前</span><span class="sxs-lookup"><span data-stu-id="6ae25-127">Before you begin</span></span>

- <span data-ttu-id="6ae25-128">若要创建并运行内容搜索，您必须是电子数据展示管理员角色组的成员，或者分配有“合规性搜索”管理角色。</span><span class="sxs-lookup"><span data-stu-id="6ae25-128">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="6ae25-129">若要删除邮件，您必须是组织管理角色组的成员或分配有“搜索并清除”管理角色。</span><span class="sxs-lookup"><span data-stu-id="6ae25-129">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="6ae25-130">有关将用户添加到角色组的信息，请参阅[分配安全与合规中心中的电子数据展示权限](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-130">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).</span></span>
    
- <span data-ttu-id="6ae25-131">非活动邮箱不支持本文中介绍的过程。</span><span class="sxs-lookup"><span data-stu-id="6ae25-131">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="6ae25-132">这是因为在删除保留（或 Office 365 保留策略）后，不能将其重新应用到非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-132">That's because you can't reapply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="6ae25-133">从非活动邮箱删除保留时，它会更改为标准软删除邮箱，并且在托管文件夹助理处理后，将从组织中永久删除。</span><span class="sxs-lookup"><span data-stu-id="6ae25-133">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="6ae25-134">您无法对已被分配到 Office 365 保留策略的邮箱执行此过程，该保留策略已通过保留锁定进行锁定。</span><span class="sxs-lookup"><span data-stu-id="6ae25-134">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock.</span></span> <span data-ttu-id="6ae25-135">这是因为保留锁可防止您从 Office 365 保留策略中删除或排除邮箱，也无法在邮箱上禁用托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="6ae25-135">That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="6ae25-136">有关锁定保留策略的详细信息，请参阅[锁定保留策略](retention-policies.md#locking-a-retention-policy)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-136">For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="6ae25-137">如果未将邮箱置于保留状态（或未启用单个项目恢复），则可以从 "可恢复的项目" 文件夹中删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-137">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="6ae25-138">有关如何执行此操作的详细信息，请参阅[在 Office 365 组织中搜索和删除电子邮件](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-138">For more information about how to do this, see [Search for and delete email messages in your Office 365 organization](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="6ae25-139">步骤1：收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="6ae25-139">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="6ae25-140">第一步是收集将影响此过程的目标邮箱中的所选属性。</span><span class="sxs-lookup"><span data-stu-id="6ae25-140">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="6ae25-141">请务必记下这些设置或将其保存到一个文本文件中，因为在从 "可恢复的项目" 文件夹中删除项目后，您将更改其中一些属性，然后再还原为第6步中的原始值。</span><span class="sxs-lookup"><span data-stu-id="6ae25-141">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="6ae25-142">下面列出了需要收集的邮箱属性。</span><span class="sxs-lookup"><span data-stu-id="6ae25-142">Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="6ae25-143">*SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;如有必要，您将禁用单个恢复并在步骤3中增加已删除项目的保留期。</span><span class="sxs-lookup"><span data-stu-id="6ae25-143">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="6ae25-144">*LitigationHoldEnabled*和*InPlaceHolds* ;您需要确定邮箱上放置的所有保留，以便可以在步骤3中临时删除它们。</span><span class="sxs-lookup"><span data-stu-id="6ae25-144">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="6ae25-145">请参阅[详细信息](#more-information)部分，了解有关如何识别邮箱上可能放置的类型保留的提示。</span><span class="sxs-lookup"><span data-stu-id="6ae25-145">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="6ae25-146">此外，您还需要获取邮箱客户端访问设置，以便您可以暂时禁用它们，以便所有者（或其他用户）在此过程中无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-146">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="6ae25-147">最后，您可以获取 "可恢复的项目" 文件夹中的当前大小和项目数。</span><span class="sxs-lookup"><span data-stu-id="6ae25-147">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="6ae25-148">在第5步中删除 "可恢复的项目" 文件夹中的项目后，您将使用此信息验证项目是否已删除。</span><span class="sxs-lookup"><span data-stu-id="6ae25-148">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="6ae25-149">[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-149">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="6ae25-150">请务必对已在 Exchange Online 中为其分配了适当管理角色的管理员帐户使用用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="6ae25-150">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="6ae25-151">运行以下命令以获取有关单个项目恢复和已删除项目保留期限的信息。</span><span class="sxs-lookup"><span data-stu-id="6ae25-151">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="6ae25-152">如果启用了单个项目恢复，则必须在第2步中禁用它。</span><span class="sxs-lookup"><span data-stu-id="6ae25-152">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="6ae25-153">如果已删除项目的保留期未设置为30天（Exchange Online 中的最大值），则可以在第2步中增加它。</span><span class="sxs-lookup"><span data-stu-id="6ae25-153">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="6ae25-154">运行以下命令以获取邮箱的邮箱访问设置。</span><span class="sxs-lookup"><span data-stu-id="6ae25-154">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="6ae25-155">您将在步骤2中禁用所有这些访问方法。</span><span class="sxs-lookup"><span data-stu-id="6ae25-155">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="6ae25-156">运行以下命令以获取有关保留和适用于邮箱的 Office 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="6ae25-156">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="6ae25-157">如果*InPlaceHolds*属性中的值过多，并且不是全部显示，则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行中显示每个值。</span><span class="sxs-lookup"><span data-stu-id="6ae25-157">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="6ae25-158">运行以下命令以获取有关组织范围内的 Office 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="6ae25-158">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   <span data-ttu-id="6ae25-159">如果您的组织具有任何组织范围的 Office 365 保留策略，则必须在步骤3中将邮箱排除在这些策略之外。</span><span class="sxs-lookup"><span data-stu-id="6ae25-159">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="6ae25-160">如果*InPlaceHolds*属性中的值过多，并且不是全部显示，则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行中显示每个值。</span><span class="sxs-lookup"><span data-stu-id="6ae25-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="6ae25-161">运行以下命令，获取用户主邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="6ae25-161">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="6ae25-162">如果已启用用户的存档邮箱，请运行以下命令，以获取存档邮箱中 "可恢复的项目" 文件夹中的文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="6ae25-162">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="6ae25-163">删除步骤5中的项目时，可以选择删除或不删除用户的主存档邮箱中的 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-163">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="6ae25-164">如果为邮箱启用了自动扩展存档，则不会删除辅助存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-164">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="6ae25-165">步骤2：准备邮箱</span><span class="sxs-lookup"><span data-stu-id="6ae25-165">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="6ae25-166">收集并保存有关邮箱的信息后，下一步是通过执行以下任务来准备邮箱：</span><span class="sxs-lookup"><span data-stu-id="6ae25-166">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="6ae25-167">**禁用对邮箱的客户端访问**，以便邮箱所有者无法访问其邮箱，并在此过程中对邮箱数据进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="6ae25-167">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="6ae25-168">将**已删除项目的保留期增加**到30天（Exchange Online 中的最大值），以便从 "可恢复的项目" 文件夹中清除这些项目，然后才能在步骤5中将其删除。</span><span class="sxs-lookup"><span data-stu-id="6ae25-168">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="6ae25-169">**禁用单个项目恢复**，以便在从第5步中的 "可恢复的项目" 文件夹中删除项目后，将不会保留项目（在已删除项目的保留期内）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-169">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="6ae25-170">**禁用托管文件夹助理**，使其不处理邮箱，并保留您在步骤5中删除的项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-170">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="6ae25-171">在 Exchange Online PowerShell 中执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="6ae25-171">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="6ae25-172">运行以下命令以禁用对邮箱的所有客户端访问。</span><span class="sxs-lookup"><span data-stu-id="6ae25-172">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="6ae25-173">命令语法假定已在邮箱上启用所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="6ae25-173">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="6ae25-174">最长可能需要60分钟才能禁用邮箱的所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="6ae25-174">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="6ae25-175">请注意，禁用这些访问方法不会断开他们当前登录的邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="6ae25-175">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="6ae25-176">如果未登录到所有者，则在禁用这些访问方法后，他们将无法访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-176">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="6ae25-177">运行以下命令，将已删除项目的保留期增加到最大30天。</span><span class="sxs-lookup"><span data-stu-id="6ae25-177">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="6ae25-178">这假定当前设置少于30天。</span><span class="sxs-lookup"><span data-stu-id="6ae25-178">This assumes that the current setting is less than 30 days.</span></span> 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="6ae25-179">运行以下命令以禁用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="6ae25-179">Run the following command to disable single item recovery.</span></span>
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="6ae25-180">可能需要长达60分钟才能禁用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="6ae25-180">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="6ae25-181">在此期间之前，请勿删除 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-181">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="6ae25-182">运行以下命令以阻止托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-182">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="6ae25-183">正如前面所述，仅当具有保留锁定的 Office 365 保留策略未应用于邮箱时，才可以禁用托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="6ae25-183">As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="6ae25-184">步骤3：从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-184">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="6ae25-185">从 "可恢复的项目" 文件夹中删除项目之前的最后一步是删除邮箱上的所有保留（在第1步中标识）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-185">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="6ae25-186">必须删除所有保留，以便在从 "可恢复的项目" 文件夹中删除项目后，不会保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-186">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="6ae25-187">以下各节包含有关删除邮箱的不同类型的保留的信息。</span><span class="sxs-lookup"><span data-stu-id="6ae25-187">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="6ae25-188">请参阅[详细信息](#more-information)部分，了解有关如何识别邮箱上可能放置的类型保留的提示。</span><span class="sxs-lookup"><span data-stu-id="6ae25-188">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="6ae25-189">有关详细信息，请参阅[如何识别 Exchange Online 邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-189">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6ae25-190">如前所述，在从邮箱中删除保留之前，请与您的记录管理或法律部门核实。</span><span class="sxs-lookup"><span data-stu-id="6ae25-190">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="6ae25-191">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-191">Litigation Hold</span></span>
  
<span data-ttu-id="6ae25-192">在 Exchange Online PowerShell 中运行以下命令，以从邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-192">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="6ae25-193">类似于禁用客户端访问方法和单个项目恢复，可能需要长达60分钟的时间才能删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-193">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="6ae25-194">在此时间段过后，请勿从 "可恢复的项目" 文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-194">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="6ae25-195">就地保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-195">In-Place Hold</span></span>
  
<span data-ttu-id="6ae25-196">在 Exchange Online PowerShell 中运行以下命令，以标识邮箱中放置的就地保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-196">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="6ae25-197">对您在步骤1中标识的就地保留使用 GUID。</span><span class="sxs-lookup"><span data-stu-id="6ae25-197">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="6ae25-198">在确定就地保留之后，可以使用 Exchange 管理中心（EAC）或 Exchange Online PowerShell 将邮箱从保留中删除。</span><span class="sxs-lookup"><span data-stu-id="6ae25-198">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="6ae25-199">有关详细信息，请参阅[创建或删除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-199">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="6ae25-200">应用于特定邮箱的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="6ae25-200">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="6ae25-201">在[Security & 合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以确定应用于邮箱的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="6ae25-201">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="6ae25-202">对您在步骤1中标识`mbx`的`skp`保留策略使用 GUID （不包括或前缀）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-202">Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="6ae25-203">在确定保留策略后，请转到安全 & 合规性中心中的 "**信息管理** \> "**保留**页，编辑在上一步中标识的保留策略，然后从保留策略中包含的收件人列表中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-203">After you identify the retention policy, go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="6ae25-204">组织范围内的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="6ae25-204">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="6ae25-205">组织范围和 Exchange 范围的 Office 365 保留策略应用于组织中的每个邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-205">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="6ae25-206">它们在组织级别（而不是邮箱级别）应用，并在您在步骤1中运行**set-organizationconfig** cmdlet 时返回。</span><span class="sxs-lookup"><span data-stu-id="6ae25-206">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="6ae25-207">在[Security & 合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以确定组织范围内的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="6ae25-207">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="6ae25-208">对您在步骤1中确定`mbx`的组织范围的保留策略使用 GUID （不包括前缀）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-208">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="6ae25-209">在确定组织范围内的 Office 365 保留策略后，请转到安全 & 合规性中心中的 "**信息管理** \> "**保留**页，编辑在上一步中标识的每个组织范围的保留策略，并将邮箱添加到排除的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="6ae25-209">After you identify the organization-wide Office 365 retention policies, go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="6ae25-210">执行此操作会将用户的邮箱从保留策略中删除。</span><span class="sxs-lookup"><span data-stu-id="6ae25-210">Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="6ae25-211">Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="6ae25-211">Office 365 retention labels</span></span>

<span data-ttu-id="6ae25-212">每当用户应用配置为保留内容或保留内容，然后将内容删除到其邮箱中的任何文件夹或项目的标签时， *ComplianceTagHoldApplied*邮箱属性将设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="6ae25-212">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="6ae25-213">发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留状态或分配到 Office 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="6ae25-213">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="6ae25-214">若要查看*ComplianceTagHoldApplied*属性的值，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6ae25-214">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="6ae25-215">确定邮箱处于保留状态，因为保留标签应用于文件夹或项目，您可以使用 "安全和合规中心" 中的 "内容搜索" 工具来搜索带标签的项目，方法是使用 New-compliancetag 搜索条件。</span><span class="sxs-lookup"><span data-stu-id="6ae25-215">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="6ae25-216">有关详细信息，请参阅关键字查询中的 "搜索条件" 部分[和内容搜索的搜索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-216">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="6ae25-217">有关标签的详细信息，请参阅[Office 365 概述标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-217">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="6ae25-218">电子数据展示事例保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-218">eDiscovery case holds</span></span>
  
<span data-ttu-id="6ae25-219">在[Security & 合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令，以确定与应用于邮箱的电子数据展示事例关联的保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-219">Run the following commands in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox.</span></span> <span data-ttu-id="6ae25-220">使用您在步骤1中确定`UniH`的电子数据展示保留的 GUID （不包括前缀）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-220">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="6ae25-221">第二个命令显示与保留相关联的电子数据展示事例的名称;第三个命令显示保留的名称。</span><span class="sxs-lookup"><span data-stu-id="6ae25-221">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="6ae25-222">确定电子数据展示事例的名称和保留后，请转到合规中心中的**电子数据** \>展示**电子数据**展示页面，打开事例，并将邮箱从保留中删除。</span><span class="sxs-lookup"><span data-stu-id="6ae25-222">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="6ae25-223">有关详细信息，请参阅[电子数据展示事例](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-223">For more information, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="6ae25-224">步骤4：从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-224">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="6ae25-225">从邮箱中删除了任何类型的保留后， *DelayHoldApplied*或*DelayReleaseHoldApplied*邮箱属性的值将设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="6ae25-225">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="6ae25-226">在下次托管文件夹助理处理邮箱并检测已删除保留时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="6ae25-226">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="6ae25-227">这称为*延迟保留*，意味着实际删除保留的延迟时间为30天，以防止永久删除邮箱中的数据。</span><span class="sxs-lookup"><span data-stu-id="6ae25-227">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="6ae25-228">（延迟保留的目的是使管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。） 将延迟保留放在邮箱上时，该邮箱仍被视为无限持续时间处于保留状态，就像该邮箱处于诉讼保留状态一样。</span><span class="sxs-lookup"><span data-stu-id="6ae25-228">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="6ae25-229">30天后，延迟保留过期，Office 365 将自动尝试删除延迟保留（通过将*DelayHoldApplied*或*DelayReleaseHoldApplied*属性设置为**False**），以便删除保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-229">After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="6ae25-230">有关延迟保留的详细信息，请参阅[如何识别 Exchange Online 邮箱上的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)一节中的 "管理延迟挂起的邮箱" 一节。</span><span class="sxs-lookup"><span data-stu-id="6ae25-230">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="6ae25-231">在您可以删除步骤5中的项目之前，必须从邮箱中删除延迟保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-231">Before you can delete items in Step 5, you have to remove a delay hold from the mailbox.</span></span> <span data-ttu-id="6ae25-232">首先，通过在 Exchange Online PowerShell 中运行以下命令来确定是否对邮箱应用延迟保留：</span><span class="sxs-lookup"><span data-stu-id="6ae25-232">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

<span data-ttu-id="6ae25-233">如果将*DelayHoldApplied*或*DelayReleaseHoldApplied*属性的值设置为**False**，则不会在邮箱上放置延迟保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-233">If the value of either the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="6ae25-234">您可以转到步骤5并删除 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="6ae25-234">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="6ae25-235">如果*DelayHoldApplied*或*DelayReleaseHoldApplied*属性的值设置为**True**，则运行以下命令之一以删除延迟保留：</span><span class="sxs-lookup"><span data-stu-id="6ae25-235">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="6ae25-236">或</span><span class="sxs-lookup"><span data-stu-id="6ae25-236">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="6ae25-237">您必须在 Exchange Online 中向您分配 "合法保留" 角色，才能使用*RemoveDelayHoldApplied*或*RemoveDelayReleaseHoldApplied*参数。</span><span class="sxs-lookup"><span data-stu-id="6ae25-237">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="6ae25-238">步骤5：删除 "可恢复的项目" 文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="6ae25-238">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="6ae25-239">现在，您已准备好在 "可恢复的项目" 文件夹中实际删除项目，方法是使用 Security & 合规性中心中的[new-compliancesearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)和[new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6ae25-239">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch) and [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) cmdlets in the Security & Compliance Center.</span></span> 

<span data-ttu-id="6ae25-240">若要执行此操作，请参阅[搜索和删除电子邮件](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-240">To do this, see [Search for and delete email messages](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="6ae25-241">验证项目是否已被删除</span><span class="sxs-lookup"><span data-stu-id="6ae25-241">Verify that items were deleted</span></span>

<span data-ttu-id="6ae25-242">若要验证是否已成功删除邮箱的 "可恢复的项目" 文件夹中的项目，请使用 Exchange Online PowerShell 中的**get-mailboxfolderstatistics** cmdlet 检查 "可恢复的项目" 文件夹中的邮件大小和数量。</span><span class="sxs-lookup"><span data-stu-id="6ae25-242">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="6ae25-243">您可以将这些统计信息与您在步骤1中收集的统计信息进行比较。</span><span class="sxs-lookup"><span data-stu-id="6ae25-243">You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="6ae25-244">在中运行以下命令，以获取用户主邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="6ae25-244">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="6ae25-245">运行以下命令以获取用户存档邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="6ae25-245">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="6ae25-246">步骤6：将邮箱还原到其以前的状态</span><span class="sxs-lookup"><span data-stu-id="6ae25-246">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="6ae25-247">最后一步是将邮箱还原回其以前的配置。</span><span class="sxs-lookup"><span data-stu-id="6ae25-247">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="6ae25-248">这意味着重置您在步骤2中更改的属性，并重新应用您在步骤3中删除的保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-248">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="6ae25-249">这包括：</span><span class="sxs-lookup"><span data-stu-id="6ae25-249">This includes:</span></span>
  
- <span data-ttu-id="6ae25-250">将已删除项目的保留期更改回其以前的值。</span><span class="sxs-lookup"><span data-stu-id="6ae25-250">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="6ae25-251">或者，您可以仅将此设置保留为30天，即 Exchange Online 中的最大值。</span><span class="sxs-lookup"><span data-stu-id="6ae25-251">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="6ae25-252">重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="6ae25-252">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="6ae25-253">重新启用客户端访问方法，以便所有者可以访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-253">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="6ae25-254">重新应用已删除的保留策略和 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="6ae25-254">Reapplying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="6ae25-255">重新启用托管文件夹助理以处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-255">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="6ae25-256">建议您在重新启用托管文件夹助理以处理邮箱之前，等待24小时后再365应用保留策略（并验证是否已就绪）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-256">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="6ae25-257">在 Exchange Online PowerShell 中执行以下步骤（按指定的顺序）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-257">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="6ae25-258">运行以下命令，将已删除项目的保留期更改回其原始值。</span><span class="sxs-lookup"><span data-stu-id="6ae25-258">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="6ae25-259">这假定上一个设置的时间不到30天;例如，14天。</span><span class="sxs-lookup"><span data-stu-id="6ae25-259">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span> 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="6ae25-260">运行以下命令以重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="6ae25-260">Run the following command to re-enable single item recovery.</span></span>
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="6ae25-261">运行以下命令，将所有客户端访问方法重新启用到邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-261">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="6ae25-262">重新应用您在步骤3中删除的保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-262">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="6ae25-263">根据保留的类型，使用以下过程之一。</span><span class="sxs-lookup"><span data-stu-id="6ae25-263">Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="6ae25-264">**诉讼保留**</span><span class="sxs-lookup"><span data-stu-id="6ae25-264">**Litigation Hold**</span></span>
    
    <span data-ttu-id="6ae25-265">运行以下命令以重新启用邮箱的诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-265">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="6ae25-266">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="6ae25-266">**In-Place Hold**</span></span>
    
    <span data-ttu-id="6ae25-267">使用 EAC （或 Exchange Online PowerShell）将邮箱重新添加到就地保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-267">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="6ae25-268">**应用于特定邮箱的 Office 365 保留策略**</span><span class="sxs-lookup"><span data-stu-id="6ae25-268">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="6ae25-269">使用安全 & 合规性中心将邮箱重新添加到保留策略。</span><span class="sxs-lookup"><span data-stu-id="6ae25-269">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="6ae25-270">转到 "安全性 & 合规性中心" 中的 "**信息管理** \> "**保留**页，编辑保留策略，并将邮箱重新添加到应用保留策略的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="6ae25-270">Go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="6ae25-271">**组织范围内的 Office 365 保留策略**</span><span class="sxs-lookup"><span data-stu-id="6ae25-271">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="6ae25-272">如果通过从策略中排除组织范围或 Exchange 范围内的保留策略，则使用安全 & 合规性中心将邮箱从排除的用户列表中删除。</span><span class="sxs-lookup"><span data-stu-id="6ae25-272">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="6ae25-273">转到 "安全性 & 合规性中心" 中的 "**信息管理** \> "**保留**页，编辑组织范围的保留策略，然后从排除的收件人列表中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-273">Go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="6ae25-274">执行此操作将把保留策略重新应用到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-274">Doing this will reapply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="6ae25-275">**电子数据展示事例保留**</span><span class="sxs-lookup"><span data-stu-id="6ae25-275">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="6ae25-276">使用安全 & 合规性中心将邮箱重新添加到与电子数据展示事例相关联的保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-276">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="6ae25-277">转到 "**电子数据展示** \> **电子数据**展示" 页，打开事例，并将邮箱重新添加到保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-277">Go to the **eDiscovery** \> **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="6ae25-278">运行以下命令，以允许托管文件夹助理再次处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-278">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="6ae25-279">如前所述，在重新启用托管文件夹助理之前，我们建议您等待24小时后再重新应用365保留策略（并验证是否已就绪）。</span><span class="sxs-lookup"><span data-stu-id="6ae25-279">As previously stated, we recommend that you wait 24 hours after reapplying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="6ae25-280">若要验证是否已将邮箱还原回其以前的配置，可以运行以下命令，然后将设置与您在步骤1中收集的设置进行比较。</span><span class="sxs-lookup"><span data-stu-id="6ae25-280">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="6ae25-281">更多信息</span><span class="sxs-lookup"><span data-stu-id="6ae25-281">More information</span></span>

<span data-ttu-id="6ae25-282">下面的表格介绍了在运行 Set-organizationconfig **cmdlet 或** \*\*\*\* cmdlet 时，如何根据*InPlaceHolds*属性中的值标识不同类型的保留。</span><span class="sxs-lookup"><span data-stu-id="6ae25-282">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="6ae25-283">有关更多详细信息，请参阅[如何识别 Exchange Online 邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae25-283">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="6ae25-284">如前所述，在成功删除 "可恢复的项目" 文件夹中的项目之前，必须从邮箱中删除所有保留和 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="6ae25-284">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="6ae25-285">**保留类型**</span><span class="sxs-lookup"><span data-stu-id="6ae25-285">**Hold type**</span></span>|<span data-ttu-id="6ae25-286">**示例值**</span><span class="sxs-lookup"><span data-stu-id="6ae25-286">**Example value**</span></span>|<span data-ttu-id="6ae25-287">**如何识别保留**</span><span class="sxs-lookup"><span data-stu-id="6ae25-287">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6ae25-288">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-288">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="6ae25-289">*LitigationHoldEnabled*属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="6ae25-289">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="6ae25-290">就地保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-290">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="6ae25-291">*InPlaceHolds*属性包含邮箱中放置的就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="6ae25-291">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="6ae25-292">您可以指示这是就地保留，因为 GUID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="6ae25-292">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="6ae25-293">您可以使用 Exchange `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Online PowerShell 中的命令来获取有关邮箱的就地保留的信息。</span><span class="sxs-lookup"><span data-stu-id="6ae25-293">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="6ae25-294">在应用于特定邮箱的安全性 & 合规性中心中的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="6ae25-294">Office 365 retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="6ae25-295">或</span><span class="sxs-lookup"><span data-stu-id="6ae25-295">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="6ae25-296">当您运行**邮箱获取**cmdlet 时， *InPlaceHolds*属性还包含应用于邮箱的 Office 365 保留策略的 guid。</span><span class="sxs-lookup"><span data-stu-id="6ae25-296">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="6ae25-297">您可以确定保留策略，因为 GUID 以`mbx`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="6ae25-297">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="6ae25-298">如果保留策略的 GUID 以`skp`前缀开头，则表示该保留策略应用于 Skype for business 会话。</span><span class="sxs-lookup"><span data-stu-id="6ae25-298">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="6ae25-299">若要标识应用于邮箱的 Office 365 保留策略，请在 Security & 合规性中心 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6ae25-299">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="6ae25-300">运行此命令时， `mbx`请`skp`务必删除或前缀。</span><span class="sxs-lookup"><span data-stu-id="6ae25-300">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="6ae25-301">安全 & 合规中心中的组织范围内的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="6ae25-301">Organization-wide Office 365 retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="6ae25-302">无值</span><span class="sxs-lookup"><span data-stu-id="6ae25-302">No value</span></span>  <br/> <span data-ttu-id="6ae25-303">或</span><span class="sxs-lookup"><span data-stu-id="6ae25-303">or</span></span>  <br/>  <span data-ttu-id="6ae25-304">`-mbxe9b52bf7ab3b46a286308ecb29624696`（指示邮箱已从组织范围的策略中排除）</span><span class="sxs-lookup"><span data-stu-id="6ae25-304">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="6ae25-305">即使在运行**邮箱**cmdlet 时， *InPlaceHolds*属性为空，仍可能会将一个或多个组织范围内的 Office 365 保留策略应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="6ae25-305">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="6ae25-306">若要验证这一点，可以在`Get-OrganizationConfig | FL InPlaceHolds` Exchange Online PowerShell 中运行命令，以获取组织范围内的 Office 365 保留策略的 guid 列表。</span><span class="sxs-lookup"><span data-stu-id="6ae25-306">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="6ae25-307">应用于 Exchange 邮箱的组织范围的保留策略的 GUID 以`mbx`前缀开头;例如， `mbxa3056bb15562480fadb46ce523ff7b02`。</span><span class="sxs-lookup"><span data-stu-id="6ae25-307">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="6ae25-308">若要标识应用于邮箱的组织范围内的 Office 365 保留策略，请在 Security & 合规性中心 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6ae25-308">To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="6ae25-309">如果从组织范围内的 Office 365 保留策略中排除了邮箱，则在运行 "**获取邮箱**" cmdlet 时，保留策略的 GUID 将显示在用户邮箱的*InPlaceHolds*属性中。它是由前缀`-mbx`标识的;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="6ae25-309">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="6ae25-310">安全 & 合规中心中的电子数据展示案例保留</span><span class="sxs-lookup"><span data-stu-id="6ae25-310">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="6ae25-311">*InPlaceHolds*属性还包含与可能位于邮箱上的安全性 & 合规性中心中的电子数据展示事例相关的任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="6ae25-311">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="6ae25-312">你可以告诉这是电子数据展示事例保留，因为 GUID 以`UniH`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="6ae25-312">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="6ae25-313">您可以使用 Security `Get-CaseHoldPolicy` & 合规性中心 PowerShell 中的 cmdlet 来获取有关邮箱中的保留与邮箱关联的电子数据展示事例的信息。</span><span class="sxs-lookup"><span data-stu-id="6ae25-313">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="6ae25-314">例如，您可以运行命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`以显示邮箱上的事例保留的名称。</span><span class="sxs-lookup"><span data-stu-id="6ae25-314">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="6ae25-315">运行此命令时， `UniH`请务必删除前缀。</span><span class="sxs-lookup"><span data-stu-id="6ae25-315">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="6ae25-316">若要标识与邮箱的保留内容相关联的电子数据展示事例，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6ae25-316">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


