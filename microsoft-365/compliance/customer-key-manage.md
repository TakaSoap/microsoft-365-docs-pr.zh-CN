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
description: 设置客户密钥后，了解如何通过还原 AKV 密钥来管理它，以及如何管理权限和数据加密策略。
ms.openlocfilehash: 8f55667254ce7f5cbd9d4de274623ca4a3c4aa9d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909944"
---
# <a name="manage-customer-key"></a><span data-ttu-id="7a149-103">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="7a149-103">Manage Customer Key</span></span>

<span data-ttu-id="7a149-104">为 Office 365 设置客户密钥后，可以管理密钥，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="7a149-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="7a149-105">在相关主题中了解有关客户密钥的信息。</span><span class="sxs-lookup"><span data-stu-id="7a149-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="7a149-106">还原 Azure 密钥保管库密钥</span><span class="sxs-lookup"><span data-stu-id="7a149-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="7a149-107">在执行还原之前，请使用软删除提供的恢复功能。</span><span class="sxs-lookup"><span data-stu-id="7a149-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="7a149-108">必须启用软删除，才能使用客户密钥的所有密钥。</span><span class="sxs-lookup"><span data-stu-id="7a149-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="7a149-109">软删除的作用与回收站类似，允许恢复最多 90 天，而无需还原。</span><span class="sxs-lookup"><span data-stu-id="7a149-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="7a149-110">只有在极端或异常情况下（例如，密钥或密钥保管库丢失）才需要还原。</span><span class="sxs-lookup"><span data-stu-id="7a149-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="7a149-111">如果必须还原密钥以用于客户密钥，在 Azure PowerShell 中，Restore-AzureKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7a149-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="7a149-112">例如：</span><span class="sxs-lookup"><span data-stu-id="7a149-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="7a149-113">如果密钥保管库已包含同名密钥，则还原操作将失败。</span><span class="sxs-lookup"><span data-stu-id="7a149-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="7a149-114">Restore-AzKeyVaultKey还原密钥的所有密钥版本和元数据，包括密钥名称。</span><span class="sxs-lookup"><span data-stu-id="7a149-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="7a149-115">管理密钥保管库权限</span><span class="sxs-lookup"><span data-stu-id="7a149-115">Manage key vault permissions</span></span>

<span data-ttu-id="7a149-116">可以使用多个 cmdlet 查看密钥保管库权限，并在必要时删除密钥保管库权限。</span><span class="sxs-lookup"><span data-stu-id="7a149-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="7a149-117">例如，当员工离开团队时，可能需要删除权限。</span><span class="sxs-lookup"><span data-stu-id="7a149-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="7a149-118">对于其中每个任务，你将使用 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7a149-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="7a149-119">有关 Azure Powershell 的信息，请参阅 [Azure PowerShell 概述](/powershell/azure/)。</span><span class="sxs-lookup"><span data-stu-id="7a149-119">For information about Azure Powershell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="7a149-120">若要查看密钥保管库权限，请运行 Get-AzKeyVault cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a149-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="7a149-121">例如：</span><span class="sxs-lookup"><span data-stu-id="7a149-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="7a149-122">若要删除管理员的权限，请运行以下Remove-AzKeyVaultAccessPolicy cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7a149-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="7a149-123">例如：</span><span class="sxs-lookup"><span data-stu-id="7a149-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="7a149-124">使用客户密钥 (数据加密策略) 数据加密策略</span><span class="sxs-lookup"><span data-stu-id="7a149-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="7a149-125">客户密钥在不同的服务之间以不同方式处理 DEP。</span><span class="sxs-lookup"><span data-stu-id="7a149-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="7a149-126">例如，您可以为不同的服务创建不同数量的 DESP。</span><span class="sxs-lookup"><span data-stu-id="7a149-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="7a149-127">**Exchange Online 和 Skype for Business：** 您可以创建最多 50 个 DESP。</span><span class="sxs-lookup"><span data-stu-id="7a149-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="7a149-128">有关说明，请参阅 [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="7a149-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="7a149-129">**SharePoint Online、OneDrive for Business 和 Teams 文件：** DEP 适用于一个地理位置（也称为地理位置） _的数据_。</span><span class="sxs-lookup"><span data-stu-id="7a149-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="7a149-130">如果使用 Office 365 的多地理位置功能，可以为每个地理位置创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="7a149-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="7a149-131">如果不使用多地理位置，可以创建一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="7a149-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="7a149-132">通常，在设置客户密钥时创建 DEP。</span><span class="sxs-lookup"><span data-stu-id="7a149-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="7a149-133">有关说明，请参阅 [为每个 SharePoint Online](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)和 OneDrive for Business (DEP) 创建数据加密策略。</span><span class="sxs-lookup"><span data-stu-id="7a149-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7a149-134">查看为 Exchange Online 和 Skype for Business 创建的 DESP</span><span class="sxs-lookup"><span data-stu-id="7a149-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7a149-135">若要查看使用 Get-DataEncryptionPolicy PowerShell cmdlet 为 Exchange Online 和 Skype for Business 创建的所有 DESP 的列表，请完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="7a149-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="7a149-136">使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7a149-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7a149-137">若要返回组织的所有 DEP，请运行不带Get-DataEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a149-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="7a149-138">有关此 cmdlet Get-DataEncryptionPolicy，请参阅 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="7a149-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="7a149-139">在将邮箱迁移到云之前分配 DEP</span><span class="sxs-lookup"><span data-stu-id="7a149-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="7a149-140">分配 DEP 时，Microsoft 365 在迁移过程中使用分配的 DEP 对邮箱内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="7a149-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="7a149-141">此过程比迁移邮箱、分配 DEP，然后等待加密发生（可能需要数小时或数天）更有效。</span><span class="sxs-lookup"><span data-stu-id="7a149-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="7a149-142">若要在将 DEP 迁移到 Office 365 之前将其分配给邮箱，请运行 Exchange Online PowerShell Set-MailUser cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7a149-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="7a149-143">使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7a149-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7a149-144">运行 Set-MailUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a149-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="7a149-145">其中 *，GeneralMailboxOrMailUserIdParameter* 指定邮箱 *，DataEncryptionPolicyIdParameter* 是 DEP 的 ID。</span><span class="sxs-lookup"><span data-stu-id="7a149-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="7a149-146">有关此 cmdlet Set-MailUser，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="7a149-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="7a149-147">确定分配给邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="7a149-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="7a149-148">若要确定分配给邮箱的 DEP，请使用 Get-MailboxStatistics cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a149-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="7a149-149">此 cmdlet 返回 GUID (的唯) 。</span><span class="sxs-lookup"><span data-stu-id="7a149-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="7a149-150">使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7a149-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="7a149-151">其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱，DataEncryptionPolicyID 返回 DEP 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="7a149-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="7a149-152">有关此 cmdlet Get-MailboxStatistics，请参阅 [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics)。</span><span class="sxs-lookup"><span data-stu-id="7a149-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="7a149-153">运行 Get-DataEncryptionPolicy cmdlet，查找邮箱分配到的 DEP 的友好名称。</span><span class="sxs-lookup"><span data-stu-id="7a149-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="7a149-154">其中 *GUID* 是上一步中 Get-MailboxStatistics cmdlet 返回的 GUID。</span><span class="sxs-lookup"><span data-stu-id="7a149-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="7a149-155">确认客户密钥已完成加密</span><span class="sxs-lookup"><span data-stu-id="7a149-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="7a149-156">无论是刚刚汇总了客户密钥、分配了新的 DEP 还是迁移了邮箱，请使用本节中的步骤确保加密完成。</span><span class="sxs-lookup"><span data-stu-id="7a149-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7a149-157">验证 Exchange Online 和 Skype for Business 的加密是否已完成</span><span class="sxs-lookup"><span data-stu-id="7a149-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7a149-158">加密邮箱可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="7a149-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="7a149-159">建议在更改 DEP 或首次向邮箱分配 DEP 后等待 72 小时，然后再尝试验证加密。</span><span class="sxs-lookup"><span data-stu-id="7a149-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="7a149-160">使用 Get-MailboxStatistics cmdlet 确定邮箱是否加密。</span><span class="sxs-lookup"><span data-stu-id="7a149-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="7a149-161">如果邮箱已加密，则 IsEncrypted 属性返回 **true** 值;如果邮箱未加密，则返回 **false** 值。</span><span class="sxs-lookup"><span data-stu-id="7a149-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="7a149-162">完成邮箱移动的时间取决于邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="7a149-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="7a149-163">如果自分配新 DEP 起 72 小时后客户密钥尚未完全加密邮箱，请联系 Microsoft 支持人员寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="7a149-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="7a149-164">此New-MoveRequest cmdlet 不再可用于本地邮箱移动。</span><span class="sxs-lookup"><span data-stu-id="7a149-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="7a149-165">有关其他 [信息，](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 请参阅此通知。</span><span class="sxs-lookup"><span data-stu-id="7a149-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="7a149-166">验证 SharePoint Online、OneDrive for Business 和 Teams 文件的加密是否完成</span><span class="sxs-lookup"><span data-stu-id="7a149-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="7a149-167">按如下所示运行 Get-SPODataEncryptionPolicy cmdlet 检查加密状态：</span><span class="sxs-lookup"><span data-stu-id="7a149-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="7a149-168">此 cmdlet 的输出包括：</span><span class="sxs-lookup"><span data-stu-id="7a149-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="7a149-169">主键的 URI。</span><span class="sxs-lookup"><span data-stu-id="7a149-169">The URI of the primary key.</span></span>

- <span data-ttu-id="7a149-170">辅助密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="7a149-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="7a149-171">地理位置的加密状态。</span><span class="sxs-lookup"><span data-stu-id="7a149-171">The encryption status for the geo.</span></span> <span data-ttu-id="7a149-172">可能状态包括：</span><span class="sxs-lookup"><span data-stu-id="7a149-172">Possible states include:</span></span>

  - <span data-ttu-id="7a149-173">**注销：** 尚未应用客户密钥加密。</span><span class="sxs-lookup"><span data-stu-id="7a149-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="7a149-174">**注册：** 已应用客户密钥加密，你的文件正在加密中。</span><span class="sxs-lookup"><span data-stu-id="7a149-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="7a149-175">如果地理位置的密钥正在注册，还将显示有关地理位置中完成的网站百分比的信息，以便你可以监视加密进度。</span><span class="sxs-lookup"><span data-stu-id="7a149-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="7a149-176">**已注册：** 已应用客户密钥加密，并且所有网站中的所有文件已加密。</span><span class="sxs-lookup"><span data-stu-id="7a149-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="7a149-177">**滚动：** 密钥滚动正在进行中。</span><span class="sxs-lookup"><span data-stu-id="7a149-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="7a149-178">如果地理位置的密钥正在滚动，你还将看到有关完成密钥滚动操作的网站百分比的信息，以便你可以监视进度。</span><span class="sxs-lookup"><span data-stu-id="7a149-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="7a149-179">从邮箱取消分配 DEP</span><span class="sxs-lookup"><span data-stu-id="7a149-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="7a149-180">使用 Set-mailbox PowerShell cmdlet 从邮箱取消分配 DEP，将 `DataEncryptionPolicy` 设置为 `$NULL` 。</span><span class="sxs-lookup"><span data-stu-id="7a149-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="7a149-181">运行此 cmdlet 可取消分配当前分配的 DEP，然后使用与默认 Microsoft 托管密钥关联的 DEP 重新加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="7a149-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="7a149-182">不能取消分配 Microsoft 托管密钥使用的 DEP。</span><span class="sxs-lookup"><span data-stu-id="7a149-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="7a149-183">如果您不想使用 Microsoft 托管密钥，您可以为邮箱分配另一个 DEP。</span><span class="sxs-lookup"><span data-stu-id="7a149-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="7a149-184">若要使用 PowerShell cmdlet 从邮箱取消Set-Mailbox DEP，请完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="7a149-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="7a149-185">使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7a149-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7a149-186">运行 Set-Mailbox cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a149-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="7a149-187">撤销密钥并开始数据清除路径过程</span><span class="sxs-lookup"><span data-stu-id="7a149-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="7a149-188">控制所有根密钥（包括可用性密钥）的吊销。</span><span class="sxs-lookup"><span data-stu-id="7a149-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="7a149-189">客户密钥可控制法规要求的退出计划方面。</span><span class="sxs-lookup"><span data-stu-id="7a149-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="7a149-190">如果决定撤销密钥以清除数据并退出服务，则服务会在数据清除过程完成后删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="7a149-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="7a149-191">Microsoft 365 审核并验证数据清除路径。</span><span class="sxs-lookup"><span data-stu-id="7a149-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="7a149-192">有关详细信息，请参阅服务信任门户上提供的 SSAE 18 SOC 2 [报告](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="7a149-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="7a149-193">此外，Microsoft 建议以下文档：</span><span class="sxs-lookup"><span data-stu-id="7a149-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="7a149-194">Microsoft 云中金融机构的风险评估和合规性指南</span><span class="sxs-lookup"><span data-stu-id="7a149-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="7a149-195">O365 退出规划注意事项</span><span class="sxs-lookup"><span data-stu-id="7a149-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="7a149-196">不同服务之间的数据清除路径略有不同。</span><span class="sxs-lookup"><span data-stu-id="7a149-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="7a149-197">撤销你的客户密钥和 Exchange Online 和 Skype for Business 的可用性密钥</span><span class="sxs-lookup"><span data-stu-id="7a149-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="7a149-198">为 Exchange Online 和 Skype for Business 启动数据清除路径时，会在 DEP 上设置永久数据清除请求。</span><span class="sxs-lookup"><span data-stu-id="7a149-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="7a149-199">这样做会永久删除分配给 DEP 的邮箱中的加密数据。</span><span class="sxs-lookup"><span data-stu-id="7a149-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="7a149-200">由于一次只能对一个 DEP 运行 PowerShell cmdlet，因此在启动数据清除路径之前，请考虑将单个 DEP 重新分配给所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="7a149-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="7a149-201">请勿使用数据清除路径删除邮箱的子集。</span><span class="sxs-lookup"><span data-stu-id="7a149-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="7a149-202">此过程仅适用于退出服务的客户。</span><span class="sxs-lookup"><span data-stu-id="7a149-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="7a149-203">若要启动数据清除路径，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7a149-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="7a149-204">从 Azure 密钥保管库删除"O365 Exchange Online"的自动换行和取消打包权限。</span><span class="sxs-lookup"><span data-stu-id="7a149-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="7a149-205">使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7a149-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="7a149-206">对于包含要删除的邮箱的每个 DEP，运行 [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7a149-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="7a149-207">如果命令失败，请确保你已删除 Azure 密钥保管库中的两个密钥的 Exchange Online 权限，如此任务前面所述。</span><span class="sxs-lookup"><span data-stu-id="7a149-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="7a149-208">使用 Set-DataEncryptionPolicy cmdlet 设置 PermanentDataPurgeRequested 开关后，将无法再将此 DEP 分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="7a149-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="7a149-209">联系 Microsoft 支持人员并请求"数据清除"eDocument。</span><span class="sxs-lookup"><span data-stu-id="7a149-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="7a149-210">根据你的请求，Microsoft 会向您发送一份法律文档，以确认和授权删除数据。</span><span class="sxs-lookup"><span data-stu-id="7a149-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="7a149-211">在载入期间在 FastTrack 产品/服务中注册为审批者的组织人员需要签署此文档。</span><span class="sxs-lookup"><span data-stu-id="7a149-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="7a149-212">通常，这是公司中经法律授权代表你的组织签署书面材料的公司主管或其他指定人员。</span><span class="sxs-lookup"><span data-stu-id="7a149-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="7a149-213">在代表签署法律文档后，通常 (eDoc 签名文件将该文档) 。</span><span class="sxs-lookup"><span data-stu-id="7a149-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="7a149-214">Microsoft 收到法律文档后，Microsoft 将运行 cmdlet 触发数据清除，首先删除策略，将邮箱标记为永久删除，然后删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="7a149-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="7a149-215">数据清除过程完成后，数据已被清除，Exchange Online 无法访问数据，并且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="7a149-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="7a149-216">撤销 SharePoint Online、OneDrive for Business 和 Teams 文件的客户密钥和可用性密钥</span><span class="sxs-lookup"><span data-stu-id="7a149-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="7a149-217">若要启动 SharePoint Online、OneDrive for Business 和 Teams 文件的数据清除路径，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7a149-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="7a149-218">撤销 Azure 密钥保管库访问权限。</span><span class="sxs-lookup"><span data-stu-id="7a149-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="7a149-219">所有密钥保管库管理员都必须同意撤销访问权限。</span><span class="sxs-lookup"><span data-stu-id="7a149-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="7a149-220">不要删除 SharePoint Online 的 Azure 密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="7a149-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="7a149-221">密钥保管库可以在多个 SharePoint Online 租户和 DESP 之间共享。</span><span class="sxs-lookup"><span data-stu-id="7a149-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="7a149-222">请与 Microsoft 联系以删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="7a149-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="7a149-223">当你联系 Microsoft 以删除可用性密钥时，我们将向您发送一份法律文档。</span><span class="sxs-lookup"><span data-stu-id="7a149-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="7a149-224">在载入期间在 FastTrack 产品/服务中注册为审批者的组织人员需要签署此文档。</span><span class="sxs-lookup"><span data-stu-id="7a149-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="7a149-225">通常，这是公司中法律授权代表你的组织签署书面材料的公司主管或其他指定人员。</span><span class="sxs-lookup"><span data-stu-id="7a149-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="7a149-226">在代表签署法律文档后，通常 (eDoc 签名文件将该文档) 。</span><span class="sxs-lookup"><span data-stu-id="7a149-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="7a149-227">Microsoft 收到法律文档后，我们运行 cmdlet 触发数据清除，以加密方式删除租户密钥、站点密钥以及所有单独每文档密钥，从而不可撤销地破坏密钥层次结构。</span><span class="sxs-lookup"><span data-stu-id="7a149-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="7a149-228">数据清除 cmdlet 完成后，数据即被清除。</span><span class="sxs-lookup"><span data-stu-id="7a149-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7a149-229">相关文章</span><span class="sxs-lookup"><span data-stu-id="7a149-229">Related articles</span></span>

- [<span data-ttu-id="7a149-230">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="7a149-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="7a149-231">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="7a149-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="7a149-232">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="7a149-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="7a149-233">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="7a149-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="7a149-234">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="7a149-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="7a149-235">服务加密</span><span class="sxs-lookup"><span data-stu-id="7a149-235">Service Encryption</span></span>](office-365-service-encryption.md)