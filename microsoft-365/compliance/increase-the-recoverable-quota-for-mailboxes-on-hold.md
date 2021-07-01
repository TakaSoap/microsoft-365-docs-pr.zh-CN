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
description: 启用存档邮箱并启用自动扩展存档，以增加邮箱中邮箱的"可恢复的项目"文件夹Microsoft 365。
ms.openlocfilehash: 47227e066f922a9e4b8bccedaa9573c001194836
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226583"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="ac01b-103">为置于保留状态的邮箱增加可恢复项目的配额</span><span class="sxs-lookup"><span data-stu-id="ac01b-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="ac01b-104">自动Exchange新邮箱的默认保留策略（名为"*默认 MR Exchange Online M* 策略）"包含名为"可恢复的项目 14 天移动到存档"的保留标记。</span><span class="sxs-lookup"><span data-stu-id="ac01b-104">The default Exchange retention policy—named *Default MRM Policy*—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="ac01b-105">此保留标记在项目的 14 天保留期到期后，将项目从用户主邮箱中的"可恢复的项目"文件夹移动到用户存档邮箱中的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="ac01b-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="ac01b-106">为此，必须启用用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="ac01b-107">如果未启用存档邮箱，则不执行任何操作，这意味着保留邮箱的"可恢复的项目"文件夹中的项目在 14 天保留期到期后不会移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="ac01b-108">由于不会从保留邮箱中删除任何内容，因此可能会超出"可恢复的项目"文件夹的存储配额，尤其是在用户的存档邮箱未启用的情况下。</span><span class="sxs-lookup"><span data-stu-id="ac01b-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span>

<span data-ttu-id="ac01b-109">为了帮助降低超出此限制的可能性，当邮箱处于保留状态时，"可恢复的项目"文件夹的存储配额会自动从 30 GB 增加到 100 GB Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ac01b-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="ac01b-110">如果存档邮箱已启用，则存档邮箱中"可恢复的项目"文件夹的存储配额也将从 30 GB 增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="ac01b-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="ac01b-111">如果启用用户存档中的自动扩展存档Exchange Online，则用户存档中"可恢复的项目"文件夹的存储配额将不受限制。</span><span class="sxs-lookup"><span data-stu-id="ac01b-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>

 <span data-ttu-id="ac01b-112">下表总结了"可恢复的项目"文件夹的存储配额。</span><span class="sxs-lookup"><span data-stu-id="ac01b-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span>

|<span data-ttu-id="ac01b-113">**"可恢复的项目"文件夹的位置**</span><span class="sxs-lookup"><span data-stu-id="ac01b-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="ac01b-114">**邮箱未置于保留状态**</span><span class="sxs-lookup"><span data-stu-id="ac01b-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="ac01b-115">**保留的邮箱**</span><span class="sxs-lookup"><span data-stu-id="ac01b-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac01b-116">主邮箱</span><span class="sxs-lookup"><span data-stu-id="ac01b-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="ac01b-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="ac01b-117">30 GB</span></span>  <br/> |<span data-ttu-id="ac01b-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="ac01b-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="ac01b-119">存档邮箱<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ac01b-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="ac01b-120">无限制</span><span class="sxs-lookup"><span data-stu-id="ac01b-120">Unlimited</span></span>  <br/> |<span data-ttu-id="ac01b-121">无限制</span><span class="sxs-lookup"><span data-stu-id="ac01b-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="ac01b-122">**"可恢复的项目"文件夹的总存储配额**</span><span class="sxs-lookup"><span data-stu-id="ac01b-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="ac01b-123">无限制</span><span class="sxs-lookup"><span data-stu-id="ac01b-123">Unlimited</span></span>  <br/> |<span data-ttu-id="ac01b-124">无限制</span><span class="sxs-lookup"><span data-stu-id="ac01b-124">Unlimited</span></span>  <br/> |

> [!NOTE]
> <span data-ttu-id="ac01b-125"><sup>\*</sup>存档邮箱的初始存储配额是 100 GB（对于拥有 Exchange Online (计划 2) 许可证的用户）。</span><span class="sxs-lookup"><span data-stu-id="ac01b-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="ac01b-126">但是，当为保留邮箱启用自动扩展存档时，存档邮箱和"可恢复的项目"文件夹的存储配额将增加到 110 GB。</span><span class="sxs-lookup"><span data-stu-id="ac01b-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="ac01b-127">如有必要，将设置额外的存档存储空间，这将产生无限数量的存档存储空间。</span><span class="sxs-lookup"><span data-stu-id="ac01b-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="ac01b-128">有关自动扩展存档的信息，请参阅 overview [of unlimited archiving in Office 365](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="ac01b-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

<span data-ttu-id="ac01b-129">当置于保留状态的邮箱的主邮箱"可恢复的项目"文件夹的存储配额接近其限额时，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ac01b-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>

- <span data-ttu-id="ac01b-130">**启用存档邮箱并启用自动扩展存档。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-130">**Enable the archive mailbox and turn on auto-expanding archiving.**</span></span> <span data-ttu-id="ac01b-131">只需启用存档邮箱，然后启用 ExchangeOnline 中的自动扩展存档功能，就可以为“可恢复的项目”文件夹开启无限制存储容量。</span><span class="sxs-lookup"><span data-stu-id="ac01b-131">You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="ac01b-132">这导致主邮箱中的"可恢复的项目"文件夹达到 110 GB，并且用户存档中的"可恢复的项目"文件夹的存储容量不受限制。</span><span class="sxs-lookup"><span data-stu-id="ac01b-132">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="ac01b-133">请参阅如何[：在安全与合规&启用](enable-archive-mailboxes.md)存档邮箱，并启用存档[Office 365。](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="ac01b-133">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac01b-134">为接近超出"可恢复的项目"文件夹存储配额的邮箱启用存档后，您可能需要运行托管文件夹助理以手动触发助理处理邮箱，以便过期项目移动到存档邮箱中的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="ac01b-134">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="ac01b-135">有关[说明，请参阅步骤 4。](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)</span><span class="sxs-lookup"><span data-stu-id="ac01b-135">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="ac01b-136">注意，用户邮箱中的其他项目可能会移至新的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-136">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="ac01b-137">请考虑告知用户启用存档邮箱后可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="ac01b-137">Consider telling the user that this may happen after you enable the archive mailbox.</span></span>

- <span data-ttu-id="ac01b-138">**为保留Exchange邮箱创建自定义保留策略。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-138">**Create a custom Exchange retention policy for mailboxes on hold.**</span></span> <span data-ttu-id="ac01b-139">除了为诉讼保留或 In-Place 保留的邮箱启用存档邮箱和自动扩展存档外，您可能还需要为保留邮箱创建自定义 Exchange 保留策略。</span><span class="sxs-lookup"><span data-stu-id="ac01b-139">In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom Exchange retention policy for mailboxes on hold.</span></span> <span data-ttu-id="ac01b-140">这使你可以将保留策略应用于保留的邮箱，该策略不同于应用于未置于保留状态邮箱的默认 MRM 策略，并允许您应用为保留邮箱设计的保留标记。</span><span class="sxs-lookup"><span data-stu-id="ac01b-140">This lets you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold, and lets you apply retention tags that are designed for mailboxes on hold.</span></span> <span data-ttu-id="ac01b-141">其中包括为"可恢复的项目"文件夹创建新的保留标记。</span><span class="sxs-lookup"><span data-stu-id="ac01b-141">This includes creating a new retention tag for the Recoverable Items folder.</span></span>

<span data-ttu-id="ac01b-142">本主题的其余部分介绍了为保留邮箱创建自定义邮箱保留Exchange的分步过程。</span><span class="sxs-lookup"><span data-stu-id="ac01b-142">The remainder of this topic describes the step-by-step procedures to create a custom Exchange retention policy for mailboxes on hold.</span></span>

[<span data-ttu-id="ac01b-143">步骤 1：为"可恢复的项目"文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="ac01b-143">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[<span data-ttu-id="ac01b-144">步骤 2：为保留Exchange创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="ac01b-144">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[<span data-ttu-id="ac01b-145">步骤 3：将新的Exchange保留策略应用于保留的邮箱</span><span class="sxs-lookup"><span data-stu-id="ac01b-145">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="ac01b-146"> (可选) 步骤 4：运行托管文件夹助理以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="ac01b-146">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)

## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="ac01b-147">步骤 1：为"可恢复的项目"文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="ac01b-147">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="ac01b-148">第一步是为"可恢复的项目"文件夹 (保留策略标记或 RPT) 保留标记。</span><span class="sxs-lookup"><span data-stu-id="ac01b-148">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="ac01b-149">如前所述，此 RPT 将项目从用户主邮箱中的"可恢复的项目"文件夹移动到用户存档邮箱中的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="ac01b-149">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="ac01b-150">您必须使用 PowerShell 为"可恢复的项目"文件夹创建 RPT。</span><span class="sxs-lookup"><span data-stu-id="ac01b-150">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="ac01b-151">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="ac01b-151">You can't use the Exchange admin center (EAC).</span></span>

1. [<span data-ttu-id="ac01b-152">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ac01b-152">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="ac01b-153">运行以下命令，为"可恢复的项目"文件夹创建新的 RPT：</span><span class="sxs-lookup"><span data-stu-id="ac01b-153">Run the following command to create a new RPT for the Recoverable Items folder:</span></span>

    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="ac01b-154">例如，以下命令为名为"保留邮箱的可恢复项目 30 天"的"可恢复的项目"文件夹创建一个 RPT，保留期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="ac01b-154">For example, the following command creates an RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="ac01b-155">这意味着，在项目在"可恢复的项目"文件夹中保留 30 天后，该项目将移动到用户存档邮箱中的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="ac01b-155">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>

    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="ac01b-156">我们建议由  _AgeLimitForRetention_ 参数) 为"可恢复的项目"RPT 定义的保留期 (与将应用 RPT 的邮箱的已删除项目保留期相同。</span><span class="sxs-lookup"><span data-stu-id="ac01b-156">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="ac01b-157">这允许用户在将已删除项目移至存档邮箱之前，在已删除邮件的整个保留期内恢复这些项目。</span><span class="sxs-lookup"><span data-stu-id="ac01b-157">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="ac01b-158">在上一示例中，根据邮箱的已删除项目保留期也是 30 天的假设，保留期设置为 30 天。</span><span class="sxs-lookup"><span data-stu-id="ac01b-158">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="ac01b-159">默认情况下Exchange Online邮箱将已删除项目保留 14 天。</span><span class="sxs-lookup"><span data-stu-id="ac01b-159">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="ac01b-160">但你可以将此设置更改为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="ac01b-160">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="ac01b-161">有关详细信息，请参阅 Change [the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go)。</span><span class="sxs-lookup"><span data-stu-id="ac01b-161">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span>

## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="ac01b-162">步骤 2：为保留Exchange创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="ac01b-162">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>

<span data-ttu-id="ac01b-163">下一步是创建新的保留策略，并添加保留标记，包括在步骤 1 中创建的"可恢复的项目 RPT"。</span><span class="sxs-lookup"><span data-stu-id="ac01b-163">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1.</span></span> <span data-ttu-id="ac01b-164">此新策略将应用于下一步中保留的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-164">This new policy will be applied to mailboxes on hold in the next step.</span></span>

<span data-ttu-id="ac01b-165">在创建新的保留策略之前，确定要添加的其他保留标记。</span><span class="sxs-lookup"><span data-stu-id="ac01b-165">Before you create the new retention policy, determine the additional retention tags that you want to add.</span></span> <span data-ttu-id="ac01b-166">有关添加到默认 MRM 策略的保留标记的列表，以及有关创建新的保留标记的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="ac01b-166">For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>

- [<span data-ttu-id="ac01b-167">Exchange Online 中的默认保留策略</span><span class="sxs-lookup"><span data-stu-id="ac01b-167">Default Retention Policy in Exchange Online</span></span>](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- [<span data-ttu-id="ac01b-168">支持保留策略标记的默认文件夹</span><span class="sxs-lookup"><span data-stu-id="ac01b-168">Default folders that support Retention Policy Tags</span></span>](/exchange/security-and-compliance/messaging-records-management/default-folders)

- <span data-ttu-id="ac01b-169">创建保留策略主题中的"创建 [保留标记"](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) 部分。</span><span class="sxs-lookup"><span data-stu-id="ac01b-169">The "Create a retention tag" section in the [Create a Retention Policy](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) topic.</span></span>

<span data-ttu-id="ac01b-170">可以使用 EAC 或 Exchange Online PowerShell 创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="ac01b-170">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>

### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="ac01b-171">使用 EAC 创建保留策略</span><span class="sxs-lookup"><span data-stu-id="ac01b-171">Use the EAC to create a retention policy</span></span>

1. <span data-ttu-id="ac01b-172">在 EAC 中，转到" **合规性管理**""保留 \> **策略"，** 然后单击" **添加添加** ![ 图标 ](../media/ITPro-EAC-AddIcon.gif) "。</span><span class="sxs-lookup"><span data-stu-id="ac01b-172">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

2. <span data-ttu-id="ac01b-173">在" **新建保留策略"** 页上的" **名称"** 下，键入描述保留策略用途的名称;例如， **保留邮箱的 MRM 策略**。</span><span class="sxs-lookup"><span data-stu-id="ac01b-173">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span>

3. <span data-ttu-id="ac01b-174">在" **保留标记"下**，单击 **"添加** ![ 添加图标 ](../media/ITPro-EAC-AddIcon.gif) "。</span><span class="sxs-lookup"><span data-stu-id="ac01b-174">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="ac01b-175">在保留标记列表中，选择在步骤 1 中创建的"可恢复的项目 RPT"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-175">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>

    ![选择自定义的“可恢复的项目”保留标记](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)

5. <span data-ttu-id="ac01b-177">选择要添加到保留策略的其他保留标记。</span><span class="sxs-lookup"><span data-stu-id="ac01b-177">Select additional retention tags to add to the retention policy.</span></span> <span data-ttu-id="ac01b-178">例如，您可能需要添加默认 MRM 策略中包含的相同标记。</span><span class="sxs-lookup"><span data-stu-id="ac01b-178">For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>

6. <span data-ttu-id="ac01b-179">添加完保留标记后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-179">When you're finished adding retention tags, click **OK**.</span></span>

7. <span data-ttu-id="ac01b-180">单击 **"保存** "创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="ac01b-180">Click **Save** to create the new retention policy.</span></span>

    <span data-ttu-id="ac01b-181">请注意，链接到保留策略的保留标记显示在详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="ac01b-181">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>

    ![在详细信息窗格中显示链接到保留策略的保留标记](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)

### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="ac01b-183">使用 Exchange Online PowerShell 创建保留策略</span><span class="sxs-lookup"><span data-stu-id="ac01b-183">Use Exchange Online PowerShell to create a retention policy</span></span>

<span data-ttu-id="ac01b-184">运行以下命令，为保留邮箱创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="ac01b-184">Run the following command to create new retention policy for mailboxes on hold.</span></span>

```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="ac01b-185">例如，以下命令将创建上图中显示的保留策略和链接的保留标记。</span><span class="sxs-lookup"><span data-stu-id="ac01b-185">For example, the following command creates the retention policy and linked retention tags that are displayed in the previous illustration.</span></span>

```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="ac01b-186">步骤 3：将新的Exchange保留策略应用于保留的邮箱</span><span class="sxs-lookup"><span data-stu-id="ac01b-186">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>

<span data-ttu-id="ac01b-187">最后一步是将步骤 2 中创建的新保留策略应用于组织中保留的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-187">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="ac01b-188">可以使用 EAC 或 Exchange Online PowerShell 将保留策略应用于单个邮箱或多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-188">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span>

### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="ac01b-189">使用 EAC 应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="ac01b-189">Use the EAC to apply the new retention policy</span></span>

1. <span data-ttu-id="ac01b-190">转到 **"收件人**  >  **""邮箱"。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-190">Go to **Recipients** > **Mailboxes**.</span></span>

2. <span data-ttu-id="ac01b-191">在列表视图中，选择要应用保留策略的邮箱，然后单击"编辑 **编辑** ![ "图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="ac01b-191">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

3. <span data-ttu-id="ac01b-192">在"**用户邮箱"页上**，单击"**邮箱功能"。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-192">On the **User Mailbox** page, click **Mailbox features**.</span></span>

4. <span data-ttu-id="ac01b-193">在 **"保留策略**"下，选择在步骤 2 中创建的保留策略，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-193">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>

<span data-ttu-id="ac01b-194">您还可以使用 EAC 将保留策略应用于多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-194">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>

1. <span data-ttu-id="ac01b-195">转到 **"收件人**  >  **""邮箱"。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-195">Go to **Recipients** > **Mailboxes**.</span></span>

2. <span data-ttu-id="ac01b-196">在此列表视图中，使用 Shift 或 Ctrl 键选择多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-196">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>

3. <span data-ttu-id="ac01b-197">在详细信息窗格中，单击“更多选项”。</span><span class="sxs-lookup"><span data-stu-id="ac01b-197">In the details pane, click **More options**.</span></span>

4. <span data-ttu-id="ac01b-198">在“保留策略”下，单击“更新”。</span><span class="sxs-lookup"><span data-stu-id="ac01b-198">Under **Retention Policy**, click **Update**.</span></span>

5. <span data-ttu-id="ac01b-199">在"**批量分配保留策略"** 页上，选择在步骤 2 中创建的保留策略，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="ac01b-199">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="ac01b-200">使用 Exchange Online PowerShell 应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="ac01b-200">Use Exchange Online PowerShell to apply the new retention policy</span></span>

<span data-ttu-id="ac01b-201">可以使用 PowerShell Exchange Online单个邮箱应用新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="ac01b-201">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="ac01b-202">但是 PowerShell 的真正功能是，您可以使用它快速标识组织中置于诉讼保留或 In-Place 保留状态的所有邮箱，然后在单个命令中将新的保留策略应用于所有保留邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-202">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="ac01b-203">下面是使用 PowerShell 将保留Exchange应用于一个或多个邮箱的一些示例。</span><span class="sxs-lookup"><span data-stu-id="ac01b-203">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="ac01b-204">所有示例都应用在步骤 2 中创建的保留策略。</span><span class="sxs-lookup"><span data-stu-id="ac01b-204">All of the examples apply the retention policy that was created in Step 2.</span></span>

<span data-ttu-id="ac01b-205">本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-205">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>

```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="ac01b-206">本示例将新的保留策略应用于组织中置于诉讼保留状态的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-206">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>

```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="ac01b-207">本示例将新的保留策略应用于组织中置于保留状态的所有In-Place邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-207">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>

```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="ac01b-208">您可以使用 **Get-Mailbox** cmdlet 验证是否应用了新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="ac01b-208">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span>

<span data-ttu-id="ac01b-209">下面是一些示例，用于验证之前示例中的命令是否将"保留邮箱的 MRM 策略"保留策略应用于诉讼保留的邮箱和置于保留In-Place邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-209">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>

```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="ac01b-210"> (可选) 步骤 4：运行托管文件夹助理以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="ac01b-210">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="ac01b-211">将新的 Exchange 保留策略应用于保留的邮箱后，托管文件夹助理最多可能需要 Exchange Online 7 天的时间才能使用新保留策略中的设置处理这些邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-211">After you apply the new Exchange retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="ac01b-212">无需等待托管文件夹助理运行，您可以使用 **Start-ManagedFolderAssistant** cmdlet 手动触发助理，以处理应用了新保留策略的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-212">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span>

<span data-ttu-id="ac01b-213">运行以下命令以启动 Pilar Pinilla 邮箱的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="ac01b-213">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>

```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="ac01b-214">运行以下命令以启动所有保留邮箱的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="ac01b-214">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>

```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="ac01b-215">更多信息</span><span class="sxs-lookup"><span data-stu-id="ac01b-215">More information</span></span>

- <span data-ttu-id="ac01b-216">启用用户的存档邮箱后，请考虑告知用户，其邮箱中的其他项目 ("可恢复的项目"文件夹中的项目) 可能会移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-216">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="ac01b-217">这是因为分配给 Exchange Online 邮箱的默认 MRM 策略包含名为"默认 2 年"的保留标记 (移动到存档) ，该标记在邮件传递到邮箱或由用户创建项目两年后将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="ac01b-217">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="ac01b-218">有关详细信息，请参阅默认[保留策略Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="ac01b-218">For more information, see [Default Retention Policy in Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span></span>

- <span data-ttu-id="ac01b-219">启用用户的存档邮箱后，您还可以告诉用户他们可以恢复其存档邮箱中"可恢复的项目"文件夹中的已删除项目。</span><span class="sxs-lookup"><span data-stu-id="ac01b-219">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="ac01b-220">他们可以通过选择存档邮箱Outlook"已删除邮件"文件夹，然后单击"开始"选项卡上的"从服务器恢复已删除邮件"，来在邮箱 **中** 执行这一操作。有关恢复已删除项目的信息，请参阅 Recover [deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829)。</span><span class="sxs-lookup"><span data-stu-id="ac01b-220">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span>
