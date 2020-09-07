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
ms.openlocfilehash: e12f46b68feb4b64ade14cfb046061d89e1a607c
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394709"
---
# <a name="learn-about-retention-for-exchange"></a><span data-ttu-id="0b3a6-103">了解用于 Exchange 的保留</span><span class="sxs-lookup"><span data-stu-id="0b3a6-103">Learn about retention for Exchange</span></span>

<span data-ttu-id="0b3a6-104">本文中的信息是对[了解保留](retention.md)的补充，因为它包含特定于 Exchange 的信息。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-104">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Exchange.</span></span>

## <a name="how-retention-works-for-exchange"></a><span data-ttu-id="0b3a6-105">用于 Exchange 的保留的工作原理</span><span class="sxs-lookup"><span data-stu-id="0b3a6-105">How retention works for Exchange</span></span>

<span data-ttu-id="0b3a6-106">邮箱和公用文件夹都使用“[可恢复的项目](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)”文件夹来保留项目。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-106">Both a mailbox and a public folder use the [Recoverable Items folder](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="0b3a6-107">只有已分配电子数据展示权限的人员才可以查看其他用户的“可恢复的项目”文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-107">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="0b3a6-108">当用户从“已删除邮件”文件夹以外的文件夹中删除邮件时，默认情况下，该邮件将移动到“已删除邮件”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-108">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="0b3a6-109">当用户删从“已删除邮件”文件夹中删除邮件时，该邮件将移动到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-109">When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder.</span></span> <span data-ttu-id="0b3a6-110">但是，用户可以软删除 (Shift+Delete) 任何文件夹中的邮件，这会避开“已删除邮件”文件夹，直接将邮件移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-110">However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="0b3a6-111">在你向 Exchange 数据应用保留设置时，计时器作业会定期评估“可恢复项”文件夹中的项。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-111">When you apply retention settings to Exchange data, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="0b3a6-112">如果某项与至少一个保留策略或保留标签的规则不匹配，则会从“可恢复项”文件夹中永久删除（亦称为“硬删除”）。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-112">If an item doesn't match the rules of at least one retention policy or retention label, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

<span data-ttu-id="0b3a6-113">计时器作业运行可能需要长达 7 天的时间，并且 Exchange 位置必须至少包含 10 MB。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-113">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="0b3a6-114">当用户尝试更改邮箱邮件的属性（如主题、正文、附件、发件人和收件人或邮件发送和接收日期）时，在提交更改之前，会将原始邮件的副本保存到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-114">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed.</span></span> <span data-ttu-id="0b3a6-115">每个后续更改都会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-115">This action happens for each subsequent change.</span></span> <span data-ttu-id="0b3a6-116">保留期结束时，将永久删除“可恢复的项目”文件夹中的副本。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-116">At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="0b3a6-117">在向 Exchange 内容应用保留设置后，内容路径取决于保留设置是“保留后删除”、“仅保留”还是“仅删除”。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-117">After retention settings are applied to Exchange content, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="0b3a6-118">如果保留设置为“保留后删除”：</span><span class="sxs-lookup"><span data-stu-id="0b3a6-118">When the retention settings are to retain and delete:</span></span>

![电子邮件和公用文件夹中的保留流关系图](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="0b3a6-120">**如果邮件在保留期限内被用户修改或永久删除**（使用 SHIFT+DELETE 或从“已删除邮件”中删除）：邮件会移动到（被编辑时会复制到）“可恢复的项目”文件夹。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-120">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="0b3a6-121">因此会定期运行一个计时器作业，识别超过保留期限的邮件，并在保留期限结束后 14 天内将这些邮件永久删除。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-121">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="0b3a6-122">请注意，默认设置是 14 天，但可以将其配置为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-122">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="0b3a6-123">**如果邮件在保留期限内未被修改或删除**：对邮箱中的所有文件夹定期运行相同的流程，识别超过保留期限的邮件，并在保留期限结束后 14 天内将这些邮件永久删除。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-123">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="0b3a6-124">请注意，默认设置是 14 天，但可以将其配置为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-124">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="0b3a6-125">如果保留设置为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化：</span><span class="sxs-lookup"><span data-stu-id="0b3a6-125">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="0b3a6-126">“仅保留”保留设置的内容路径</span><span class="sxs-lookup"><span data-stu-id="0b3a6-126">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="0b3a6-127">**如果有人在保持期内修改或删除项**：则会在“可恢复的项”文件夹中创建原始项的副本，并保留到保持期结束，然后“可恢复的项”文件夹中的副本会在到期后的 14 天后永久删除。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-127">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="0b3a6-128">**如果项在保持期内未遭修改或删除**：保持期前后无变化；项仍保留在它的原始位置上。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-128">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="0b3a6-129">“仅删除”保留设置的内容路径</span><span class="sxs-lookup"><span data-stu-id="0b3a6-129">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="0b3a6-130">**如果项目在配置的期限内未遭删除**：在保留策略中配置的期限结束时，项目会移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-130">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="0b3a6-131">**如果项目在配置的期限内遭到删除**：项目会立即移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-131">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="0b3a6-132">如果用户从“可恢复的项”文件夹中删除项或清空此文件夹，该项将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-132">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="0b3a6-133">否则，项会在“可恢复的项”文件夹中保留 14 天后永久删除。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-133">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="0b3a6-134">如果某用户离开组织</span><span class="sxs-lookup"><span data-stu-id="0b3a6-134">When a user leaves the organization</span></span> 

<span data-ttu-id="0b3a6-135">如果某用户离开组织，且此用户的邮箱包含在保留策略内，那么在此用户的 Microsoft 365 帐户遭到删除后，其邮箱会变成非活动状态。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-135">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="0b3a6-136">非活动邮箱的内容仍受在邮箱变成非活动状态之前对邮箱应用的所有保留策略约束，且内容支持电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-136">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="0b3a6-137">有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-137">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="0b3a6-138">配置指南</span><span class="sxs-lookup"><span data-stu-id="0b3a6-138">Configuration guidance</span></span>

<span data-ttu-id="0b3a6-139">如果你刚开始在 Microsoft 365 中配置保留，请参阅[开始使用保留策略和保留标签](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="0b3a6-139">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="0b3a6-140">如果你已准备好配置 Exchange 的保留策略或保留标签，请参阅以下说明：</span><span class="sxs-lookup"><span data-stu-id="0b3a6-140">If you're ready to configure a retention policy or retention label for Exchange, see the following instructions:</span></span>
- [<span data-ttu-id="0b3a6-141">创建和配置保留策略</span><span class="sxs-lookup"><span data-stu-id="0b3a6-141">Create and configure retention policies</span></span>](create-retention-policies.md)
- [<span data-ttu-id="0b3a6-142">创建保留标签并在应用中应用它们</span><span class="sxs-lookup"><span data-stu-id="0b3a6-142">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="0b3a6-143">自动向内容应用保留标签</span><span class="sxs-lookup"><span data-stu-id="0b3a6-143">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)