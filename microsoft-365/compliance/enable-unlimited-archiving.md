---
title: 启用无限制存档 - 管理员帮助
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 对于管理员：了解如何启用自动扩展存档，这为用户提供了 Exchange Online 邮箱的无限存储空间。 您可以为整个组织或仅为特定用户启用自动扩展存档。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac5661ac43ed9c0f35eba20007f0c4c4406ebf20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927822"
---
# <a name="enable-unlimited-archiving---admin-help"></a><span data-ttu-id="c46a4-104">启用无限制存档 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="c46a4-104">Enable unlimited archiving - Admin Help</span></span>

<span data-ttu-id="c46a4-105">可以使用 Exchange Online 自动扩展存档功能为存档邮箱启用无限存储空间。</span><span class="sxs-lookup"><span data-stu-id="c46a4-105">You can use the Exchange Online auto-expanding archiving feature to enable unlimited storage space for archive mailboxes.</span></span> <span data-ttu-id="c46a4-106">启用自动扩展存档后，在接近存储限制时，会自动向用户的存档邮箱添加额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="c46a4-106">When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit.</span></span> <span data-ttu-id="c46a4-107">结果是邮箱存储容量不受限制。</span><span class="sxs-lookup"><span data-stu-id="c46a4-107">The result is unlimited mailbox storage capacity.</span></span> <span data-ttu-id="c46a4-108">您可以为组织中的每个人或只为特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-108">You can turn on auto-expanding archiving for everyone in your organization or just for specific users.</span></span> <span data-ttu-id="c46a4-109">有关自动扩展存档详细信息，请参阅 Overview [of unlimited archiving in Office 365](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c46a4-109">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-enable-auto-expanding-archiving"></a><span data-ttu-id="c46a4-110">启用自动扩展存档之前</span><span class="sxs-lookup"><span data-stu-id="c46a4-110">Before you enable auto-expanding archiving</span></span>

- <span data-ttu-id="c46a4-111">您必须是组织的全局管理员或 Exchange Online 组织中组织管理角色组的成员，才能为整个组织或特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-111">You have to be a global administrator in your organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users.</span></span> <span data-ttu-id="c46a4-112">或者，您必须是分配有"邮件收件人"角色的角色组的成员，才能为特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-112">Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>

- <span data-ttu-id="c46a4-113">必须启用用户的存档邮箱，然后才能启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-113">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving.</span></span> <span data-ttu-id="c46a4-114">必须为用户分配 Exchange Online 计划 2 许可证才能启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-114">A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox.</span></span> <span data-ttu-id="c46a4-115">如果为用户分配了 Exchange Online 计划 1 许可证，您必须为其分配单独的 Exchange Online Archiving 许可证才能启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-115">If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox.</span></span> <span data-ttu-id="c46a4-116">请参阅 [在安全与合规中心&存档邮箱](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="c46a4-116">See [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md).</span></span>

- <span data-ttu-id="c46a4-117">您还可以使用 PowerShell 启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-117">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="c46a4-118">有关 [可用于为](#more-information) 组织中所有用户启用存档邮箱的 PowerShell 命令的示例，请参阅详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="c46a4-118">See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span>

- <span data-ttu-id="c46a4-119">自动扩展存档还支持共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-119">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="c46a4-120">若要为共享邮箱启用存档，需要 Exchange Online 计划 2 许可证或 Exchange Online 计划 1 Exchange Online Archiving许可证。</span><span class="sxs-lookup"><span data-stu-id="c46a4-120">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

- <span data-ttu-id="c46a4-121">自动扩展存档可防止恢复或还原非 [活动邮箱](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="c46a4-121">Auto-expanding archiving prevents you from recovering or restoring an [inactive mailbox](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes).</span></span> <span data-ttu-id="c46a4-122">这意味着，如果为邮箱启用自动扩展存档，并且邮箱在以后变为非活动状态，将无法通过将非活动邮箱 [ (](recover-an-inactive-mailbox.md) 转换为活动邮箱) 或通过将内容合并到现有邮箱) 来将其 [还原到](restore-an-inactive-mailbox.md) (。</span><span class="sxs-lookup"><span data-stu-id="c46a4-122">That means if you enable auto-expanding archiving for a mailbox and the mailbox is made inactive at a later date, you won't be able to [recover the inactive mailbox](recover-an-inactive-mailbox.md) (by converting it to an active mailbox) or [restore it](restore-an-inactive-mailbox.md) (by merging the contents to an existing mailbox).</span></span> <span data-ttu-id="c46a4-123">如果在非活动邮箱上启用了自动扩展存档，则恢复数据的唯一方法就是使用 Microsoft 365 合规中心中的内容搜索工具将数据从邮箱导出并导入另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-123">If auto-expanding archiving is enabled on an inactive mailbox, the only way to recover data is by using the Content search tool in the Microsoft 365 compliance center to export the data from the mailbox and import to another mailbox.</span></span> <span data-ttu-id="c46a4-124">有关详细信息，请参阅 Overview of inactive mailboxes 中的"非活动邮箱和自动扩展 [存档"部分](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives)。</span><span class="sxs-lookup"><span data-stu-id="c46a4-124">For more information, see the "Inactive mailboxes and auto-expanding archives" section in [Overview of inactive mailboxes](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives).</span></span>

- <span data-ttu-id="c46a4-125">You can't use the Exchange admin center or the Security & Compliance Center to enable auto-expanding archiving.</span><span class="sxs-lookup"><span data-stu-id="c46a4-125">You can't use the Exchange admin center or the Security & Compliance Center to enable auto-expanding archiving.</span></span> <span data-ttu-id="c46a4-126">您必须使用 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c46a4-126">You have to use Exchange Online PowerShell.</span></span> <span data-ttu-id="c46a4-127">若要使用远程 PowerShell 连接到 Exchange Online 组织，请参阅[连接到 Exchange Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="c46a4-127">To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="c46a4-128">为整个组织启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="c46a4-128">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="c46a4-129">您可以为整个组织启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-129">You can enable auto-expanding archiving for your entire organization.</span></span> <span data-ttu-id="c46a4-130">启用后，将为现有用户邮箱和已创建的新用户邮箱启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-130">After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created.</span></span> <span data-ttu-id="c46a4-131">创建用户邮箱时，请确保启用用户的主存档邮箱，以便自动扩展存档功能适用于新的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-131">When you create user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature works for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="c46a4-132">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="c46a4-132">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="c46a4-133">在 Exchange Online PowerShell 中运行以下命令，为整个组织启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-133">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="c46a4-134">为特定用户启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="c46a4-134">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="c46a4-135">您可以仅为特定用户启用存档，而不是为组织每个用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-135">Instead of enabling auto-expanding archiving for every user in your organization, you can enable it only for specific users.</span></span> <span data-ttu-id="c46a4-136">您可以这样做，因为只有部分用户可能需要较大的存档存储容量。</span><span class="sxs-lookup"><span data-stu-id="c46a4-136">You might do this because only some users might have a need for a large archive storage capacity.</span></span>
  
<span data-ttu-id="c46a4-137">当您为特定用户启用自动扩展存档，并将该用户的邮箱置于保留状态或分配到保留策略时，将进行以下两种配置更改：</span><span class="sxs-lookup"><span data-stu-id="c46a4-137">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to a retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="c46a4-138">用户的主存档邮箱的存储配额增加了 10 GB， (从 100 GB 增加到 110 GB) 。</span><span class="sxs-lookup"><span data-stu-id="c46a4-138">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB).</span></span> <span data-ttu-id="c46a4-139">存档警告配额也增加了 10 GB， (从 90 GB 增加到 100 GB) 。</span><span class="sxs-lookup"><span data-stu-id="c46a4-139">The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>

- <span data-ttu-id="c46a4-140">用户主邮箱中"可恢复的项目"文件夹的存储配额增加了 10 GB (从 100 GB 增加到 110 GB) 。</span><span class="sxs-lookup"><span data-stu-id="c46a4-140">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB).</span></span> <span data-ttu-id="c46a4-141">"可恢复的项目"警告配额也增加了 10 GB， (从 90 GB 增加到 100 GB) 。</span><span class="sxs-lookup"><span data-stu-id="c46a4-141">The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span> <span data-ttu-id="c46a4-142">这些更改仅在邮箱置于保留状态或分配到保留策略时适用。</span><span class="sxs-lookup"><span data-stu-id="c46a4-142">These changes are applicable only if the mailbox in on hold or assigned to a retention policy.</span></span>

<span data-ttu-id="c46a4-143">添加此额外空间，以防止在设置自动扩展存档之前可能会发生的任何存储问题。</span><span class="sxs-lookup"><span data-stu-id="c46a4-143">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned.</span></span> <span data-ttu-id="c46a4-144">为整个  *组织启用*  自动扩展存档时，不会增加额外存储空间，如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="c46a4-144">Additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span>
  
1. [<span data-ttu-id="c46a4-145">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="c46a4-145">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="c46a4-146">在 Exchange Online PowerShell 中运行以下命令，为特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-146">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user.</span></span> <span data-ttu-id="c46a4-147">如前所述，必须先启用用户的存档邮箱 (主存档) 才能为该用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-147">As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> <span data-ttu-id="c46a4-148">在 Exchange 混合部署中，不能使用 **Enable-Mailbox -AutoExpandingArchive** 命令为主邮箱位于本地且存档邮箱为基于云的特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-148">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for a specific user whose primary mailbox is on-premises and whose archive mailbox is cloud-based.</span></span> <span data-ttu-id="c46a4-149">若要在 Exchange 混合部署中为基于云的存档邮箱启用自动扩展存档，您必须在 Exchange Online PowerShell 中运行 **Set-OrganizationConfig -AutoExpandingArchive** 命令，以启用整个组织的自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-149">To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization.</span></span> <span data-ttu-id="c46a4-150">如果用户的主邮箱和存档邮箱都基于云的，您可以使用 **Enable-Mailbox -AutoExpandingArchive** 命令为特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-150">If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span>
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="c46a4-151">验证是否已启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="c46a4-151">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="c46a4-152">若要验证是否为组织启用了自动扩展存档，请运行 Exchange Online PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="c46a4-152">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="c46a4-153">值  `True` 表示为组织启用了自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-153">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="c46a4-154">若要验证是否为特定用户启用了自动扩展存档，请运行 Exchange Online PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="c46a4-154">To verify that auto-expanding archiving is enabled for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="c46a4-155">值  `True` 表示为用户启用了自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-155">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span>
  
<span data-ttu-id="c46a4-156">若要确定是否为非活动邮箱启用自动扩展存档，请运行 Exchange Online PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="c46a4-156">To determine if auto-expanding archiving is enabled for inactive mailboxes, run the following command in Exchange Online PowerShell.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

<span data-ttu-id="c46a4-157">值 表示为非活动邮箱  `True` 启用了自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-157">A value of  `True` indicates that auto-expanding archiving is enabled for the inactive mailbox.</span></span> <span data-ttu-id="c46a4-158">值 `False` 表示未启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-158">A value of `False` indicates that auto-expanding archiving isn't enabled.</span></span>

<span data-ttu-id="c46a4-159">启用自动扩展存档后，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="c46a4-159">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="c46a4-160">如果运行 **Set-OrganizationConfig -AutoExpandingArchive** 命令为组织启用自动扩展存档，则不必对单个邮箱运行 **Enable-Mailbox -AutoExpandingArchive。**</span><span class="sxs-lookup"><span data-stu-id="c46a4-160">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes.</span></span> <span data-ttu-id="c46a4-161">运行 **Set-OrganizationConfig** cmdlet 为组织启用自动扩展存档不会将用户邮箱上的  *AutoExpandingArchiveEnabled*  属性更改为 `True` 。</span><span class="sxs-lookup"><span data-stu-id="c46a4-161">Running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to `True`.</span></span>

- <span data-ttu-id="c46a4-162">同样，启用自动扩展存档时  *，ArchiveQuota*  和  *ArchiveWarningQuota*  邮箱属性的值不会更改。</span><span class="sxs-lookup"><span data-stu-id="c46a4-162">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving.</span></span> <span data-ttu-id="c46a4-163">事实上，当您为用户邮箱启用自动扩展存档且  *AutoExpandingArchiveEnabled*  属性设置为 时  `True`  *，ArchiveQuota*  和  *ArchiveWarningQuota*  属性将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c46a4-163">In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are ignored.</span></span> <span data-ttu-id="c46a4-164">下面是为用户邮箱启用自动扩展存档后这些邮箱属性的示例。</span><span class="sxs-lookup"><span data-stu-id="c46a4-164">Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 

    ![启用自动扩展存档后，ArchiveQuota 和 ArchiveWarningQuota 属性将被忽略](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a><span data-ttu-id="c46a4-166">更多信息</span><span class="sxs-lookup"><span data-stu-id="c46a4-166">More information</span></span>

- <span data-ttu-id="c46a4-167">您还可以使用 PowerShell 启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-167">You can also use PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="c46a4-168">例如，您可以在 Exchange Online PowerShell 中运行以下命令，为尚未启用存档邮箱的所有用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-168">For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="c46a4-169">为组织或特定用户启用自动扩展存档后，当存档邮箱（包括"可恢复的项目"文件夹）达到 90 GB 时 () 存档邮箱将转换为自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-169">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB.</span></span> <span data-ttu-id="c46a4-170">预配额外存储空间可能需要 30 天。</span><span class="sxs-lookup"><span data-stu-id="c46a4-170">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

- <span data-ttu-id="c46a4-171">启用自动扩展存档后，无法将其关闭。</span><span class="sxs-lookup"><span data-stu-id="c46a4-171">After you turn on auto-expanding archiving, it can't be turned off.</span></span> <span data-ttu-id="c46a4-172">此外，管理员无法调整用于自动扩展存档的存储配额。</span><span class="sxs-lookup"><span data-stu-id="c46a4-172">Additionally, administrators can't adjust the storage quota for auto-expanding archiving.</span></span>

- <span data-ttu-id="c46a4-173">对于拥有本地主邮箱的用户，Exchange 混合部署中的基于云的存档邮箱支持自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-173">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox.</span></span> <span data-ttu-id="c46a4-174">但是，为基于云的存档邮箱启用自动扩展存档后，无法将存档邮箱注销回内部部署 Exchange 组织。</span><span class="sxs-lookup"><span data-stu-id="c46a4-174">However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span> <span data-ttu-id="c46a4-175">在任何版本的邮箱中，内部部署邮箱都不支持自动扩展Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="c46a4-175">Auto-expanding archiving isn't supported for on-premises mailboxes in any version of Exchange Server.</span></span>

- <span data-ttu-id="c46a4-176">有关用户可用于访问存档邮箱中其他存储区域中的项目的 Outlook 客户端列表，请参阅无限制存档概述中的"访问自动扩展存档中的项目的 Outlook 要求"[部分。](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)</span><span class="sxs-lookup"><span data-stu-id="c46a4-176">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>

- <span data-ttu-id="c46a4-177">如前所述，当您运行 **Enable-Mailbox -AutoExpandingArchive** 命令时，如果邮箱位于保留状态) 则 10 GB 将添加到用户主存档邮箱 (的存储配额和"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="c46a4-177">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command.</span></span> <span data-ttu-id="c46a4-178">这将提供额外的存储空间，直到自动扩展的存储空间预配 (可能需要 30 天) 。</span><span class="sxs-lookup"><span data-stu-id="c46a4-178">This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days).</span></span> <span data-ttu-id="c46a4-179">运行 **Set-OrganizationConfig -AutoExpandingArchive** 以启用组织中所有邮箱的自动扩展存档时，不会添加此额外存储空间。</span><span class="sxs-lookup"><span data-stu-id="c46a4-179">This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization.</span></span> <span data-ttu-id="c46a4-180">如果为整个组织启用自动扩展存档，但需要为特定用户添加额外的 10 GB 存储空间，可以针对该邮箱运行 **Enable-Mailbox -AutoExpandingArchive** 命令。</span><span class="sxs-lookup"><span data-stu-id="c46a4-180">If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox.</span></span> <span data-ttu-id="c46a4-181">您将收到一条错误消息，指出已启用自动扩展存档，但会向邮箱添加额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="c46a4-181">You will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c46a4-182">自动扩展存档仅支持用于单个用户邮箱或每天增长不超过 1 GB 的共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="c46a4-182">Auto-expanding archiving is only supported for mailboxes used for individual users or shared mailboxes with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="c46a4-183">不允许使用日记、传输规则或自动转发规则将邮件复制到存档邮箱进行存档。</span><span class="sxs-lookup"><span data-stu-id="c46a4-183">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox for the purposes of archiving is not permitted.</span></span> <span data-ttu-id="c46a4-184">用户的存档邮箱只供该用户使用。</span><span class="sxs-lookup"><span data-stu-id="c46a4-184">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="c46a4-185">Microsoft 保留拒绝在用户的存档邮箱用于存储其他用户的存档数据或其他不当使用情况下的无限制存档的权利。</span><span class="sxs-lookup"><span data-stu-id="c46a4-185">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of inappropriate use.</span></span>