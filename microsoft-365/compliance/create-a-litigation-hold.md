---
title: 创建诉讼保留
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: 了解如何将邮箱置于诉讼保留状态，在调查期间保留所有邮箱内容。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 046ee6fdc7c42026b1a69805883175982e3100b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908396"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="0ea07-103">创建诉讼保留</span><span class="sxs-lookup"><span data-stu-id="0ea07-103">Create a Litigation Hold</span></span>

<span data-ttu-id="0ea07-104">可以将邮箱置于诉讼保留状态，以保留所有邮箱内容，包括已删除项目和已修改项目的原始版本。</span><span class="sxs-lookup"><span data-stu-id="0ea07-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="0ea07-105">当您将用户邮箱置于诉讼保留时，用户的存档邮箱中的内容 (如果已启用，) 内容也会保留。</span><span class="sxs-lookup"><span data-stu-id="0ea07-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="0ea07-106">创建保留时，您可以指定保留持续时间 *(也称为* 基于时间保留) 以便已删除和修改的项目保留指定的时间段，然后从邮箱中永久删除。</span><span class="sxs-lookup"><span data-stu-id="0ea07-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="0ea07-107">或者，您可以无限期地保留 (称为"无限期保留") 或删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="0ea07-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="0ea07-108">如果您指定了保留持续时间，则从收到邮件或创建邮箱项目的日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="0ea07-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="0ea07-109">下面是创建诉讼保留时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="0ea07-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="0ea07-110">在保留期间，用户永久删除的项目将保留在用户邮箱的"可恢复的项目"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0ea07-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="0ea07-111">用户从"可恢复的项目"文件夹中清除的项目将在保留期间保留。</span><span class="sxs-lookup"><span data-stu-id="0ea07-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="0ea07-112">"可恢复的项目"文件夹的存储配额从 30 GB 增加到 110 GB。</span><span class="sxs-lookup"><span data-stu-id="0ea07-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="0ea07-113">用户的主邮箱和存档邮箱中的项目将保留</span><span class="sxs-lookup"><span data-stu-id="0ea07-113">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="assign-an-exchange-online-plan-2-license"></a><span data-ttu-id="0ea07-114">分配 Exchange Online 计划 2 许可证</span><span class="sxs-lookup"><span data-stu-id="0ea07-114">Assign an Exchange Online Plan 2 license</span></span>

- <span data-ttu-id="0ea07-115">若要将 Exchange Online 邮箱置于诉讼保留状态，必须为其分配 Exchange Online 计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="0ea07-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="0ea07-116">如果为邮箱分配了 Exchange Online 计划 1 许可证，必须为其分配单独的 Exchange Online Archiving 许可证才能将其置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="0ea07-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="0ea07-117">将邮箱置于诉讼保留</span><span class="sxs-lookup"><span data-stu-id="0ea07-117">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="0ea07-118">下面是使用 Exchange 管理中心将邮箱置于诉讼保留中的步骤。</span><span class="sxs-lookup"><span data-stu-id="0ea07-118">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="0ea07-119">转到 [https://outlook.office.com/ecp](https://outlook.office.com/ecp) ，然后使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="0ea07-119">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="0ea07-120">单击 **左侧>窗格中的** "收件人""邮箱"。</span><span class="sxs-lookup"><span data-stu-id="0ea07-120">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="0ea07-121">选择要置于诉讼保留的邮箱，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ea07-121">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="0ea07-122">在"邮箱属性"页上，单击"**邮箱功能"。**</span><span class="sxs-lookup"><span data-stu-id="0ea07-122">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="0ea07-123">在 **"诉讼保留： 已禁用"** 下，单击 **"启用** "将邮箱置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="0ea07-123">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="0ea07-124">在" **诉讼保留"** 页上，输入以下可选信息：</span><span class="sxs-lookup"><span data-stu-id="0ea07-124">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="0ea07-125">**诉讼保留 (天)** - 使用此框可以创建基于时间保留，并指定邮箱项目在置于诉讼保留时保留的时间。</span><span class="sxs-lookup"><span data-stu-id="0ea07-125">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="0ea07-126">持续时间从接收或创建邮箱项目的日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="0ea07-126">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="0ea07-127">当特定项目的保留期到期时，将不再保留该项目。</span><span class="sxs-lookup"><span data-stu-id="0ea07-127">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="0ea07-128">如果保留此框为空，项目将无限期保留或一直保留到删除保留。</span><span class="sxs-lookup"><span data-stu-id="0ea07-128">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="0ea07-129">使用天指定持续时间。</span><span class="sxs-lookup"><span data-stu-id="0ea07-129">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="0ea07-130">**注意** - 使用此框通知用户其邮箱已置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="0ea07-130">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="0ea07-131">如果用户使用的是 Outlook 2010 或更高版本，则注释将显示在用户邮箱的"帐户信息"页上。</span><span class="sxs-lookup"><span data-stu-id="0ea07-131">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="0ea07-132">若要访问此页面，用户可以单击"Outlook **中的** 文件"。</span><span class="sxs-lookup"><span data-stu-id="0ea07-132">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="0ea07-133">**URL** - 使用此框将用户引导到网站，详细了解诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="0ea07-133">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="0ea07-134">如果用户使用的是 Outlook 2010 或更高版本，则此 URL 将显示在用户邮箱的"帐户信息"页上。</span><span class="sxs-lookup"><span data-stu-id="0ea07-134">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="0ea07-135">若要访问此页面，用户可以 **单击"Outlook** 中的文件"。</span><span class="sxs-lookup"><span data-stu-id="0ea07-135">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="0ea07-136">在 **"诉讼** 保留 **"** 页上单击"保存"，然后在 **邮箱属性页上** 单击"保存"。</span><span class="sxs-lookup"><span data-stu-id="0ea07-136">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="0ea07-137">使用 PowerShell 创建诉讼保留</span><span class="sxs-lookup"><span data-stu-id="0ea07-137">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="0ea07-138">您还可以在 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中运行以下命令来创建诉讼保留：</span><span class="sxs-lookup"><span data-stu-id="0ea07-138">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="0ea07-139">上一个命令无限期保留项目，因为未指定保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="0ea07-139">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="0ea07-140">若要创建基于时间保留，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0ea07-140">To created a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="0ea07-141">有关详细信息，请参阅 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="0ea07-141">For more information, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="0ea07-142">诉讼保留的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="0ea07-142">How does Litigation Hold work?</span></span>

<span data-ttu-id="0ea07-143">在正常的已删除邮件工作流中，当用户永久删除 (Shift + Delete) 或从已删除邮件文件夹中删除某个邮箱项目时，会将该项目移动到"可恢复的项目"文件夹中的"删除"子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ea07-143">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="0ea07-144">当保留期到期时，删除策略（这是使用删除保留操作配置的保留标记）也将项目移动到"删除"子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ea07-144">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="0ea07-145">当用户清除"可恢复的项目"文件夹中的某个项目时或者当某个项目的已删除邮件保留期到期时，该项目将被移动到"可恢复的项目"文件夹中的"清除"子文件夹并标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="0ea07-145">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="0ea07-146">下一次通过托管文件夹助理 (MFA) 处理邮箱时，将从 Exchange 中清除该邮箱。</span><span class="sxs-lookup"><span data-stu-id="0ea07-146">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="0ea07-p108">如果邮箱置于诉讼保留状态，在由诉讼保留指定的保留期限内会保留"清除"子文件中的项目。保留期限自接收或创建项目的原始日期算起，并且定义了保留"清除"子文件中的项目的时长。"清除"子文件中的某个项目的保留期限到期时，将该项目标记为永久删除，并且下一次通过 MFA 处理邮箱时该项目将从 Exchange 中清除。如果邮箱中设置了无限期保留，则永远不会将项目从"清除"子文件中清除。</span><span class="sxs-lookup"><span data-stu-id="0ea07-p108">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="0ea07-151">下图显示了"可恢复的项目"文件夹中的子文件夹和保留工作流程。</span><span class="sxs-lookup"><span data-stu-id="0ea07-151">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![诉讼保留生命周期](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="0ea07-153">如果邮箱上放置了与电子数据展示案例关联的保留，则清除的项目会从"删除"子文件夹移动到 DiscoveryHolds 子文件夹，并一直保留，直到邮箱从电子数据展示保留中释放。</span><span class="sxs-lookup"><span data-stu-id="0ea07-153">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
