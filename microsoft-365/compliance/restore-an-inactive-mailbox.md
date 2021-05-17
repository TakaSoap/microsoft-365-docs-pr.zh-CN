---
title: 还原非活动邮箱
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
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 了解如何将非 (邮箱) 的内容还原到非活动邮箱中的现有邮箱Office 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bc9039d21f76affce7f58f1f83597dd9e5eb4ecf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917296"
---
# <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="cd963-103">还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="cd963-103">Restore an inactive mailbox</span></span>

<span data-ttu-id="cd963-104">非活动 (邮箱邮箱是一种软) 邮箱类型，用于在前员工离开组织后保留其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cd963-104">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="cd963-105">如果另一名员工接替离职员工的工作职责，或者该员工回到您的组织，有两种方法可以将非活动邮箱的内容提供给用户：</span><span class="sxs-lookup"><span data-stu-id="cd963-105">If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span>

- <span data-ttu-id="cd963-p102">**还原非活动邮箱** 如果另一名员工接替离职员工的工作职责，或者如果另一个用户需要访问非活动邮箱的内容，您可以将非活动邮箱的内容还原（或 合并）到某个现有邮箱。您还可以从非活动邮箱还原存档。还原后，非活动邮箱将保留，并仍保留为非活动状态。本主题介绍还原非活动邮箱的过程。</span><span class="sxs-lookup"><span data-stu-id="cd963-p102">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.</span></span>

- <span data-ttu-id="cd963-110">**恢复非活动邮箱** 如果离职的员工回到您的组织，或者如果某位新员工要接替离职员工的工作职责，则可以恢复非活动邮箱的内容。</span><span class="sxs-lookup"><span data-stu-id="cd963-110">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="cd963-111">此方法将非活动邮箱转换为包含非活动邮箱内容的新邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-111">This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="cd963-112">恢复后，非活动邮箱不再存在。</span><span class="sxs-lookup"><span data-stu-id="cd963-112">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="cd963-113">有关分步过程，请参阅恢复邮箱中的[非活动Office 365。](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="cd963-113">For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

<span data-ttu-id="cd963-114">有关 [还原和恢复](#more-information) 非活动邮箱之间的差异的更多详细信息，请参阅本文中的详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="cd963-114">See the [More information](#more-information) section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="cd963-115">无法恢复或还原使用自动扩展存档配置的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-115">You can't recover or restore an inactive mailbox that's configured with an auto-expanding archive.</span></span> <span data-ttu-id="cd963-116">如果需要从具有自动扩展存档的非活动邮箱恢复数据，请使用内容搜索从邮箱导出数据，然后导入另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-116">If you need to recover data from an inactive mailbox with an auto-expanding archive, use content search to export the data from the mailbox and then import to another mailbox.</span></span> <span data-ttu-id="cd963-117">有关说明，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="cd963-117">For instructions, see following topics:</span></span>
>
> - [<span data-ttu-id="cd963-118">内容搜索</span><span class="sxs-lookup"><span data-stu-id="cd963-118">Content search</span></span>](content-search.md)
> - [<span data-ttu-id="cd963-119">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="cd963-119">Export content search results</span></span>](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a><span data-ttu-id="cd963-120">还原非活动邮箱的要求</span><span class="sxs-lookup"><span data-stu-id="cd963-120">Requirements to restore an inactive mailbox</span></span>

- <span data-ttu-id="cd963-121">您必须使用 PowerShell Exchange Online还原非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-121">You have to use Exchange Online PowerShell to restore an inactive mailbox.</span></span> <span data-ttu-id="cd963-122">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="cd963-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="cd963-123">有关分步说明，请参阅[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cd963-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="cd963-124">在 PowerShell Exchange Online以下命令，获取组织中非活动邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="cd963-124">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  <span data-ttu-id="cd963-125">使用此命令返回的信息来还原特定的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-125">Use the information returned by this command to restore a specific inactive mailbox.</span></span>

- <span data-ttu-id="cd963-126">有关非活动邮箱的信息，[请参阅非活动](inactive-mailboxes-in-office-365.md)Office 365。</span><span class="sxs-lookup"><span data-stu-id="cd963-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="restore-inactive-mailboxes"></a><span data-ttu-id="cd963-127">还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="cd963-127">Restore inactive mailboxes</span></span>

<span data-ttu-id="cd963-p106">将 **New-MailboxRestoreRequest** cmdlet 与  _SourceMailbox_ 和  _TargetMailbox_ 参数一起使用，将非活动邮箱的内容还原到现有邮箱。有关使用此 cmdlet 的详细信息，请参阅 [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest)。</span><span class="sxs-lookup"><span data-stu-id="cd963-p106">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest).</span></span>

1. <span data-ttu-id="cd963-130">创建包含非活动邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="cd963-130">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="cd963-p107">在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="cd963-p107">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="cd963-p108">将非活动邮箱的内容还原到现有邮箱。非活动邮箱（源邮箱）的内容将合并到现有邮箱（目标邮箱）中的相应文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd963-p108">Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   <span data-ttu-id="cd963-p109">或者，可以指定要从非活动邮箱还原内容的目标邮箱中的顶级文件夹。如果指定的目标文件夹或目标文件夹结构在目标邮箱中不存在，将在还原过程中创建。</span><span class="sxs-lookup"><span data-stu-id="cd963-p109">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span>

   <span data-ttu-id="cd963-137">本示例将邮箱项目和子文件夹从非活动邮箱复制到目标邮箱的顶级文件夹结构中一个名为"非活动邮箱"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd963-137">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="cd963-138">从非活动邮箱还原存档</span><span class="sxs-lookup"><span data-stu-id="cd963-138">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="cd963-139">如果非活动邮箱具有存档邮箱，您还可以将其还原到现有邮箱的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-139">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox.</span></span> <span data-ttu-id="cd963-140">若要从非活动邮箱还原存档，您必须将 _SourceIsArchive_ 和 _TargetIsArchive_ 开关添加到用于还原非活动邮箱的命令。</span><span class="sxs-lookup"><span data-stu-id="cd963-140">To restore the archive from an inactive mailbox, you have to add the _SourceIsArchive_ and _TargetIsArchive_ switches to the command used to restore an inactive mailbox.</span></span>

1. <span data-ttu-id="cd963-141">创建包含非活动邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="cd963-141">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > <span data-ttu-id="cd963-p111">在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="cd963-p111">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="cd963-p112">将非活动邮箱的存档（源存档）内容还原到现有邮箱的存档（目标存档）。在此示例中，将源存档的内容复制到目标邮箱的存档中一个名为"非活动邮箱存档"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd963-p112">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a><span data-ttu-id="cd963-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="cd963-146">More information</span></span>

- <span data-ttu-id="cd963-147">**恢复和还原非活动邮箱的主要区别是什么？**</span><span class="sxs-lookup"><span data-stu-id="cd963-147">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="cd963-148">恢复非活动邮箱时，邮箱基本上会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cd963-148">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="cd963-149">恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。</span><span class="sxs-lookup"><span data-stu-id="cd963-149">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="cd963-150">相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-150">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="cd963-151">非活动邮箱将保留，并且仍保留非活动状态。</span><span class="sxs-lookup"><span data-stu-id="cd963-151">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="cd963-152">对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。</span><span class="sxs-lookup"><span data-stu-id="cd963-152">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="cd963-153">仍可以使用内容搜索工具搜索非活动邮箱，其内容[](content-search.md)可以还原到另一个邮箱，也可以稍后恢复或删除。</span><span class="sxs-lookup"><span data-stu-id="cd963-153">The inactive mailbox can still be searched by using the [Content Search tool](content-search.md), its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span>

- <span data-ttu-id="cd963-p114">**如何查找非活动邮箱？** 要获取您组织中的非活动邮箱的列表，并显示可用于恢复非活动邮箱的信息，可以运行此命令。</span><span class="sxs-lookup"><span data-stu-id="cd963-p114">**How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="cd963-156">**使用诉讼保留或Microsoft 365保留策略保留非活动邮箱内容。**</span><span class="sxs-lookup"><span data-stu-id="cd963-156">**Use a Litigation Hold or Microsoft 365 retention policy to retain inactive mailbox content.**</span></span> <span data-ttu-id="cd963-157">如果要在还原后保留非活动邮箱的状态，可以将目标邮箱置于诉讼保留状态，或在还原非活动邮箱之前应用[](create-a-litigation-hold.md)Microsoft 365[保留](retention.md)策略。</span><span class="sxs-lookup"><span data-stu-id="cd963-157">If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](create-a-litigation-hold.md) or apply an [Microsoft 365 retention policy](retention.md) before you restore the inactive mailbox.</span></span> <span data-ttu-id="cd963-158">这样可以防止在将非活动邮箱还原到目标邮箱之后，永久删除非活动邮箱中的任何项目。</span><span class="sxs-lookup"><span data-stu-id="cd963-158">This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span>

- <span data-ttu-id="cd963-159">**在还原非活动邮箱之前，在目标邮箱上启用保留挂起功能。**</span><span class="sxs-lookup"><span data-stu-id="cd963-159">**Enable retention hold on the target mailbox before you restore an inactive mailbox.**</span></span> <span data-ttu-id="cd963-160">由于非活动邮箱中的邮箱项目可能已过时，您可能会考虑在还原非活动邮箱之前在目标邮箱上启用保留挂起功能。</span><span class="sxs-lookup"><span data-stu-id="cd963-160">Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox.</span></span> <span data-ttu-id="cd963-161">将邮箱置于保留挂起状态时，在移除保留挂起或保留挂起期到期之前，将不会处理向其分配的保留策略。</span><span class="sxs-lookup"><span data-stu-id="cd963-161">When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires.</span></span> <span data-ttu-id="cd963-162">这使目标邮箱的所有者有时间管理非活动邮箱中的邮件。</span><span class="sxs-lookup"><span data-stu-id="cd963-162">This gives the owner of the target mailbox time to manage old messages from the inactive mailbox.</span></span> <span data-ttu-id="cd963-163">否则，保留策略可能会删除根据为目标邮箱配置的保留设置已到期的旧项目，或将项目移动到存档邮箱（如果已启用）中。</span><span class="sxs-lookup"><span data-stu-id="cd963-163">Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox.</span></span> <span data-ttu-id="cd963-164">有关详细信息，请参阅 Place [a mailbox on retention hold in Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)。</span><span class="sxs-lookup"><span data-stu-id="cd963-164">For more information, see [Place a mailbox on retention hold in Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).</span></span>

- <span data-ttu-id="cd963-165">**AllowLegacyDNMismatch 开关有什么作用？**</span><span class="sxs-lookup"><span data-stu-id="cd963-165">**What does the AllowLegacyDNMismatch switch do?**</span></span> <span data-ttu-id="cd963-166">在前面还原非活动邮箱的示例中， **AllowLegacyDNMismatch** 开关用来允许将非活动邮箱还原到不同的目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-166">In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox.</span></span> <span data-ttu-id="cd963-167">在典型的还原方案中，目标是还原源邮箱和目标邮箱为同一个邮箱的内容。</span><span class="sxs-lookup"><span data-stu-id="cd963-167">In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox.</span></span> <span data-ttu-id="cd963-168">因此，默认情况下 **，New-MailboxRestoreRequest** cmdlet 会进行检查以确保源邮箱和目标邮箱上的 **LegacyExchangeDN** 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="cd963-168">So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same.</span></span> <span data-ttu-id="cd963-169">此检查可防止您将源邮箱意外还原到错误的目标邮箱中。</span><span class="sxs-lookup"><span data-stu-id="cd963-169">This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox.</span></span> <span data-ttu-id="cd963-170">如果您尝试在不使用 **AllowLegacyDNMismatch** 开关的情况下还原非活动邮箱，则当源邮箱和目标邮箱具有不同的 **LegacyExchangeDN** 属性值时，该命令可能会失败。</span><span class="sxs-lookup"><span data-stu-id="cd963-170">If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span>

- <span data-ttu-id="cd963-p118">**可以使用 New-MailboxRestoreRequest cmdlet 与其他参数实现非活动邮箱的其他还原方案。** 例如，您可以运行此命令，将非活动邮箱的存档还原到目标邮箱的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="cd963-p118">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="cd963-173">通过运行此命令，还可以将非活动的主邮箱还原到目标邮箱的存档中。</span><span class="sxs-lookup"><span data-stu-id="cd963-173">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="cd963-p119">**TargetRootFolder 参数有什么作用？** 如前面所述，您可以使用 **TargetRootFolder** 参数指定将向其还原非活动邮箱内容的目标邮箱中文件夹结构顶部的一个文件夹（也称为 根）。如果不使用此参数，非活动邮箱中的邮箱项目将合并到目标邮箱相应的默认文件夹中，并在目标邮箱的根目录中重新创建自定义文件夹。下图重点说明不使用和使用 **TargetRootFolder** 参数的区别。</span><span class="sxs-lookup"><span data-stu-id="cd963-p119">**What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span>

  <span data-ttu-id="cd963-178">**不使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**</span><span class="sxs-lookup"><span data-stu-id="cd963-178">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>

  ![不使用 TargetRootFolder 参数时的屏幕截图](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  <span data-ttu-id="cd963-180">**使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**</span><span class="sxs-lookup"><span data-stu-id="cd963-180">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>

  ![使用 TargetRootFolder 参数时的屏幕截图](../media/300da592-7323-48db-b8a4-07012259d113.png)