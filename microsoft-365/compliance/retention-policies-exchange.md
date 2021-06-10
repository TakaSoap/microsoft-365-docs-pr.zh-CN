---
title: 了解 Exchange 的保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解用于 Exchange 的保留的工作原理。
ms.openlocfilehash: efb95b22355bff292ef63c77fb77fb5a15d66722
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861127"
---
# <a name="learn-about-retention-for-exchange"></a><span data-ttu-id="2cc7e-103">了解用于 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="2cc7e-103">Learn about retention for Exchange</span></span>

<span data-ttu-id="2cc7e-104">本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Exchange 的信息。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-104">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Exchange.</span></span>  <span data-ttu-id="2cc7e-105">有关其他工作负载，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2cc7e-105">For other workloads, see:</span></span>

- [<span data-ttu-id="2cc7e-106">了解用于 SharePoint 和 OneDrive 的保留</span><span class="sxs-lookup"><span data-stu-id="2cc7e-106">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="2cc7e-107">了解用于 Microsoft Teams 的保留</span><span class="sxs-lookup"><span data-stu-id="2cc7e-107">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="2cc7e-108">了解用于 Yammer 的保留</span><span class="sxs-lookup"><span data-stu-id="2cc7e-108">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="2cc7e-109">保留和删除包括哪些内容</span><span class="sxs-lookup"><span data-stu-id="2cc7e-109">What's included for retention and deletion</span></span>

<span data-ttu-id="2cc7e-110">可通过使用保留策略和保留标签来保留和删除以下 Exchange 项目：带有任何附件的邮件（包括草稿）、具有结束日期的任务和注释。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-110">The following Exchange items can be retained and deleted by using retention policies and retention labels: Mail messages (includes drafts) with any attachments, tasks when they have an end date, and notes.</span></span> 

<span data-ttu-id="2cc7e-111">保留策略支持具有结束日期的日历项目，但保留标签不支持。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-111">Calendar items that have an end date are supported for retention policies but aren't supported for retention labels.</span></span>

<span data-ttu-id="2cc7e-112">不支持联系人以及任何没有结束日期的任务和日历项目。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-112">Contacts, and any tasks and calendar items that don't have an end date are not supported.</span></span>

<span data-ttu-id="2cc7e-p102">存储在邮箱中的其他项目（如 Skype 和 Teams 消息）不包括在 Exchange 的保留策略或标签内。这些项目有自己的保留策略。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-p102">Other items stored in a mailbox, such as Skype and Teams messages, aren't included in retention policies or labels for Exchange. These items have their own retention policies.</span></span>

## <a name="how-retention-works-for-exchange"></a><span data-ttu-id="2cc7e-115">用于 Exchange 的保留的工作原理</span><span class="sxs-lookup"><span data-stu-id="2cc7e-115">How retention works for Exchange</span></span>

<span data-ttu-id="2cc7e-116">邮箱和公用文件夹都使用“[可恢复的项目](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)”文件夹来保留项目。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-116">Both a mailbox and a public folder use the [Recoverable Items folder](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="2cc7e-117">只有已分配电子数据展示权限的人员才可以查看其他用户的“可恢复的项目”文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-117">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="2cc7e-p104">当用户从“已删除邮件”文件夹以外的文件夹中删除邮件时，默认情况下，该邮件将移动到“已删除邮件”文件夹中。当用户从“已删除邮件”文件夹中删除邮件时，该邮件将移动到“可恢复的项目”文件夹中。但是，用户可以软删除 (Shift+Delete) 任何文件夹中的邮件，这会避开“已删除邮件”文件夹，直接将邮件移至“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-p104">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder. When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder. However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="2cc7e-121">将保留设置应用于 Exchange 数据时，计时器作业会定期评估“可恢复的项目”文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-121">When you apply retention settings to Exchange data, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="2cc7e-122">如果某项目与至少一个保留策略或保留标签的规则不匹配，则将从“可恢复的项目”文件夹中永久删除该项目（亦称为“硬删除”）。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-122">If an item doesn't match the rules of at least one retention policy or retention label to retain the item, it is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc7e-123">由于[第一个保留策略](retention.md#the-principles-of-retention-or-what-takes-precedence)，如果由于另一个保留策略或保留标签而必须保留同一项目，或者由于法律或调查原因而处于电子数据展示保留状态，则永久删除始终处于暂停状态。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-123">Because of the [first principle of retention](retention.md#the-principles-of-retention-or-what-takes-precedence), permanent deletion is always suspended if the same item must be retained because of another retention policy or retention label, or it is under eDiscovery holds for legal or investigative reasons.</span></span>

<span data-ttu-id="2cc7e-124">计时器作业运行可能需要长达七天时间，并且 Exchange 位置必须至少包含 10 MB。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-124">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="2cc7e-p106">当用户尝试更改邮箱邮件的属性（如主题、正文、附件、发件人和收件人或邮件发送和接收日期）时，在提交更改之前，会将原始邮件的副本保存到“可恢复的项目”文件夹中。每个后续更改都会执行此操作。保留期结束时，将永久删除“可恢复的项目”文件夹中的副本。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-p106">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed. This action happens for each subsequent change. At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="2cc7e-128">在向 Exchange 内容应用保留设置后，内容路径取决于保留设置是“保留后删除”、“仅保留”还是“仅删除”。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-128">After retention settings are applied to Exchange content, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="2cc7e-129">如果保留设置为“保留后删除”：</span><span class="sxs-lookup"><span data-stu-id="2cc7e-129">When the retention settings are to retain and delete:</span></span>

![电子邮件和公用文件夹中的保留流关系图](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="2cc7e-131">**如果邮件在保留期限内被用户修改或永久删除**（使用 SHIFT+DELETE 或从“已删除邮件”中删除）：邮件会移动到（被编辑时会复制到）“可恢复的项目”文件夹。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-131">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="2cc7e-132">因此会定期运行一个计时器作业，识别超过保留期限的邮件，并在保留期限结束后 14 天内将这些邮件永久删除。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-132">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="2cc7e-133">请注意，默认设置是 14 天，但可以将其配置为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-133">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="2cc7e-p108">**如果未在保留期内修改或删除邮件**：对邮箱中的所有文件夹定期运行相同的流程，识别超过保留期限的邮件，并在保留期限结束后 14 天内将这些邮件永久删除。请注意，默认设置是 14 天，但可以将其配置为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-p108">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period. Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="2cc7e-136">如果保留设置为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化：</span><span class="sxs-lookup"><span data-stu-id="2cc7e-136">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="2cc7e-137">“仅保留”保留设置的内容路径</span><span class="sxs-lookup"><span data-stu-id="2cc7e-137">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="2cc7e-138">**如果有人在保持期内修改或删除项**：则会在“可恢复的项”文件夹中创建原始项的副本，并保留到保持期结束，然后“可恢复的项”文件夹中的副本会在到期后的 14 天后永久删除。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-138">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="2cc7e-139">**如果项在保持期内未遭修改或删除**：保持期前后无变化；项仍保留在它的原始位置上。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-139">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="2cc7e-140">“仅删除”保留设置的内容路径</span><span class="sxs-lookup"><span data-stu-id="2cc7e-140">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="2cc7e-141">**如果项目在配置的期限内未遭删除**：在保留策略中配置的期限结束时，项目会移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-141">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="2cc7e-142">**如果项目在配置的期限内遭到删除**：项目会立即移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-142">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="2cc7e-143">如果用户从“可恢复的项”文件夹中删除项或清空此文件夹，该项将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-143">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="2cc7e-144">否则，项会在“可恢复的项”文件夹中保留 14 天后永久删除。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-144">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="2cc7e-145">如果某用户离开组织</span><span class="sxs-lookup"><span data-stu-id="2cc7e-145">When a user leaves the organization</span></span> 

<span data-ttu-id="2cc7e-146">如果某用户离开组织，且此用户的邮箱包含在保留策略内，那么在此用户的 Microsoft 365 帐户遭到删除后，其邮箱会变成非活动状态。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-146">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="2cc7e-147">非活动邮箱的内容仍受在邮箱变成非活动状态之前对邮箱应用的所有保留策略约束，且内容支持电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-147">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="2cc7e-148">有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-148">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="2cc7e-149">配置指南</span><span class="sxs-lookup"><span data-stu-id="2cc7e-149">Configuration guidance</span></span>

<span data-ttu-id="2cc7e-150">如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="2cc7e-150">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="2cc7e-151">如果你已准备好配置 Exchange 的保留策略或保留标签，请参阅以下说明：</span><span class="sxs-lookup"><span data-stu-id="2cc7e-151">If you're ready to configure a retention policy or retention label for Exchange, see the following instructions:</span></span>
- [<span data-ttu-id="2cc7e-152">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="2cc7e-152">Create and configure retention policies</span></span>](create-retention-policies.md)
- [<span data-ttu-id="2cc7e-153">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="2cc7e-153">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="2cc7e-154">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="2cc7e-154">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)