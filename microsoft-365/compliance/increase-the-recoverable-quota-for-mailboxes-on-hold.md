---
title: 为置于保留状态的邮箱增加可恢复项目的配额
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 启用存档邮箱并打开自动扩展存档，以增加 Microsoft 365 中邮箱的 "可恢复的项目" 文件夹的大小。
ms.openlocfilehash: 3c2ac29fe650d03db7e5d4d1282b870eaece447c
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138264"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="2172f-103">为置于保留状态的邮箱增加可恢复项目的配额</span><span class="sxs-lookup"><span data-stu-id="2172f-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="2172f-104">将自动应用于 Exchange Online 中的新邮箱的默认 Exchange 保留策略（名为 "*默认 MRM 策略*"）包含一个名为 "可恢复的项目" 的保留标记。移动到存档的14天。</span><span class="sxs-lookup"><span data-stu-id="2172f-104">The default Exchange retention policy—named *Default MRM Policy*—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="2172f-105">此保留标记将项目从用户主邮箱中的 "可恢复的项目" 文件夹移动到用户的存档邮箱中的 "可恢复的项目" 文件夹中，在该项目的14天保留期到期之后。</span><span class="sxs-lookup"><span data-stu-id="2172f-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="2172f-106">为此，必须启用用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="2172f-107">如果未启用存档邮箱，则不会执行任何操作，这意味着保留邮箱的 "可恢复的项目" 文件夹中的项目在14天保留期过期后不会移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="2172f-108">由于保留邮箱时不会从邮箱中删除任何内容，因此可能会超出 "可恢复的项目" 文件夹的存储配额，尤其是在未启用用户的存档邮箱的情况下。</span><span class="sxs-lookup"><span data-stu-id="2172f-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="2172f-109">为了帮助降低超出此限制的可能性，在 Exchange Online 中的邮箱上放置保留时，"可恢复的项目" 文件夹的存储配额将自动从 30 GB 增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="2172f-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="2172f-110">如果启用存档邮箱，则存档邮箱中的 "可恢复的项目" 文件夹的存储配额也会从 30 GB 增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="2172f-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="2172f-111">如果启用了 Exchange Online 中的自动扩展存档功能，则用户存档中的 "可恢复的项目" 文件夹的存储配额将不受限制。</span><span class="sxs-lookup"><span data-stu-id="2172f-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="2172f-112">下表汇总了 "可恢复的项目" 文件夹的存储配额。</span><span class="sxs-lookup"><span data-stu-id="2172f-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="2172f-113">**"可恢复的项目" 文件夹的位置**</span><span class="sxs-lookup"><span data-stu-id="2172f-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="2172f-114">**不处于保留状态的邮箱**</span><span class="sxs-lookup"><span data-stu-id="2172f-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="2172f-115">**处于保留状态的邮箱**</span><span class="sxs-lookup"><span data-stu-id="2172f-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2172f-116">主邮箱</span><span class="sxs-lookup"><span data-stu-id="2172f-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="2172f-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="2172f-117">30 GB</span></span>  <br/> |<span data-ttu-id="2172f-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="2172f-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="2172f-119">存档邮箱<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2172f-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="2172f-120">无限制</span><span class="sxs-lookup"><span data-stu-id="2172f-120">Unlimited</span></span>  <br/> |<span data-ttu-id="2172f-121">无限制</span><span class="sxs-lookup"><span data-stu-id="2172f-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="2172f-122">**"可恢复的项目" 文件夹的总存储配额**</span><span class="sxs-lookup"><span data-stu-id="2172f-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="2172f-123">无限制</span><span class="sxs-lookup"><span data-stu-id="2172f-123">Unlimited</span></span>  <br/> |<span data-ttu-id="2172f-124">无限制</span><span class="sxs-lookup"><span data-stu-id="2172f-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="2172f-125"><sup>\*</sup>存档邮箱的初始存储配额为 100 GB （适用于具有 Exchange Online （计划2）许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="2172f-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="2172f-126">但是，如果在保留时为邮箱启用自动扩展存档，则存档邮箱和 "可恢复的项目" 文件夹的存储配额将增加到 110 GB。</span><span class="sxs-lookup"><span data-stu-id="2172f-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="2172f-127">必要时将预配其他存档存储空间，从而导致存档存储量不受限制。</span><span class="sxs-lookup"><span data-stu-id="2172f-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="2172f-128">有关自动扩展存档的详细信息，请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="2172f-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="2172f-129">当置于保留状态的邮箱的主邮箱"可恢复的项目"文件夹的存储配额接近其限额时，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2172f-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="2172f-130">**启用存档邮箱并启用自动扩展存档。**</span><span class="sxs-lookup"><span data-stu-id="2172f-130">**Enable the archive mailbox and turn on auto-expanding archiving.**</span></span> <span data-ttu-id="2172f-131">只需启用存档邮箱，然后启用 ExchangeOnline 中的自动扩展存档功能，就可以为“可恢复的项目”文件夹开启无限制存储容量。</span><span class="sxs-lookup"><span data-stu-id="2172f-131">You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="2172f-132">这将导致主邮箱中的 "可恢复的项目" 文件夹的 110 GB 和用户存档中 "可恢复的项目" 文件夹的存储容量不受限制。</span><span class="sxs-lookup"><span data-stu-id="2172f-132">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="2172f-133">请参阅如何：[在安全 & 合规性中心中启用存档邮箱](enable-archive-mailboxes.md)，以及如何[在 Office 365 中启用无限存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="2172f-133">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2172f-134">为"可恢复的项目"文件夹存储配额接近上限的邮箱启用存档功能后，可能需要运行托管文件夹助理以自动触发助理处理邮箱，以便将过期项目移至存档邮箱的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="2172f-134">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="2172f-135">有关说明，请参阅[步骤 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。</span><span class="sxs-lookup"><span data-stu-id="2172f-135">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="2172f-136">注意，用户邮箱中的其他项目可能会移至新的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-136">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="2172f-137">请考虑告诉用户在启用存档邮箱后可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="2172f-137">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="2172f-138">**为处于保留状态的邮箱创建自定义 Exchange 保留策略。**</span><span class="sxs-lookup"><span data-stu-id="2172f-138">**Create a custom Exchange retention policy for mailboxes on hold.**</span></span> <span data-ttu-id="2172f-139">除了在诉讼保留或就地保留中启用邮箱的存档邮箱和自动扩展存档之外，您可能还需要为处于保留状态的邮箱创建自定义 Exchange 保留策略。</span><span class="sxs-lookup"><span data-stu-id="2172f-139">In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom Exchange retention policy for mailboxes on hold.</span></span> <span data-ttu-id="2172f-140">这使您可以将保留策略应用于保留的邮箱，这些邮箱与应用于不保留的邮箱的默认 MRM 策略不同，并允许您应用专为邮箱保留的保留标记。</span><span class="sxs-lookup"><span data-stu-id="2172f-140">This lets you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold, and lets you apply retention tags that are designed for mailboxes on hold.</span></span> <span data-ttu-id="2172f-141">其中包括为"可恢复的项目"文件夹创建新的保留标记。</span><span class="sxs-lookup"><span data-stu-id="2172f-141">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="2172f-142">本主题的其余部分介绍了为处于保留状态的邮箱创建自定义 Exchange 保留策略的分步过程。</span><span class="sxs-lookup"><span data-stu-id="2172f-142">The remainder of this topic describes the step-by-step procedures to create a custom Exchange retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="2172f-143">步骤1：为 "可恢复的项目" 文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="2172f-143">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[<span data-ttu-id="2172f-144">步骤2：为处于保留状态的邮箱创建新的 Exchange 保留策略</span><span class="sxs-lookup"><span data-stu-id="2172f-144">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[<span data-ttu-id="2172f-145">步骤3：将新的 Exchange 保留策略应用于处于保留状态的邮箱</span><span class="sxs-lookup"><span data-stu-id="2172f-145">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="2172f-146">Optional步骤4：运行托管文件夹助理以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="2172f-146">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="2172f-147">步骤1：为 "可恢复的项目" 文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="2172f-147">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="2172f-148">第一步是为 "可恢复的项目" 文件夹创建自定义保留标记（称为保留策略标记或 RPT）。</span><span class="sxs-lookup"><span data-stu-id="2172f-148">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="2172f-149">如前所述，此 RPT 将项目从用户主邮箱中的 "可恢复的项目" 文件夹移动到用户的存档邮箱中的 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2172f-149">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="2172f-150">您必须使用 PowerShell 为 "可恢复的项目" 文件夹创建 RPT。</span><span class="sxs-lookup"><span data-stu-id="2172f-150">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="2172f-151">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="2172f-151">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="2172f-152">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2172f-152">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="2172f-153">运行以下命令，为 "可恢复的项目" 文件夹创建一个新的 RPT：</span><span class="sxs-lookup"><span data-stu-id="2172f-153">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="2172f-154">例如，以下命令为 "保留的邮箱为30天" 的 "可恢复的项目" 文件夹创建一个 RPT，保留期为30天。</span><span class="sxs-lookup"><span data-stu-id="2172f-154">For example, the following command creates an RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="2172f-155">这意味着项目已在 "可恢复的项目" 文件夹中的30天后，它将移至用户存档邮箱中的 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2172f-155">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="2172f-156">我们建议可恢复项目 RPT 的保留期（由_AgeLimitForRetention_参数定义）与 RPT 将应用到的邮箱的已删除项目保留期相同。</span><span class="sxs-lookup"><span data-stu-id="2172f-156">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="2172f-157">这允许用户整个已删除项目的保留期在将已删除邮件移至存档邮箱之前将其恢复。</span><span class="sxs-lookup"><span data-stu-id="2172f-157">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="2172f-158">在上面的示例中，假定邮箱的已删除邮件保留期也为30天，则保留期已设置为30天。</span><span class="sxs-lookup"><span data-stu-id="2172f-158">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="2172f-159">默认情况下，Exchange Online 邮箱配置为将已删除项目保留14天。</span><span class="sxs-lookup"><span data-stu-id="2172f-159">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="2172f-160">但您最多可以将此设置更改为30天。</span><span class="sxs-lookup"><span data-stu-id="2172f-160">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="2172f-161">有关详细信息，请参阅[在 Exchange Online 中更改邮箱的已删除邮件保留期](https://www.microsoft.com/?ref=go)。</span><span class="sxs-lookup"><span data-stu-id="2172f-161">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="2172f-162">步骤2：为处于保留状态的邮箱创建新的 Exchange 保留策略</span><span class="sxs-lookup"><span data-stu-id="2172f-162">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>

<span data-ttu-id="2172f-163">下一步是创建新的保留策略并向其添加保留标记，包括您在步骤1中创建的 "可恢复的项目" RPT。</span><span class="sxs-lookup"><span data-stu-id="2172f-163">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1.</span></span> <span data-ttu-id="2172f-164">在下一步中，此新策略将应用于处于保留状态的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-164">This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="2172f-165">在创建新的保留策略之前，请确定要添加的其他保留标记。</span><span class="sxs-lookup"><span data-stu-id="2172f-165">Before you create the new retention policy, determine the additional retention tags that you want to add.</span></span> <span data-ttu-id="2172f-166">有关添加到默认 MRM 策略的保留标记列表，以及有关创建新的保留标记的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="2172f-166">For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="2172f-167">Exchange Online 中的默认保留策略</span><span class="sxs-lookup"><span data-stu-id="2172f-167">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="2172f-168">支持保留策略标记的默认文件夹</span><span class="sxs-lookup"><span data-stu-id="2172f-168">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="2172f-169">"[创建保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404422)" 主题中的 "创建保留标记" 部分。</span><span class="sxs-lookup"><span data-stu-id="2172f-169">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="2172f-170">您可以使用 EAC 或 Exchange Online PowerShell 创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="2172f-170">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="2172f-171">使用 EAC 创建保留策略</span><span class="sxs-lookup"><span data-stu-id="2172f-171">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="2172f-172">在 EAC 中，转到 "**合规性管理** \> **保留策略**"，然后单击 "**添加**" "添加" ![ 图标 ](../media/ITPro-EAC-AddIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2172f-172">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="2172f-173">在 "**新建保留策略**" 页上的 "**名称**" 下，键入描述保留策略用途的名称;例如，处于**保留状态的邮箱的 MRM 策略**。</span><span class="sxs-lookup"><span data-stu-id="2172f-173">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="2172f-174">在 "**保留标记**" 下，单击 "**添加**" "添加" ![ 图标 ](../media/ITPro-EAC-AddIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2172f-174">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="2172f-175">在 "保留标记" 列表中，选择您在步骤1中创建的 "可恢复的项目" RPT，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="2172f-175">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![选择自定义的“可恢复的项目”保留标记](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="2172f-177">选择要添加到保留策略中的其他保留标记。</span><span class="sxs-lookup"><span data-stu-id="2172f-177">Select additional retention tags to add to the retention policy.</span></span> <span data-ttu-id="2172f-178">例如，您可能希望添加默认 MRM 策略中包含的相同标记。</span><span class="sxs-lookup"><span data-stu-id="2172f-178">For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="2172f-179">添加完保留标记后，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2172f-179">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="2172f-180">单击 "**保存**" 以创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="2172f-180">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="2172f-181">请注意，链接到保留策略的保留标记将显示在详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="2172f-181">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![在详细信息窗格中显示链接到保留策略的保留标记](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="2172f-183">使用 Exchange Online PowerShell 创建保留策略</span><span class="sxs-lookup"><span data-stu-id="2172f-183">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="2172f-184">运行以下命令，为处于保留状态的邮箱创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="2172f-184">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="2172f-185">例如，以下命令将创建在上图中显示的保留策略和链接的保留标记。</span><span class="sxs-lookup"><span data-stu-id="2172f-185">For example, the following command creates the retention policy and linked retention tags that are displayed in the previous illustration.</span></span>
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="2172f-186">步骤3：将新的 Exchange 保留策略应用于处于保留状态的邮箱</span><span class="sxs-lookup"><span data-stu-id="2172f-186">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>

<span data-ttu-id="2172f-187">最后一步是将您在步骤2中创建的新的保留策略应用于组织中的 "保留中的邮箱"。</span><span class="sxs-lookup"><span data-stu-id="2172f-187">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="2172f-188">您可以使用 EAC 或 Exchange Online PowerShell 将保留策略应用于单个邮箱或多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-188">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="2172f-189">使用 EAC 应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="2172f-189">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="2172f-190">转到 "**收件人**" "  >  **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="2172f-190">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="2172f-191">在列表视图中，选择要应用保留策略的邮箱，然后单击 "**编辑** ![ 编辑图标" ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2172f-191">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="2172f-192">在 "**用户邮箱**" 页上，单击 "**邮箱功能**"。</span><span class="sxs-lookup"><span data-stu-id="2172f-192">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="2172f-193">在 "**保留策略**" 下，选择您在步骤2中创建的保留策略，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2172f-193">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="2172f-194">您还可以使用 EAC 将保留策略应用于多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-194">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="2172f-195">转到 "**收件人**" "  >  **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="2172f-195">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="2172f-196">在此列表视图中，使用 Shift 或 Ctrl 键选择多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-196">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="2172f-197">在详细信息窗格中，单击“更多选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2172f-197">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="2172f-198">在“保留策略”\*\*\*\* 下，单击“更新”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2172f-198">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="2172f-199">在 "**批量分配保留策略**" 页上，选择您在步骤2中创建的保留策略，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2172f-199">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="2172f-200">使用 Exchange Online PowerShell 应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="2172f-200">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="2172f-201">您可以使用 Exchange Online PowerShell 将新的保留策略应用于单个邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-201">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="2172f-202">但是，PowerShell 真正的强大之处在于，您可以使用它来快速标识组织中的所有处于诉讼保留或就地保留状态的邮箱，然后在单个命令中将新的保留策略应用于处于保留状态的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-202">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="2172f-203">下面是使用 Exchange PowerShell 将保留策略应用于一个或多个邮箱的一些示例。</span><span class="sxs-lookup"><span data-stu-id="2172f-203">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="2172f-204">所有示例都应用在步骤2中创建的保留策略。</span><span class="sxs-lookup"><span data-stu-id="2172f-204">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="2172f-205">本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-205">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="2172f-206">本示例将新的保留策略应用于组织中处于诉讼保留状态的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-206">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="2172f-207">本示例将新的保留策略应用于组织中的 "就地保留" 中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-207">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="2172f-208">您可以使用 "**获取邮箱**" cmdlet 验证是否已应用新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="2172f-208">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="2172f-209">下面是一些示例，用于验证前面示例中的命令是否将 "MRM Policy for 邮箱保留" 保留策略应用于诉讼保留中的邮箱和就地保留中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-209">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="2172f-210">Optional步骤4：运行托管文件夹助理以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="2172f-210">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="2172f-211">将新的 Exchange 保留策略应用于保留邮箱后，在 Exchange Online 中可能需要长达7天的时间，托管文件夹助理才能使用新保留策略中的设置处理这些邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-211">After you apply the new Exchange retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="2172f-212">您可以使用**start-managedfolderassistant** cmdlet 手动触发助理以处理应用新的保留策略的邮箱，而不是等待托管文件夹助理运行。</span><span class="sxs-lookup"><span data-stu-id="2172f-212">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="2172f-213">运行以下命令以启动 Pilar Pinilla 的邮箱的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="2172f-213">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="2172f-214">运行以下命令以启动处于保留状态的所有邮箱的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="2172f-214">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="2172f-215">更多信息</span><span class="sxs-lookup"><span data-stu-id="2172f-215">More information</span></span>

- <span data-ttu-id="2172f-216">启用用户的存档邮箱后，请考虑告诉用户其邮箱中的其他项目（不仅仅是 "可恢复的项目" 文件夹中的项目）可能会被移至存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-216">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="2172f-217">这是因为分配给 Exchange Online 邮箱的默认 MRM 策略包含一个保留标记（名为 "默认2年移动到存档"），将项目在邮件传递到邮箱或由用户创建后的两年中将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="2172f-217">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="2172f-218">有关详细信息，请参阅[Exchange Online 中的默认保留策略](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="2172f-218">For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="2172f-219">启用用户的存档邮箱后，您可能还会告诉用户他们可以在其存档邮箱中的 "可恢复的项目" 文件夹中恢复已删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="2172f-219">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="2172f-220">在 Outlook 中，可以通过选择存档邮箱中的 "**已删除邮件**" 文件夹，然后在 "**开始**" 选项卡上单击 "**从服务器恢复已删除邮件**" 来执行此操作。有关恢复已删除项目的详细信息，请参阅[在 Outlook For Windows 中恢复已删除的项目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。</span><span class="sxs-lookup"><span data-stu-id="2172f-220">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
