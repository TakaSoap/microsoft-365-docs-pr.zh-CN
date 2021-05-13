---
title: 滚动或旋转客户密钥或可用性密钥
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何滚动存储在 Azure Key Vault 中与客户密钥一同使用的客户根密钥。 服务包括Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件。
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345114"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="d33c9-104">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="d33c9-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="d33c9-105">只有在安全或合规性要求规定必须滚动密钥时，才能滚动用于客户密钥的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="d33c9-106">此外，不要删除任何与策略关联的密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="d33c9-107">在滚动密钥时，将会有使用之前密钥加密的内容。</span><span class="sxs-lookup"><span data-stu-id="d33c9-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="d33c9-108">例如，虽然活动邮箱将频繁重新加密，但非活动、断开连接和禁用的邮箱仍可能会使用以前的密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="d33c9-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="d33c9-109">SharePoint联机执行内容备份以用于还原和恢复，因此可能仍使用旧密钥存档内容。</span><span class="sxs-lookup"><span data-stu-id="d33c9-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="d33c9-110">关于滚动可用性密钥</span><span class="sxs-lookup"><span data-stu-id="d33c9-110">About rolling the availability key</span></span>

<span data-ttu-id="d33c9-111">Microsoft 不会将可用性密钥的直接控制公开给客户。</span><span class="sxs-lookup"><span data-stu-id="d33c9-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="d33c9-112">例如，你只能滚动 (旋转) 你在 Azure Key Vault 中拥有密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="d33c9-113">Microsoft 365在内部定义的计划上滚动可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="d33c9-114">对于这些关键滚动，没有面向客户的服务级别协议 (SLA) SLA。</span><span class="sxs-lookup"><span data-stu-id="d33c9-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="d33c9-115">Microsoft 365在自动化的非手动Microsoft 365使用服务代码来轮换可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="d33c9-116">Microsoft 管理员可以启动滚动过程。</span><span class="sxs-lookup"><span data-stu-id="d33c9-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="d33c9-117">使用自动机制回滚密钥，无需直接访问密钥存储。</span><span class="sxs-lookup"><span data-stu-id="d33c9-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="d33c9-118">对可用性密钥密钥存储的访问未预配给 Microsoft 管理员。</span><span class="sxs-lookup"><span data-stu-id="d33c9-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="d33c9-119">可用性密钥滚动利用最初生成密钥所使用的相同机制。</span><span class="sxs-lookup"><span data-stu-id="d33c9-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="d33c9-120">有关可用性密钥详细信息，请参阅 [了解可用性密钥](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="d33c9-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d33c9-121">Exchange Online一Skype for Business DEP 的客户可以有效回滚所有可用性密钥，因为会为创建的每个 DEP 生成唯一的可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="d33c9-122">SharePoint Online、OneDrive for Business 和 Teams 文件的可用性密钥存在于林级别，并且跨 DEP 和客户共享，这意味着滚动仅在 Microsoft 内部定义的日程安排中发生。</span><span class="sxs-lookup"><span data-stu-id="d33c9-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="d33c9-123">为了降低每次新建 DEP、SharePoint、OneDrive 和 Teams 滚动租户中间密钥 (TIK) （客户根密钥和可用性密钥包装的密钥）每次创建一个新的 DEP 时不滚动可用性密钥的风险。</span><span class="sxs-lookup"><span data-stu-id="d33c9-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="d33c9-124">请求要滚动的每个现有根密钥的新版本</span><span class="sxs-lookup"><span data-stu-id="d33c9-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="d33c9-125">在滚动密钥时，将请求现有密钥的新版本。</span><span class="sxs-lookup"><span data-stu-id="d33c9-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="d33c9-126">若要请求现有密钥的新版本，请使用与最初创建密钥时相同的 cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)语法。</span><span class="sxs-lookup"><span data-stu-id="d33c9-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="d33c9-127">完成滚动与数据加密策略 (DEP) 关联的任何密钥后，运行另一个 cmdlet 以确保客户密钥开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="d33c9-128">在每个 Azure 密钥保管库和 AKV (中) 。</span><span class="sxs-lookup"><span data-stu-id="d33c9-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="d33c9-129">例如：</span><span class="sxs-lookup"><span data-stu-id="d33c9-129">For example:</span></span>

1. <span data-ttu-id="d33c9-130">使用帐户登录 Azure Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d33c9-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="d33c9-131">有关说明，请参阅[使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="d33c9-131">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="d33c9-132">运行 Add-AzKeyVaultKey cmdlet，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="d33c9-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="d33c9-133">本示例中，由于 **名为 Contoso-CK-EX-NA-VaultA1-Key001** 的密钥存在于 **Contoso-CK-EX-NA-VaultA1** 保管库中，因此该 cmdlet 会创建该密钥的新版本。</span><span class="sxs-lookup"><span data-stu-id="d33c9-133">In this example, since a key named **Contoso-CK-EX-NA-VaultA1-Key001** exists in the **Contoso-CK-EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="d33c9-134">此操作在密钥的版本历史记录中保留以前的密钥版本。</span><span class="sxs-lookup"><span data-stu-id="d33c9-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="d33c9-135">您需要以前的密钥版本来解密它仍然加密的数据。</span><span class="sxs-lookup"><span data-stu-id="d33c9-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="d33c9-136">完成滚动与 DEP 关联的任何密钥后，运行额外的 cmdlet 以确保客户密钥开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="d33c9-137">以下各节更详细地介绍了 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d33c9-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-keys-for-multi-workload-deps"></a><span data-ttu-id="d33c9-138">更新多工作负荷 DEP 的密钥</span><span class="sxs-lookup"><span data-stu-id="d33c9-138">Update the keys for multi-workload DEPs</span></span>

<span data-ttu-id="d33c9-139">在滚动与用于多个工作负荷的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-139">When you roll either of the Azure Key Vault keys associated with a DEP used with multiple workloads, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="d33c9-140">此过程不会轮换可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-140">This process does not rotate the availability key.</span></span>

<span data-ttu-id="d33c9-141">若要指示客户密钥使用新密钥加密多个工作负载，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d33c9-141">To instruct Customer Key to use the new key to encrypt multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="d33c9-142">在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，在 Windows PowerShell 窗口中连接到 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d33c9-142">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="d33c9-143">运行 Set-M365DataAtRestEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d33c9-143">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

<span data-ttu-id="d33c9-144">其中 *PolicyName* 是策略的名称或唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="d33c9-144">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="d33c9-145">例如，Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="d33c9-145">For example, Contoso_Global.</span></span>

<span data-ttu-id="d33c9-146">示例：</span><span class="sxs-lookup"><span data-stu-id="d33c9-146">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a><span data-ttu-id="d33c9-147">更新 EXCHANGE ONLINE 的密钥</span><span class="sxs-lookup"><span data-stu-id="d33c9-147">Update the keys for Exchange Online DEPs</span></span>

<span data-ttu-id="d33c9-148">滚动与用于 Exchange Online 和 Skype for Business 的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-148">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="d33c9-149">这不会旋转可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-149">This does not rotate the availability key.</span></span>

<span data-ttu-id="d33c9-150">若要指示客户密钥使用新密钥加密邮箱，请Set-DataEncryptionPolicy cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d33c9-150">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="d33c9-151">在Set-DataEncryptionPolicy中运行 Azure PowerShell：</span><span class="sxs-lookup"><span data-stu-id="d33c9-151">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. <span data-ttu-id="d33c9-152">若要检查邮箱的 DataEncryptionPolicyID 属性的值，请使用De determine the [DEP assigned to a mailbox 中的步骤](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="d33c9-152">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="d33c9-153">此服务应用更新的密钥后，此属性的值将发生更改。</span><span class="sxs-lookup"><span data-stu-id="d33c9-153">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="d33c9-154">更新 SharePoint Online、OneDrive for Business 和 Teams 文件的密钥</span><span class="sxs-lookup"><span data-stu-id="d33c9-154">Update the keys for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="d33c9-155">SharePoint联机仅允许你一次滚动一个键。</span><span class="sxs-lookup"><span data-stu-id="d33c9-155">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="d33c9-156">如果要在密钥保管库中滚动这两个密钥，请等待第一个操作完成。</span><span class="sxs-lookup"><span data-stu-id="d33c9-156">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="d33c9-157">Microsoft 建议你错开操作，以避免此问题。</span><span class="sxs-lookup"><span data-stu-id="d33c9-157">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="d33c9-158">滚动与用于 SharePoint Online 和 OneDrive for Business 的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-158">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="d33c9-159">这不会旋转可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="d33c9-159">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="d33c9-160">运行 Update-SPODataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d33c9-160">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="d33c9-161">当此 cmdlet 启动 SharePoint Online 和 OneDrive for Business 键滚动操作时，该操作不会立即完成。</span><span class="sxs-lookup"><span data-stu-id="d33c9-161">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="d33c9-162">To see the progress of the key roll operation， run the Get-SPODataEncryptionPolicy cmdlet as follows：</span><span class="sxs-lookup"><span data-stu-id="d33c9-162">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="d33c9-163">相关文章</span><span class="sxs-lookup"><span data-stu-id="d33c9-163">Related articles</span></span>

- [<span data-ttu-id="d33c9-164">使用客户密钥进行服务加密Office 365</span><span class="sxs-lookup"><span data-stu-id="d33c9-164">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="d33c9-165">设置 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="d33c9-165">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="d33c9-166">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="d33c9-166">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="d33c9-167">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="d33c9-167">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)