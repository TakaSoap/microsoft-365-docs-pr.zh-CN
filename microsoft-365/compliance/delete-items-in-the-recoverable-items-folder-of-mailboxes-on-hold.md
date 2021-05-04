---
title: 删除云邮箱保留的"可恢复的项目"文件夹中的项目
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
description: 了解管理员如何删除某个邮箱的用户"可恢复的项目"文件夹中Exchange Online，即使该邮箱已置于法定保留状态。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b6a5967784e3d82275acc4800aaabfa0bdf4c2f9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939680"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a><span data-ttu-id="f9fe1-103">删除保留状态云邮箱的“可恢复的项目”文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="f9fe1-103">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>

<span data-ttu-id="f9fe1-104">存在邮箱的"可恢复Exchange Online文件夹，防止意外或恶意删除。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-104">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="f9fe1-105">它还用于存储合规性功能（如保留项和电子数据展示搜索）保留和访问的项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-105">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="f9fe1-106">但是，在某些情况下，组织可能有无意中保留在"可恢复的项目"文件夹中必须删除的数据。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-106">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="f9fe1-107">例如，用户可能会无意中发送或转发一封电子邮件，其中包含可能导致严重业务后果的敏感信息或信息。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-107">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="f9fe1-108">即使邮件被永久删除，它也可能无限期保留，因为邮箱已被置于法定保留状态。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-108">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="f9fe1-109">此方案称为 *数据泄漏，* 因为无意中将数据溢出到Office 365。 </span><span class="sxs-lookup"><span data-stu-id="f9fe1-109">This scenario is known as *data spillage* because data has been unintentionally *spilled* into Office 365.</span></span> <span data-ttu-id="f9fe1-110">在这些情况下，您可以删除 Exchange Online 邮箱的用户"可恢复的项目"文件夹中的项目，即使该邮箱被置于保留状态，但 Office 365 中具有一个不同的保留功能。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-110">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="f9fe1-111">这些类型的保留包括诉讼保留、In-Place保留、电子数据展示保留和在 Office 365 或 Microsoft 365 安全与合规中心创建的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-111">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="f9fe1-112">本文介绍了管理员如何从保留的基于云的邮箱的"可恢复的项目"文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-112">This article explains how admins can delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="f9fe1-113">此过程涉及禁用对邮箱的访问和禁用单个项目恢复、禁用托管文件夹助理处理邮箱、临时删除保留、从"可恢复的项目"文件夹中删除项目，然后将邮箱还原到其以前的配置。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-113">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="f9fe1-114">以下是过程：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-114">Here's the process:</span></span>
  
[<span data-ttu-id="f9fe1-115">步骤 1：收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="f9fe1-115">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="f9fe1-116">步骤 2：准备邮箱</span><span class="sxs-lookup"><span data-stu-id="f9fe1-116">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="f9fe1-117">步骤 3：从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-117">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="f9fe1-118">步骤 4：从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-118">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="f9fe1-119">步骤 5：删除"可恢复的项目"文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="f9fe1-119">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="f9fe1-120">步骤 6：将邮箱还原到以前的状态</span><span class="sxs-lookup"><span data-stu-id="f9fe1-120">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="f9fe1-121">本文中概述的过程将导致数据被永久删除， (从) 中Exchange Online数据。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-121">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="f9fe1-122">这意味着从"可恢复的项目"文件夹中删除的邮件无法恢复，并且不能用于法律发现或其他合规性目的。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-122">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="f9fe1-123">如果要从作为诉讼保留、In-Place 保留、电子数据展示保留或在安全与合规中心创建的保留策略的一部分置于保留的邮箱中删除邮件，请在删除保留之前，与记录管理或法律部门核实。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-123">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="f9fe1-124">您的组织可能拥有一个策略，用于定义邮箱是置于保留状态还是数据泄漏事件优先。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-124">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span>
  
## <a name="before-you-delete-items"></a><span data-ttu-id="f9fe1-125">删除项目之前</span><span class="sxs-lookup"><span data-stu-id="f9fe1-125">Before you delete items</span></span>

- <span data-ttu-id="f9fe1-126">若要创建并运行内容搜索，您必须是电子数据展示管理员角色组的成员，或者分配有“合规性搜索”管理角色。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-126">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="f9fe1-127">若要删除邮件，您必须是组织管理角色组的成员或分配有“搜索并清除”管理角色。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-127">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="f9fe1-128">有关将用户添加到角色组的信息，请参阅[分配安全与合规中心中的电子数据展示权限](./assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-128">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](./assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="f9fe1-129">非活动邮箱不支持本文中描述的过程。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-129">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="f9fe1-130">这是因为在删除非活动邮箱 (无法将保留策略) 或保留策略重新应用至非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-130">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="f9fe1-131">从非活动邮箱删除保留时，该保留将更改为普通软删除邮箱，并且将在托管文件夹助理处理后从组织永久删除。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-131">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="f9fe1-132">对于已分配保留设置，具有使用保留锁定锁定的策略的邮箱，无法执行此过程。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-132">You can't perform this procedure for a mailbox that has been assigned retention settings with a policy that's locked by using Preservation Lock.</span></span> <span data-ttu-id="f9fe1-133">这是因为此锁定可防止您从策略中删除或排除邮箱，以及禁用邮箱上的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-133">That's because this lock prevents you from removing or excluding the mailbox from the policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="f9fe1-134">有关锁定保留策略详细信息，请参阅使用保留锁定来限制对保留策略 [和保留标签策略的更改](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-134">For more information about locking policies for retention,see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

- <span data-ttu-id="f9fe1-135">如果邮箱未处于保留状态 (或未启用单个项目恢复) ，可以从"可恢复的项目"文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-135">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-136">若要详细了解如何操作，请参阅在组织中搜索和 [删除电子邮件](./search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-136">For more information about how to do this, see [Search for and delete email messages in your organization](./search-for-and-delete-messages-in-your-organization.md).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="f9fe1-137">步骤 1：收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="f9fe1-137">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="f9fe1-138">第一步是从将影响此过程的目标邮箱中收集所选属性。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-138">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="f9fe1-139">请务必记下这些设置或将它们保存到文本文件中，因为您将更改其中一些属性，然后在从"可恢复的项目"文件夹中删除项目后，恢复步骤 6 中的原始值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-139">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-140">以下是需要收集的邮箱属性的列表。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-140">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="f9fe1-141">*SingleItemRecoveryEnabled*  和  *RetainDeletedItemsFor*。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-141">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="f9fe1-142">如有必要，您将在步骤 3 中禁用单个恢复并增加已删除项目的保留期。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-142">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span>

- <span data-ttu-id="f9fe1-143">*LitigationHoldEnabled*  和  *InPlaceHolds*。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-143">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="f9fe1-144">您需要标识邮箱上设置的所有保留，以便可以在步骤 3 中临时删除它们。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-144">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="f9fe1-145">有关如何 [标识邮箱](#more-information) 上可能设置的类型保留的提示，请参阅详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-145">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span>

<span data-ttu-id="f9fe1-146">此外，您需要获取邮箱客户端访问设置，以便您可以暂时禁用这些设置，以便所有者 (或其他) 无法访问此邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-146">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="f9fe1-147">最后，你可以获取"可恢复的项目"文件夹中的当前大小和项目数。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-147">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-148">在步骤 5 中删除"可恢复的项目"文件夹中的项目后，您将使用此信息验证项目已删除。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-148">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="f9fe1-149">[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-149">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f9fe1-150">请确保为管理员帐户使用用户名和密码，该帐户在 Exchange Online 中分配了适当的管理角色。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-150">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span>

2. <span data-ttu-id="f9fe1-151">运行以下命令，获取有关单个项目恢复和已删除邮件保留期的信息。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-151">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="f9fe1-152">如果启用单个项目恢复，您必须在步骤 2 中禁用它。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-152">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="f9fe1-153">如果已删除项目的保留期未设置为 (中最大值的 30 Exchange Online) ，可以在步骤 2 中增加该值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-153">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span>

3. <span data-ttu-id="f9fe1-154">运行以下命令获取邮箱的邮箱访问设置。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-154">Run the following command to get the mailbox access settings for the mailbox.</span></span>

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="f9fe1-155">您将在步骤 2 中禁用所有这些访问方法。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-155">You'll disable all of these access methods in Step 2.</span></span>

4. <span data-ttu-id="f9fe1-156">运行以下命令，获取有关应用于邮箱的保留和保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-156">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

   > [!TIP]
    > <span data-ttu-id="f9fe1-157">如果  *InPlaceHolds*  属性中的值太多，并且并非所有值都显示出来，可以运行命令以在单独的行上  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 显示每个值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-157">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span>
  
5. <span data-ttu-id="f9fe1-158">运行以下命令，获取有关任何组织范围内的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-158">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   <span data-ttu-id="f9fe1-159">如果您的组织具有任何组织范围的保留策略，您必须在步骤 3 中将邮箱从这些策略中排除。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-159">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="f9fe1-160">如果  *InPlaceHolds*  属性中的值太多，并且并非所有值都显示出来，可以运行命令以在单独的行上  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 显示每个值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="f9fe1-161">运行以下命令，确定是否对邮箱应用了延迟保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-161">Run the following command to determine if a delay hold is applied to the mailbox.</span></span>

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   <span data-ttu-id="f9fe1-162">如果 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性的值设置为 **True，** 则延迟保留将应用于邮箱，并且必须删除。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-162">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, a delay hold is applied to the mailbox and must be removed.</span></span> <span data-ttu-id="f9fe1-163">有关延迟保留详细信息，请参阅步骤 [4：从邮箱中删除延迟保留](#step-4-remove-the-delay-hold-from-the-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-163">For more information about delay holds, see [Step 4: Remove the delay hold from the mailbox](#step-4-remove-the-delay-hold-from-the-mailbox).</span></span>

   <span data-ttu-id="f9fe1-164">如果任一属性的值都设置为 **False，** 则延迟保留不会应用于邮箱，您可以跳过步骤 4。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-164">If the value of either properties is set to **False**, a delay hold is not applied to the mailbox, and you can skip Step 4.</span></span>

7. <span data-ttu-id="f9fe1-165">运行以下命令，获取用户主邮箱中"可恢复的项目"文件夹中文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-165">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="f9fe1-166">如果用户的存档邮箱已启用，请运行以下命令，获取存档邮箱中"可恢复的项目"文件夹的文件夹和子文件夹中的项目的大小和总数。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-166">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="f9fe1-167">在步骤 5 中删除项目时，可以选择删除或不删除用户主存档邮箱中"可恢复的项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-167">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="f9fe1-168">如果为邮箱启用自动扩展存档，将不会删除辅助存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-168">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="f9fe1-169">步骤 2：准备邮箱</span><span class="sxs-lookup"><span data-stu-id="f9fe1-169">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="f9fe1-170">收集和保存有关邮箱的信息后，下一步是通过执行以下任务来准备邮箱：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-170">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span>
  
- <span data-ttu-id="f9fe1-171">**禁用对邮箱的** 客户端访问，以便邮箱所有者在此过程中无法访问其邮箱并更改邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-171">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span>

- <span data-ttu-id="f9fe1-172">**将已删除邮件** 的保留期增加至 (Exchange Online) 中的最大值，以便项目不会从"可恢复的项目"文件夹中清除，然后才能在步骤 5 中删除它们。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-172">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span>

- <span data-ttu-id="f9fe1-173">禁用 **单个项目** 恢复，以便从步骤 5 中的"可恢复的项目"文件夹中删除 (在已删除项目保留期) 期间不会保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-173">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span>

- <span data-ttu-id="f9fe1-174">**禁用托管文件夹助理** ，以便它不会处理邮箱并保留在步骤 5 中删除的项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-174">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span>

<span data-ttu-id="f9fe1-175">在 PowerShell 中Exchange Online步骤。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-175">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="f9fe1-176">运行以下命令以禁用对邮箱的所有客户端访问。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-176">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="f9fe1-177">命令语法假定邮箱上已启用所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-177">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="f9fe1-178">可能需要 60 分钟才能禁用邮箱的所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-178">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="f9fe1-179">请注意，禁用这些访问方法不会断开邮箱所有者（如果他们当前已登录）断开连接。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-179">Note that disabling these access methods won't disconnect the mailbox owner if they are currently signed in.</span></span> <span data-ttu-id="f9fe1-180">如果所有者未登录，则禁用这些访问方法后，他们无法访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-180">If the owner isn't signed in, they won't be able to access their mailbox after these access methods are disabled.</span></span>
  
2. <span data-ttu-id="f9fe1-181">运行以下命令，将已删除项目的保留期最长增加 30 天。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-181">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="f9fe1-182">这假定当前设置小于 30 天。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-182">This assumes that the current setting is less than 30 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="f9fe1-183">运行以下命令以禁用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-183">Run the following command to disable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="f9fe1-184">禁用单个项目恢复可能需要 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-184">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="f9fe1-185">不要删除"可恢复的项目"文件夹中的项目，直到此期限结束。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-185">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="f9fe1-186">运行以下命令以防止托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-186">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="f9fe1-187">如前所述，只有当具有保留锁定的保留策略未应用于邮箱时，才能禁用托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-187">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="f9fe1-188">步骤 3：从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-188">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="f9fe1-189">从"可恢复的项目"文件夹中删除项目前的最后一步是删除在步骤 1 (对邮箱) 标识的所有保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-189">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="f9fe1-190">必须删除所有保留，以便从"可恢复的项目"文件夹中删除项目后不会保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-190">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-191">以下各节包含有关删除邮箱上不同类型的保留的信息。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-191">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="f9fe1-192">有关如何 [标识邮箱](#more-information) 上可能设置的类型保留的提示，请参阅详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-192">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="f9fe1-193">有关详细信息，请参阅如何标识邮箱[中置于Exchange Online的类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-193">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f9fe1-194">如前所述，在从邮箱中删除保留之前，请与记录管理或法律部门核实。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-194">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
### <a name="litigation-hold"></a><span data-ttu-id="f9fe1-195">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-195">Litigation Hold</span></span>
  
<span data-ttu-id="f9fe1-196">在 PowerShell Exchange Online以下命令以从邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-196">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> <span data-ttu-id="f9fe1-197">与禁用客户端访问方法和单个项目恢复类似，可能需要 60 分钟才能删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-197">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="f9fe1-198">在此期限过后，不要从"可恢复的项目"文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-198">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
### <a name="in-place-hold"></a><span data-ttu-id="f9fe1-199">就地保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-199">In-Place Hold</span></span>
  
<span data-ttu-id="f9fe1-200">在 PowerShell Exchange Online以下命令，In-Place邮箱上设置的邮件保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-200">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="f9fe1-201">使用在步骤 1 中In-Place标识的保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-201">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="f9fe1-202">确定保留In-Place后，可以使用 Exchange 管理中心 (EAC) 或 Exchange Online PowerShell 从保留中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-202">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="f9fe1-203">有关详细信息，请参阅创建[或删除In-Place保留。](/exchange/security-and-compliance/create-or-remove-in-place-holds)</span><span class="sxs-lookup"><span data-stu-id="f9fe1-203">For more information, see [Create or remove an In-Place Hold](/exchange/security-and-compliance/create-or-remove-in-place-holds).</span></span>
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="f9fe1-204">应用于特定邮箱的保留策略</span><span class="sxs-lookup"><span data-stu-id="f9fe1-204">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="f9fe1-205">在安全与合规& [PowerShell 中](/powershell/exchange/exchange-online-powershell) 运行以下命令，以标识应用于邮箱的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-205">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="f9fe1-206">此命令还将返回应用于Teams的任何会话保留策略。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-206">This command will also return any Teams conversation retention policies applied to a mailbox.</span></span> <span data-ttu-id="f9fe1-207">使用 GUID (步骤 1 中) 标识的保留策略的 或 前缀 `mbx` `skp` 。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-207">Use the GUID (not including the `mbx` or `skp` prefix) for the retention policy that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="f9fe1-208">确定保留策略后，请转到安全  >  & 合规中心中的"信息治理""保留"页，编辑在上一步中确定的保留策略，并从保留策略中包含的收件人列表中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-208">After you identify the retention policy, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span>
  
### <a name="organization-wide-retention-policies"></a><span data-ttu-id="f9fe1-209">组织范围内的保留策略</span><span class="sxs-lookup"><span data-stu-id="f9fe1-209">Organization-wide retention policies</span></span>
  
<span data-ttu-id="f9fe1-210">组织范围内、Exchange和Teams保留策略将应用于组织的每一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-210">Organization-wide, Exchange-wide, and Teams-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="f9fe1-211">它们在组织级别应用， (邮箱级别应用) 在步骤 1 中运行 **Get-OrganizationConfig** cmdlet 时返回。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-211">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="f9fe1-212">在安全与合规& [PowerShell 中](/powershell/exchange/exchange-online-powershell) 运行以下命令，以标识组织范围内的保留策略。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-212">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="f9fe1-213">使用 GUID (步骤 1) 确定的组织范围的保留策略的前缀  `mbx` 值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-213">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="f9fe1-214">确定组织范围的保留策略后，请转到安全  >  & 合规中心中的"信息治理""保留"页，编辑在上一步中确定的每个组织范围内的保留策略，将邮箱添加到已排除收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-214">After you identify the organization-wide retention policies, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="f9fe1-215">执行此操作将删除保留策略中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-215">Doing this will remove the user's mailbox from the retention policy.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="f9fe1-216">保留标签</span><span class="sxs-lookup"><span data-stu-id="f9fe1-216">Retention labels</span></span>

<span data-ttu-id="f9fe1-217">每当用户应用配置为保留内容或保留内容的标签，然后删除其邮箱中任何文件夹或项目的内容时 *，ComplianceTagHoldApplied* 邮箱属性都设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-217">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="f9fe1-218">发生这种情况时，邮箱被视为处于保留状态，就像将其置于诉讼保留或分配给保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-218">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="f9fe1-219">若要查看 *ComplianceTagHoldApplied* 属性的值，请运行 PowerShell 中的以下Exchange Online命令：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-219">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="f9fe1-220">确定邮箱因保留标签应用于文件夹或项目而置于保留状态后，可以使用安全与合规中心内的内容搜索工具，使用 ComplianceTag 搜索条件搜索已标记项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-220">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="f9fe1-221">有关详细信息，请参阅内容搜索的关键字查询 [和搜索条件中的"搜索条件"部分](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-221">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="f9fe1-222">有关标签详细信息，请参阅 [了解保留策略和保留标签](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-222">For more information about labels, see [Learn about retention policies and retention labels](retention.md).</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="f9fe1-223">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-223">eDiscovery holds</span></span>
  
<span data-ttu-id="f9fe1-224">在安全&合规中心[PowerShell](/powershell/exchange/connect-to-scc-powershell)中运行以下命令，以标识与应用于邮箱 (电子数据展示) 保留相关联的保留。 </span><span class="sxs-lookup"><span data-stu-id="f9fe1-224">Run the following commands in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds*) that's applied to the mailbox.</span></span> <span data-ttu-id="f9fe1-225">使用 GUID (不包括在步骤 1) 标识的电子数据展示保留的前缀  `UniH` 值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-225">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="f9fe1-226">第二个命令显示与保留关联的电子数据展示案例的名称;第三个命令显示保留的名称。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-226">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span>
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="f9fe1-227">确定电子数据展示案例的名称和保留后，请转到合规性中心中的电子数据展示 \> **电子数据** 展示页面，打开该案例，然后从保留中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-227">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="f9fe1-228">有关标识电子数据展示保留项详细信息，请参阅如何识别邮箱中保留的保留类型中的"电子数据展示保留Exchange Online[部分](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-228">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="f9fe1-229">步骤 4：从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-229">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="f9fe1-230">从邮箱中删除任何类型的保留后 *，DelayHoldApplied* 或 *DelayReleaseHoldApplied* 邮箱属性的值将设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-230">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="f9fe1-231">这发生在托管文件夹助理下次处理邮箱并检测已删除保留时。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-231">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="f9fe1-232">这称为 *延迟保留* ，意味着保留的实际删除延迟 30 天，以防止从邮箱中永久删除数据。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-232">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="f9fe1-233"> (延迟保留的目的是使管理员有机会搜索或恢复将在删除保留后清除的邮箱项目。) 当邮箱上设置延迟保留时，该邮箱仍被视为处于无限期保留状态，就像邮箱处于诉讼保留状态一样。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-233">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="f9fe1-234">30 天后，延迟保留过期，Microsoft 365 将自动尝试删除延迟保留 (，将 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性设置为 **False**) 以便删除该保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-234">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="f9fe1-235">有关延迟保留详细信息，请参阅如何标识邮箱上置于的保留类型中的"管理处于延迟保留状态Exchange Online[部分](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-235">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="f9fe1-236">如果 *DelayHoldApplied* 或 *DelayReleaseHoldApplied* 属性的值设置为 **True，** 请运行以下命令之一来删除延迟保留：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-236">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="f9fe1-237">或</span><span class="sxs-lookup"><span data-stu-id="f9fe1-237">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="f9fe1-238">您必须获得法定保留角色Exchange Online *RemoveDelayHoldApplied* 或 *RemoveDelayReleaseHoldApplied* 参数。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-238">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="f9fe1-239">步骤 5：删除"可恢复的项目"文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="f9fe1-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="f9fe1-240">现在，可以使用安全与合规中心 PowerShell 中的 [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) 和 [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) cmdlet 实际删除"可恢复的项目"文件夹中&项。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-240">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) and [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) cmdlets in Security & Compliance Center PowerShell.</span></span>

<span data-ttu-id="f9fe1-241">若要搜索位于"可恢复的项目"文件夹中的项目，我们建议您执行目标 *集合*。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-241">To search for items that are located in the Recoverable Items folder, we recommend that you perform a *targeted collection*.</span></span> <span data-ttu-id="f9fe1-242">这意味着您仅将搜索范围缩小到"可恢复的项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-242">This means you narrow the scope of your search only to items located in the Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-243">为此，可以运行使用目标集合的内容 [搜索文章中的脚本](use-content-search-for-targeted-collections.md) 。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-243">You can do this by running the script in the [Use Content Search for targeted collections](use-content-search-for-targeted-collections.md) article.</span></span> <span data-ttu-id="f9fe1-244">此脚本返回目标"可恢复的项目"文件夹中所有子文件夹的文件夹 ID 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-244">This script returns the value of the folder ID property for all the subfolders in the target Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-245">然后，在搜索查询中使用该文件夹 ID 返回位于该文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-245">Then you use the folder ID in a search query to return items located in that folder.</span></span>

<span data-ttu-id="f9fe1-246">以下是搜索和删除用户的"可恢复的项目"文件夹中的项目的过程概述：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-246">Here's an overview of the process to search for and delete items in a user's Recoverable Items folder:</span></span>

1. <span data-ttu-id="f9fe1-247">运行目标集合脚本，该脚本返回目标用户邮箱中所有文件夹的文件夹 ID。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-247">Run the targeted collection script that returns the folder IDs for all folders in the target user's mailbox.</span></span> <span data-ttu-id="f9fe1-248">该脚本连接到同Exchange Online PowerShell 会话中&安全与安全与合规 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-248">The script connects to Exchange Online PowerShell and Security & Compliance PowerShell in the same PowerShell session.</span></span> <span data-ttu-id="f9fe1-249">有关详细信息，请参阅 [运行脚本获取邮箱的文件夹列表](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-249">For more information, see [Run the script to get a list of folders for a mailbox](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site).</span></span>

2. <span data-ttu-id="f9fe1-250">复制"可恢复的项目"文件夹中所有子文件夹的文件夹 ID。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-250">Copy the folder IDs for all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-251">或者，可以将脚本的输出重定向到文本文件。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-251">Alternatively, you can redirect the output of the script to a text file.</span></span>

   <span data-ttu-id="f9fe1-252">以下是"可恢复的项目"文件夹中的子文件夹的列表和说明，可以从中搜索和删除项目：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-252">Here's a list and description of the subfolders in the Recoverable Items folder that you can search and delete items from:</span></span>

   - <span data-ttu-id="f9fe1-253">**删除**：包含已删除项目的保留期尚未到期的软删除项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-253">**Deletions**: Contains soft-deleted items whose deleted item retention period has not expired.</span></span> <span data-ttu-id="f9fe1-254">用户可以使用 Outlook 中的"恢复已删除邮件"工具从此子文件夹恢复软删除Outlook。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-254">Users can recover soft-deleted items from this subfolder using the Recover Deleted Items tool in Outlook.</span></span>

   - <span data-ttu-id="f9fe1-255">**清除**：包含已删除项目的保留期已到期的硬删除项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-255">**Purges**: Contains hard-deleted items whose deleted item retention period has expired.</span></span> <span data-ttu-id="f9fe1-256">用户还可通过清除其"可恢复的项目"文件夹中的项目来硬删除项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-256">Users can also hard-delete items by purging items from their Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-257">如果邮箱置于保留状态，则保留硬删除的项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-257">If the mailbox is on hold, hard-deleted items are preserved.</span></span> <span data-ttu-id="f9fe1-258">此子文件夹对最终用户不可见。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-258">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="f9fe1-259">**DiscoveryHolds：** 包含已由电子数据展示保留或保留策略保留的硬删除项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-259">**DiscoveryHolds**: Contains hard-deleted items that have been preserved by an eDiscovery hold or a retention policy.</span></span> <span data-ttu-id="f9fe1-260">此子文件夹对最终用户不可见。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-260">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="f9fe1-261">**SubstrateHolds：** 包含来自Teams保留策略或另一种保留类型已保留的其他基于云的应用的硬删除项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-261">**SubstrateHolds**: Contains hard-deleted items from Teams and other cloud-based apps that have been preserved by a retention policy or other type of hold.</span></span> <span data-ttu-id="f9fe1-262">此子文件夹对最终用户不可见。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-262">This subfolder isn't visible to end users.</span></span>

3. <span data-ttu-id="f9fe1-263">使用安全 & 合规中心 PowerShell) 中的 **New-ComplianceSearch** cmdlet (或使用合规性中心中的内容搜索工具创建从目标用户的"可恢复的项目"文件夹中返回项目的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-263">Use the **New-ComplianceSearch** cmdlet (in Security & Compliance Center PowerShell) or use the Content search tool in the compliance center to create a content search that returns items from the target user's Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-264">为此，可以在要搜索的所有子文件夹的搜索查询中包括 FolderId。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-264">You can do this by including the FolderId in the search query for all subfolders that you want to search.</span></span> <span data-ttu-id="f9fe1-265">例如，以下查询返回"清除"和"eDiscoveryHolds"子文件夹内的所有邮件：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-265">For example, the following query returns all messages in the Purges and eDiscoveryHolds subfolders:</span></span>

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   <span data-ttu-id="f9fe1-266">有关运行使用文件夹 ID 属性的内容搜索的信息和示例，请参阅使用文件夹 [ID 或执行目标集合](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-266">For more information and examples about running content searches that use the folder ID property, see [Use a folder ID or to perform a targeted collection](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).</span></span>

   > [!NOTE]
   > <span data-ttu-id="f9fe1-267">如果使用 **New-ComplianceSearch** cmdlet 搜索"可恢复的项目"文件夹，请务必使用 **Start-ComplianceSearch** cmdlet 运行搜索。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-267">If you use the **New-ComplianceSearch** cmdlet to search the Recoverable Items folder, be sure to use **Start-ComplianceSearch** cmdlet to run the search.</span></span>

4. <span data-ttu-id="f9fe1-268">创建内容搜索并验证它返回要删除的项目后，使用安全 & 合规中心 PowerShell) 中的命令 (永久删除在上一步中创建的内容搜索返回的项目。 `New-ComplianceSearchAction -Purge -PurgeType HardDelete`</span><span class="sxs-lookup"><span data-stu-id="f9fe1-268">After you've created a content search and validated that it returns the items that you wan to delete, use the `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command (in Security & Compliance Center PowerShell) to permanently delete the items returned by the content search that you created in the previous step.</span></span> <span data-ttu-id="f9fe1-269">例如，可以运行类似于以下命令的命令：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-269">For example, you can run a command similar to the following command:</span></span>

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. <span data-ttu-id="f9fe1-270">运行上一个命令时，每个邮箱最多删除 10 个项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-270">A maximum of 10 items per mailbox are deleted when you run the previous command.</span></span> <span data-ttu-id="f9fe1-271">这意味着您可能必须多次运行该命令，以删除要删除的"可恢复的项目"文件夹中 `New-ComplianceSearchAction -Purge` 的所有项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-271">That means you may have to run the `New-ComplianceSearchAction -Purge` command multiple times to delete all the items that you want to delete in the Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-272">若要删除其他项目，首先必须删除以前的合规性搜索清除操作。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-272">To delete additional items, you first have to remove the previous compliance search purge action.</span></span> <span data-ttu-id="f9fe1-273">通过运行 `Remove-ComplianceSearchAction` cmdlet 可完成此操作。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-273">You do this by running the `Remove-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="f9fe1-274">例如，若要删除在上一步中运行的清除操作，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-274">For example, to delete the purge action that was run in the previous step, run the following command:</span></span>

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   <span data-ttu-id="f9fe1-275">完成此操作后，可以创建新的合规性搜索清除操作以删除更多项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-275">After you do this, you can create a new compliance search purge action to delete more items.</span></span> <span data-ttu-id="f9fe1-276">在创建新的清除操作之前，必须删除每个清除操作。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-276">You'll have to delete each purge action before creating a new one.</span></span>

   <span data-ttu-id="f9fe1-277">若要获取合规性搜索操作的列表，可以运行 `Get-ComplianceSearchAction` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-277">To get a list of the compliance search actions, you can run the `Get-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="f9fe1-278">清除操作通过附加到 `_Purge` 搜索名称进行标识。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-278">Purge actions are identified by `_Purge` appended to the search name.</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="f9fe1-279">验证项目已删除</span><span class="sxs-lookup"><span data-stu-id="f9fe1-279">Verify that items were deleted</span></span>

<span data-ttu-id="f9fe1-280">若要验证您是否已成功从邮箱的"可恢复的项目"文件夹中删除项目，请使用 Exchange Online PowerShell 中的 **Get-MailboxFolderStatistics** cmdlet 检查"可恢复的项目"文件夹中的项目大小和数量。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-280">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="f9fe1-281">可以将这些统计信息与在步骤 1 中收集的统计信息进行比较。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-281">You can compare these statistics with the ones you collected in Step 1.</span></span>
  
<span data-ttu-id="f9fe1-282">在 中运行以下命令，获取用户主邮箱中"可恢复的项目"文件夹中文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-282">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="f9fe1-283">运行以下命令，获取用户存档邮箱中"可恢复的项目"文件夹的文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-283">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span>

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="f9fe1-284">步骤 6：将邮箱还原到以前的状态</span><span class="sxs-lookup"><span data-stu-id="f9fe1-284">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="f9fe1-285">最后一步是将邮箱恢复为以前的配置。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-285">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="f9fe1-286">这意味着重置在步骤 2 中更改的属性，并重新应用在步骤 3 中删除的保留项。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-286">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="f9fe1-287">这包括：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-287">This includes:</span></span>
  
- <span data-ttu-id="f9fe1-288">将已删除项目的保留期更改回其以前的值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-288">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="f9fe1-289">或者，你可以仅将此值保留为 30 天，即 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-289">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>

- <span data-ttu-id="f9fe1-290">重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-290">Re-enabling single Item recovery.</span></span>

- <span data-ttu-id="f9fe1-291">重新启用客户端访问方法，以便所有者可以访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-291">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>

- <span data-ttu-id="f9fe1-292">重新应用已删除的保留和保留策略。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-292">Reapplying the holds and retention policies that you removed.</span></span>

- <span data-ttu-id="f9fe1-293">重新启用托管文件夹助理以处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-293">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9fe1-294">建议在重新应用保留策略或保留策略 (并验证其是否已在) 之后等待 24 小时，然后再重新启用托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-294">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span>
  
<span data-ttu-id="f9fe1-295">在 PowerShell (按指定顺序) 执行Exchange Online步骤。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-295">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="f9fe1-296">运行以下命令，将已删除项目的保留期更改回其原始值。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-296">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="f9fe1-297">这假定上一个设置小于 30 天;例如，14 天。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-297">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="f9fe1-298">运行以下命令以重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-298">Run the following command to re-enable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="f9fe1-299">运行以下命令以重新启用邮箱的所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-299">Run the following command to re-enable all client access methods to the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="f9fe1-300">重新应用在步骤 3 中删除的保留项。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-300">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="f9fe1-301">根据保留类型，请使用以下过程之一。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-301">Depending on the type of hold, use one of the following procedures.</span></span>

    <span data-ttu-id="f9fe1-302">**诉讼保留**</span><span class="sxs-lookup"><span data-stu-id="f9fe1-302">**Litigation Hold**</span></span>

    <span data-ttu-id="f9fe1-303">运行以下命令以重新启用邮箱的诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-303">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="f9fe1-304">**就地保留**</span><span class="sxs-lookup"><span data-stu-id="f9fe1-304">**In-Place Hold**</span></span>

    <span data-ttu-id="f9fe1-305">使用 EAC (或 Exchange Online PowerShell) 将邮箱添加回"In-Place保留"。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-305">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span>

    <span data-ttu-id="f9fe1-306">**应用于特定邮箱的保留策略**</span><span class="sxs-lookup"><span data-stu-id="f9fe1-306">**Retention policies applied to specific mailboxes**</span></span>

    <span data-ttu-id="f9fe1-307">使用安全&中心将邮箱添加回保留策略。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-307">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="f9fe1-308">转到安全与合规中心内的信息治理保留&编辑保留策略，将邮箱添加回应用保留策略的收件人  >  列表。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-308">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span>

    <span data-ttu-id="f9fe1-309">**组织范围内的保留策略**</span><span class="sxs-lookup"><span data-stu-id="f9fe1-309">**Organization-wide Retention policies**</span></span>

    <span data-ttu-id="f9fe1-310">如果通过从策略中排除组织范围内的保留策略或 Exchange 范围的保留策略，则使用安全 & 合规中心从已排除用户列表中删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-310">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="f9fe1-311">转到安全与合规中心内的信息治理保留&，编辑组织范围的保留策略，并从排除的收件人列表中  >  删除邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-311">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="f9fe1-312">执行此操作后，保留策略将重新应用至用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-312">Doing this will reapply the retention policy to the user's mailbox.</span></span>

    <span data-ttu-id="f9fe1-313">**电子数据展示案例保留**</span><span class="sxs-lookup"><span data-stu-id="f9fe1-313">**eDiscovery case holds**</span></span>

    <span data-ttu-id="f9fe1-314">使用安全&中心将邮箱添加回与电子数据展示案例关联的保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-314">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="f9fe1-315">转到电子 **数据展示**  >  **电子数据** 展示页面，打开案例，将邮箱添加回保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-315">Go to the **eDiscovery** > **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 

5. <span data-ttu-id="f9fe1-316">运行以下命令以允许托管文件夹助理再次处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-316">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="f9fe1-317">如前所述，建议在重新应用保留策略 (并验证其是否已在) 之后等待 24 小时，然后再重新启用托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-317">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span>

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="f9fe1-318">若要验证邮箱已恢复为以前的配置，可以运行以下命令，然后将设置与在步骤 1 中收集的设置进行比较。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-318">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="f9fe1-319">更多信息</span><span class="sxs-lookup"><span data-stu-id="f9fe1-319">More information</span></span>

<span data-ttu-id="f9fe1-320">下表介绍了在运行 **Get-Mailbox** 或 **Get-OrganizationConfig** cmdlet 时，如何根据 *InPlaceHolds* 属性的值标识不同类型的保留。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-320">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="f9fe1-321">有关更多详细信息，请参阅如何标识邮箱中置于Exchange Online[的类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-321">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="f9fe1-322">如前所述，您必须从邮箱中删除所有保留和保留策略，然后才能成功删除"可恢复的项目"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-322">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span>
  
| <span data-ttu-id="f9fe1-323">保留类型</span><span class="sxs-lookup"><span data-stu-id="f9fe1-323">Hold type</span></span> | <span data-ttu-id="f9fe1-324">示例值</span><span class="sxs-lookup"><span data-stu-id="f9fe1-324">Example value</span></span> | <span data-ttu-id="f9fe1-325">如何识别保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-325">How to identify the hold</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="f9fe1-326">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-326">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="f9fe1-327">*LitigationHoldEnabled* 属性设置为 `True` 。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-327">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="f9fe1-328">就地保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-328">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="f9fe1-329">*InPlaceHolds* 属性包含邮箱In-Place保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-329">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="f9fe1-330">你可以判断这是一个In-Place保留，因为 GUID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-330">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="f9fe1-331">可以在 `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` PowerShell Exchange Online 命令获取有关邮箱In-Place保留的信息。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-331">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="f9fe1-332">安全与合规中心&策略应用于特定邮箱</span><span class="sxs-lookup"><span data-stu-id="f9fe1-332">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="f9fe1-333">或</span><span class="sxs-lookup"><span data-stu-id="f9fe1-333">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="f9fe1-334">运行 **Get-Mailbox** cmdlet 时  *，InPlaceHolds*  属性还包含应用于邮箱的保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-334">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="f9fe1-335">您可以标识保留策略，因为 GUID 以前缀  `mbx` 开头。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-335">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="f9fe1-336">如果保留策略的 GUID 以前缀开头，则表明保留策略 `skp` 应用于Skype for Business对话。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-336">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="f9fe1-337">若要标识应用于邮箱的保留策略，请运行安全与合规中心 PowerShell &命令：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-337">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="f9fe1-338">运行此命令时，  `mbx` 请务必删除 或  `skp` 前缀。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-338">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="f9fe1-339">安全与合规中心内&保留策略</span><span class="sxs-lookup"><span data-stu-id="f9fe1-339">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="f9fe1-340">无值</span><span class="sxs-lookup"><span data-stu-id="f9fe1-340">No value</span></span>  <br/> <span data-ttu-id="f9fe1-341">或</span><span class="sxs-lookup"><span data-stu-id="f9fe1-341">or</span></span>  <br/>  <span data-ttu-id="f9fe1-342">`-mbxe9b52bf7ab3b46a286308ecb29624696` (指示邮箱从组织范围内的策略中) </span><span class="sxs-lookup"><span data-stu-id="f9fe1-342">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="f9fe1-343">即使运行 **Get-Mailbox** cmdlet 时 *InPlaceHolds* 属性为空，也可能有一个或多个组织范围内的保留策略应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-343">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="f9fe1-344">若要验证这一点，可以在 Exchange Online PowerShell 中运行命令，获取组织范围内的保留策略的 `Get-OrganizationConfig | FL InPlaceHolds` GUID 列表。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-344">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="f9fe1-345">应用于邮箱的组织范围的保留策略的 GUID Exchange前缀开头; `mbx` 例如， `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-345">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="f9fe1-346">若要标识应用于邮箱的组织范围的保留策略，请运行安全与合规中心 PowerShell &命令：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-346">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="f9fe1-347">如果从组织范围的保留策略中排除邮箱，则在您运行 **Get-Mailbox** cmdlet 时，保留策略的 GUID 将显示在用户邮箱的 *InPlaceHolds* 属性中;它由 前缀标识 `-mbx` ;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="f9fe1-347">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="f9fe1-348">安全与合规中心中的电子数据&保留</span><span class="sxs-lookup"><span data-stu-id="f9fe1-348">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="f9fe1-349">*InPlaceHolds* 属性还包含与安全与合规中心内电子数据展示案例关联的任何保留的 GUID&可能会置于邮箱上。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-349">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="f9fe1-350">你可以判断这是电子数据展示案例保留，因为 GUID 以前缀  `UniH` 开头。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-350">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="f9fe1-351">您可以使用安全与合规& PowerShell 中的 cmdlet 获取有关邮箱上的保留相关联的电子数据展示  `Get-CaseHoldPolicy` 案例的信息。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-351">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="f9fe1-352">例如，可以运行命令来显示邮箱上案例  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 保留的名称。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-352">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="f9fe1-353">运行此命令时  `UniH` ，请务必删除前缀。</span><span class="sxs-lookup"><span data-stu-id="f9fe1-353">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="f9fe1-354">若要标识与邮箱上的保留相关联的电子数据展示案例，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f9fe1-354">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`