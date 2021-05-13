---
title: 管理客户密钥
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
description: 设置客户密钥后，了解如何通过还原 AKV 密钥、管理权限以及创建和分配数据加密策略来管理它。
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345054"
---
# <a name="manage-customer-key"></a><span data-ttu-id="3681e-103">管理客户密钥</span><span class="sxs-lookup"><span data-stu-id="3681e-103">Manage Customer Key</span></span>

<span data-ttu-id="3681e-104">为用户设置客户密钥Office 365，需要在 DEP 策略中创建并分配一个或多个 (加密) 。</span><span class="sxs-lookup"><span data-stu-id="3681e-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="3681e-105">分配 DESP 后，你可以管理密钥，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="3681e-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="3681e-106">在相关主题中了解有关客户密钥的信息。</span><span class="sxs-lookup"><span data-stu-id="3681e-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="3681e-107">创建一个 DEP 以用于所有租户用户的多个工作负载</span><span class="sxs-lookup"><span data-stu-id="3681e-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="3681e-108">开始之前，请确保已完成设置 Customer 所需的任务。</span><span class="sxs-lookup"><span data-stu-id="3681e-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="3681e-109">有关信息，请参阅 [设置客户密钥](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="3681e-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="3681e-110">若要创建 DEP，您需要在安装期间获取的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3681e-111">有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI。](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3681e-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="3681e-112">若要创建多工作负荷 DEP，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="3681e-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="3681e-113">在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，在 Windows PowerShell 窗口中连接到 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3681e-114">若要创建 DEP，请使用 New-M365DataAtRestEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="3681e-115">其中：</span><span class="sxs-lookup"><span data-stu-id="3681e-115">Where:</span></span>

   - <span data-ttu-id="3681e-116">*PolicyName* 是你想要用于策略的名称。</span><span class="sxs-lookup"><span data-stu-id="3681e-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="3681e-117">名称不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="3681e-117">Names can't contain spaces.</span></span> <span data-ttu-id="3681e-118">例如，Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="3681e-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="3681e-119">*KeyVaultURI1* 是策略中第一个密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="3681e-120">例如，<https://contosoWestUSvault1.vault.azure.net/keys/Key_01>。</span><span class="sxs-lookup"><span data-stu-id="3681e-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="3681e-121">*KeyVaultURI2* 是策略中第二个密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="3681e-122">例如，<https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>。</span><span class="sxs-lookup"><span data-stu-id="3681e-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="3681e-123">用逗号和空格分隔这两个 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="3681e-124">*策略* 说明是策略的用户友好说明，有助于你记住策略用于什么。</span><span class="sxs-lookup"><span data-stu-id="3681e-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="3681e-125">可以在说明中包括空格。</span><span class="sxs-lookup"><span data-stu-id="3681e-125">You can include spaces in the description.</span></span> <span data-ttu-id="3681e-126">例如，"租户中所有用户的多个工作负荷的根策略"。</span><span class="sxs-lookup"><span data-stu-id="3681e-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="3681e-127">示例：</span><span class="sxs-lookup"><span data-stu-id="3681e-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="3681e-128">分配多工作负荷策略</span><span class="sxs-lookup"><span data-stu-id="3681e-128">Assign multi-workload policy</span></span>

<span data-ttu-id="3681e-129">使用 cmdlet 分配 deP Set-M365DataAtRestEncryptionPolicyAssignment cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="3681e-130">分配策略后，Microsoft 365 DEP 中标识的密钥加密数据。</span><span class="sxs-lookup"><span data-stu-id="3681e-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="3681e-131">其中 *PolicyName* 是策略的名称。</span><span class="sxs-lookup"><span data-stu-id="3681e-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="3681e-132">例如，Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="3681e-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="3681e-133">示例：</span><span class="sxs-lookup"><span data-stu-id="3681e-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="3681e-134">创建一个 DEP 以用于Exchange Online邮箱</span><span class="sxs-lookup"><span data-stu-id="3681e-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="3681e-135">开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。</span><span class="sxs-lookup"><span data-stu-id="3681e-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3681e-136">有关信息，请参阅 [设置客户密钥](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="3681e-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="3681e-137">通过远程连接到具有远程连接Exchange Online完成Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3681e-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="3681e-138">DEP 与 Azure Key Vault 中存储的一组密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="3681e-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3681e-139">您将 DEP 分配给邮箱中的Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3681e-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="3681e-140">Microsoft 365将使用策略中标识的密钥加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="3681e-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="3681e-141">若要创建 DEP，您需要在安装期间获取的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3681e-142">有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI。](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3681e-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="3681e-143">请记住！</span><span class="sxs-lookup"><span data-stu-id="3681e-143">Remember!</span></span> <span data-ttu-id="3681e-144">创建 DEP 时，可以在两个不同的 Azure 密钥保管库中指定两个密钥。</span><span class="sxs-lookup"><span data-stu-id="3681e-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="3681e-145">在两个独立的 Azure 区域创建这些密钥以确保地理位置冗余。</span><span class="sxs-lookup"><span data-stu-id="3681e-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="3681e-146">若要创建用于邮箱的 DEP，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="3681e-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="3681e-147">在本地计算机上，使用在组织中具有全局管理员或 Exchange Online 管理员权限的工作或学校帐户，在 Exchange Online 窗口中连接到 Windows PowerShell [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3681e-148">若要创建 DEP，请通过New-DataEncryptionPolicy命令使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="3681e-149">其中：</span><span class="sxs-lookup"><span data-stu-id="3681e-149">Where:</span></span>

   - <span data-ttu-id="3681e-150">*PolicyName* 是你想要用于策略的名称。</span><span class="sxs-lookup"><span data-stu-id="3681e-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="3681e-151">名称不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="3681e-151">Names can't contain spaces.</span></span> <span data-ttu-id="3681e-152">例如，USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="3681e-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="3681e-153">*策略* 说明是策略的用户友好说明，有助于你记住策略用于什么。</span><span class="sxs-lookup"><span data-stu-id="3681e-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="3681e-154">可以在说明中包括空格。</span><span class="sxs-lookup"><span data-stu-id="3681e-154">You can include spaces in the description.</span></span> <span data-ttu-id="3681e-155">例如，"美国及其区域邮箱的根密钥"。</span><span class="sxs-lookup"><span data-stu-id="3681e-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="3681e-156">*KeyVaultURI1* 是策略中第一个密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="3681e-157">例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。</span><span class="sxs-lookup"><span data-stu-id="3681e-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="3681e-158">*KeyVaultURI2* 是策略中第二个密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="3681e-159">例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。</span><span class="sxs-lookup"><span data-stu-id="3681e-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="3681e-160">用逗号和空格分隔这两个 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="3681e-161">示例：</span><span class="sxs-lookup"><span data-stu-id="3681e-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="3681e-162">有关语法和参数的详细信息，请参阅 [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="3681e-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="3681e-163">将 DEP 分配给邮箱</span><span class="sxs-lookup"><span data-stu-id="3681e-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="3681e-164">使用 cmdlet 将 DEP Set-Mailbox邮箱。</span><span class="sxs-lookup"><span data-stu-id="3681e-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="3681e-165">分配策略后，Microsoft 365使用 DEP 中标识的密钥对邮箱进行加密。</span><span class="sxs-lookup"><span data-stu-id="3681e-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="3681e-166">其中 *MailboxIdParameter* 指定用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="3681e-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="3681e-167">有关此 cmdlet Set-Mailbox，请参阅 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="3681e-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="3681e-168">在混合环境中，您可以将 DEP 分配给同步到您的 Exchange Online 租户中的内部部署邮箱数据。</span><span class="sxs-lookup"><span data-stu-id="3681e-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="3681e-169">若要为此同步的邮箱数据分配 DEP，请使用 Set-MailUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="3681e-170">有关混合环境中邮箱数据详细信息，请参阅使用混合新式验证的 Outlook [for iOS 和 Android 本地邮箱](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。</span><span class="sxs-lookup"><span data-stu-id="3681e-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="3681e-171">其中 *MailUserIdParameter* 指定邮件 (也称为启用邮件的用户) 。</span><span class="sxs-lookup"><span data-stu-id="3681e-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="3681e-172">有关此 cmdlet Set-MailUser，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="3681e-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3681e-173">创建 DEP 以用于 SharePoint Online、OneDrive for Business 和 Teams 文件</span><span class="sxs-lookup"><span data-stu-id="3681e-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3681e-174">开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。</span><span class="sxs-lookup"><span data-stu-id="3681e-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="3681e-175">有关信息，请参阅 [设置客户密钥](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="3681e-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="3681e-176">若要为 SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥，可以使用 Windows PowerShell 远程连接到 SharePoint Online 来完成Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3681e-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="3681e-177">将 DEP 与 Azure Key Vault 中存储的一组密钥关联。</span><span class="sxs-lookup"><span data-stu-id="3681e-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="3681e-178">将 DEP 应用于一个地理位置（也称为地理位置）的所有数据。</span><span class="sxs-lookup"><span data-stu-id="3681e-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="3681e-179">如果你使用多地理位置功能Office 365，你可以为每个地理位置创建一个 DEP，并能够为每个地理位置使用不同的密钥。</span><span class="sxs-lookup"><span data-stu-id="3681e-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="3681e-180">如果不使用多地理位置，可以在组织中创建一个 DEP 以用于 SharePoint Online、OneDrive for Business 和 Teams 文件。</span><span class="sxs-lookup"><span data-stu-id="3681e-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="3681e-181">Microsoft 365使用 DEP 中标识的密钥加密该地理位置的数据。</span><span class="sxs-lookup"><span data-stu-id="3681e-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="3681e-182">若要创建 DEP，您需要在安装期间获取的密钥保管库 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="3681e-183">有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI。](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)</span><span class="sxs-lookup"><span data-stu-id="3681e-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="3681e-184">请记住！</span><span class="sxs-lookup"><span data-stu-id="3681e-184">Remember!</span></span> <span data-ttu-id="3681e-185">创建 DEP 时，可以在两个不同的 Azure 密钥保管库中指定两个密钥。</span><span class="sxs-lookup"><span data-stu-id="3681e-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="3681e-186">在两个独立的 Azure 区域创建这些密钥以确保地理位置冗余。</span><span class="sxs-lookup"><span data-stu-id="3681e-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="3681e-187">若要创建 DEP，你需要使用 SharePoint Online 远程Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3681e-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="3681e-188">在本地计算机上，使用在组织中具有全局管理员权限的工作或学校帐户，连接 SharePoint Online [PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="3681e-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="3681e-189">在命令行Microsoft Office SharePoint Online命令行管理程序中，Register-SPODataEncryptionPolicy cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3681e-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="3681e-190">示例：</span><span class="sxs-lookup"><span data-stu-id="3681e-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="3681e-191">注册 DEP 时，加密从地理位置数据开始。</span><span class="sxs-lookup"><span data-stu-id="3681e-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="3681e-192">加密可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="3681e-192">Encryption can take some time.</span></span> <span data-ttu-id="3681e-193">有关使用此参数的信息，请参阅 [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="3681e-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="3681e-194">查看为邮箱创建的 EXCHANGE ONLINE报告</span><span class="sxs-lookup"><span data-stu-id="3681e-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="3681e-195">若要查看为邮箱创建的所有 DESP 的列表，请使用 Get-DataEncryptionPolicy PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="3681e-196">使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3681e-197">若要返回组织的所有 DEP，请运行不带Get-DataEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="3681e-198">有关此 cmdlet Get-DataEncryptionPolicy，请参阅 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="3681e-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="3681e-199">在将邮箱迁移到云之前分配 DEP</span><span class="sxs-lookup"><span data-stu-id="3681e-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="3681e-200">分配 DEP 时，Microsoft 365迁移期间使用分配的 DEP 对邮箱内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="3681e-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="3681e-201">此过程比迁移邮箱、分配 DEP，然后等待加密发生（可能需要数小时或数天）更有效。</span><span class="sxs-lookup"><span data-stu-id="3681e-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="3681e-202">若要在将 DEP 迁移到邮箱之前将其分配给Office 365，请运行 Set-MailUser PowerShell 中的 Exchange Online cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3681e-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="3681e-203">使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3681e-204">运行 Set-MailUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="3681e-205">其中 *，GeneralMailboxOrMailUserIdParameter* 指定邮箱 *，DataEncryptionPolicyIdParameter* 是 DEP 的 ID。</span><span class="sxs-lookup"><span data-stu-id="3681e-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="3681e-206">有关此 cmdlet Set-MailUser，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="3681e-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="3681e-207">确定分配给邮箱的 DEP</span><span class="sxs-lookup"><span data-stu-id="3681e-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="3681e-208">若要确定分配给邮箱的 DEP，请使用 Get-MailboxStatistics cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="3681e-209">此 cmdlet 返回 GUID (的唯) 。</span><span class="sxs-lookup"><span data-stu-id="3681e-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="3681e-210">使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="3681e-211">其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱，DataEncryptionPolicyID 返回 DEP 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3681e-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="3681e-212">有关此 cmdlet Get-MailboxStatistics，请参阅 [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics)。</span><span class="sxs-lookup"><span data-stu-id="3681e-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="3681e-213">运行 Get-DataEncryptionPolicy cmdlet，查找邮箱分配到的 DEP 的友好名称。</span><span class="sxs-lookup"><span data-stu-id="3681e-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="3681e-214">其中 *GUID* 是上一步中 Get-MailboxStatistics cmdlet 返回的 GUID。</span><span class="sxs-lookup"><span data-stu-id="3681e-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="3681e-215">确认客户密钥已完成加密</span><span class="sxs-lookup"><span data-stu-id="3681e-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="3681e-216">无论是已汇总客户密钥、分配了新的 DEP 还是迁移了邮箱，请使用本节中的步骤确保加密完成。</span><span class="sxs-lookup"><span data-stu-id="3681e-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="3681e-217">验证加密是否Exchange Online邮箱</span><span class="sxs-lookup"><span data-stu-id="3681e-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="3681e-218">加密邮箱可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="3681e-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="3681e-219">对于首次加密，邮箱还必须从一个数据库完全移动到另一个数据库，服务才能加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="3681e-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="3681e-220">使用 Get-MailboxStatistics cmdlet 确定邮箱是否加密。</span><span class="sxs-lookup"><span data-stu-id="3681e-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="3681e-221">如果邮箱已加密，IsEncrypted 属性将返回 **true** 值;如果邮箱未加密，则返回 **false** 值。</span><span class="sxs-lookup"><span data-stu-id="3681e-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="3681e-222">完成邮箱移动的时间取决于第一次为其分配 DEP 的邮箱数以及邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="3681e-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="3681e-223">如果邮箱自分配 DEP 起一周后未加密，请与 Microsoft 联系。</span><span class="sxs-lookup"><span data-stu-id="3681e-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="3681e-224">此New-MoveRequest cmdlet 不再可用于本地邮箱移动。</span><span class="sxs-lookup"><span data-stu-id="3681e-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="3681e-225">有关其他 [信息，](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 请参阅此通知。</span><span class="sxs-lookup"><span data-stu-id="3681e-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3681e-226">验证加密是否SharePoint Online、OneDrive for Business和Teams文件</span><span class="sxs-lookup"><span data-stu-id="3681e-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3681e-227">按如下所示运行 Get-SPODataEncryptionPolicy cmdlet 检查加密状态：</span><span class="sxs-lookup"><span data-stu-id="3681e-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="3681e-228">此 cmdlet 的输出包括：</span><span class="sxs-lookup"><span data-stu-id="3681e-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="3681e-229">主键的 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-229">The URI of the primary key.</span></span>

- <span data-ttu-id="3681e-230">辅助密钥的 URI。</span><span class="sxs-lookup"><span data-stu-id="3681e-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="3681e-231">地理位置的加密状态。</span><span class="sxs-lookup"><span data-stu-id="3681e-231">The encryption status for the geo.</span></span> <span data-ttu-id="3681e-232">可能状态包括：</span><span class="sxs-lookup"><span data-stu-id="3681e-232">Possible states include:</span></span>

  - <span data-ttu-id="3681e-233">**注销：** 尚未应用客户密钥加密。</span><span class="sxs-lookup"><span data-stu-id="3681e-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="3681e-234">**注册：** 已应用客户密钥加密，你的文件正在加密中。</span><span class="sxs-lookup"><span data-stu-id="3681e-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="3681e-235">如果地理位置的密钥正在注册，还将显示有关地理位置中完成的网站百分比的信息，以便你可以监视加密进度。</span><span class="sxs-lookup"><span data-stu-id="3681e-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="3681e-236">**已注册：** 已应用客户密钥加密，并且所有网站中的所有文件已加密。</span><span class="sxs-lookup"><span data-stu-id="3681e-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="3681e-237">**滚动：** 密钥滚动正在进行中。</span><span class="sxs-lookup"><span data-stu-id="3681e-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="3681e-238">如果地理位置的密钥正在滚动，你还将看到有关完成密钥滚动操作的网站百分比的信息，以便你可以监视进度。</span><span class="sxs-lookup"><span data-stu-id="3681e-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="3681e-239">获取有关用于多个工作负载的 DEP 的详细信息</span><span class="sxs-lookup"><span data-stu-id="3681e-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="3681e-240">若要获取有关已创建用于多个工作负荷的所有 DESP 的详细信息，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3681e-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="3681e-241">在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，在 Windows PowerShell 窗口中连接到 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="3681e-242">若要返回组织中所有多工作负荷 DEP 的列表，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="3681e-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="3681e-243">要返回有关特定 DEP 的详细信息，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="3681e-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="3681e-244">此示例返回名为"Contoso_Global"的 DEP 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3681e-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="3681e-245">获取多工作负载 DEP 分配信息</span><span class="sxs-lookup"><span data-stu-id="3681e-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="3681e-246">若要了解当前分配给租户的 DEP，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="3681e-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="3681e-247">在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，在 Windows PowerShell 窗口中连接到 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3681e-248">键入此命令。</span><span class="sxs-lookup"><span data-stu-id="3681e-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="3681e-249">禁用多工作负荷 DEP</span><span class="sxs-lookup"><span data-stu-id="3681e-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="3681e-250">在禁用多工作负荷 DEP 之前，请从租户中的工作负荷中取消分配 DEP。</span><span class="sxs-lookup"><span data-stu-id="3681e-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="3681e-251">若要禁用用于多个工作负荷的 DEP，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3681e-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="3681e-252">在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，在 Windows PowerShell 窗口中连接到 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="3681e-253">运行 Set-M365DataAtRestEncryptionPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="3681e-254">其中 *PolicyName* 是策略的名称或唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="3681e-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="3681e-255">例如，Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="3681e-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="3681e-256">示例：</span><span class="sxs-lookup"><span data-stu-id="3681e-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="3681e-257">还原 Azure 密钥保管库密钥</span><span class="sxs-lookup"><span data-stu-id="3681e-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="3681e-258">在执行还原之前，请使用软删除提供的恢复功能。</span><span class="sxs-lookup"><span data-stu-id="3681e-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="3681e-259">必须启用软删除，才能使用客户密钥的所有密钥。</span><span class="sxs-lookup"><span data-stu-id="3681e-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="3681e-260">软删除的作用与回收站类似，允许恢复最多 90 天，而无需还原。</span><span class="sxs-lookup"><span data-stu-id="3681e-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="3681e-261">只有在极端或异常情况下（例如，密钥或密钥保管库丢失）才需要还原。</span><span class="sxs-lookup"><span data-stu-id="3681e-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="3681e-262">如果必须还原用于客户密钥的密钥，Azure PowerShell运行 Restore-AzureKeyVaultKey cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3681e-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="3681e-263">例如：</span><span class="sxs-lookup"><span data-stu-id="3681e-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="3681e-264">如果密钥保管库已包含同名密钥，则还原操作将失败。</span><span class="sxs-lookup"><span data-stu-id="3681e-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="3681e-265">Restore-AzKeyVaultKey还原密钥的所有密钥版本和元数据，包括密钥名称。</span><span class="sxs-lookup"><span data-stu-id="3681e-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="3681e-266">管理密钥保管库权限</span><span class="sxs-lookup"><span data-stu-id="3681e-266">Manage key vault permissions</span></span>

<span data-ttu-id="3681e-267">可以使用多个 cmdlet 查看密钥保管库权限，并在必要时删除密钥保管库权限。</span><span class="sxs-lookup"><span data-stu-id="3681e-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="3681e-268">例如，当员工离开团队时，可能需要删除权限。</span><span class="sxs-lookup"><span data-stu-id="3681e-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="3681e-269">对于其中每个任务，将使用Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3681e-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="3681e-270">有关 Azure PowerShell 的信息，请参阅[Azure PowerShell 概述](/powershell/azure/)。</span><span class="sxs-lookup"><span data-stu-id="3681e-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="3681e-271">若要查看密钥保管库权限，请运行 Get-AzKeyVault cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="3681e-272">例如：</span><span class="sxs-lookup"><span data-stu-id="3681e-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="3681e-273">若要删除管理员的权限，请运行以下Remove-AzKeyVaultAccessPolicy cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3681e-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="3681e-274">例如：</span><span class="sxs-lookup"><span data-stu-id="3681e-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="3681e-275">从客户密钥回滚到 Microsoft 托管密钥</span><span class="sxs-lookup"><span data-stu-id="3681e-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="3681e-276">如果需要还原到 Microsoft 管理的密钥，可以。</span><span class="sxs-lookup"><span data-stu-id="3681e-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="3681e-277">当你离开时，你的数据会使用每个工作负荷支持的默认加密重新加密。</span><span class="sxs-lookup"><span data-stu-id="3681e-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="3681e-278">例如，Exchange Online Microsoft 管理的密钥支持默认加密。</span><span class="sxs-lookup"><span data-stu-id="3681e-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3681e-279">载出与数据清除不同。</span><span class="sxs-lookup"><span data-stu-id="3681e-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="3681e-280">数据清除会永久加密删除组织的数据，Microsoft 365，但无法进行载出。</span><span class="sxs-lookup"><span data-stu-id="3681e-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="3681e-281">无法对多个工作负荷策略执行数据清除。</span><span class="sxs-lookup"><span data-stu-id="3681e-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="3681e-282">如果你决定不使用客户密钥分配多工作负荷 DEP，则需要通过从客户密钥请求"退出"来联系 Microsoft 支持人员。</span><span class="sxs-lookup"><span data-stu-id="3681e-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="3681e-283">要求支持团队针对客户密钥Microsoft 365提出服务请求。</span><span class="sxs-lookup"><span data-stu-id="3681e-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="3681e-284">如果你有任何问题 m365-ck@service.microsoft.com 联系他们。</span><span class="sxs-lookup"><span data-stu-id="3681e-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="3681e-285">如果不希望再使用邮箱级别 DEPS 加密单个邮箱，可以取消分配所有邮箱的邮箱级别 DEP。</span><span class="sxs-lookup"><span data-stu-id="3681e-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="3681e-286">若要取消分配邮箱 DEP，请使用 Set-Mailbox PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="3681e-287">使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3681e-288">运行 Set-Mailbox cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3681e-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="3681e-289">运行此 cmdlet 可取消分配当前分配的 DEP，然后使用与默认 Microsoft 托管密钥关联的 DEP 重新加密邮箱。</span><span class="sxs-lookup"><span data-stu-id="3681e-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="3681e-290">不能取消分配 Microsoft 托管密钥使用的 DEP。</span><span class="sxs-lookup"><span data-stu-id="3681e-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="3681e-291">如果您不想使用 Microsoft 管理的密钥，您可以为邮箱分配另一个客户密钥 DEP。</span><span class="sxs-lookup"><span data-stu-id="3681e-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="3681e-292">撤销密钥并开始数据清除路径过程</span><span class="sxs-lookup"><span data-stu-id="3681e-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="3681e-293">控制所有根密钥（包括可用性密钥）的吊销。</span><span class="sxs-lookup"><span data-stu-id="3681e-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="3681e-294">客户密钥可控制法规要求的退出计划方面。</span><span class="sxs-lookup"><span data-stu-id="3681e-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="3681e-295">如果决定撤销密钥以清除数据并退出服务，则服务会在数据清除过程完成后删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="3681e-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="3681e-296">分配给各个邮箱的客户密钥 DEP 支持此功能。</span><span class="sxs-lookup"><span data-stu-id="3681e-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="3681e-297">Microsoft 365审核并验证数据清除路径。</span><span class="sxs-lookup"><span data-stu-id="3681e-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="3681e-298">有关详细信息，请参阅服务信任门户上提供的 SSAE 18 SOC 2 [报告](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="3681e-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="3681e-299">此外，Microsoft 建议以下文档：</span><span class="sxs-lookup"><span data-stu-id="3681e-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="3681e-300">Microsoft 云中金融机构的风险评估和合规性指南</span><span class="sxs-lookup"><span data-stu-id="3681e-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="3681e-301">O365 退出规划注意事项</span><span class="sxs-lookup"><span data-stu-id="3681e-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="3681e-302">客户密钥不支持清除多Microsoft 365 DEP。</span><span class="sxs-lookup"><span data-stu-id="3681e-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="3681e-303">多工作负载 DEP 用于跨所有租户用户的多个工作负载加密数据。</span><span class="sxs-lookup"><span data-stu-id="3681e-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="3681e-304">清除此类 DEP 将导致无法访问来自多个工作负载的数据。</span><span class="sxs-lookup"><span data-stu-id="3681e-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="3681e-305">如果决定完全退出Microsoft 365服务，可以按记录的过程采取租户删除路径。</span><span class="sxs-lookup"><span data-stu-id="3681e-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="3681e-306">了解如何 [删除 Azure Active Directoy 中的租户](/azure/active-directory/enterprise-users/directory-delete-howto)。</span><span class="sxs-lookup"><span data-stu-id="3681e-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="3681e-307">吊销你的客户密钥和用于Exchange Online Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3681e-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="3681e-308">当您启动数据清除路径的 Exchange Online Skype for Business，您将在 DEP 上设置永久数据清除请求。</span><span class="sxs-lookup"><span data-stu-id="3681e-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="3681e-309">这样做会永久删除分配给 DEP 的邮箱中的加密数据。</span><span class="sxs-lookup"><span data-stu-id="3681e-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="3681e-310">由于一次只能对一个 DEP 运行 PowerShell cmdlet，因此在启动数据清除路径之前，请考虑将单个 DEP 重新分配给所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="3681e-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="3681e-311">请勿使用数据清除路径删除邮箱的子集。</span><span class="sxs-lookup"><span data-stu-id="3681e-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="3681e-312">此过程仅适用于退出服务的客户。</span><span class="sxs-lookup"><span data-stu-id="3681e-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="3681e-313">若要启动数据清除路径，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3681e-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="3681e-314">从 Azure 密钥保管库中删除"O365 Exchange Online的自动换行和取消打包权限。</span><span class="sxs-lookup"><span data-stu-id="3681e-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="3681e-315">使用在组织中拥有全局管理员权限的工作或学校帐户连接到[Exchange Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="3681e-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="3681e-316">对于包含要删除的邮箱的每个 DEP，运行 [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3681e-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="3681e-317">如果命令失败，请确保你已删除 Azure 密钥保管库中Exchange Online Azure 密钥保管库中的两个密钥的权限，如此任务前面所述。</span><span class="sxs-lookup"><span data-stu-id="3681e-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="3681e-318">使用 Set-DataEncryptionPolicy cmdlet 设置 PermanentDataPurgeRequested 开关后，将无法再将此 DEP 分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="3681e-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="3681e-319">联系 Microsoft 支持人员并请求"数据清除"eDocument。</span><span class="sxs-lookup"><span data-stu-id="3681e-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="3681e-320">根据你的请求，Microsoft 会向您发送一份法律文档，以确认和授权删除数据。</span><span class="sxs-lookup"><span data-stu-id="3681e-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="3681e-321">在载入期间在 FastTrack 产品/服务中注册为审批者的组织人员需要签署此文档。</span><span class="sxs-lookup"><span data-stu-id="3681e-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="3681e-322">通常，这是公司中经法律授权代表你的组织签署书面材料的公司主管或其他指定人员。</span><span class="sxs-lookup"><span data-stu-id="3681e-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="3681e-323">在代表签署法律文档后，通常 (eDoc 签名文件将该文档) 。</span><span class="sxs-lookup"><span data-stu-id="3681e-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="3681e-324">Microsoft 收到法律文档后，Microsoft 将运行 cmdlet 触发数据清除，首先删除策略，将邮箱标记为永久删除，然后删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="3681e-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="3681e-325">数据清除过程完成后，数据已被清除、无法访问Exchange Online且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="3681e-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="3681e-326">吊销你的客户密钥和 SharePoint Online、OneDrive for Business 和 Teams 密钥</span><span class="sxs-lookup"><span data-stu-id="3681e-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="3681e-327">若要启动 SharePoint Online、OneDrive for Business 和 Teams 文件的数据清除路径，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3681e-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="3681e-328">撤销 Azure 密钥保管库访问权限。</span><span class="sxs-lookup"><span data-stu-id="3681e-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="3681e-329">所有密钥保管库管理员都必须同意撤销访问权限。</span><span class="sxs-lookup"><span data-stu-id="3681e-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="3681e-330">不要删除适用于 SharePoint Online 的 Azure 密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="3681e-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="3681e-331">密钥保管库可以在多个 SharePoint Online 租户和 DESP 之间共享。</span><span class="sxs-lookup"><span data-stu-id="3681e-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="3681e-332">请与 Microsoft 联系以删除可用性密钥。</span><span class="sxs-lookup"><span data-stu-id="3681e-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="3681e-333">当你联系 Microsoft 以删除可用性密钥时，我们将向您发送一份法律文档。</span><span class="sxs-lookup"><span data-stu-id="3681e-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="3681e-334">在载入期间在 FastTrack 产品/服务中注册为审批者的组织人员需要签署此文档。</span><span class="sxs-lookup"><span data-stu-id="3681e-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="3681e-335">通常，这是公司中法律授权代表你的组织签署书面材料的公司主管或其他指定人员。</span><span class="sxs-lookup"><span data-stu-id="3681e-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="3681e-336">在代表签署法律文档后，通常 (eDoc 签名文件将该文档) 。</span><span class="sxs-lookup"><span data-stu-id="3681e-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="3681e-337">Microsoft 收到法律文档后，我们运行 cmdlet 触发数据清除，以加密方式删除租户密钥、站点密钥以及所有单独每文档密钥，从而不可撤销地破坏密钥层次结构。</span><span class="sxs-lookup"><span data-stu-id="3681e-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="3681e-338">数据清除 cmdlet 完成后，数据即被清除。</span><span class="sxs-lookup"><span data-stu-id="3681e-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3681e-339">相关文章</span><span class="sxs-lookup"><span data-stu-id="3681e-339">Related articles</span></span>

- [<span data-ttu-id="3681e-340">使用客户密钥执行服务加密</span><span class="sxs-lookup"><span data-stu-id="3681e-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="3681e-341">了解可用性密钥</span><span class="sxs-lookup"><span data-stu-id="3681e-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="3681e-342">设置客户密钥</span><span class="sxs-lookup"><span data-stu-id="3681e-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="3681e-343">滚动或旋转客户密钥或可用性密钥</span><span class="sxs-lookup"><span data-stu-id="3681e-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="3681e-344">客户密码箱</span><span class="sxs-lookup"><span data-stu-id="3681e-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="3681e-345">服务加密</span><span class="sxs-lookup"><span data-stu-id="3681e-345">Service Encryption</span></span>](office-365-service-encryption.md)