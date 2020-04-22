---
title: 滚动或旋转客户密钥或可用性密钥
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
description: 了解如何滚动存储在 Azure Key Vault （与客户密钥一起使用）中存储的客户根键。 服务包括 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队文件。
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633639"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="c7f10-104">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="c7f10-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="c7f10-105">当您的安全或合规性要求规定必须滚动密钥时，仅滚动与客户密钥配合使用的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="c7f10-106">此外，请勿删除与策略关联的或与之相关联的任何密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="c7f10-107">在滚动键时，会使用以前的密钥对内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="c7f10-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="c7f10-108">例如，虽然活动邮箱将被频繁地重新加密，但非活动邮箱、断开连接和已禁用邮箱仍可以使用以前的密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="c7f10-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="c7f10-109">SharePoint Online 执行用于还原和恢复目的的内容备份，因此可能仍有存档的内容使用旧密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="c7f10-110">关于滚动可用性密钥</span><span class="sxs-lookup"><span data-stu-id="c7f10-110">About rolling the availability key</span></span>

<span data-ttu-id="c7f10-111">Microsoft 不会向客户公开对可用性密钥的直接控制。</span><span class="sxs-lookup"><span data-stu-id="c7f10-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="c7f10-112">例如，您只能在 Azure Key Vault 中滚动（旋转）您拥有的密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="c7f10-113">Microsoft 365 按内部定义的计划对可用性密钥进行回滚。</span><span class="sxs-lookup"><span data-stu-id="c7f10-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="c7f10-114">没有面向客户的服务级别协议（SLA），这些密钥将会回滚。</span><span class="sxs-lookup"><span data-stu-id="c7f10-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="c7f10-115">Microsoft 365 在自动、非手动过程中使用 Microsoft 365 服务代码旋转可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="c7f10-116">Microsoft 管理员可能会启动滚动过程。</span><span class="sxs-lookup"><span data-stu-id="c7f10-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="c7f10-117">使用自动机制对密钥进行滚动，而无需直接访问密钥存储。</span><span class="sxs-lookup"><span data-stu-id="c7f10-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="c7f10-118">无法为 Microsoft 管理员预配对可用性密钥机密存储的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c7f10-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="c7f10-119">可用性密钥滚动利用用于最初生成密钥的相同机制。</span><span class="sxs-lookup"><span data-stu-id="c7f10-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="c7f10-120">有关可用性密钥的详细信息，请参阅[了解可用性密钥](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="c7f10-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7f10-121">客户可以通过创建新的 DEP 来有效地滚动 Exchange Online 和 Skype for business 可用性密钥，因为为您创建的每个 DEP 生成唯一的可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="c7f10-122">SharePoint Online、OneDrive for Business 和团队文件的可用性密钥在林级别存在，并在 DEPs 和客户之间共享，这意味着仅在 Microsoft 内部定义的计划中进行滚动。</span><span class="sxs-lookup"><span data-stu-id="c7f10-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="c7f10-123">若要降低在每次创建新的 DEP 时不滚动可用性密钥的风险，SharePoint、OneDrive 和团队滚动租户中间密钥（TIK），每次创建新的 DEP 时，都会按客户根密钥和可用性密钥包装每个密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="c7f10-124">请求要滚动的每个现有根密钥的新版本</span><span class="sxs-lookup"><span data-stu-id="c7f10-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="c7f10-125">在滚动某个键时，将请求现有项的新版本。</span><span class="sxs-lookup"><span data-stu-id="c7f10-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="c7f10-126">若要请求现有密钥的新版本，请使用相同的 cmdlet （ [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)），其语法与您在第一个位置创建密钥时使用的语法相同。</span><span class="sxs-lookup"><span data-stu-id="c7f10-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="c7f10-127">在完成了与数据加密策略（DEP）关联的任何键的滚动后，请运行另一个 cmdlet，以确保客户密钥开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="c7f10-128">在每个 Azure Key Vault （AKV）中执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="c7f10-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="c7f10-129">例如：</span><span class="sxs-lookup"><span data-stu-id="c7f10-129">For example:</span></span>

1. <span data-ttu-id="c7f10-130">使用 Azure PowerShell 登录到你的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="c7f10-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="c7f10-131">有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="c7f10-131">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="c7f10-132">运行 AzKeyVaultKey cmdlet，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c7f10-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="c7f10-133">在此示例中，由于在**contoso-O365EX-** O365EX 保管库中存在名为**Contoso-VaultA1-Key001**的键，因此 cmdlet 会创建新版本的密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-133">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** exists in the **Contoso-O365EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="c7f10-134">此操作将保留密钥的版本历史记录中的以前的密钥版本。</span><span class="sxs-lookup"><span data-stu-id="c7f10-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="c7f10-135">您需要以前的密钥版本来解密它仍加密的数据。</span><span class="sxs-lookup"><span data-stu-id="c7f10-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="c7f10-136">在完成所有与 DEP 相关的键的滚动后，请运行额外的 cmdlet，以确保客户密钥开始使用新密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="c7f10-137">以下各节更详细地介绍了 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c7f10-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="c7f10-138">更新 Exchange Online 和 Skype for business 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="c7f10-138">Update the Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="c7f10-139">当您滚动与 Exchange Online 和 Skype for business 使用的 DEP 相关联的任何 Azure Key Vault 密钥时，您必须更新 DEP 以指向新密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-139">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="c7f10-140">这不会旋转可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-140">This does not rotate the availability key.</span></span>

<span data-ttu-id="c7f10-141">若要指示客户密钥使用新密钥加密邮箱，请运行 DataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c7f10-141">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="c7f10-142">在 Azure PowerShell 中运行 DataEncryptionPolicy cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c7f10-142">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   <span data-ttu-id="c7f10-143">在72小时内，与此 DEP 相关联的活动邮箱将使用新密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="c7f10-143">Within 72 hours, the active mailboxes associated with this DEP become encrypted with the new key.</span></span>

2. <span data-ttu-id="c7f10-144">若要检查邮箱的 DataEncryptionPolicyID 属性的值，请按照[确定分配给邮箱的 DEP](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c7f10-144">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="c7f10-145">一旦服务应用了更新的密钥，此属性的值就会更改。</span><span class="sxs-lookup"><span data-stu-id="c7f10-145">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="c7f10-146">更新 SharePoint Online、OneDrive for Business 和团队文件的客户密钥</span><span class="sxs-lookup"><span data-stu-id="c7f10-146">Update the Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="c7f10-147">SharePoint Online 仅允许您一次滚动一个项。</span><span class="sxs-lookup"><span data-stu-id="c7f10-147">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="c7f10-148">如果要将密钥存储库中的两个密钥一起滚动，请等待第一个操作完成。</span><span class="sxs-lookup"><span data-stu-id="c7f10-148">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="c7f10-149">Microsoft 建议您错开操作以避免此问题。</span><span class="sxs-lookup"><span data-stu-id="c7f10-149">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="c7f10-150">当您滚动与 SharePoint Online 和 OneDrive for Business 使用的 DEP 相关联的任何 Azure Key Vault 密钥时，您必须更新 DEP 以指向新密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-150">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="c7f10-151">这不会旋转可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="c7f10-151">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="c7f10-152">运行 SPODataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c7f10-152">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="c7f10-153">虽然此 cmdlet 启动 SharePoint Online 和 OneDrive for business 的密钥滚动操作，但操作不会立即完成。</span><span class="sxs-lookup"><span data-stu-id="c7f10-153">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="c7f10-154">若要查看密钥滚动操作的进度，请运行 SPODataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c7f10-154">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="c7f10-155">相关文章</span><span class="sxs-lookup"><span data-stu-id="c7f10-155">Related articles</span></span>

- [<span data-ttu-id="c7f10-156">使用 Office 365 的客户密钥进行服务加密</span><span class="sxs-lookup"><span data-stu-id="c7f10-156">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c7f10-157">设置 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="c7f10-157">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="c7f10-158">管理 Office 365 的客户密钥</span><span class="sxs-lookup"><span data-stu-id="c7f10-158">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c7f10-159">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="c7f10-159">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)
