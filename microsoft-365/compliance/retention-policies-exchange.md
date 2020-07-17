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
description: 了解专门适用于 Exchange 电子邮件和 Exchange 公用文件夹的保留行为。
ms.openlocfilehash: 57f0bf7737522b0435b076fee46edd1736efd856
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080089"
---
# <a name="learn-about-retention-policies-for-exchange"></a><span data-ttu-id="cf04b-103">了解 Exchange 的保留策略</span><span class="sxs-lookup"><span data-stu-id="cf04b-103">Learn about retention policies for Exchange</span></span>

<span data-ttu-id="cf04b-104">本文中的信息是对[了解保留策略](retention-policies.md)的补充，因为它包含特定于 Exchange 的信息。</span><span class="sxs-lookup"><span data-stu-id="cf04b-104">The information in this article supplements [Learn about retention policies](retention-policies.md) because it has information that's specific to Exchange.</span></span>

## <a name="how-a-retention-policy-works-with-exchange"></a><span data-ttu-id="cf04b-105">保留策略如何作用于 Exchange</span><span class="sxs-lookup"><span data-stu-id="cf04b-105">How a retention policy works with Exchange</span></span>

<span data-ttu-id="cf04b-106">对于用户的邮件、日历和其他邮箱项目，保留策略在邮箱级别应用。</span><span class="sxs-lookup"><span data-stu-id="cf04b-106">For a user's mail, calendar, and other mailbox items, a retention policy is applied at the level of a mailbox.</span></span>

<span data-ttu-id="cf04b-107">对于公用文件夹，保留策略将应用于所有公用文件夹，而不是文件夹或邮箱级别。</span><span class="sxs-lookup"><span data-stu-id="cf04b-107">For public folders, a retention policy is applied to all public folders and not at the folder or mailbox level.</span></span>

<span data-ttu-id="cf04b-108">在为这些位置配置保留策略时，会将以下邮件项目包含在内：包含任何附件的邮件（包括草稿）、任务和日历项目（如果有结束日期）以及便签。</span><span class="sxs-lookup"><span data-stu-id="cf04b-108">When you configure a retention policy for these locations, the following mail items are included: Mail messages (includes drafts) with any attachments, tasks and calendar items when they have an end date, and notes.</span></span> <span data-ttu-id="cf04b-109">其中不包括联系人以及不具备结束日期的任何任务和日历项目。</span><span class="sxs-lookup"><span data-stu-id="cf04b-109">Contacts, and any tasks and calendar items that don't have an end date are not included.</span></span> <span data-ttu-id="cf04b-110">存储在邮箱中的其他项目（如 Skype 和 Teams 保存的消息）包含在其单独的保留策略中。</span><span class="sxs-lookup"><span data-stu-id="cf04b-110">Other items stored in a mailbox, such as Skype and Teams saved messages, are included with their separate retention policy.</span></span>

<span data-ttu-id="cf04b-111">邮箱和公用文件夹都使用“[可恢复的项目](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder)”文件夹来保留项目。</span><span class="sxs-lookup"><span data-stu-id="cf04b-111">Both a mailbox and a public folder use the [Recoverable Items folder](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) to retain items.</span></span> <span data-ttu-id="cf04b-112">只有已分配电子数据展示权限的人员才可以查看其他用户的“可恢复的项目”文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="cf04b-112">Only people who have been assigned eDiscovery permissions can view items in another user's Recoverable Items folder.</span></span>
  
<span data-ttu-id="cf04b-113">当用户从“已删除邮件”文件夹以外的文件夹中删除邮件时，默认情况下，该邮件将移动到“已删除邮件”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cf04b-113">When a person deletes a message in a folder other than the Deleted Items folder, by default, the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="cf04b-114">当用户删从“已删除邮件”文件夹中删除邮件时，该邮件将移动到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cf04b-114">When a person deletes an item in the Deleted Items folder, the message is moved to the Recoverable Items folder.</span></span> <span data-ttu-id="cf04b-115">但是，用户可以软删除 (Shift+Delete) 任何文件夹中的邮件，这会避开“已删除邮件”文件夹，直接将邮件移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cf04b-115">However, a user can soft delete an item (Shift+Delete) in any folder, which bypasses the Deleted Items folder and moves the item directly to the Recoverable Items folder.</span></span>
  
<span data-ttu-id="cf04b-116">将保留策略应用于 Exchange 位置时，计时器作业会定期评估“可恢复的项目”文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="cf04b-116">When you apply a retention policy to an Exchange location, a timer job periodically evaluates items in the Recoverable Items folder.</span></span> <span data-ttu-id="cf04b-117">如果某个项目与至少一个保留策略的规则不匹配，则将从“可恢复项目”文件夹中永久删除该项目（也称为硬删除）。</span><span class="sxs-lookup"><span data-stu-id="cf04b-117">If an item doesn't match the rules of at least one retention policy, the item is permanently deleted (also called hard deleted) from the Recoverable Items folder.</span></span>

<span data-ttu-id="cf04b-118">计时器作业运行可能需要长达 7 天的时间，并且 Exchange 位置必须至少包含 10 MB。</span><span class="sxs-lookup"><span data-stu-id="cf04b-118">The timer job can take up to seven days to run and the Exchange location must contain at least 10 MB.</span></span>
  
<span data-ttu-id="cf04b-119">当用户尝试更改邮箱邮件的属性（如主题、正文、附件、发件人和收件人或邮件发送和接收日期）时，在提交更改之前，会将原始邮件的副本保存到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cf04b-119">When a user attempts to change properties of a mailbox item—such as the subject, body, attachments, senders and recipients, or date sent or received for a message—a copy of the original item is saved to the Recoverable Items folder before the change is committed.</span></span> <span data-ttu-id="cf04b-120">每个后续更改都会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cf04b-120">This action happens for each subsequent change.</span></span> <span data-ttu-id="cf04b-121">保留期结束时，将永久删除“可恢复的项目”文件夹中的副本。</span><span class="sxs-lookup"><span data-stu-id="cf04b-121">At the end of the retention period, copies in the Recoverable Items folder are permanently deleted.</span></span>

<span data-ttu-id="cf04b-122">将保留策略分配给邮箱或公用文件夹后，内容路径取决于保留设置是“保留后删除”、“仅保留”还是“仅删除”。</span><span class="sxs-lookup"><span data-stu-id="cf04b-122">After a retention policy is assigned to a mailbox or public folder, the paths the content takes depend on whether the retention settings are to retain and delete, to retain only, or delete only.</span></span>

<span data-ttu-id="cf04b-123">如果保留设置为“保留后删除”：</span><span class="sxs-lookup"><span data-stu-id="cf04b-123">When the retention settings are to retain and delete:</span></span>

![电子邮件和公用文件夹中的保留流关系图](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. <span data-ttu-id="cf04b-125">**如果邮件在保留期限内被用户修改或永久删除**（使用 SHIFT+DELETE 或从“已删除邮件”中删除）：邮件会移动到（被编辑时会复制到）“可恢复的项目”文件夹。</span><span class="sxs-lookup"><span data-stu-id="cf04b-125">**If the item is modified or permanently deleted** by the user (either SHIFT+DELETE or deleted from Deleted Items) during the retention period: The item is moved (or copied, in the case of edit) to the Recoverable Items folder.</span></span> <span data-ttu-id="cf04b-126">因此会定期运行一个计时器作业，识别超过保留期限的邮件，并在保留期限结束后 14 天内将这些邮件永久删除。</span><span class="sxs-lookup"><span data-stu-id="cf04b-126">There, a timer job runs periodically and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="cf04b-127">请注意，默认设置是 14 天，但可以将其配置为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="cf04b-127">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span>

2. <span data-ttu-id="cf04b-128">**如果邮件在保留期限内未被修改或删除**：对邮箱中的所有文件夹定期运行相同的流程，识别超过保留期限的邮件，并在保留期限结束后 14 天内将这些邮件永久删除。</span><span class="sxs-lookup"><span data-stu-id="cf04b-128">**If the item is not modified or deleted** during the retention period: The same process runs periodically on all folders in the mailbox and identifies items whose retention period has expired, and these items are permanently deleted within 14 days of the end of the retention period.</span></span> <span data-ttu-id="cf04b-129">请注意，默认设置是 14 天，但可以将其配置为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="cf04b-129">Note that 14 days is the default setting, but it can be configured up to 30 days.</span></span> 

<span data-ttu-id="cf04b-130">如果保留设置为“仅保留”或“仅删除”，内容路径在“保留后删除”策略的基础上有所变化：</span><span class="sxs-lookup"><span data-stu-id="cf04b-130">When the retention settings are retain-only, or delete-only, the contents paths are variations of retain and delete:</span></span>

### <a name="content-paths-for-retain-only-retention-settings"></a><span data-ttu-id="cf04b-131">“仅保留”保留设置的内容路径</span><span class="sxs-lookup"><span data-stu-id="cf04b-131">Content paths for retain-only retention settings</span></span>

1. <span data-ttu-id="cf04b-132">**如果有人在保持期内修改或删除项**：则会在“可恢复的项”文件夹中创建原始项的副本，并保留到保持期结束，然后“可恢复的项”文件夹中的副本会在到期后的 14 天后永久删除。</span><span class="sxs-lookup"><span data-stu-id="cf04b-132">**If the item is modified or deleted** during the retention period: A copy of the original item is created in the Recoverable Items folder and retained until the end of the retention period, when the copy in the Recoverable Items folder is permanently deleted within 14 days after the item expires.</span></span> 

2. <span data-ttu-id="cf04b-133">**如果项在保持期内未遭修改或删除**：保持期前后无变化；项仍保留在它的原始位置上。</span><span class="sxs-lookup"><span data-stu-id="cf04b-133">**If the item is not modified or deleted** during the retention period: Nothing happens before and after the retention period; the item remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-settings"></a><span data-ttu-id="cf04b-134">“仅删除”保留设置的内容路径</span><span class="sxs-lookup"><span data-stu-id="cf04b-134">Content paths for delete-only retention settings</span></span>

1. <span data-ttu-id="cf04b-135">**如果项目在配置的期限内未遭删除**：在保留策略中配置的期限结束时，项目会移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cf04b-135">**If the item is not deleted** during the configured period: At the end of the configured period in the retention policy, the item is moved to the Recoverable Items folder.</span></span> 

2. <span data-ttu-id="cf04b-136">**如果项目在配置的期限内遭到删除**：项目会立即移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cf04b-136">**If the item is deleted** during the configured period: The item is immediately moved to the Recoverable Items folder.</span></span> <span data-ttu-id="cf04b-137">如果用户从“可恢复的项”文件夹中删除项或清空此文件夹，该项将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="cf04b-137">If a user deletes the item from there or empties the Recoverable Items folder, the item is permanently deleted.</span></span> <span data-ttu-id="cf04b-138">否则，项会在“可恢复的项”文件夹中保留 14 天后永久删除。</span><span class="sxs-lookup"><span data-stu-id="cf04b-138">Otherwise, the item is permanently deleted after being in the Recoverable Items folder for 14 days.</span></span> 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a><span data-ttu-id="cf04b-139">从保留策略中排除特定类型的 Exchange 项目</span><span class="sxs-lookup"><span data-stu-id="cf04b-139">Excluding specific types of Exchange items from a retention policy</span></span>

<span data-ttu-id="cf04b-140">通过使用 PowerShell，当保留设置对应的是仅保留时，可以从保留策略中排除特定类型的 Exchange 项目。</span><span class="sxs-lookup"><span data-stu-id="cf04b-140">By using PowerShell, you can exclude specific types of Exchange items from a retention policy when the retention settings are for retain-only.</span></span> <span data-ttu-id="cf04b-141">例如，可以排除邮箱中的语音邮件、即时消息对话和其他 Skype for Business Online 内容。</span><span class="sxs-lookup"><span data-stu-id="cf04b-141">For example, you can exclude voicemail messages, IM conversations, and other Skype for Business Online content in mailboxes.</span></span> <span data-ttu-id="cf04b-142">此外，还可以排除日历、便笺和任务项目。</span><span class="sxs-lookup"><span data-stu-id="cf04b-142">You can also exclude calendar, note, and task items.</span></span> <span data-ttu-id="cf04b-143">此功能仅可通过 PowerShell 使用；使用 Microsoft 365 合规中心中的向导创建保留策略时，此功能不可用。</span><span class="sxs-lookup"><span data-stu-id="cf04b-143">This capability is available only by using PowerShell; it's not available when you create a retention policy by using the wizard in the Microsoft 365 compliance center.</span></span>
  
<span data-ttu-id="cf04b-144">若要在保留策略中排除 Exchange 项目的选定类型，请将 `ExcludedItemClasses` 参数与 [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) 和 [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule) cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="cf04b-144">To exclude your selected types for Exchange items in a retention policy, use the  `ExcludedItemClasses` parameter with the [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) and  [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule) cmdlets.</span></span>

<span data-ttu-id="cf04b-145">若要使用保留策略 cmdlet，必须先[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="cf04b-145">To use the retention policies cmdlets, you must first [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="cf04b-146">如果某用户离开组织</span><span class="sxs-lookup"><span data-stu-id="cf04b-146">When a user leaves the organization</span></span> 

<span data-ttu-id="cf04b-147">如果某用户离开组织，且此用户的邮箱包含在保留策略内，那么在此用户的 Microsoft 365 帐户遭到删除后，其邮箱会变成非活动状态。</span><span class="sxs-lookup"><span data-stu-id="cf04b-147">If a user leaves your organization and the user's mailbox is included in a retention policy, the mailbox becomes an inactive mailbox when the user's Microsoft 365 account is deleted.</span></span> <span data-ttu-id="cf04b-148">非活动邮箱的内容仍受在邮箱变成非活动状态之前对邮箱应用的所有保留策略约束，且内容支持电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="cf04b-148">The contents of an inactive mailbox are still subject to any retention policy that was placed on the mailbox before it was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="cf04b-149">有关详细信息，请参阅 [Exchange Online 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="cf04b-149">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a><span data-ttu-id="cf04b-150">如何配置 Exchange 的保留策略</span><span class="sxs-lookup"><span data-stu-id="cf04b-150">How to configure a retention policy for Exchange</span></span>

<span data-ttu-id="cf04b-151">按照[创建和配置保留策略](create-retention-policies.md)以及向导的**选择位置**页面的说明，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="cf04b-151">Follow the instructions for [Create and configure retention policies](create-retention-policies.md) and for the **Choose locations**  page of the wizard, select one of the following options:</span></span>

- <span data-ttu-id="cf04b-152">**仅将策略应用于 Exchange 电子邮件、公用文件夹、Office 365 组、OneDrive 和 SharePoint 文档中的内容**</span><span class="sxs-lookup"><span data-stu-id="cf04b-152">**Apply policy only to content in Exchange email, public folders, Office 365 groups, OneDrive and SharePoint documents**</span></span>

- <span data-ttu-id="cf04b-153">**让我选择特定位置** > **Exchange 电子邮件**、**Exchange 公用文件夹**和 **Office 365 组**。</span><span class="sxs-lookup"><span data-stu-id="cf04b-153">**Let me choose specific locations** > **Exchange email**, **Exchange public folders**, and **Office 365 groups**.</span></span>

<span data-ttu-id="cf04b-154">即使 Microsoft 365 组有 Exchange 邮箱，涵盖整个 **Exchange 电子邮件**位置的保留策略也不会包含 Microsoft 365 组邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="cf04b-154">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="cf04b-155">若要保留这些邮箱中的内容，请选择 **Office 365 组**的位置。</span><span class="sxs-lookup"><span data-stu-id="cf04b-155">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>
