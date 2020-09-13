---
title: 管理客户密钥
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 在设置客户密钥之后，请了解如何通过还原 AKV 密钥以及管理权限和数据加密策略来管理它。
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547082"
---
# <a name="manage-customer-key"></a><span data-ttu-id="d428f-103">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="d428f-103">Manage Customer Key</span></span>

<span data-ttu-id="d428f-104">在设置了 Office 365 的客户密钥之后，您可以按本文所述管理密钥。</span><span class="sxs-lookup"><span data-stu-id="d428f-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="d428f-105">有关详细信息，请参阅相关主题中的客户密钥。</span><span class="sxs-lookup"><span data-stu-id="d428f-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="d428f-106">还原 Azure Key Vault 密钥</span><span class="sxs-lookup"><span data-stu-id="d428f-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="d428f-107">在执行还原之前，请使用由软删除提供的恢复功能。</span><span class="sxs-lookup"><span data-stu-id="d428f-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="d428f-108">需要使用与客户密钥一起使用的所有密钥才能启用软删除。</span><span class="sxs-lookup"><span data-stu-id="d428f-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="d428f-109">软删除操作类似于回收站，允许恢复最长为90天，而无需进行还原。</span><span class="sxs-lookup"><span data-stu-id="d428f-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="d428f-110">只有在极端或异常情况下才需要还原，例如，密钥或密钥存储库丢失。</span><span class="sxs-lookup"><span data-stu-id="d428f-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="d428f-111">如果您必须还原密钥以用于客户密钥，请在 Azure PowerShell 中运行 AzureKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d428f-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="d428f-112">例如：</span><span class="sxs-lookup"><span data-stu-id="d428f-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="d428f-113">如果密钥保管库已包含具有相同名称的密钥，还原操作将失败。</span><span class="sxs-lookup"><span data-stu-id="d428f-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="d428f-114">Restore-AzKeyVaultKey 还原密钥的所有密钥版本和所有元数据，包括密钥名称。</span><span class="sxs-lookup"><span data-stu-id="d428f-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="d428f-115">管理密钥存储库权限</span><span class="sxs-lookup"><span data-stu-id="d428f-115">Manage key vault permissions</span></span>

<span data-ttu-id="d428f-116">提供了多个 cmdlet，以便你可以查看并在必要时删除密钥保管库权限（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="d428f-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="d428f-117">您可能需要删除权限，例如，当员工离开团队时。</span><span class="sxs-lookup"><span data-stu-id="d428f-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="d428f-118">对于这些任务中的每一项，都将使用 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d428f-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="d428f-119">有关 Azure Powershell 的信息，请参阅 [Azure Powershell 概述](https://docs.microsoft.com/powershell/azure/)。</span><span class="sxs-lookup"><span data-stu-id="d428f-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="d428f-120">若要查看密钥存储区权限，请运行 AzKeyVault cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d428f-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="d428f-121">例如：</span><span class="sxs-lookup"><span data-stu-id="d428f-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="d428f-122">若要删除管理员权限，请运行 AzKeyVaultAccessPolicy cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d428f-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="d428f-123">例如：</span><span class="sxs-lookup"><span data-stu-id="d428f-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="d428f-124">使用客户密钥管理 (DEPs) 的数据加密策略</span><span class="sxs-lookup"><span data-stu-id="d428f-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="d428f-125">客户密钥处理不同服务之间的 DEPs 不同。</span><span class="sxs-lookup"><span data-stu-id="d428f-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="d428f-126">例如，您可以为不同的服务创建不同数量的 DEPs。</span><span class="sxs-lookup"><span data-stu-id="d428f-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="d428f-127">**Exchange Online 和 Skype For business：** 最高可创建 50 DEPs。</span><span class="sxs-lookup"><span data-stu-id="d428f-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="d428f-128">有关说明，请参阅 [Create a data encryption policy (DEP) 以用于 Exchange Online 和 Skype For business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="d428f-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="d428f-129">**SharePoint Online、OneDrive For business 和团队文件：** DEP 适用于一个地理位置（也称为 _地理_位置）中的数据。</span><span class="sxs-lookup"><span data-stu-id="d428f-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="d428f-130">如果使用 Office 365 的多地理位置功能，则可以为每个地理位置创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="d428f-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="d428f-131">如果您不使用多地理位置，则可以创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="d428f-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="d428f-132">通常情况下，在设置 "客户密钥" 时创建 DEP。</span><span class="sxs-lookup"><span data-stu-id="d428f-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="d428f-133">有关说明，请参阅 [Create a data encryption policy (DEP) for Each SharePoint Online 和 OneDrive For business 地域](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)。</span><span class="sxs-lookup"><span data-stu-id="d428f-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d428f-134">查看您为 Exchange Online 和 Skype for Business 创建的 DEPs</span><span class="sxs-lookup"><span data-stu-id="d428f-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d428f-135">若要查看您使用 DataEncryptionPolicy PowerShell cmdlet 为 Exchange Online 和 Skype for business 创建的所有 DEPs 的列表，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d428f-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="d428f-136">使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d428f-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d428f-137">若要返回组织中的所有 DEPs，请运行不带任何参数的 DataEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d428f-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="d428f-138">有关 DataEncryptionPolicy cmdlet 的详细信息，请参阅 [DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="d428f-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="d428f-139">在将邮箱迁移到云中之前分配一个 DEP</span><span class="sxs-lookup"><span data-stu-id="d428f-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="d428f-140">分配 DEP 时，Microsoft 365 会在迁移过程中使用分配的 DEP 对邮箱的内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="d428f-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="d428f-141">此过程比迁移邮箱、分配 DEP 并等待进行加密更高效，这可能需要数小时或数天。</span><span class="sxs-lookup"><span data-stu-id="d428f-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="d428f-142">若要在将 DEP 迁移到 Office 365 之前将其分配给邮箱，请在 Exchange Online PowerShell 中运行 MailUser cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d428f-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="d428f-143">使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d428f-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d428f-144">运行 MailUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d428f-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="d428f-145">其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱， *DataEncryptionPolicyIdParameter* 是 DEP 的 ID。</span><span class="sxs-lookup"><span data-stu-id="d428f-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="d428f-146">有关 MailUser cmdlet 的详细信息，请参阅 [MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="d428f-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="d428f-147">确定分配给邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="d428f-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="d428f-148">若要确定分配给邮箱的 DEP，请使用 Get-mailboxstatistics cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d428f-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="d428f-149">Cmdlet 返回 (GUID) 的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d428f-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="d428f-150">使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d428f-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="d428f-151">其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱和 DATAENCRYPTIONPOLICYID 返回 DEP 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d428f-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="d428f-152">有关 Get-mailboxstatistics cmdlet 的详细信息，请参阅 [get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics)。</span><span class="sxs-lookup"><span data-stu-id="d428f-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="d428f-153">运行 DataEncryptionPolicy cmdlet 以查找邮箱分配到的 DEP 的友好名称。</span><span class="sxs-lookup"><span data-stu-id="d428f-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="d428f-154">其中 *guid* 是上一步中的 get-mailboxstatistics cmdlet 返回的 guid。</span><span class="sxs-lookup"><span data-stu-id="d428f-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="d428f-155">验证客户密钥是否已完成加密</span><span class="sxs-lookup"><span data-stu-id="d428f-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="d428f-156">无论您是仅滚动了客户密钥、分配了新的 DEP 还是迁移了邮箱，都可以使用本节中的步骤来确保加密完成。</span><span class="sxs-lookup"><span data-stu-id="d428f-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d428f-157">验证 Exchange Online 和 Skype for business 的加密是否已完成</span><span class="sxs-lookup"><span data-stu-id="d428f-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d428f-158">对邮箱加密可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="d428f-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="d428f-159">建议您在更改 DEP 或首次将 DEP 分配到邮箱之后，先等待72小时，再尝试验证加密。</span><span class="sxs-lookup"><span data-stu-id="d428f-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="d428f-160">使用 Get-mailboxstatistics cmdlet 可以确定邮箱是否已加密。</span><span class="sxs-lookup"><span data-stu-id="d428f-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="d428f-161">如果邮箱已加密，则 IsEncrypted 属性返回 **true** ，如果邮箱未加密，则返回 **false** 值。</span><span class="sxs-lookup"><span data-stu-id="d428f-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="d428f-162">完成邮箱移动的时间取决于邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="d428f-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="d428f-163">如果客户密钥尚未在72小时后从分配新的 DEP 中完全加密邮箱，请与 Microsoft 支持部门联系以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="d428f-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="d428f-164">New-moverequest cmdlet 不再可用于本地邮箱移动。</span><span class="sxs-lookup"><span data-stu-id="d428f-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="d428f-165">有关详细信息，请参阅本次 [通知](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 。</span><span class="sxs-lookup"><span data-stu-id="d428f-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="d428f-166">验证 SharePoint Online、OneDrive for Business 和团队文件的加密是否已完成</span><span class="sxs-lookup"><span data-stu-id="d428f-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="d428f-167">通过运行 SPODataEncryptionPolicy cmdlet 检查加密状态，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d428f-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="d428f-168">此 cmdlet 的输出包括：</span><span class="sxs-lookup"><span data-stu-id="d428f-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="d428f-169">主键的 URI。</span><span class="sxs-lookup"><span data-stu-id="d428f-169">The URI of the primary key.</span></span>

- <span data-ttu-id="d428f-170">辅助密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="d428f-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="d428f-171">地理位置的加密状态。</span><span class="sxs-lookup"><span data-stu-id="d428f-171">The encryption status for the geo.</span></span> <span data-ttu-id="d428f-172">可能的状态包括：</span><span class="sxs-lookup"><span data-stu-id="d428f-172">Possible states include:</span></span>

  - <span data-ttu-id="d428f-173">未**注册：** 尚未应用客户密钥加密。</span><span class="sxs-lookup"><span data-stu-id="d428f-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="d428f-174">**注册：** 客户密钥加密已应用，并且您的文件正在被加密。</span><span class="sxs-lookup"><span data-stu-id="d428f-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="d428f-175">如果正在注册 geo 的密钥，还会显示有关 geo 中的多少个网站的完成百分比的信息，以便您可以监视加密进度。</span><span class="sxs-lookup"><span data-stu-id="d428f-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="d428f-176">**注册：** 客户密钥加密已应用，并且所有网站中的所有文件均已加密。</span><span class="sxs-lookup"><span data-stu-id="d428f-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="d428f-177">**滚动：** 正在进行密钥滚动。</span><span class="sxs-lookup"><span data-stu-id="d428f-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="d428f-178">如果正在滚动 geo 的键，则还会显示有关已完成密钥滚动操作的网站百分比的信息，以便您可以监视进度。</span><span class="sxs-lookup"><span data-stu-id="d428f-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="d428f-179">从邮箱中取消分配 DEP</span><span class="sxs-lookup"><span data-stu-id="d428f-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="d428f-180">您可以使用 "设置邮箱 PowerShell" cmdlet 从邮箱中取消分配 DEP，并将设置 `DataEncryptionPolicy` 为 `$NULL` 。</span><span class="sxs-lookup"><span data-stu-id="d428f-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="d428f-181">运行此 cmdlet 取消分配当前分配的 DEP，并使用与默认 Microsoft 管理密钥关联的 DEP reencrypts 邮箱。</span><span class="sxs-lookup"><span data-stu-id="d428f-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="d428f-182">无法取消分配 Microsoft 托管密钥使用的 DEP。</span><span class="sxs-lookup"><span data-stu-id="d428f-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="d428f-183">如果不想使用 Microsoft 托管密钥，可以为邮箱分配另一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="d428f-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="d428f-184">若要使用设置邮箱 PowerShell cmdlet 从邮箱中取消分配 DEP，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d428f-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="d428f-185">使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d428f-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d428f-186">运行 "设置邮箱" cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d428f-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="d428f-187">废除你的密钥并启动数据清除路径过程</span><span class="sxs-lookup"><span data-stu-id="d428f-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="d428f-188">您可以控制所有根项（包括可用性密钥）的吊销。</span><span class="sxs-lookup"><span data-stu-id="d428f-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="d428f-189">客户密钥为您提供管理法规要求的退出规划方面的控制权。</span><span class="sxs-lookup"><span data-stu-id="d428f-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="d428f-190">如果您决定撤销密钥以清除数据并退出服务，则在数据清除过程完成后，服务将删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d428f-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="d428f-191">Microsoft 365 审核并验证数据清除路径。</span><span class="sxs-lookup"><span data-stu-id="d428f-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="d428f-192">有关详细信息，请参阅 [服务信任门户](https://servicetrust.microsoft.com/)上提供的 SSAE 18 SOC 2 报告。</span><span class="sxs-lookup"><span data-stu-id="d428f-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="d428f-193">此外，Microsoft 建议采用以下文档：</span><span class="sxs-lookup"><span data-stu-id="d428f-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="d428f-194">Microsoft 云中的金融机构风险评估和合规性指南</span><span class="sxs-lookup"><span data-stu-id="d428f-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="d428f-195">O365 退出规划注意事项</span><span class="sxs-lookup"><span data-stu-id="d428f-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="d428f-196">不同服务之间的数据清除路径略有不同。</span><span class="sxs-lookup"><span data-stu-id="d428f-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d428f-197">吊销客户密钥和 Exchange Online 和 Skype for business 的可用性密钥</span><span class="sxs-lookup"><span data-stu-id="d428f-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d428f-198">启动 Exchange Online 和 Skype for business 的数据清除路径时，请在 DEP 上设置永久的数据清除请求。</span><span class="sxs-lookup"><span data-stu-id="d428f-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="d428f-199">这样做会永久删除为其分配了该 DEP 的邮箱中的加密数据。</span><span class="sxs-lookup"><span data-stu-id="d428f-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="d428f-200">由于您一次只能对一个 DEP 运行 PowerShell cmdlet，因此请考虑先将一个 DEP 分配给所有邮箱，然后再启动数据清除路径。</span><span class="sxs-lookup"><span data-stu-id="d428f-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="d428f-201">请勿使用数据清除路径删除邮箱的子集。</span><span class="sxs-lookup"><span data-stu-id="d428f-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="d428f-202">此过程仅适用于正在退出该服务的客户。</span><span class="sxs-lookup"><span data-stu-id="d428f-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="d428f-203">若要启动数据清除路径，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d428f-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="d428f-204">从 Azure 密钥保管库中删除 "O365 Exchange Online" 的包装和解包权限。</span><span class="sxs-lookup"><span data-stu-id="d428f-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="d428f-205">在您的组织中使用具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d428f-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="d428f-206">对于包含要删除的邮箱的每个 DEP，请运行 [DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="d428f-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="d428f-207">如果该命令失败，请确保已从 Azure Key Vault 中的两个密钥中删除了 Exchange Online 权限，如本任务前面所述。</span><span class="sxs-lookup"><span data-stu-id="d428f-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="d428f-208">使用 DataEncryptionPolicy cmdlet 设置 PermanentDataPurgeRequested 开关后，您将无法再将此 DEP 分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="d428f-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="d428f-209">请联系 Microsoft 支持部门并请求数据清除 eDocument。</span><span class="sxs-lookup"><span data-stu-id="d428f-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="d428f-210">在你请求时，Microsoft 会向你发送法律文档以确认和授权数据删除。</span><span class="sxs-lookup"><span data-stu-id="d428f-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="d428f-211">您组织中在 FastTrack 提供的审批者注册的人员需要对此文档进行签名。</span><span class="sxs-lookup"><span data-stu-id="d428f-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="d428f-212">通常情况下，这是公司中有权代表你的组织签署文书工作的行政或其他指定人员。</span><span class="sxs-lookup"><span data-stu-id="d428f-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="d428f-213">在你的代表签署法律文档后，通常通过 eDoc 签名) 将其返回到 Microsoft (。</span><span class="sxs-lookup"><span data-stu-id="d428f-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="d428f-214">一旦 Microsoft 收到法律文档，Microsoft 将运行 cmdlet 以触发数据清除，这会先删除策略，将邮箱标记为永久删除，然后删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d428f-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="d428f-215">数据清除过程完成后，Exchange Online 中的数据将被清除，不可恢复，且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="d428f-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="d428f-216">吊销客户密钥和 SharePoint Online、OneDrive for Business 和团队文件的可用性密钥</span><span class="sxs-lookup"><span data-stu-id="d428f-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="d428f-217">若要启动 SharePoint Online、OneDrive for Business 和团队文件的数据清除路径，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d428f-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="d428f-218">吊销 Azure Key Vault 访问权限。</span><span class="sxs-lookup"><span data-stu-id="d428f-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="d428f-219">所有密钥保管库管理员必须同意撤销访问权限。</span><span class="sxs-lookup"><span data-stu-id="d428f-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="d428f-220">您不会删除 SharePoint Online 的 Azure Key Vault。</span><span class="sxs-lookup"><span data-stu-id="d428f-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="d428f-221">主要电子仓库可在多个 SharePoint Online 租户和 DEPs 之间共享。</span><span class="sxs-lookup"><span data-stu-id="d428f-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="d428f-222">请与 Microsoft 联系以删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d428f-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="d428f-223">当你与 Microsoft 联系删除可用性密钥时，我们会向你发送法律文档。</span><span class="sxs-lookup"><span data-stu-id="d428f-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="d428f-224">您组织中在 FastTrack 提供的审批者注册的人员需要对此文档进行签名。</span><span class="sxs-lookup"><span data-stu-id="d428f-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="d428f-225">通常情况下，这是公司中有权代表你的组织签署文书工作的行政或其他指定人员。</span><span class="sxs-lookup"><span data-stu-id="d428f-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="d428f-226">在你的代表签署法律文档后，通常通过 eDoc 签名) 将其返回到 Microsoft (。</span><span class="sxs-lookup"><span data-stu-id="d428f-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="d428f-227">在 Microsoft 收到法律文档后，我们将运行 cmdlet 以触发数据清除，这将对租户密钥、网站密钥和所有单个文档的密钥执行加密删除，irrevocably 破坏密钥层次结构。</span><span class="sxs-lookup"><span data-stu-id="d428f-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="d428f-228">数据清除 cmdlet 完成后，你的数据已被清除。</span><span class="sxs-lookup"><span data-stu-id="d428f-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d428f-229">相关文章</span><span class="sxs-lookup"><span data-stu-id="d428f-229">Related articles</span></span>

- [<span data-ttu-id="d428f-230">使用客户密钥进行服务加密</span><span class="sxs-lookup"><span data-stu-id="d428f-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="d428f-231">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="d428f-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="d428f-232">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="d428f-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="d428f-233">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="d428f-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="d428f-234">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="d428f-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="d428f-235">服务加密</span><span class="sxs-lookup"><span data-stu-id="d428f-235">Service Encryption</span></span>](office-365-service-encryption.md)
