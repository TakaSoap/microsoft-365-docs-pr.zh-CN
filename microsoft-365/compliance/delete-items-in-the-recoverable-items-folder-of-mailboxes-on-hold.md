---
title: 删除云邮箱保留中的 "可恢复的项目" 文件夹中的项目
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
description: 了解管理员如何删除 Exchange Online 邮箱的用户的 "可恢复的项目" 文件夹中的项目，即使该邮箱位于法定保留中也是如此。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7a51a78280885a8a7aa7c65a0c04110b46ed7f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919952"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a><span data-ttu-id="1fcc2-103">删除保留状态云邮箱的“可恢复的项目”文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="1fcc2-103">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>

<span data-ttu-id="1fcc2-104">Exchange Online 邮箱的 "可恢复的项目" 文件夹存在，以防止意外或恶意删除。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-104">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="1fcc2-105">它还用于存储由合规性功能（如保留和电子数据展示搜索）保留和访问的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-105">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="1fcc2-106">但是，在某些情况下，组织可能会在必须删除的 "可恢复的项目" 文件夹中包含意外保留的数据。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-106">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="1fcc2-107">例如，用户可能在不知情的情况下发送或转发包含敏感信息的电子邮件或可能有严重业务后果的信息。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-107">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="1fcc2-108">即使邮件永久删除，它仍可能会无限期保留，因为邮箱中已设置了合法保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-108">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="1fcc2-109">此方案称为 *数据外泄* ，因为数据被意外地 *溅* 入 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-109">This scenario is known as *data spillage* because data has been unintentionally *spilled* into Office 365.</span></span> <span data-ttu-id="1fcc2-110">在这些情况下，您可以删除 Exchange Online 邮箱的用户的 "可恢复的项目" 文件夹中的项目，即使该邮箱是使用 Office 365 中的一种不同的保留功能来保留的。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-110">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="1fcc2-111">这些保留类型包括诉讼保留、In-Place 保留、电子数据展示保留和在 Office 365 或 Microsoft 365 的安全与合规中心中创建的保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-111">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="1fcc2-112">本文介绍管理员如何可以从处于保留状态的基于云的邮箱的 "可恢复的项目" 文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-112">This article explains how admins can delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="1fcc2-113">此过程涉及到禁用对邮箱的访问和禁用单个项目恢复，禁用托管文件夹助理处理邮箱，暂时删除保留，从 "可恢复的项目" 文件夹中删除项目，然后将邮箱还原到其以前的配置。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-113">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="1fcc2-114">过程如下：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-114">Here's the process:</span></span>
  
[<span data-ttu-id="1fcc2-115">步骤1：收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="1fcc2-115">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="1fcc2-116">步骤2：准备邮箱</span><span class="sxs-lookup"><span data-stu-id="1fcc2-116">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="1fcc2-117">步骤3：从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-117">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="1fcc2-118">步骤4：从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-118">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="1fcc2-119">步骤5：删除 "可恢复的项目" 文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="1fcc2-119">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="1fcc2-120">步骤6：将邮箱还原到其以前的状态</span><span class="sxs-lookup"><span data-stu-id="1fcc2-120">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="1fcc2-121">本文中所述的过程将导致数据永久删除 (从 Exchange Online 邮箱中清除) 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-121">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="1fcc2-122">这意味着无法恢复从 "可恢复的项目" 文件夹中删除的邮件，也不会提供用于法律查询或其他合规性的邮件。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-122">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="1fcc2-123">如果要从作为诉讼保留的一部分的邮箱中删除邮件，请在 "安全与合规中心" 中创建的 In-Place 保留、电子数据展示保留或保留策略，在删除保留项之前，请与您的记录管理或法律部门进行确认。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-123">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="1fcc2-124">您的组织可能有定义邮箱处于保留状态或 data 外泄事件是否优先的策略。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-124">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span>
  
## <a name="before-you-delete-items"></a><span data-ttu-id="1fcc2-125">删除项目之前</span><span class="sxs-lookup"><span data-stu-id="1fcc2-125">Before you delete items</span></span>

- <span data-ttu-id="1fcc2-126">若要创建并运行内容搜索，您必须是电子数据展示管理员角色组的成员，或者分配有“合规性搜索”管理角色。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-126">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="1fcc2-127">若要删除邮件，您必须是组织管理角色组的成员或分配有“搜索并清除”管理角色。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-127">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="1fcc2-128">有关将用户添加到角色组的信息，请参阅[分配安全与合规中心中的电子数据展示权限](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-128">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).</span></span>

- <span data-ttu-id="1fcc2-129">非活动邮箱不支持本文中介绍的过程。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-129">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="1fcc2-130">这是因为在删除保留 (或保留策略时无法将其重新应用) 到非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-130">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="1fcc2-131">从非活动邮箱删除保留时，它会更改为标准软删除邮箱，并且在托管文件夹助理处理后，将从组织中永久删除。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-131">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="1fcc2-132">您无法对已为其分配保留设置的邮箱执行此过程，该策略已通过使用保留锁定进行锁定。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-132">You can't perform this procedure for a mailbox that has been assigned retention settings with a policy that's locked by using Preservation Lock.</span></span> <span data-ttu-id="1fcc2-133">这是因为，这是因为此锁定会阻止您从策略中删除或排除邮箱，也无法在邮箱上禁用托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-133">That's because this lock prevents you from removing or excluding the mailbox from the policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="1fcc2-134">有关锁定策略以进行保留的详细信息，请参阅 [使用保留锁定来限制对保留策略和保留标签策略的更改](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-134">For more information about locking policies for retention,see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

- <span data-ttu-id="1fcc2-135">如果未将邮箱置于保留状态 (或者未启用单个项目恢复) ，则可以从 "可恢复的项目" 文件夹中删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-135">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-136">有关如何执行此操作的详细信息，请参阅 [在组织中搜索和删除电子邮件](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-136">For more information about how to do this, see [Search for and delete email messages in your organization](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="1fcc2-137">步骤1：收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="1fcc2-137">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="1fcc2-138">第一步是收集将影响此过程的目标邮箱中的所选属性。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-138">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="1fcc2-139">请务必记下这些设置或将其保存到一个文本文件中，因为在从 "可恢复的项目" 文件夹中删除项目后，您将更改其中一些属性，然后再还原为第6步中的原始值。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-139">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-140">下面列出了需要收集的邮箱属性。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-140">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="1fcc2-141">*SingleItemRecoveryEnabled*  和  *RetainDeletedItemsFor* 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-141">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="1fcc2-142">如有必要，您将禁用单个恢复并在步骤3中增加已删除项目的保留期。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-142">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span>

- <span data-ttu-id="1fcc2-143">*LitigationHoldEnabled*  和  *InPlaceHolds* 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-143">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="1fcc2-144">您需要确定邮箱上放置的所有保留，以便可以在步骤3中临时删除它们。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-144">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="1fcc2-145">请参阅 [详细信息](#more-information) 部分，了解有关如何识别邮箱上可能放置的类型保留的提示。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-145">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span>

<span data-ttu-id="1fcc2-146">此外，您还需要获取邮箱客户端访问设置，以便您可以暂时禁用它们，以便所有者 (或其他用户) 在此过程中无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-146">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="1fcc2-147">最后，您可以获取 "可恢复的项目" 文件夹中的当前大小和项目数。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-147">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-148">在第5步中删除 "可恢复的项目" 文件夹中的项目后，您将使用此信息验证项目是否已删除。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-148">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="1fcc2-149">[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-149">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="1fcc2-150">请务必对已在 Exchange Online 中为其分配了适当管理角色的管理员帐户使用用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-150">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span>

2. <span data-ttu-id="1fcc2-151">运行以下命令以获取有关单个项目恢复和已删除项目保留期限的信息。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-151">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="1fcc2-152">如果启用了单个项目恢复，则必须在第2步中禁用它。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-152">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="1fcc2-153">如果已删除项目的保留期未设置为30天 (Exchange Online) 中的最大值，则可以在第2步中增加它。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-153">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span>

3. <span data-ttu-id="1fcc2-154">运行以下命令以获取邮箱的邮箱访问设置。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-154">Run the following command to get the mailbox access settings for the mailbox.</span></span>

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="1fcc2-155">您将在步骤2中禁用所有这些访问方法。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-155">You'll disable all of these access methods in Step 2.</span></span>

4. <span data-ttu-id="1fcc2-156">运行以下命令以获取有关应用于邮箱的保留策略和保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-156">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

   > [!TIP]
    > <span data-ttu-id="1fcc2-157">如果  *InPlaceHolds*  属性中的值过多，并且不是全部显示，则可以运行  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 命令以在单独的行中显示每个值。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-157">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span>
  
5. <span data-ttu-id="1fcc2-158">运行以下命令以获取有关组织范围内的所有保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-158">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   <span data-ttu-id="1fcc2-159">如果您的组织具有任何组织范围的保留策略，则必须在步骤3中将邮箱排除在这些策略之外。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-159">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="1fcc2-160">如果  *InPlaceHolds*  属性中的值过多，并且不是全部显示，则可以运行  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 命令以在单独的行中显示每个值。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="1fcc2-161">运行以下命令，获取用户主邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-161">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="1fcc2-162">如果已启用用户的存档邮箱，请运行以下命令，以获取存档邮箱中 "可恢复的项目" 文件夹中的文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-162">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="1fcc2-163">删除步骤5中的项目时，可以选择删除或不删除用户的主存档邮箱中的 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-163">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="1fcc2-164">如果为邮箱启用了自动扩展存档，则不会删除辅助存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-164">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="1fcc2-165">步骤2：准备邮箱</span><span class="sxs-lookup"><span data-stu-id="1fcc2-165">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="1fcc2-166">收集并保存有关邮箱的信息后，下一步是通过执行以下任务来准备邮箱：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-166">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span>
  
- <span data-ttu-id="1fcc2-167">**禁用对邮箱的客户端访问** ，以便邮箱所有者无法访问其邮箱，并在此过程中对邮箱数据进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-167">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span>

- <span data-ttu-id="1fcc2-168">将 **已删除项目的保留期增加** 到30天 (Exchange Online) 中的最大值，以便在步骤5中删除之前，不会从 "可恢复的项目" 文件夹中清除项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-168">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span>

- <span data-ttu-id="1fcc2-169">**禁用单个项目恢复** ，以便在已删除项目的保留期) 从步骤5中的 "可恢复的项目" 文件夹中删除后，不会将项目保留 (的持续时间。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-169">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span>

- <span data-ttu-id="1fcc2-170">**禁用托管文件夹助理** ，使其不处理邮箱，并保留您在步骤5中删除的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-170">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span>

<span data-ttu-id="1fcc2-171">在 Exchange Online PowerShell 中执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-171">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="1fcc2-172">运行以下命令以禁用对邮箱的所有客户端访问。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-172">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="1fcc2-173">命令语法假定已在邮箱上启用所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-173">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="1fcc2-174">最长可能需要60分钟才能禁用邮箱的所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-174">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="1fcc2-175">请注意，禁用这些访问方法不会断开他们当前登录的邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-175">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="1fcc2-176">如果未登录到所有者，则在禁用这些访问方法后，他们将无法访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-176">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span>
  
2. <span data-ttu-id="1fcc2-177">运行以下命令，将已删除项目的保留期增加到最大30天。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-177">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="1fcc2-178">这假定当前设置少于30天。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-178">This assumes that the current setting is less than 30 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="1fcc2-179">运行以下命令以禁用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-179">Run the following command to disable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="1fcc2-180">可能需要长达60分钟才能禁用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-180">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="1fcc2-181">在此期间之前，请勿删除 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-181">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="1fcc2-182">运行以下命令以阻止托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-182">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="1fcc2-183">如前所述，只有当具有保留锁定的保留策略未应用于邮箱时，才可以禁用托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-183">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="1fcc2-184">步骤3：从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-184">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="1fcc2-185">从 "可恢复的项目" 文件夹中删除项目之前的最后一步是删除在邮箱上设置的步骤 1) 中标识的所有保留 (。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-185">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="1fcc2-186">必须删除所有保留，以便在从 "可恢复的项目" 文件夹中删除项目后，不会保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-186">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-187">以下各节包含有关删除邮箱的不同类型的保留的信息。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-187">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="1fcc2-188">请参阅 [详细信息](#more-information) 部分，了解有关如何识别邮箱上可能放置的类型保留的提示。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-188">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="1fcc2-189">有关详细信息，请参阅 [如何识别 Exchange Online 邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-189">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1fcc2-190">如前所述，在从邮箱中删除保留之前，请与您的记录管理或法律部门核实。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-190">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
### <a name="litigation-hold"></a><span data-ttu-id="1fcc2-191">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-191">Litigation Hold</span></span>
  
<span data-ttu-id="1fcc2-192">在 Exchange Online PowerShell 中运行以下命令，以从邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-192">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> <span data-ttu-id="1fcc2-193">类似于禁用客户端访问方法和单个项目恢复，可能需要长达60分钟的时间才能删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-193">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="1fcc2-194">在此时间段过后，请勿从 "可恢复的项目" 文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-194">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
### <a name="in-place-hold"></a><span data-ttu-id="1fcc2-195">就地保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-195">In-Place Hold</span></span>
  
<span data-ttu-id="1fcc2-196">在 Exchange Online PowerShell 中运行以下命令，以标识邮箱中放置的 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-196">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="1fcc2-197">使用您在步骤1中标识的 In-Place 保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-197">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="1fcc2-198">在确定 In-Place 保留之后，可以使用 Exchange 管理中心 (EAC) 或 Exchange Online PowerShell 将邮箱从保留中删除。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-198">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="1fcc2-199">有关详细信息，请参阅 [创建或删除 In-Place 保留](https://go.microsoft.com/fwlink/?linkid=852668)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-199">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="1fcc2-200">应用于特定邮箱的保留策略</span><span class="sxs-lookup"><span data-stu-id="1fcc2-200">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="1fcc2-201">在 [Security & 合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) 中运行以下命令，以确定应用于邮箱的保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-201">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="1fcc2-202">此命令还将返回应用于邮箱的任何团队对话保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-202">This command will also return any Teams conversation retention policies applied to a mailbox.</span></span> <span data-ttu-id="1fcc2-203">`mbx` `skp` 对于您在步骤1中标识的保留策略，使用 GUID (不包括或前缀) 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-203">Use the GUID (not including the `mbx` or `skp` prefix) for the retention policy that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="1fcc2-204">在确定保留策略后，请转到安全 & 合规性中心中的 " **信息管理** "  >  **保留** 页，编辑在上一步中标识的保留策略，然后从保留策略中包含的收件人列表中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-204">After you identify the retention policy, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span>
  
### <a name="organization-wide-retention-policies"></a><span data-ttu-id="1fcc2-205">组织范围内的保留策略</span><span class="sxs-lookup"><span data-stu-id="1fcc2-205">Organization-wide retention policies</span></span>
  
<span data-ttu-id="1fcc2-206">组织范围内的 Exchange 范围和团队范围的保留策略将应用于组织中的每个邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-206">Organization-wide, Exchange-wide, and Teams-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="1fcc2-207">它们在组织级别应用 (不是邮箱级别) 并在您在步骤1中运行 **set-organizationconfig** cmdlet 时返回。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-207">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="1fcc2-208">在 [Security & 合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) 中运行以下命令，以确定组织范围内的保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-208">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="1fcc2-209">使用 GUID (不包括  `mbx` 您在步骤1中确定的组织范围的保留策略的前缀) 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-209">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="1fcc2-210">在确定组织范围内的保留策略后，请转到安全 & 合规中心中的 " **信息管理** "  >  **保留** 页，编辑在上一步中标识的每个组织范围的保留策略，并将邮箱添加到排除的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-210">After you identify the organization-wide retention policies, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="1fcc2-211">执行此操作会将用户的邮箱从保留策略中删除。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-211">Doing this will remove the user's mailbox from the retention policy.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="1fcc2-212">保留标签</span><span class="sxs-lookup"><span data-stu-id="1fcc2-212">Retention labels</span></span>

<span data-ttu-id="1fcc2-213">每当用户应用配置为保留内容或保留内容，然后将内容删除到其邮箱中的任何文件夹或项目的标签时， *ComplianceTagHoldApplied* 邮箱属性将设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-213">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="1fcc2-214">发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留状态或分配给保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-214">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="1fcc2-215">若要查看 *ComplianceTagHoldApplied* 属性的值，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-215">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="1fcc2-216">确定邮箱处于保留状态，因为保留标签应用于文件夹或项目，您可以使用 "安全和合规中心" 中的 "内容搜索" 工具来搜索带标签的项目，方法是使用 New-compliancetag 搜索条件。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-216">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="1fcc2-217">有关详细信息，请参阅关键字查询中的 "搜索条件" 部分 [和内容搜索的搜索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-217">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="1fcc2-218">有关标签的详细信息，请参阅 [了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-218">For more information about labels, see [Learn about retention policies and retention labels](retention.md).</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="1fcc2-219">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-219">eDiscovery holds</span></span>
  
<span data-ttu-id="1fcc2-220">在 [Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 中运行以下命令，以确定与应用于邮箱的电子数据展示案例 (的电子数据展示 *保留* ) 相关的保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-220">Run the following commands in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds* ) that's applied to the mailbox.</span></span> <span data-ttu-id="1fcc2-221">使用 GUID (不包括  `UniH` 您在步骤1中确定的电子数据展示保留的前缀) 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-221">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="1fcc2-222">第二个命令显示与保留相关联的电子数据展示事例的名称;第三个命令显示保留的名称。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-222">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span>
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="1fcc2-223">确定电子数据展示事例的名称和保留后，请转到合规中心中的 **电子数据** 展示 \> **电子数据** 展示页面，打开事例，并将邮箱从保留中删除。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-223">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="1fcc2-224">有关识别电子数据展示保留的详细信息，请参阅 [如何识别 Exchange Online 邮箱上的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)一节中的 "电子数据展示保留" 一节。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-224">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="1fcc2-225">步骤4：从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-225">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="1fcc2-226">从邮箱中删除了任何类型的保留后， *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 邮箱属性的值将设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-226">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="1fcc2-227">在下次托管文件夹助理处理邮箱并检测已删除保留时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-227">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="1fcc2-228">这称为 *延迟保留* ，意味着实际删除保留的延迟时间为30天，以防止永久删除邮箱中的数据。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-228">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="1fcc2-229"> (延迟保留的目的是为管理员提供搜索或恢复在删除保留后将清除的邮箱项目的机会。 ) 在邮箱上放置延迟保留时，邮箱仍被视为无限持续时间的保留状态，就像邮箱处于诉讼保留状态一样。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-229">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="1fcc2-230">30天后，延迟保留过期，Microsoft 365 将自动尝试删除延迟保留 (通过将 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性设置为 **False** ) 以便删除保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-230">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False** ) so that the hold is removed.</span></span> <span data-ttu-id="1fcc2-231">有关延迟保留的详细信息，请参阅 [如何识别 Exchange Online 邮箱上的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)一节中的 "管理延迟挂起的邮箱" 一节。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-231">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="1fcc2-232">在您可以删除步骤5中的项目之前，必须从邮箱中删除延迟保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-232">Before you can delete items in Step 5, you have to remove a delay hold from the mailbox.</span></span> <span data-ttu-id="1fcc2-233">首先，通过在 Exchange Online PowerShell 中运行以下命令来确定是否对邮箱应用延迟保留：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-233">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

<span data-ttu-id="1fcc2-234">如果将 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性的值设置为 **False** ，则不会在邮箱上放置延迟保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-234">If the value of either the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **False** , a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="1fcc2-235">您可以转到步骤5并删除 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-235">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="1fcc2-236">如果 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性的值设置为 **True** ，则运行以下命令之一以删除延迟保留：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-236">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True** , run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="1fcc2-237">或</span><span class="sxs-lookup"><span data-stu-id="1fcc2-237">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="1fcc2-238">您必须在 Exchange Online 中向您分配 "合法保留" 角色，才能使用 *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 参数。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-238">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="1fcc2-239">步骤5：删除 "可恢复的项目" 文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="1fcc2-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="1fcc2-240">现在，您已准备好在 "可恢复的项目" 文件夹中实际删除项目，方法是使用 Security & 合规性中心 PowerShell 中的 [new-compliancesearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) 和 [new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-240">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) and [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) cmdlets in Security & Compliance Center PowerShell.</span></span>

<span data-ttu-id="1fcc2-241">若要搜索位于 "可恢复的项目" 文件夹中的项目，我们建议您执行 *目标集合* 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-241">To search for items that are located in the Recoverable Items folder, we recommend that you perform a *targeted collection*.</span></span> <span data-ttu-id="1fcc2-242">这意味着您只将搜索范围缩小到 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-242">This means you narrow the scope of your search only to items located in the Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-243">若要执行此操作，可以在 " [使用内容搜索目标集合](use-content-search-for-targeted-collections.md) " 文章中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-243">You can do this by running the script in the [Use Content Search for targeted collections](use-content-search-for-targeted-collections.md) article.</span></span> <span data-ttu-id="1fcc2-244">此脚本返回 "目标可恢复的项目" 文件夹中所有子文件夹的文件夹 ID 属性的值。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-244">This script returns the value of the folder ID property for all the subfolders in the target Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-245">然后，在搜索查询中使用文件夹 ID 返回位于该文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-245">Then you use the folder ID in a search query to return items located in that folder.</span></span>

<span data-ttu-id="1fcc2-246">以下是搜索和删除用户的 "可恢复的项目" 文件夹中的项目的过程概述：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-246">Here's an overview of the process to search for and delete items in a user's Recoverable Items folder:</span></span>

1. <span data-ttu-id="1fcc2-247">运行目标集合脚本，该脚本返回目标用户邮箱中的所有文件夹的文件夹 Id。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-247">Run the targeted collection script that returns the folder IDs for all folders in the target user's mailbox.</span></span> <span data-ttu-id="1fcc2-248">脚本在同一个 PowerShell 会话中连接到 Exchange Online PowerShell 和 Security & 合规性 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-248">The script connects to Exchange Online PowerShell and Security & Compliance PowerShell in the same PowerShell session.</span></span> <span data-ttu-id="1fcc2-249">有关详细信息，请参阅 [运行脚本以获取邮箱的文件夹列表](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-249">For more information, see [Run the script to get a list of folders for a mailbox](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site).</span></span>

2. <span data-ttu-id="1fcc2-250">复制 "可恢复的项目" 文件夹中所有子文件夹的文件夹 Id。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-250">Copy the folder IDs for all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-251">或者，可以将脚本的输出重定向到文本文件。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-251">Alternatively, you can redirect the output of the script to a text file.</span></span>

   <span data-ttu-id="1fcc2-252">以下是您可以从中搜索和删除项目的 "可恢复的项目" 文件夹中的子文件夹的列表和说明：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-252">Here's a list and description of the subfolders in the Recoverable Items folder that you can search and delete items from:</span></span>

   - <span data-ttu-id="1fcc2-253">**删除** ：包含已删除项目保留期尚未过期的软删除项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-253">**Deletions** : Contains soft-deleted items whose deleted item retention period has not expired.</span></span> <span data-ttu-id="1fcc2-254">用户可以使用 Outlook 中的 "恢复已删除项目" 工具，从该子文件夹恢复软删除的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-254">Users can recover soft-deleted items from this subfolder using the Recover Deleted Items tool in Outlook.</span></span>

   - <span data-ttu-id="1fcc2-255">**清除** ：包含已删除项目保留期已过期的硬删除项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-255">**Purges** : Contains hard-deleted items whose deleted item retention period has expired.</span></span> <span data-ttu-id="1fcc2-256">用户也可以通过清除其 "可恢复的项目" 文件夹中的项目来硬删除项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-256">Users can also hard-delete items by purging items from their Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-257">如果邮箱处于保留状态，则保留硬删除的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-257">If the mailbox is on hold, hard-deleted items are preserved.</span></span> <span data-ttu-id="1fcc2-258">此子文件夹对最终用户不可见。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-258">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="1fcc2-259">**DiscoveryHolds** ：包含已被电子数据展示保留或保留策略保留的硬删除项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-259">**DiscoveryHolds** : Contains hard-deleted items that have been preserved by an eDiscovery hold or a retention policy.</span></span> <span data-ttu-id="1fcc2-260">此子文件夹对最终用户不可见。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-260">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="1fcc2-261">**SubstrateHolds** ：包含来自团队和其他基于云的应用程序的硬删除项目，这些应用已被保留策略或其他类型的保留保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-261">**SubstrateHolds** : Contains hard-deleted items from Teams and other cloud-based apps that have been preserved by a retention policy or other type of hold.</span></span> <span data-ttu-id="1fcc2-262">此子文件夹对最终用户不可见。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-262">This subfolder isn't visible to end users.</span></span>

3. <span data-ttu-id="1fcc2-263">在安全 & 合规中心 PowerShell) 中使用 **new-compliancesearch** cmdlet (，或使用合规性中心中的内容搜索工具创建从目标用户的 "可恢复的项目" 文件夹中返回项目的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-263">Use the **New-ComplianceSearch** cmdlet (in Security & Compliance Center PowerShell) or use the Content search tool in the compliance center to create a content search that returns items from the target user's Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-264">为此，您可以在搜索查询中包括要搜索的所有子文件夹的 FolderId。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-264">You can do this by including the FolderId in the search query for all subfolders that you want to search.</span></span> <span data-ttu-id="1fcc2-265">例如，以下查询将返回 "清除" 和 "eDiscoveryHolds" 子文件夹中的所有邮件：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-265">For example, the following query returns all messages in the Purges and eDiscoveryHolds subfolders:</span></span>

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   <span data-ttu-id="1fcc2-266">有关运行使用文件夹 ID 属性的内容搜索的详细信息和示例，请参阅 [使用文件夹 id 或执行目标集合](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-266">For more information and examples about running content searches that use the folder ID property, see [Use a folder ID or to perform a targeted collection](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).</span></span>

   > [!NOTE]
   > <span data-ttu-id="1fcc2-267">如果使用 **new-compliancesearch** cmdlet 搜索 "可恢复的项目" 文件夹，请务必使用 **new-compliancesearch** cmdlet 运行搜索。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-267">If you use the **New-ComplianceSearch** cmdlet to search the Recoverable Items folder, be sure to use **Start-ComplianceSearch** cmdlet to run the search.</span></span>

4. <span data-ttu-id="1fcc2-268">在创建内容搜索并验证它将返回您要删除的项时，请使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` Security & 合规性中心 PowerShell) 中的命令 (，以永久删除在上一步中创建的内容搜索返回的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-268">After you've created a content search and validated that it returns the items that you wan to delete, use the `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command (in Security & Compliance Center PowerShell) to permanently delete the items returned by the content search that you created in the previous step.</span></span> <span data-ttu-id="1fcc2-269">例如，您可以运行类似于以下命令的命令：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-269">For example, you can run a command similar to the following command:</span></span>

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. <span data-ttu-id="1fcc2-270">运行上一个命令时，每个邮箱最多可以删除10个项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-270">A maximum of 10 items per mailbox are deleted when you run the previous command.</span></span> <span data-ttu-id="1fcc2-271">这意味着，您可能需要多次运行 `New-ComplianceSearchAction -Purge` 命令以删除要在 "可恢复的项目" 文件夹中删除的所有项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-271">That means you may have to run the `New-ComplianceSearchAction -Purge` command multiple times to delete all the items that you want to delete in the Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-272">若要删除其他项目，首先必须删除以前的合规性搜索清除操作。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-272">To delete additional items, you first have to remove the previous compliance search purge action.</span></span> <span data-ttu-id="1fcc2-273">可以通过运行 cmdlet 来执行此操作 `Remove-ComplianceSearchAction` 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-273">You do this by running the `Remove-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="1fcc2-274">例如，若要删除在上一步中运行的清除操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-274">For example, to delete the purge action that was run in the previous step, run the following command:</span></span>

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   <span data-ttu-id="1fcc2-275">执行此操作后，您可以创建新的合规性搜索清除操作以删除更多项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-275">After you do this, you can create a new compliance search purge action to delete more items.</span></span> <span data-ttu-id="1fcc2-276">在创建新的清除操作之前，必须删除每个清除操作。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-276">You'll have to delete each purge action before creating a new one.</span></span>

   <span data-ttu-id="1fcc2-277">若要获取合规性搜索操作的列表，可以运行 `Get-ComplianceSearchAction` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-277">To get a list of the compliance search actions, you can run the `Get-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="1fcc2-278">清除操作通过 `_Purge` 追加到搜索名称来标识。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-278">Purge actions are identified by `_Purge` appended to the search name.</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="1fcc2-279">验证项目是否已被删除</span><span class="sxs-lookup"><span data-stu-id="1fcc2-279">Verify that items were deleted</span></span>

<span data-ttu-id="1fcc2-280">若要验证是否已成功删除邮箱的 "可恢复的项目" 文件夹中的项目，请使用 Exchange Online PowerShell 中的 **get-mailboxfolderstatistics** cmdlet 检查 "可恢复的项目" 文件夹中的邮件大小和数量。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-280">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="1fcc2-281">您可以将这些统计信息与您在步骤1中收集的统计信息进行比较。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-281">You can compare these statistics with the ones you collected in Step 1.</span></span>
  
<span data-ttu-id="1fcc2-282">在中运行以下命令，以获取用户主邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-282">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="1fcc2-283">运行以下命令以获取用户存档邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-283">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span>

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="1fcc2-284">步骤6：将邮箱还原到其以前的状态</span><span class="sxs-lookup"><span data-stu-id="1fcc2-284">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="1fcc2-285">最后一步是将邮箱还原回其以前的配置。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-285">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="1fcc2-286">这意味着重置您在步骤2中更改的属性，并重新应用您在步骤3中删除的保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-286">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="1fcc2-287">这包括：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-287">This includes:</span></span>
  
- <span data-ttu-id="1fcc2-288">将已删除项目的保留期更改回其以前的值。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-288">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="1fcc2-289">或者，您可以仅将此设置保留为30天，即 Exchange Online 中的最大值。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-289">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>

- <span data-ttu-id="1fcc2-290">重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-290">Re-enabling single Item recovery.</span></span>

- <span data-ttu-id="1fcc2-291">重新启用客户端访问方法，以便所有者可以访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-291">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>

- <span data-ttu-id="1fcc2-292">重新应用已删除的保留和保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-292">Reapplying the holds and retention policies that you removed.</span></span>

- <span data-ttu-id="1fcc2-293">重新启用托管文件夹助理以处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-293">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fcc2-294">我们建议您在重新应用保留策略 (并在重新启用托管文件夹助理以处理邮箱之前，等待24小时后再对其进行) 验证。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-294">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span>
  
<span data-ttu-id="1fcc2-295">按照指定的顺序) 在 Exchange Online PowerShell 中，执行以下步骤 (。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-295">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="1fcc2-296">运行以下命令，将已删除项目的保留期更改回其原始值。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-296">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="1fcc2-297">这假定上一个设置的时间不到30天;例如，14天。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-297">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="1fcc2-298">运行以下命令以重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-298">Run the following command to re-enable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="1fcc2-299">运行以下命令，将所有客户端访问方法重新启用到邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-299">Run the following command to re-enable all client access methods to the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="1fcc2-300">重新应用您在步骤3中删除的保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-300">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="1fcc2-301">根据保留的类型，使用以下过程之一。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-301">Depending on the type of hold, use one of the following procedures.</span></span>

    <span data-ttu-id="1fcc2-302">**诉讼保留**</span><span class="sxs-lookup"><span data-stu-id="1fcc2-302">**Litigation Hold**</span></span>

    <span data-ttu-id="1fcc2-303">运行以下命令以重新启用邮箱的诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-303">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="1fcc2-304">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="1fcc2-304">**In-Place Hold**</span></span>

    <span data-ttu-id="1fcc2-305">使用 EAC (或 Exchange Online PowerShell) 将邮箱重新添加到 In-Place 保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-305">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span>

    <span data-ttu-id="1fcc2-306">**应用于特定邮箱的保留策略**</span><span class="sxs-lookup"><span data-stu-id="1fcc2-306">**Retention policies applied to specific mailboxes**</span></span>

    <span data-ttu-id="1fcc2-307">使用安全 & 合规性中心将邮箱重新添加到保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-307">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="1fcc2-308">转到 "安全性 & 合规性中心" 中的 " **信息管理** "  >  **保留** 页，编辑保留策略，并将邮箱重新添加到应用保留策略的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-308">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span>

    <span data-ttu-id="1fcc2-309">**组织范围内的保留策略**</span><span class="sxs-lookup"><span data-stu-id="1fcc2-309">**Organization-wide Retention policies**</span></span>

    <span data-ttu-id="1fcc2-310">如果通过从策略中排除组织范围或 Exchange 范围内的保留策略，则使用安全 & 合规性中心将邮箱从排除的用户列表中删除。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-310">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="1fcc2-311">转到 "安全性 & 合规性中心" 中的 " **信息管理** "  >  **保留** 页，编辑组织范围的保留策略，然后从排除的收件人列表中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-311">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="1fcc2-312">执行此操作将把保留策略重新应用到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-312">Doing this will reapply the retention policy to the user's mailbox.</span></span>

    <span data-ttu-id="1fcc2-313">**电子数据展示事例保留**</span><span class="sxs-lookup"><span data-stu-id="1fcc2-313">**eDiscovery case holds**</span></span>

    <span data-ttu-id="1fcc2-314">使用安全 & 合规性中心将邮箱重新添加到与电子数据展示事例相关联的保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-314">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="1fcc2-315">转到 " **电子数据展示**  >  **电子数据** 展示" 页，打开事例，并将邮箱重新添加到保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-315">Go to the **eDiscovery** > **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 

5. <span data-ttu-id="1fcc2-316">运行以下命令，以允许托管文件夹助理再次处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-316">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="1fcc2-317">如前所述，我们建议您在重新应用保留策略 (并在重新启用托管文件夹助理之前验证是否已将其保留) ，以等待24小时。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-317">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span>

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="1fcc2-318">若要验证是否已将邮箱还原回其以前的配置，可以运行以下命令，然后将设置与您在步骤1中收集的设置进行比较。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-318">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="1fcc2-319">更多信息</span><span class="sxs-lookup"><span data-stu-id="1fcc2-319">More information</span></span>

<span data-ttu-id="1fcc2-320">下面的表格介绍了在运行 Set-organizationconfig **cmdlet 或** **Get-OrganizationConfig** cmdlet 时，如何根据 *InPlaceHolds* 属性中的值标识不同类型的保留。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-320">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="1fcc2-321">有关更多详细信息，请参阅 [如何识别 Exchange Online 邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-321">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="1fcc2-322">如前所述，您必须删除邮箱中的所有保留策略，然后才能成功删除 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-322">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span>
  
| <span data-ttu-id="1fcc2-323">保留类型</span><span class="sxs-lookup"><span data-stu-id="1fcc2-323">Hold type</span></span> | <span data-ttu-id="1fcc2-324">示例值</span><span class="sxs-lookup"><span data-stu-id="1fcc2-324">Example value</span></span> | <span data-ttu-id="1fcc2-325">如何识别保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-325">How to identify the hold</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="1fcc2-326">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-326">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="1fcc2-327">*LitigationHoldEnabled* 属性设置为 `True` 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-327">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="1fcc2-328">就地保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-328">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="1fcc2-329">*InPlaceHolds* 属性包含邮箱中放置的 In-Place 保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-329">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="1fcc2-330">你可以告诉这是一个 In-Place 的保留，因为 GUID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-330">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="1fcc2-331">您可以使用  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Exchange Online PowerShell 中的命令来获取有关邮箱上的 In-Place 保留的信息。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-331">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="1fcc2-332">应用于特定邮箱的安全性 & 合规性中心内的保留策略</span><span class="sxs-lookup"><span data-stu-id="1fcc2-332">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="1fcc2-333">或</span><span class="sxs-lookup"><span data-stu-id="1fcc2-333">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="1fcc2-334">当您运行 **邮箱获取** cmdlet 时，  *InPlaceHolds*  属性还包含应用于邮箱的保留策略的 guid。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-334">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="1fcc2-335">您可以确定保留策略，因为 GUID 以前缀开头  `mbx` 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-335">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="1fcc2-336">如果保留策略的 GUID 以前缀开头，则  `skp` 表示该保留策略应用于 Skype For business 会话。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-336">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="1fcc2-337">若要标识应用于邮箱的保留策略，请在 Security & 合规性中心 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-337">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="1fcc2-338">`mbx`运行此命令时，请务必删除或 `skp` 前缀。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-338">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="1fcc2-339">安全 & 合规中心中的组织范围内的保留策略</span><span class="sxs-lookup"><span data-stu-id="1fcc2-339">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="1fcc2-340">无值</span><span class="sxs-lookup"><span data-stu-id="1fcc2-340">No value</span></span>  <br/> <span data-ttu-id="1fcc2-341">或</span><span class="sxs-lookup"><span data-stu-id="1fcc2-341">or</span></span>  <br/>  <span data-ttu-id="1fcc2-342">`-mbxe9b52bf7ab3b46a286308ecb29624696` (指示邮箱已从组织范围的策略中排除) </span><span class="sxs-lookup"><span data-stu-id="1fcc2-342">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="1fcc2-343">即使在运行 " **获取邮箱** " cmdlet 时， *InPlaceHolds* 属性为空，仍可能会有一个或多个应用于邮箱的组织范围内保留策略。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-343">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="1fcc2-344">若要验证这一点，可以  `Get-OrganizationConfig | FL InPlaceHolds` 在 Exchange Online PowerShell 中运行命令，以获取组织范围的保留策略的 guid 列表。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-344">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="1fcc2-345">应用于 Exchange 邮箱的组织范围的保留策略的 GUID 以前缀开头  `mbx` ; 例如，  `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-345">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="1fcc2-346">若要标识应用于邮箱的组织范围的保留策略，请在 Security & 合规性中心 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-346">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="1fcc2-347">如果从组织范围的保留策略中排除了某个邮箱，则当您运行 " **获取邮箱** " cmdlet 时，该保留策略的 GUID 将显示在用户邮箱的 *InPlaceHolds* 属性中。它是由前缀标识的 `-mbx` ; 例如，`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="1fcc2-347">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="1fcc2-348">安全 & 合规中心中的电子数据展示案例保留</span><span class="sxs-lookup"><span data-stu-id="1fcc2-348">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="1fcc2-349">*InPlaceHolds* 属性还包含与可能位于邮箱上的安全性 & 合规性中心中的电子数据展示事例相关的任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-349">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="1fcc2-350">你可以告诉这是电子数据展示事例保留，因为 GUID 以  `UniH` 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-350">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="1fcc2-351">您可以使用  `Get-CaseHoldPolicy` Security & 合规性中心 PowerShell 中的 cmdlet 来获取有关邮箱中的保留与邮箱关联的电子数据展示事例的信息。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-351">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="1fcc2-352">例如，您可以运行命令  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 以显示邮箱上的事例保留的名称。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-352">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="1fcc2-353">`UniH`运行此命令时，请务必删除前缀。</span><span class="sxs-lookup"><span data-stu-id="1fcc2-353">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="1fcc2-354">若要标识与邮箱的保留内容相关联的电子数据展示事例，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1fcc2-354">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
