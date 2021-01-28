---
title: 无限制存档概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自动扩展存档，为 Exchange Online 邮箱提供无限制的存档存储。
ms.openlocfilehash: 9692ba27c64f41ac584bb4008a8b860daab031f5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029428"
---
# <a name="overview-of-unlimited-archiving"></a><span data-ttu-id="58049-103">无限制存档概述</span><span class="sxs-lookup"><span data-stu-id="58049-103">Overview of unlimited archiving</span></span>

<span data-ttu-id="58049-104">在 Office 365 中，存档邮箱为用户提供了额外的邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="58049-105">启用用户的存档邮箱后，最多 100 GB 的额外存储空间可用。</span><span class="sxs-lookup"><span data-stu-id="58049-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="58049-106">过去，当达到 100 GB 存储配额时，组织必须联系 Microsoft 以请求为存档邮箱提供额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="58049-107">情况不再如此。</span><span class="sxs-lookup"><span data-stu-id="58049-107">That's no longer the case.</span></span>

<span data-ttu-id="58049-108">Microsoft 365 中的无限制存档功能 (*自动* 扩展存档) 在存档邮箱中提供额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-108">The unlimited archiving feature in Microsoft 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="58049-109">当达到存档邮箱中的存储配额时，Microsoft 365 会自动增加存档的大小，这意味着用户不会用完邮箱存储空间，管理员也无需为存档邮箱请求额外存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-109">When the storage quota in the archive mailbox is reached, Microsoft 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="58049-110">有关启用自动扩展存档的分步说明，请参阅"[启用无限制存档"。](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="58049-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="58049-111">自动扩展存档还支持共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="58049-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="58049-112">若要启用共享邮箱的存档，需要 Exchange Online 计划 2 许可证或具有 Exchange Online Archiving 许可证的 Exchange Online 计划 1 许可证。</span><span class="sxs-lookup"><span data-stu-id="58049-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="58049-113">自动扩展存档的工作原理</span><span class="sxs-lookup"><span data-stu-id="58049-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="58049-114">如前所述，启用用户的存档邮箱时将创建额外的邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="58049-115">启用自动扩展存档后，Microsoft 365 会定期检查存档邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="58049-115">When auto-expanding archiving is enabled, Microsoft 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="58049-116">当存档邮箱接近其存储限制时，Microsoft 365 会自动为存档创建额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-116">When an archive mailbox gets close to its storage limit, Microsoft 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="58049-117">如果用户耗尽此额外存储空间，Microsoft 365 会向用户的存档中增加更多存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-117">If the user runs out of this additional storage space, Microsoft 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="58049-118">此过程会自动执行，这意味着管理员无需请求额外的存档存储或管理自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="58049-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="58049-119">以下是此过程的快速概述。</span><span class="sxs-lookup"><span data-stu-id="58049-119">Here's a quick overview of the process.</span></span>

![自动扩展存档过程概述](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="58049-121">为用户邮箱或共享邮箱启用存档。</span><span class="sxs-lookup"><span data-stu-id="58049-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="58049-122">将创建存储空间为 100 GB 的存档邮箱，存档邮箱的警告配额设置为 90 GB。</span><span class="sxs-lookup"><span data-stu-id="58049-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="58049-123">管理员启用邮箱的自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="58049-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="58049-124">当存档邮箱 ("可恢复的项目"文件夹) 达到 90 GB 时，它将转换为自动扩展存档，并且 Microsoft 365 会向存档添加存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Microsoft 365 adds storage space to the archive.</span></span> <span data-ttu-id="58049-125">设置额外存储空间可能需要 30 天。</span><span class="sxs-lookup"><span data-stu-id="58049-125">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="58049-126">如果邮箱处于保留状态或已分配给保留策略，则启用自动扩展存档时，存档邮箱的存储配额将增加到 110 GB。</span><span class="sxs-lookup"><span data-stu-id="58049-126">If a mailbox is placed on hold or assigned to a retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="58049-127">同样，存档警告配额增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="58049-127">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="58049-128">如有必要，Microsoft 365 会自动添加更多存储空间。</span><span class="sxs-lookup"><span data-stu-id="58049-128">Microsoft 365 automatically adds more storage space when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58049-129">自动扩展存档仅支持用于单个用户 (或共享) 的邮箱，其增长速率不超过每天 1 GB。</span><span class="sxs-lookup"><span data-stu-id="58049-129">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="58049-130">用户的存档邮箱只供该用户使用。</span><span class="sxs-lookup"><span data-stu-id="58049-130">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="58049-131">不允许使用日记、传输规则或自动转发规则将邮件复制到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="58049-131">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="58049-132">在用户的存档邮箱用于存储其他用户的存档数据或其他不当使用的情况下，Microsoft 保留拒绝无限制存档的权利。</span><span class="sxs-lookup"><span data-stu-id="58049-132">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of the inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="58049-133">哪些内容会移到其他存档存储空间中？</span><span class="sxs-lookup"><span data-stu-id="58049-133">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="58049-134">若要高效地使用自动扩展存档存储，文件夹可能会移动。</span><span class="sxs-lookup"><span data-stu-id="58049-134">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="58049-135">Microsoft 365 确定在向存档中添加额外存储空间时移动的文件夹。</span><span class="sxs-lookup"><span data-stu-id="58049-135">Microsoft 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="58049-136">有时，当移动文件夹时，会自动创建一个或多个子文件夹，并且原始文件夹中的项目将分发到这些文件夹，以便于移动过程。</span><span class="sxs-lookup"><span data-stu-id="58049-136">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="58049-137">在 Outlook 中查看文件夹列表的存档部分时，这些子文件夹将显示在原始文件夹下。</span><span class="sxs-lookup"><span data-stu-id="58049-137">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="58049-138">Microsoft 365 用于命名这些子文件夹的命名约定是_yyyy (**\<folder name\> mmm dd， yyyyy** h_mm) 创建的，其中：</span><span class="sxs-lookup"><span data-stu-id="58049-138">The naming convention that Microsoft 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="58049-139">**yyyy 是** 文件夹中收到邮件的年份。</span><span class="sxs-lookup"><span data-stu-id="58049-139">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="58049-140">**mmm dd， yyyy h_m** is the date and time that the subfolder was created by Office 365， in UTC format， based on the user's time zone and regional settings in Outlook.</span><span class="sxs-lookup"><span data-stu-id="58049-140">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="58049-141">以下屏幕截图显示了将邮件移动到自动展开存档之前和之后的文件夹列表。</span><span class="sxs-lookup"><span data-stu-id="58049-141">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="58049-142">**添加额外存储空间之前**</span><span class="sxs-lookup"><span data-stu-id="58049-142">**Before additional storage is added**</span></span>

![预配自动扩展存档之前存档邮箱的文件夹列表](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="58049-144">**添加额外存储空间后**</span><span class="sxs-lookup"><span data-stu-id="58049-144">**After additional storage is added**</span></span>

![设置自动扩展存档后存档邮箱的文件夹列表](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="58049-146">如前所述，Microsoft 365 将项目移动到子文件夹 (，然后使用上述) 命名约定命名它们，以帮助将内容分发到辅助存档。</span><span class="sxs-lookup"><span data-stu-id="58049-146">As previously described, Microsoft 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="58049-147">但是，将项目移动到子文件夹可能并不总是如此。</span><span class="sxs-lookup"><span data-stu-id="58049-147">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="58049-148">有时，可能会将整个文件夹移动到辅助存档。</span><span class="sxs-lookup"><span data-stu-id="58049-148">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="58049-149">在这种情况下，文件夹将保留其原始名称。</span><span class="sxs-lookup"><span data-stu-id="58049-149">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="58049-150">在 Outlook 的文件夹列表中，该文件夹已移动到辅助存档中，这一点并不明显。</span><span class="sxs-lookup"><span data-stu-id="58049-150">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="58049-151">用于访问自动扩展存档中的项目的 Outlook 要求</span><span class="sxs-lookup"><span data-stu-id="58049-151">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="58049-152">若要访问存储在自动扩展存档中的邮件，用户必须使用以下 Outlook 客户端之一：</span><span class="sxs-lookup"><span data-stu-id="58049-152">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="58049-153">Outlook 2016 或 Outlook 2019 for Windows</span><span class="sxs-lookup"><span data-stu-id="58049-153">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="58049-154">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="58049-154">Outlook on the web</span></span>

- <span data-ttu-id="58049-155">Outlook 2016 或 Outlook 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="58049-155">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="58049-156">以下是使用 Outlook 或 Web 上的 Outlook 访问存储在自动扩展存档中的邮件时要考虑的一些情况。</span><span class="sxs-lookup"><span data-stu-id="58049-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="58049-157">可以访问存档邮箱中的任意文件夹，包括已移动到自动扩展存储区域的文件夹。</span><span class="sxs-lookup"><span data-stu-id="58049-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="58049-158">Outlook 网页中提供了自动扩展存档搜索功能。</span><span class="sxs-lookup"><span data-stu-id="58049-158">Search for auto-expanded archiving is available in Outlook for the web.</span></span> <span data-ttu-id="58049-159">与联机存档类似，只有搜索当前文件夹本身，才能搜索已移动到其他存储区域的项目。</span><span class="sxs-lookup"><span data-stu-id="58049-159">Similar to Online Archive, you can search for items that were moved to an additional storage area only by searching the current folder itself.</span></span> <span data-ttu-id="58049-160">这意味着您必须选择文件夹列表中的存档文件夹，然后选择单个文件夹作为搜索范围。</span><span class="sxs-lookup"><span data-stu-id="58049-160">This means that you must select the archive folder in the folder list, and then select a single folder as your search scope.</span></span> <span data-ttu-id="58049-161">同样，如果自动扩展存储区域中的文件夹包含子文件夹，则必须单独搜索每个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="58049-161">Similarly, if a folder in an auto-expanded storage area contains subfolders, you must search each subfolder separately.</span></span>
- <span data-ttu-id="58049-162">"当前频道"和"预览版"中的 Outlook 桌面 (自动展开) 。</span><span class="sxs-lookup"><span data-stu-id="58049-162">Auto-expanded archive search is available in Outlook Desktop in Current Channel (Preview).</span></span> <span data-ttu-id="58049-163">在此预览版中，当前邮箱范围可用，因此允许您搜索自动展开的存档。</span><span class="sxs-lookup"><span data-stu-id="58049-163">Within this preview, the Current Mailbox scope is available, thus allowing you to search the auto-expanded archive.</span></span> <span data-ttu-id="58049-164">有关此功能和其他 Microsoft 搜索支持功能的信息，请参阅 [Outlook for Windows](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)连接到 Exchange Online 如何使用 Microsoft 搜索。</span><span class="sxs-lookup"><span data-stu-id="58049-164">For more information about this and other Microsoft Search support features, see [How Outlook for Windows connected to Exchange Online utilizes Microsoft Search](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045).</span></span> 

- <span data-ttu-id="58049-165">在自动展开的存档 (Outlook 和 Outlook 网页) 中的项目计数和读取/未读计数可能不准确。</span><span class="sxs-lookup"><span data-stu-id="58049-165">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="58049-166">可以删除指向自动扩展存储区的子文件夹中的项目，但无法删除文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="58049-166">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="58049-167">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span><span class="sxs-lookup"><span data-stu-id="58049-167">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-compliance-features"></a><span data-ttu-id="58049-168">自动扩展存档和其他合规性功能</span><span class="sxs-lookup"><span data-stu-id="58049-168">Auto-expanding archiving and other compliance features</span></span>

<span data-ttu-id="58049-169">本节介绍自动扩展存档与其他合规性和数据管理功能之间的功能。</span><span class="sxs-lookup"><span data-stu-id="58049-169">This section explains the functionality between auto-expanding archiving and other compliance and data governance features.</span></span>

- <span data-ttu-id="58049-170">**电子数据展示：** 使用电子数据展示工具（如内容搜索或In-Place电子数据展示）时，也会搜索自动扩展存档中的其他存储区域。</span><span class="sxs-lookup"><span data-stu-id="58049-170">**eDiscovery:** When you use an eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="58049-171">**保留：** 使用 Exchange Online 中的诉讼保留或安全与合规中心中的电子数据展示案例保留和保留策略等工具将邮箱置于保留状态时，自动扩展存档中的内容也会置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="58049-171">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="58049-172">**邮件记录管理 (MRM) ：** 如果使用 Exchange Online 中的 MRM 删除策略永久删除过期的邮箱项目，则位于自动扩展存档中的过期项目也将被删除。</span><span class="sxs-lookup"><span data-stu-id="58049-172">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="58049-173">**导入服务：** 可以使用 Office 365 导入服务将 PST 文件导入用户的自动展开存档。</span><span class="sxs-lookup"><span data-stu-id="58049-173">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="58049-174">您最多可以将 100 GB 的数据从 PST 文件导入到用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="58049-174">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="58049-175">更多信息</span><span class="sxs-lookup"><span data-stu-id="58049-175">More information</span></span>

<span data-ttu-id="58049-176">有关自动扩展存档的更多技术详细信息，请参阅 [Microsoft 365：自动扩展存档常见问题解答](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)。</span><span class="sxs-lookup"><span data-stu-id="58049-176">For more technical details about auto-expanding archiving, see [Microsoft 365: Auto-Expanding Archives FAQ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784).</span></span>
