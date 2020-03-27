---
title: 将就地保留置于 Exchange Online 中的软删除邮箱上
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。
ms.openlocfilehash: 1986a4bfca72c192b268984b7d2f49eb2e88134a
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978152"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="2536a-104">将就地保留置于 Exchange Online 中的软删除邮箱上</span><span class="sxs-lookup"><span data-stu-id="2536a-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="2536a-p102">了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="2536a-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2536a-107">随着我们继续投资保留邮箱内容的不同方式，我们宣布在 Exchange 管理中心（EAC）中停用就地保留。</span><span class="sxs-lookup"><span data-stu-id="2536a-107">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="2536a-108">从2020年6月1日开始，你将无法在 Exchange Online 中创建新的就地保留。</span><span class="sxs-lookup"><span data-stu-id="2536a-108">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="2536a-109">但您仍可以在 EAC 中管理就地保留或通过在 Exchange Online PowerShell 中使用**new-mailboxsearch** cmdlet 来管理。</span><span class="sxs-lookup"><span data-stu-id="2536a-109">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="2536a-110">但是，从2020年10月1日开始，你将无法管理就地保留。</span><span class="sxs-lookup"><span data-stu-id="2536a-110">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="2536a-111">您只能将其从 EAC 中删除或使用**new-mailboxsearch** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2536a-111">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="2536a-112">有关停用就地保留的详细信息，请参阅[旧版电子数据展示工具的退休](legacy-ediscovery-retirement.md)。</span><span class="sxs-lookup"><span data-stu-id="2536a-112">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="2536a-113">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="2536a-113">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="2536a-114">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="2536a-114">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="2536a-115">What can you do?</span><span class="sxs-lookup"><span data-stu-id="2536a-115">What can you do?</span></span> <span data-ttu-id="2536a-116">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="2536a-116">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="2536a-117">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="2536a-117">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="2536a-118">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="2536a-118">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="2536a-119">在邮箱变为非活动状态后，可以使用 Exchange Online 中的就地电子数据展示、安全性 & 合规性中心中的内容搜索或 SharePoint Online 中的电子数据展示中心来搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="2536a-119">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2536a-p105">在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。Exchange Online 中的软删除邮箱保留期为 30 天。这意味着该邮箱可以在删除后 30 天内进行恢复（或变为非活动邮箱）。30 天后，软删除邮箱将标记为永久删除并且无法恢复或变为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="2536a-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="2536a-124">准备工作</span><span class="sxs-lookup"><span data-stu-id="2536a-124">Before you begin</span></span>

- <span data-ttu-id="2536a-125">您必须在 Windows PowerShell 中使用**new-mailboxsearch** cmdlet 在软删除的邮箱上放置就地保留。</span><span class="sxs-lookup"><span data-stu-id="2536a-125">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="2536a-126">不能使用 SharePoint Online 中的 Exchange 管理中心 (EAC) 或电子数据展示中心。</span><span class="sxs-lookup"><span data-stu-id="2536a-126">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="2536a-127">若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="2536a-127">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="2536a-128">运行以下命令获取组织中软删除邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="2536a-128">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="2536a-129">有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱概述](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="2536a-129">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="2536a-130">将就地保留置于软删除邮箱以使其变为非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="2536a-130">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="2536a-131">使用**new-mailboxsearch** cmdlet 可将软删除的邮箱设置为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="2536a-131">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="2536a-132">有关详细信息，请参阅 [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2536a-132">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="2536a-133">创建包含软删除邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="2536a-133">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="2536a-134">在上一个命令中，使用**DistinguishedName**或**ExchangeGuid**属性的值来标识软删除的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2536a-134">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="2536a-135">这些属性对于组织中的每个邮箱都是唯一的，但活动邮箱和软删除邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="2536a-135">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="2536a-p109">创建就地保留并将其置于软删除邮箱上。在此示例中，未指定保留持续时间。这意味着项目将被无限期保留或一直保留到将该保留从非活动邮箱中删除为止。</span><span class="sxs-lookup"><span data-stu-id="2536a-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="2536a-p110">还可以在创建就地保留时指定保留持续时间。此示例保留非活动邮箱中的项目近 7 年。</span><span class="sxs-lookup"><span data-stu-id="2536a-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="2536a-141">一段时间后，运行下列命令之一，验证软删除邮箱是否为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="2536a-141">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="2536a-142">或</span><span class="sxs-lookup"><span data-stu-id="2536a-142">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="2536a-143">详细信息</span><span class="sxs-lookup"><span data-stu-id="2536a-143">More information</span></span>

<span data-ttu-id="2536a-p111">在将软删除邮箱变为非活动邮箱后，有多种方法可以管理该邮箱。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2536a-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="2536a-146">更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="2536a-146">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="2536a-147">恢复非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="2536a-147">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="2536a-148">还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="2536a-148">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="2536a-149">[删除非活动邮箱](delete-an-inactive-mailbox.md)（通过删除保留）</span><span class="sxs-lookup"><span data-stu-id="2536a-149">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
