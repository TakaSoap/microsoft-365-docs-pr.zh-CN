---
title: Office 365 中的无限制存档概述
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
description: 了解 Office 365 中的自动扩展存档，该存档为 Exchange Online 邮箱提供无限制的存档存储。
ms.openlocfilehash: e7d004c7ef92fbcb331191432a70114f36dabc07
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601360"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="3a2fc-103">Office 365 中的无限制存档概述</span><span class="sxs-lookup"><span data-stu-id="3a2fc-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="3a2fc-104">在 Office 365 中，存档邮箱为用户提供额外的邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="3a2fc-105">启用用户的存档邮箱后，最多可有 100 GB 的附加存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="3a2fc-106">过去，当达到 100 GB 的存储配额时，组织必须与 Microsoft 联系以请求存档邮箱的额外存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="3a2fc-107">这就不再是这样。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-107">That's no longer the case.</span></span>

<span data-ttu-id="3a2fc-108">Office 365 中的无限制存档功能（称为*自动扩展存档*）在存档邮箱中提供了额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-108">The unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="3a2fc-109">当达到存档邮箱中的存储配额时，Office 365 将自动增加存档的大小，这意味着用户将不会用尽邮箱存储空间，并且管理员不必为存档邮箱请求额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-109">When the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="3a2fc-110">有关启用自动扩展存档的分步说明，请参阅[在 Office 365 中启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3a2fc-111">自动扩展存档还支持共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="3a2fc-112">若要为共享邮箱启用存档，需要具有 Exchange Online 存档许可证的 Exchange Online 计划2许可证或 Exchange Online 计划1许可证。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="3a2fc-113">自动扩展存档的工作方式</span><span class="sxs-lookup"><span data-stu-id="3a2fc-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="3a2fc-114">如前所述，在启用用户的存档邮箱时，会创建额外的邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="3a2fc-115">启用自动扩展存档后，Office 365 将定期检查存档邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-115">When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="3a2fc-116">当存档邮箱接近其存储限制时，Office 365 会自动为存档创建额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-116">When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="3a2fc-117">如果用户在此额外的存储空间中耗尽，Office 365 将为用户的存档增加更多的存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-117">If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="3a2fc-118">此过程会自动发生，这意味着管理员无需请求额外存档存储或管理自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="3a2fc-119">以下是此过程的快速概述。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-119">Here's a quick overview of the process.</span></span>

![自动扩展存档过程概述](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="3a2fc-121">对用户邮箱或共享邮箱启用存档。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="3a2fc-122">将创建一个具有 100 GB 存储空间的存档邮箱，并将存档邮箱的警告配额设置为 90 GB。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="3a2fc-123">管理员可自动展开邮箱的存档。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="3a2fc-124">当存档邮箱（包括 "可恢复的项目" 文件夹）达到 90 GB 时，它将转换为自动扩展存档，而 Office 365 会将存储空间添加到存档中。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive.</span></span> <span data-ttu-id="3a2fc-125">最多可能需要30天的时间来设置额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-125">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3a2fc-126">如果将邮箱置于保留状态或分配到 Office 365 保留策略，则在启用自动扩展存档时，存档邮箱的存储配额将增加到 110 GB。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-126">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="3a2fc-127">同样，存档警告配额增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-127">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="3a2fc-128">必要时，Office 365 会自动添加更多的存储空间。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-128">Office 365 automatically adds more storage space when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a2fc-129">仅对用于单个用户（或共享邮箱）的邮箱支持自动扩展存档，该邮箱的增长率不超过每日的 1 GB。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-129">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="3a2fc-130">用户的存档邮箱只供该用户使用。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-130">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="3a2fc-131">不允许使用日记、传输规则或自动转发规则将邮件复制到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-131">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="3a2fc-132">Microsoft 保留在用户的存档邮箱用于存储其他用户的存档数据的情况下或在不恰当使用的其他情况下，拒绝无限存档的权利。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-132">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of the inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="3a2fc-133">移动到其他存档存储空间的内容是什么？</span><span class="sxs-lookup"><span data-stu-id="3a2fc-133">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="3a2fc-134">为了高效地使用自动扩展存档存储，文件夹可能会移动。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-134">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="3a2fc-135">Office 365 确定在将其他存储添加到存档中时哪些文件夹发生移动。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-135">Office 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="3a2fc-136">有时移动文件夹时，会自动创建一个或多个子文件夹，并将原始文件夹中的项目分发到这些文件夹，以促进移动过程。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-136">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="3a2fc-137">在 Outlook 中查看文件夹列表的存档部分时，这些子文件夹将显示在原始文件夹下。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-137">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="3a2fc-138">Office 365 用于命名这些子文件夹的命名约定是\*\* \<文件夹\>名称 _yyyy （在 mmm dd，yyyy h_mm 上创建）\*\*，其中：</span><span class="sxs-lookup"><span data-stu-id="3a2fc-138">The naming convention that Office 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="3a2fc-139">**yyyy**是接收文件夹中邮件的年份。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-139">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="3a2fc-140">**mmm dd，yyyy h_m**是 Office 365 创建子文件夹的日期和时间，以 UTC 格式为单位，基于用户的时区和 Outlook 中的区域设置。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-140">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="3a2fc-141">下面的屏幕截图显示在邮件移动到自动展开的存档之前和之后的文件夹列表。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-141">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="3a2fc-142">**添加额外的存储之前**</span><span class="sxs-lookup"><span data-stu-id="3a2fc-142">**Before additional storage is added**</span></span>

![预配自动扩展存档之前的存档邮箱的文件夹列表](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="3a2fc-144">**添加额外的存储后**</span><span class="sxs-lookup"><span data-stu-id="3a2fc-144">**After additional storage is added**</span></span>

![预配自动扩展存档后存档邮箱的文件夹列表](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="3a2fc-146">如前面所述，Office 365 将项目移至子文件夹（并使用上述命名约定对其进行命名），以帮助将内容分发到辅助存档。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-146">As previously described, Office 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="3a2fc-147">但将项目移动到子文件夹可能并非总是如此。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-147">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="3a2fc-148">有时可能会将整个文件夹移动到辅助存档中。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-148">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="3a2fc-149">在这种情况下，文件夹将保留其原始名称。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-149">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="3a2fc-150">在 Outlook 的文件夹列表中，该文件夹已移动到辅助存档中并不明显。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-150">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="3a2fc-151">用于访问自动扩展存档中的项目的 Outlook 要求</span><span class="sxs-lookup"><span data-stu-id="3a2fc-151">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="3a2fc-152">若要访问存储在自动扩展的存档中的邮件，用户必须使用以下 Outlook 客户端之一：</span><span class="sxs-lookup"><span data-stu-id="3a2fc-152">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="3a2fc-153">Outlook 2016 或 Outlook 2019 for Windows</span><span class="sxs-lookup"><span data-stu-id="3a2fc-153">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="3a2fc-154">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="3a2fc-154">Outlook on the web</span></span>

- <span data-ttu-id="3a2fc-155">Outlook 2016 或 Outlook 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="3a2fc-155">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="3a2fc-156">以下是在使用 Outlook 或 web 上的 Outlook 访问存储在自动扩展的存档中的邮件时需要考虑的一些事项。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="3a2fc-157">您可以访问存档邮箱中的任何文件夹，包括已移动到自动扩展存储区域的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="3a2fc-158">您可以仅通过搜索文件夹本身来搜索已移动到其他存储区域的项目。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-158">You can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="3a2fc-159">这意味着，您必须在文件夹列表中选择 "存档" 文件夹，以选择**当前文件夹**选项作为搜索范围。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-159">This means that you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="3a2fc-160">同样，如果自动扩展存储区域中的文件夹包含子文件夹，则必须单独搜索每个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-160">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span>

- <span data-ttu-id="3a2fc-161">Outlook 中的项目计数和可读/未读的计数（在 Outlook 和 web 上的 outlook 中）在自动展开的存档中可能不准确。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-161">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="3a2fc-162">您可以删除子文件夹中指向自动扩展存储区域的项目，但不能删除该文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-162">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="3a2fc-163">无法使用 "恢复已删除邮件" 功能恢复从自动扩展的存储区域中删除的项目。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-163">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="3a2fc-164">自动扩展存档和其他 Office 365 合规性功能</span><span class="sxs-lookup"><span data-stu-id="3a2fc-164">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="3a2fc-165">本部分介绍自动扩展存档和其他 Office 365 合规性和数据管理功能之间的功能。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-165">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>

- <span data-ttu-id="3a2fc-166">**电子数据展示：** 当您使用 Office 365 电子数据展示工具（如内容搜索或就地电子数据展示）时，还会搜索自动扩展存档中的其他存储区域。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-166">**eDiscovery:** When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="3a2fc-167">**保留：** 将邮箱置于保留状态时，使用诸如 Exchange Online 中的诉讼保留或电子数据展示事例保留和合规性中心中的保留策略等工具，位于自动扩展存档中的内容也会置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-167">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="3a2fc-168">**邮件记录管理（MRM）：** 如果使用 Exchange Online 中的 MRM 删除策略以永久删除过期的邮箱项目，则也会删除位于自动展开的存档中的已过期项目。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-168">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="3a2fc-169">**导入服务：** 您可以使用 Office 365 导入服务将 PST 文件导入到用户的自动扩展存档中。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-169">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="3a2fc-170">你可以将 PST 文件中的最大为 100 GB 的数据导入用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-170">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="3a2fc-171">更多信息</span><span class="sxs-lookup"><span data-stu-id="3a2fc-171">More information</span></span>

<span data-ttu-id="3a2fc-172">有关自动扩展存档的更多技术详细信息，请参阅[Office 365：自动扩展存档常见问题解答](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。</span><span class="sxs-lookup"><span data-stu-id="3a2fc-172">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>
