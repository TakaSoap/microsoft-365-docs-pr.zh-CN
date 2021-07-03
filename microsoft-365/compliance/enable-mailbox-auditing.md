---
title: 管理邮箱审核
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: 默认情况下，邮箱审核日志记录在邮箱Microsoft 365 (也称为默认邮箱审核或默认启用邮箱审核) 。 这意味着邮箱所有者、代理人和管理员执行的某些操作会自动记录在邮箱 审核日志 中，您可以在其中搜索对邮箱执行的活动。
ms.openlocfilehash: f74cb23a029d4710a19aeb18999169f6adc636a4
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287025"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="469bf-104">管理邮箱审核</span><span class="sxs-lookup"><span data-stu-id="469bf-104">Manage mailbox auditing</span></span>

<span data-ttu-id="469bf-105">从 2019 年 1 月开始，Microsoft 将默认启用所有组织的邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="469bf-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all organizations.</span></span> <span data-ttu-id="469bf-106">这意味着自动记录由邮箱所有者、代理人和管理员执行的某些操作，当您在邮箱邮箱中搜索相应的邮箱审核记录时，这些记录审核日志。</span><span class="sxs-lookup"><span data-stu-id="469bf-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="469bf-107">默认情况下，在启用邮箱审核之前，您必须为组织的每个用户邮箱手动启用它。</span><span class="sxs-lookup"><span data-stu-id="469bf-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="469bf-108">以下是默认情况下启用邮箱审核的一些好处：</span><span class="sxs-lookup"><span data-stu-id="469bf-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="469bf-109">创建新邮箱时将自动启用审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="469bf-110">无需为新用户手动启用它。</span><span class="sxs-lookup"><span data-stu-id="469bf-110">You don't need to manually enable it for new users.</span></span>
- <span data-ttu-id="469bf-111">无需管理审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="469bf-112">默认情况下，会针对管理员、代理和所有者管理员 (类型的每个预定义邮箱操作) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>
- <span data-ttu-id="469bf-113">当 Microsoft 发布新的邮箱操作时，该操作可能会自动添加到默认审核的邮箱操作列表中 (受具有相应许可证的用户) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-113">When Microsoft releases a new mailbox action, the action might be automatically added to the list of mailbox actions that are audited by default (subject to the user having the appropriate license).</span></span> <span data-ttu-id="469bf-114">这意味着无需监视在邮箱上添加新操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-114">This means you don't need to monitor add new actions on mailboxes.</span></span>
- <span data-ttu-id="469bf-115">由于要审核组织中所有邮箱的相同操作，因此 (组织中具有一致的邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="469bf-116">默认情况下，对于发布邮箱审核，需要记住的重要一点就是：无需执行任何操作来管理邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-116">The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="469bf-117">但是，若要了解更多信息，请根据默认设置自定义邮箱审核，或完全关闭它，本文将帮助你。</span><span class="sxs-lookup"><span data-stu-id="469bf-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this article can help you.</span></span>
> - <span data-ttu-id="469bf-118">默认情况下，只有 E5 用户的邮箱审核事件在安全 & 合规中心的 审核日志 搜索中或通过 Office 365 管理活动 API 提供。</span><span class="sxs-lookup"><span data-stu-id="469bf-118">By default, only mailbox audit events for E5 users are available in audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span> <span data-ttu-id="469bf-119">有关详细信息，请参阅本文 [中的](#more-information) 详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="469bf-119">For more information, see the [More information](#more-information) section in this article.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="469bf-120">验证是否已默认启用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-120">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="469bf-121">若要验证默认情况下是否为组织启用邮箱审核，请运行[PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)Exchange Online命令：</span><span class="sxs-lookup"><span data-stu-id="469bf-121">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="469bf-122">值 **False** 表示默认情况下为组织启用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-122">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="469bf-123">默认情况下，此启用的组织值会覆盖特定邮箱上的邮箱审核设置。</span><span class="sxs-lookup"><span data-stu-id="469bf-123">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="469bf-124">例如，如果对邮箱禁用邮箱审核 (则邮箱) 的 *AuditEnabled* 属性为 **False，** 则仍将审核邮箱的默认邮箱操作，因为默认情况下会为组织启用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-124">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="469bf-125">若要对特定邮箱禁用邮箱审核，请为邮箱所有者和已委派邮箱访问权限的其他用户配置邮箱审核绕过。</span><span class="sxs-lookup"><span data-stu-id="469bf-125">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="469bf-126">有关详细信息，请参阅本文中的 [绕过邮箱审核](#bypass-mailbox-audit-logging) 日志记录部分。</span><span class="sxs-lookup"><span data-stu-id="469bf-126">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="469bf-127">当组织默认启用邮箱审核时，受影响邮箱的 *AuditEnabled* 属性不会从 **False** 更改为 **True**。</span><span class="sxs-lookup"><span data-stu-id="469bf-127">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="469bf-128">换句话说，默认情况下启用的邮箱审核将忽略邮箱上的 *AuditEnabled* 属性。</span><span class="sxs-lookup"><span data-stu-id="469bf-128">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="469bf-129">支持的邮箱类型</span><span class="sxs-lookup"><span data-stu-id="469bf-129">Supported mailbox types</span></span>

<span data-ttu-id="469bf-130">下表显示了默认情况下邮箱审核当前支持的邮箱类型：</span><span class="sxs-lookup"><span data-stu-id="469bf-130">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

<br>

****

|<span data-ttu-id="469bf-131">邮箱类型</span><span class="sxs-lookup"><span data-stu-id="469bf-131">Mailbox type</span></span>|<span data-ttu-id="469bf-132">受支持</span><span class="sxs-lookup"><span data-stu-id="469bf-132">Supported</span></span>|
|---|:---:|
|<span data-ttu-id="469bf-133">用户邮箱</span><span class="sxs-lookup"><span data-stu-id="469bf-133">User mailboxes</span></span>|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-135">共享邮箱</span><span class="sxs-lookup"><span data-stu-id="469bf-135">Shared mailboxes</span></span>|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-137">Microsoft 365组邮箱</span><span class="sxs-lookup"><span data-stu-id="469bf-137">Microsoft 365 Group mailboxes</span></span>|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-139">资源邮箱</span><span class="sxs-lookup"><span data-stu-id="469bf-139">Resource mailboxes</span></span>||
|<span data-ttu-id="469bf-140">公用文件夹邮箱</span><span class="sxs-lookup"><span data-stu-id="469bf-140">Public folder mailboxes</span></span>||
|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="469bf-141">登录类型和邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-141">Logon types and mailbox actions</span></span>

<span data-ttu-id="469bf-142">登录类型对对邮箱执行审核操作的用户进行分类。</span><span class="sxs-lookup"><span data-stu-id="469bf-142">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="469bf-143">以下列表介绍了邮箱审核日志记录中使用的登录类型：</span><span class="sxs-lookup"><span data-stu-id="469bf-143">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="469bf-144">**所有者**：邮箱 (与邮箱邮箱关联的帐户) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-144">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>
- <span data-ttu-id="469bf-145">**委派**：</span><span class="sxs-lookup"><span data-stu-id="469bf-145">**Delegate**:</span></span>
  - <span data-ttu-id="469bf-146">已分配有其他邮箱的 SendAs、SendOnBehalf 或 FullAccess 权限的用户。</span><span class="sxs-lookup"><span data-stu-id="469bf-146">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>
  - <span data-ttu-id="469bf-147">已分配有用户邮箱的 FullAccess 权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="469bf-147">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>
- <span data-ttu-id="469bf-148">**管理员**：</span><span class="sxs-lookup"><span data-stu-id="469bf-148">**Admin**:</span></span>
  - <span data-ttu-id="469bf-149">使用下列 Microsoft 电子数据展示工具之一搜索邮箱：</span><span class="sxs-lookup"><span data-stu-id="469bf-149">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>
    - <span data-ttu-id="469bf-150">合规性中心的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="469bf-150">Content Search in the Compliance center.</span></span>
    - <span data-ttu-id="469bf-151">合规性中心Advanced eDiscovery电子数据展示或电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="469bf-151">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>
    - <span data-ttu-id="469bf-152">In-Place电子数据展示Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="469bf-152">In-Place eDiscovery in Exchange Online.</span></span>
  - <span data-ttu-id="469bf-153">通过使用 MAPI 编辑器访问Microsoft Exchange Server邮箱。</span><span class="sxs-lookup"><span data-stu-id="469bf-153">The mailbox is accessed by using the Microsoft Exchange Server MAPI Editor.</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="469bf-154">用户邮箱和共享邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-154">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="469bf-155">下表描述了用户邮箱和共享邮箱的邮箱审核日志记录中可用的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-155">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="469bf-156">复选标记 (</span><span class="sxs-lookup"><span data-stu-id="469bf-156">A check mark (</span></span>![复选标记](../media/checkmark.png)<span data-ttu-id="469bf-158">) 指示可以针对登录类型记录邮箱操作， (并非所有操作都可用于所有登录类型) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-158">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>
- <span data-ttu-id="469bf-159">在选中 () 默认情况下会记录登录类型的邮箱操作后，使用星号 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="469bf-159">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>
- <span data-ttu-id="469bf-160">请记住，对邮箱具有完全访问权限的管理员将被视为代理。</span><span class="sxs-lookup"><span data-stu-id="469bf-160">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

<br>

****

|<span data-ttu-id="469bf-161">邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-161">Mailbox action</span></span>|<span data-ttu-id="469bf-162">说明</span><span class="sxs-lookup"><span data-stu-id="469bf-162">Description</span></span>|<span data-ttu-id="469bf-163">管理员</span><span class="sxs-lookup"><span data-stu-id="469bf-163">Admin</span></span>|<span data-ttu-id="469bf-164">委派用户</span><span class="sxs-lookup"><span data-stu-id="469bf-164">Delegate</span></span>|<span data-ttu-id="469bf-165">所有者</span><span class="sxs-lookup"><span data-stu-id="469bf-165">Owner</span></span>|
|---|---|:---:|:---:|:---:|
|<span data-ttu-id="469bf-166">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="469bf-166">**AddFolderPermissions**</span></span>|<span data-ttu-id="469bf-167">尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且未单独审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-167">Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="469bf-168">换句话说，请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="469bf-168">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="469bf-169">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="469bf-169">**ApplyRecord**</span></span>|<span data-ttu-id="469bf-170">项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="469bf-170">An item is labeled as a record.</span></span>|<span data-ttu-id="469bf-171">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-171">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-172">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-172">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-173">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-173">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-174">**复制**</span><span class="sxs-lookup"><span data-stu-id="469bf-174">**Copy**</span></span>|<span data-ttu-id="469bf-175">已将某个邮件复制到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="469bf-175">A message was copied to another folder.</span></span>|![复选标记](../media/checkmark.png)|||
|<span data-ttu-id="469bf-177">**Create**</span><span class="sxs-lookup"><span data-stu-id="469bf-177">**Create**</span></span>|<span data-ttu-id="469bf-178">在邮箱邮箱的"日历、联系人、便笺"或"任务"文件夹中创建了 (例如，会创建一个新的会议) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-178">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="469bf-179">不会审核邮件的创建、发送或接收。</span><span class="sxs-lookup"><span data-stu-id="469bf-179">Creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="469bf-180">也不会审核邮箱文件夹的创建。</span><span class="sxs-lookup"><span data-stu-id="469bf-180">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="469bf-181">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-181">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-182">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-182">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-184">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="469bf-184">**FolderBind**</span></span>|<span data-ttu-id="469bf-185">已访问某个邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="469bf-185">A mailbox folder was accessed.</span></span> <span data-ttu-id="469bf-186">管理员或代理人打开邮箱时也会记录此操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-186">This action is also logged when the admin or delegate opens the mailbox.</span></span> <br/><br/> <span data-ttu-id="469bf-187">**注意**：合并由代理执行的文件夹绑定操作审核记录。</span><span class="sxs-lookup"><span data-stu-id="469bf-187">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="469bf-188">在 24 小时内为单个文件夹访问生成一个审核记录。</span><span class="sxs-lookup"><span data-stu-id="469bf-188">One audit record is generated for individual folder access within a 24-hour period.</span></span>|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|<span data-ttu-id="469bf-191">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="469bf-191">**HardDelete**</span></span>|<span data-ttu-id="469bf-192">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="469bf-192">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="469bf-193">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-193">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-194">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-194">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-195">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-195">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-196">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="469bf-196">**MailboxLogin**</span></span>|<span data-ttu-id="469bf-197">用户登录到其邮箱。</span><span class="sxs-lookup"><span data-stu-id="469bf-197">The user signed into their mailbox.</span></span>|||![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-199">**MailItemsAccessed**</span><span class="sxs-lookup"><span data-stu-id="469bf-199">**MailItemsAccessed**</span></span>|<span data-ttu-id="469bf-200">**注意**：此值仅适用于 E5 或 E5 合规性附加订阅用户。</span><span class="sxs-lookup"><span data-stu-id="469bf-200">**Note**: This value is available only for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="469bf-201">有关详细信息，请参阅在 Microsoft 365[中设置高级Microsoft 365。](set-up-advanced-audit.md)</span><span class="sxs-lookup"><span data-stu-id="469bf-201">For more information, see [Set up Advanced Audit in Microsoft 365](set-up-advanced-audit.md).</span></span> <p> <span data-ttu-id="469bf-202">邮件数据由邮件协议和客户端访问。</span><span class="sxs-lookup"><span data-stu-id="469bf-202">Mail data is accessed by mail protocols and clients.</span></span>|<span data-ttu-id="469bf-203">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-203">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-204">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-204">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-205">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-205">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-206">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="469bf-206">**MessageBind**</span></span>|<span data-ttu-id="469bf-207">**注意**：此值仅适用于没有 E5 或 E5 (E5 合规性附加订阅的 E3 用户) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-207">**Note**: This value is available only for E3 users (users without E5 or E5 Compliance add-on subscriptions).</span></span> <p> <span data-ttu-id="469bf-208">邮件在预览窗格中查看或由管理员打开。</span><span class="sxs-lookup"><span data-stu-id="469bf-208">A message was viewed in the preview pane or opened by an admin.</span></span>|![复选标记](../media/checkmark.png)|||
|<span data-ttu-id="469bf-210">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="469bf-210">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="469bf-211">尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且未单独审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-211">Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="469bf-212">换句话说，请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="469bf-212">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="469bf-213">**移动**</span><span class="sxs-lookup"><span data-stu-id="469bf-213">**Move**</span></span>|<span data-ttu-id="469bf-214">已将某个邮件移至另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="469bf-214">A message was moved to another folder.</span></span>|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-218">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="469bf-218">**MoveToDeletedItems**</span></span>|<span data-ttu-id="469bf-219">已删除邮件，并已将其移动到“已删除邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="469bf-219">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="469bf-220">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-220">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-221">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-221">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-222">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-222">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-223">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="469bf-223">**RecordDelete**</span></span>|<span data-ttu-id="469bf-224">标记为记录的项目被软删除， ("可恢复的项目"文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-224">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="469bf-225">标记为记录的项目无法永久删除， ("可恢复的项目"文件夹中) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-225">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-229">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="469bf-229">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="469bf-230">尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且未单独审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-230">Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="469bf-231">换句话说，请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="469bf-231">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="469bf-232">**SearchQueryInitiated**</span><span class="sxs-lookup"><span data-stu-id="469bf-232">**SearchQueryInitiated**</span></span>|<span data-ttu-id="469bf-233">**注意**：此值仅适用于 E5 或 E5 合规性附加订阅用户。</span><span class="sxs-lookup"><span data-stu-id="469bf-233">**Note**: This value is available only for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="469bf-234">有关详细信息，请参阅在 Microsoft 365[中设置高级Microsoft 365。](set-up-advanced-audit.md)</span><span class="sxs-lookup"><span data-stu-id="469bf-234">For more information, see [Set up Advanced Audit in Microsoft 365](set-up-advanced-audit.md).</span></span> <p> <span data-ttu-id="469bf-235">用户使用 Outlook (Windows、Mac、iOS、Android 或 Outlook 网页版) 或邮件应用程序Windows 10搜索邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="469bf-235">A person uses Outlook (Windows, Mac, iOS, Android, or Outlook on the web) or the Mail app for Windows 10 to search for items in a mailbox.</span></span>|||![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-237">**Send**</span><span class="sxs-lookup"><span data-stu-id="469bf-237">**Send**</span></span>|<span data-ttu-id="469bf-238">**注意**：此值仅适用于 E5 或 E5 合规性附加订阅用户。</span><span class="sxs-lookup"><span data-stu-id="469bf-238">**Note**: This value is available only for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="469bf-239">有关详细信息，请参阅在 Microsoft 365[中设置高级Microsoft 365。](set-up-advanced-audit.md)</span><span class="sxs-lookup"><span data-stu-id="469bf-239">For more information, see [Set up Advanced Audit in Microsoft 365](set-up-advanced-audit.md).</span></span> <p> <span data-ttu-id="469bf-240">用户发送电子邮件、答复电子邮件或转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-240">The user sends an email message, replies to an email message, or forwards an email message.</span></span>|<span data-ttu-id="469bf-241">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-241">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||<span data-ttu-id="469bf-242">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-242">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-243">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="469bf-243">**SendAs**</span></span>|<span data-ttu-id="469bf-244">已使用“发送方式”权限发送邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-244">A message was sent using the SendAs permission.</span></span> <span data-ttu-id="469bf-245">这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="469bf-245">This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="469bf-246">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-246">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-247">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-247">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="469bf-248">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="469bf-248">**SendOnBehalf**</span></span>|<span data-ttu-id="469bf-249">已使用“代表发送”权限发送邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-249">A message was sent using the SendOnBehalf permission.</span></span> <span data-ttu-id="469bf-250">这表示另一个用户代表邮箱所有者发送了邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-250">This means another user sent the message on behalf of the mailbox owner.</span></span> <span data-ttu-id="469bf-251">邮件将向收件人说明发送此邮件时使用的身份及实际发送者。</span><span class="sxs-lookup"><span data-stu-id="469bf-251">The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="469bf-252">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-252">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-253">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-253">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="469bf-254">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="469bf-254">**SoftDelete**</span></span>|<span data-ttu-id="469bf-255">已永久删除或已从“已删除邮件”文件夹中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-255">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="469bf-256">软删除的项目将移动到"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="469bf-256">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="469bf-257">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-257">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-258">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-258">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-259">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-259">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-260">**更新**</span><span class="sxs-lookup"><span data-stu-id="469bf-260">**Update**</span></span>|<span data-ttu-id="469bf-261">已更改邮件或邮件的任何属性。</span><span class="sxs-lookup"><span data-stu-id="469bf-261">A message or any of its properties was changed.</span></span>|<span data-ttu-id="469bf-262">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-262">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-263">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-263">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-264">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-264">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-265">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="469bf-265">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="469bf-266">日历委派已分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="469bf-266">A calendar delegation was assigned to a mailbox.</span></span> <span data-ttu-id="469bf-267">日历代理为同一组织内的其他人授予管理邮箱所有者日历的权限。</span><span class="sxs-lookup"><span data-stu-id="469bf-267">Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="469bf-268">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-268">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||<span data-ttu-id="469bf-269">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-269">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-270">**UpdateComplianceTag**</span><span class="sxs-lookup"><span data-stu-id="469bf-270">**UpdateComplianceTag**</span></span>|<span data-ttu-id="469bf-271">其他保留标签应用于邮件项目 (一个项目只能分配有一个保留标签) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-271">A different retention label is applied to a mail item (an item can only have one retention label assigned to it).</span></span>|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="469bf-275">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="469bf-275">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="469bf-276">文件夹权限已更改。</span><span class="sxs-lookup"><span data-stu-id="469bf-276">A folder permission was changed.</span></span> <span data-ttu-id="469bf-277">文件夹权限用于控制组织中的哪些用户可以访问邮箱中的文件夹以及位于这些文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-277">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="469bf-278">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-278">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-279">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-279">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-280">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-280">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-281">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="469bf-281">**UpdateInboxRules**</span></span>|<span data-ttu-id="469bf-282">已添加、删除或已更改收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="469bf-282">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="469bf-283">收件箱规则用于根据指定条件处理用户收件箱中的邮件，并满足规则条件时采取措施，例如将邮件移动到指定文件夹或删除邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-283">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="469bf-284">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-284">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-285">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-285">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-286">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-286">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="469bf-287">如果在组织中默认启用邮箱审核之前，自定义了要审核的任何登录类型的邮箱操作，则自定义设置将保留在邮箱上，并且不会覆盖默认邮箱操作，如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="469bf-287">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="469bf-288">若要将审核邮箱操作还原为 (您随时都可以) ，请参阅本文稍后的还原默认邮箱操作部分。 [](#restore-the-default-mailbox-actions)</span><span class="sxs-lookup"><span data-stu-id="469bf-288">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this article.</span></span>

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a><span data-ttu-id="469bf-289">组Microsoft 365的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-289">Mailbox actions for Microsoft 365 Group mailboxes</span></span>

<span data-ttu-id="469bf-290">默认情况下启用的邮箱审核将邮箱审核日志记录引入 Microsoft 365 组邮箱，但无法自定义要记录的内容 (无法添加或删除为任何登录类型) 记录的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-290">Mailbox auditing on by default brings mailbox audit logging to Microsoft 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="469bf-291">下表介绍了默认情况下在每个登录类型的组邮箱Microsoft 365记录的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-291">The following table describes the mailbox actions that are logged by default on Microsoft 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="469bf-292">请记住，对组邮箱具有完全访问权限Microsoft 365管理员将被视为代理。</span><span class="sxs-lookup"><span data-stu-id="469bf-292">Remember, an admin with Full Access permission to a Microsoft 365 Group mailbox is considered a delegate.</span></span>

<br>

****

|<span data-ttu-id="469bf-293">邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-293">Mailbox action</span></span>|<span data-ttu-id="469bf-294">说明</span><span class="sxs-lookup"><span data-stu-id="469bf-294">Description</span></span>|<span data-ttu-id="469bf-295">管理员</span><span class="sxs-lookup"><span data-stu-id="469bf-295">Admin</span></span>|<span data-ttu-id="469bf-296">委派用户</span><span class="sxs-lookup"><span data-stu-id="469bf-296">Delegate</span></span>|<span data-ttu-id="469bf-297">所有者</span><span class="sxs-lookup"><span data-stu-id="469bf-297">Owner</span></span>|
|---|---|:---:|:---:|:---:|
|<span data-ttu-id="469bf-298">**Create**</span><span class="sxs-lookup"><span data-stu-id="469bf-298">**Create**</span></span>|<span data-ttu-id="469bf-299">创建日历项目。</span><span class="sxs-lookup"><span data-stu-id="469bf-299">Creation of a calendar Item.</span></span> <span data-ttu-id="469bf-300">不会审核邮件的创建、发送或接收。</span><span class="sxs-lookup"><span data-stu-id="469bf-300">Creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="469bf-301">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-301">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-302">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-302">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="469bf-303">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="469bf-303">**HardDelete**</span></span>|<span data-ttu-id="469bf-304">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="469bf-304">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="469bf-305">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-305">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-306">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-306">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-307">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-307">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-308">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="469bf-308">**MoveToDeletedItems**</span></span>|<span data-ttu-id="469bf-309">已删除邮件，并已将其移动到“已删除邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="469bf-309">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="469bf-310">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-310">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-311">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-311">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-312">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-312">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-313">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="469bf-313">**SendAs**</span></span>|<span data-ttu-id="469bf-314">已使用“发送方式”权限发送邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-314">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="469bf-315">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-315">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-316">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-316">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="469bf-317">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="469bf-317">**SendOnBehalf**</span></span>|<span data-ttu-id="469bf-318">已使用“代表发送”权限发送邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-318">A message was sent using the SendOnBehalf permission.</span></span>|<span data-ttu-id="469bf-319">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-319">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-320">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-320">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="469bf-321">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="469bf-321">**SoftDelete**</span></span>|<span data-ttu-id="469bf-322">已永久删除或已从“已删除邮件”文件夹中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="469bf-322">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="469bf-323">软删除的项目将移动到"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="469bf-323">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="469bf-324">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-324">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-325">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-325">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-326">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-326">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="469bf-327">**更新**</span><span class="sxs-lookup"><span data-stu-id="469bf-327">**Update**</span></span>|<span data-ttu-id="469bf-328">已更改邮件或邮件的任何属性。</span><span class="sxs-lookup"><span data-stu-id="469bf-328">A message or any of its property was changed.</span></span>|<span data-ttu-id="469bf-329">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-329">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-330">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-330">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="469bf-331">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="469bf-331">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="469bf-332">验证是否针对每种登录类型记录默认邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-332">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="469bf-333">默认情况下启用的邮箱审核会将新的 *DefaultAuditSet* 属性添加到所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="469bf-333">Mailbox auditing on by default adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="469bf-334">此属性的值指示是否正在审核由 Microsoft (管理) 操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-334">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="469bf-335">若要在用户邮箱或共享邮箱上显示值，请将 替换为邮箱的名称、别名、电子邮件地址或用户主体名称 \<MailboxIdentity\> (用户名) ，在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469bf-335">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="469bf-336">若要在组邮箱Microsoft 365值，请将 替换为共享邮箱的名称、别名或电子邮件地址，然后使用 \<MailboxIdentity\> PowerShell Exchange Online命令：</span><span class="sxs-lookup"><span data-stu-id="469bf-336">To display the value on Microsoft 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="469bf-337">值 `Admin, Delegate, Owner` 指示：</span><span class="sxs-lookup"><span data-stu-id="469bf-337">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="469bf-338">将审核所有三种登录类型的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-338">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="469bf-339">这是你将在组邮箱上看到的唯一Microsoft 365值。</span><span class="sxs-lookup"><span data-stu-id="469bf-339">This is the only value you'll see on Microsoft 365 Group mailboxes.</span></span>
- <span data-ttu-id="469bf-340">管理员 *未更改* 用户邮箱或共享邮箱上任何登录类型的已审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-340">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="469bf-341">请注意，这是在组织中最初启用邮箱审核之后的默认状态。</span><span class="sxs-lookup"><span data-stu-id="469bf-341">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="469bf-342">如果管理员曾经使用 **Set-Mailbox** cmdlet) 上的 AuditAdmin、AuditDelegate或 *AuditOwner* 参数更改了针对登录类型 (审核的邮箱操作，属性值将有所不同。</span><span class="sxs-lookup"><span data-stu-id="469bf-342">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="469bf-343">例如，用户邮箱或共享邮箱的 `Owner` *DefaultAuditSet* 属性的值指示：</span><span class="sxs-lookup"><span data-stu-id="469bf-343">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="469bf-344">正在审核邮箱所有者的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-344">The default mailbox actions for the mailbox owner are being audited.</span></span>
- <span data-ttu-id="469bf-345">和 登录类型的审核邮箱 `Delegate` 操作已更改 `Admin` 为默认操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-345">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="469bf-346">*DefaultAuditSet* 属性的空值表示用户邮箱或共享邮箱上所有三种登录类型的邮箱操作已更改。</span><span class="sxs-lookup"><span data-stu-id="469bf-346">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="469bf-347">有关详细信息，请参阅本文中的更改或还原默认 [记录的](#change-or-restore-mailbox-actions-logged-by-default) 邮箱操作部分。</span><span class="sxs-lookup"><span data-stu-id="469bf-347">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this article</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="469bf-348">显示正在登录的邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-348">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="469bf-349">若要查看当前正在登录的用户邮箱或共享邮箱的邮箱操作，请将 替换为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名) ，并运行 Exchange Online PowerShell 中的以下一个或多个命令。 \<MailboxIdentity\></span><span class="sxs-lookup"><span data-stu-id="469bf-349">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="469bf-350">尽管可以将开关添加到组邮箱的以下 `-GroupMailbox` **Get-Mailbox** Microsoft 365，但不要认为返回的值。</span><span class="sxs-lookup"><span data-stu-id="469bf-350">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Microsoft 365 Group mailboxes, don't believe the values that are returned.</span></span> <span data-ttu-id="469bf-351">为组邮箱审核的默认和静态Microsoft 365操作在本文前面"Microsoft 365组邮箱的邮箱操作["](#mailbox-actions-for-microsoft-365-group-mailboxes)部分中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="469bf-351">The default and static mailbox actions that are audited for Microsoft 365 Group mailboxes are described in the [Mailbox actions for Microsoft 365 Group mailboxes](#mailbox-actions-for-microsoft-365-group-mailboxes) section earlier in this article.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="469bf-352">所有者操作</span><span class="sxs-lookup"><span data-stu-id="469bf-352">Owner actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="469bf-353">委派操作</span><span class="sxs-lookup"><span data-stu-id="469bf-353">Delegate actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="469bf-354">管理员操作</span><span class="sxs-lookup"><span data-stu-id="469bf-354">Admin actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="469bf-355">更改或还原默认情况下记录的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-355">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="469bf-356">如前所述，默认情况下启用邮箱审核的主要好处之一是：无需管理审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-356">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="469bf-357">Microsoft 会为用户完成此操作，我们将在发布新邮箱操作时自动添加要默认审核的新邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-357">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="469bf-358">但是，您的组织可能需要审核用户邮箱和共享邮箱的不同邮箱操作集。</span><span class="sxs-lookup"><span data-stu-id="469bf-358">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="469bf-359">本节中的过程将向您展示如何更改针对每种登录类型审核的邮箱操作，以及如何还原到 Microsoft 管理的默认操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-359">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="469bf-360">如果您使用以下过程自定义已登录用户邮箱或共享邮箱的邮箱操作，Microsoft 发布的任何新的默认邮箱操作将不会在这些邮箱上自动审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-360">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="469bf-361">需要手动将任何新邮箱操作添加到自定义操作列表。</span><span class="sxs-lookup"><span data-stu-id="469bf-361">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="469bf-362">将邮箱操作更改为审核</span><span class="sxs-lookup"><span data-stu-id="469bf-362">Change the mailbox actions to audit</span></span>

<span data-ttu-id="469bf-363">可以使用 **Set-Mailbox** cmdlet 上的 *AuditAdmin、AuditDelegate* 或 *AuditOwner* 参数更改已审核的用户邮箱和共享邮箱的邮箱操作 (Microsoft 365 组邮箱的审核操作无法自定义) 。 </span><span class="sxs-lookup"><span data-stu-id="469bf-363">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Microsoft 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="469bf-364">可以使用两种不同的方法来指定邮箱操作：</span><span class="sxs-lookup"><span data-stu-id="469bf-364">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="469bf-365">*使用此* (替换) 覆盖现有邮箱操作的内容 `action1,action2,...actionN` ：。</span><span class="sxs-lookup"><span data-stu-id="469bf-365">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>
- <span data-ttu-id="469bf-366">*使用此语法* 添加或删除邮箱操作，而不影响其他现有 `@{Add="action1","action2",..."actionN"}` 值：或 `@{Remove="action1","action2",..."actionN"}` 。</span><span class="sxs-lookup"><span data-stu-id="469bf-366">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="469bf-367">此示例通过使用 SoftDelete 和 HardDelete 覆盖默认操作来更改名为"Gabriela Laureano"的邮箱的管理邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-367">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="469bf-368">本示例将 MailboxLogin 所有者操作添加到邮箱 laura@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="469bf-368">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="469bf-369">本示例删除团队讨论邮箱的 MoveToDeletedItems 委派操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-369">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="469bf-370">无论使用哪种方法，自定义用户邮箱或共享邮箱上的已审核邮箱操作都会产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="469bf-370">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="469bf-371">对于自定义的登录类型，Microsoft 不再管理审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-371">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>
- <span data-ttu-id="469bf-372">您自定义的登录类型不再如前面所述显示在邮箱的 *DefaultAuditSet* [属性值中](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。</span><span class="sxs-lookup"><span data-stu-id="469bf-372">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="469bf-373">还原默认邮箱操作</span><span class="sxs-lookup"><span data-stu-id="469bf-373">Restore the default mailbox actions</span></span>

> [!NOTE]
> <span data-ttu-id="469bf-374">以下过程不适用于组Microsoft 365组 (仅限于默认操作，如本文) 。 [](#mailbox-actions-for-microsoft-365-group-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="469bf-374">The following procedures don't apply to Microsoft 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-microsoft-365-group-mailboxes)).</span></span>

<span data-ttu-id="469bf-375">如果自定义了在用户邮箱或共享邮箱上审核的邮箱操作，可以使用以下语法还原一种或所有登录类型的默认邮箱操作：</span><span class="sxs-lookup"><span data-stu-id="469bf-375">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="469bf-376">可以指定用逗号分隔的多个 *DefaultAuditSet* 值</span><span class="sxs-lookup"><span data-stu-id="469bf-376">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="469bf-377">本示例还原邮箱邮箱上所有登录类型的默认审核 mark@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="469bf-377">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="469bf-378">此示例还原邮箱 chris@contoso.onmicrosoft.com 上管理员登录类型的默认审核邮箱操作，但保留"委派"和"所有者"登录类型的自定义审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-378">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="469bf-379">还原登录类型的默认审核邮箱操作将具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="469bf-379">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="469bf-380">邮箱操作的当前列表将替换为登录类型的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-380">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>
- <span data-ttu-id="469bf-381">Microsoft 发布的任何新邮箱操作都会自动添加到登录类型的审核操作列表中。</span><span class="sxs-lookup"><span data-stu-id="469bf-381">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>
- <span data-ttu-id="469bf-382">更新 *邮箱的 DefaultAuditSet* 属性值以包括还原的登录类型。</span><span class="sxs-lookup"><span data-stu-id="469bf-382">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="469bf-383">默认情况下，为组织关闭邮箱审核</span><span class="sxs-lookup"><span data-stu-id="469bf-383">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="469bf-384">默认情况下，可以在 PowerShell 中运行以下命令，为整个组织关闭Exchange Online审核：</span><span class="sxs-lookup"><span data-stu-id="469bf-384">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="469bf-385">默认情况下关闭邮箱审核具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="469bf-385">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="469bf-386">为组织禁用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-386">Mailbox auditing is disabled for your organization.</span></span>
- <span data-ttu-id="469bf-387">从默认情况下禁用邮箱审核起，不会审核任何邮箱操作，即使对邮箱启用了审核 (邮箱的 *AuditEnabled* 属性为 **True**) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-387">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>
- <span data-ttu-id="469bf-388">未针对新邮箱启用邮箱审核，并且将忽略新邮箱或现有邮箱的 *AuditEnabled* 属性设置为 **True。**</span><span class="sxs-lookup"><span data-stu-id="469bf-388">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>
- <span data-ttu-id="469bf-389">任何邮箱审核绕过关联 (**Set-MailboxAuditBypassAssociation** cmdlet 配置的任何邮箱审核绕过) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="469bf-389">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>
- <span data-ttu-id="469bf-390">现有邮箱审核记录将一直保留到审核日志期限到期为止。</span><span class="sxs-lookup"><span data-stu-id="469bf-390">Existing mailbox audit records are retained until the audit log age limit for the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="469bf-391">默认情况下打开邮箱审核</span><span class="sxs-lookup"><span data-stu-id="469bf-391">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="469bf-392">若要为组织重新启用邮箱审核，在 PowerShell 中Exchange Online命令：</span><span class="sxs-lookup"><span data-stu-id="469bf-392">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="469bf-393">绕过邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="469bf-393">Bypass mailbox audit logging</span></span>

<span data-ttu-id="469bf-394">目前，组织内已默认启用邮箱审核时，不能为特定邮箱禁用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-394">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="469bf-395">例如，将 *AuditEnabled* 邮箱属性设置为 **False** 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="469bf-395">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="469bf-396">但是，您仍可以在 Exchange Online PowerShell 中使用 **Set-MailboxAuditBypassAssociation** cmdlet来防止记录指定用户的任何邮箱操作以及所有邮箱操作，而不管这些操作在何处发生。</span><span class="sxs-lookup"><span data-stu-id="469bf-396">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="469bf-397">例如：</span><span class="sxs-lookup"><span data-stu-id="469bf-397">For example:</span></span>

- <span data-ttu-id="469bf-398">不会记录绕过的用户执行的邮箱所有者操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-398">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>
- <span data-ttu-id="469bf-399">被绕过的用户对其他用户的邮箱执行的委派 (包括共享邮箱) 不会记录。</span><span class="sxs-lookup"><span data-stu-id="469bf-399">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>
- <span data-ttu-id="469bf-400">不会记录绕过用户执行的管理员操作。</span><span class="sxs-lookup"><span data-stu-id="469bf-400">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="469bf-401">若要绕过特定用户的邮箱审核日志记录，请将 替换为用户的名称、电子邮件地址、别名或用户主体名称 (用户名) 并运行 \<MailboxIdentity\> 以下命令：</span><span class="sxs-lookup"><span data-stu-id="469bf-401">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="469bf-402">若要验证是否已绕过对指定用户的审核，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469bf-402">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="469bf-403">值 **True** 表示将绕过用户的邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="469bf-403">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="469bf-404">更多信息</span><span class="sxs-lookup"><span data-stu-id="469bf-404">More information</span></span>

- <span data-ttu-id="469bf-405">尽管默认情况下会为所有组织启用邮箱审核日志记录，但只有具有 E5 许可证的用户才能在安全 & 合规中心或通过 Office 365 管理活动 [API](/office/office-365-management-api/office-365-management-activity-api-reference)在 审核日志 搜索中返回邮箱 [审核日志](search-the-audit-log-in-security-and-compliance.md)**事件**。</span><span class="sxs-lookup"><span data-stu-id="469bf-405">Although mailbox audit logging on by default is enabled for all organizations, only users with E5 licenses will return mailbox audit log events in [audit log searches in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md) or via the [Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference) **by default**.</span></span>

  <span data-ttu-id="469bf-406">若要检索审核日志 E5 许可证的用户的邮箱邮箱条目，您可以：</span><span class="sxs-lookup"><span data-stu-id="469bf-406">To retrieve mailbox audit log entries for users without E5 licenses, you can:</span></span>

  - <span data-ttu-id="469bf-407">手动启用单个邮箱的邮箱审核 (运行命令 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ，) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-407">Manually enable mailbox auditing on individual mailboxes (run the command, `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`).</span></span> <span data-ttu-id="469bf-408">完成此操作后，可以在安全审核日志中心或 &管理活动 API Office 365搜索。</span><span class="sxs-lookup"><span data-stu-id="469bf-408">After you do this, you can use audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span>

    > [!NOTE]
    > <span data-ttu-id="469bf-409">如果邮箱审核功能在邮箱上显示为已启用，但搜索未返回任何结果，请更改 _AuditEnabled_ 参数的值，然后再更改 `$false` 回 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="469bf-409">If mailbox auditing already appears to be enabled on the mailbox, but your searches return no results, change the value of the _AuditEnabled_ parameter to `$false` and then back to `$true`.</span></span>

  - <span data-ttu-id="469bf-410">在 PowerShell 中使用以下 cmdlet Exchange Online Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="469bf-410">Use the following cmdlets in Exchange Online PowerShell:</span></span>
    - <span data-ttu-id="469bf-411">[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) 搜索特定审核日志邮箱邮箱。</span><span class="sxs-lookup"><span data-stu-id="469bf-411">[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) to search the mailbox audit log for specific users.</span></span>
    - <span data-ttu-id="469bf-412">[New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) 可搜索特定审核日志邮箱邮箱，并通过电子邮件将结果发送给指定收件人。</span><span class="sxs-lookup"><span data-stu-id="469bf-412">[New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) to search the mailbox audit log for specific users and to have the results sent via email to specified recipients.</span></span>

  - <span data-ttu-id="469bf-413">使用 Exchange管理中心 (EAC) Exchange Online执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="469bf-413">Use the Exchange admin center (EAC) in Exchange Online to do the following actions:</span></span>
    - [<span data-ttu-id="469bf-414">导出邮箱审核日志</span><span class="sxs-lookup"><span data-stu-id="469bf-414">Export mailbox audit logs</span></span>](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [<span data-ttu-id="469bf-415">运行非所有者邮箱访问报告</span><span class="sxs-lookup"><span data-stu-id="469bf-415">Run a non-owner mailbox access report</span></span>](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- <span data-ttu-id="469bf-416">默认情况下，邮箱审核日志记录在被删除前保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="469bf-416">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="469bf-417">您可以使用 PowerShell 中 **Set-Mailbox** cmdlet 审核日志 *AuditLogAgeLimit* 参数更改记录Exchange Online期限。</span><span class="sxs-lookup"><span data-stu-id="469bf-417">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="469bf-418">但是，如果增加此值，则不允许搜索超过 90 天的 审核日志。</span><span class="sxs-lookup"><span data-stu-id="469bf-418">However, increasing this value doesn't allow you to search for events that are older than 90 days in the audit log.</span></span>

  <span data-ttu-id="469bf-419">如果增加期限，则需要使用 Exchange Online PowerShell 中的[Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) cmdlet 在用户的邮箱 审核日志 中搜索超过 90 天的记录。</span><span class="sxs-lookup"><span data-stu-id="469bf-419">If you increase the age limit, you need to use the [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="469bf-420">如果在默认情况下为组织启用邮箱审核之前更改了邮箱的 *AuditLogAgeLimit* 属性，则邮箱的现有 审核日志 期限不会更改。</span><span class="sxs-lookup"><span data-stu-id="469bf-420">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="469bf-421">换句话说，默认情况下启用的邮箱审核不会影响邮箱审核记录的当前期限。</span><span class="sxs-lookup"><span data-stu-id="469bf-421">In other words, mailbox auditing on by default doesn't affect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="469bf-422">若要更改组邮箱上的 *AuditLogAgeLimit* Microsoft 365，您需要在 `-GroupMailbox` **Set-Mailbox** 命令中包括开关。</span><span class="sxs-lookup"><span data-stu-id="469bf-422">To change the *AuditLogAgeLimit* value on a Microsoft 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="469bf-423">邮箱审核日志记录存储在每个用户邮箱的"可恢复 (文件夹中) "审核"文件夹的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="469bf-423">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="469bf-424">对于邮箱审核记录和"可恢复的项目"文件夹，请牢记以下事项：</span><span class="sxs-lookup"><span data-stu-id="469bf-424">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="469bf-425">邮箱审核记录计数针对"可恢复的项目"文件夹的存储配额（默认为 30 GB） (警告配额为 20 GB) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-425">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30 GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="469bf-426">在出现以下两种操作时，存储配额 (90 GB 警告配额) 100 GB：</span><span class="sxs-lookup"><span data-stu-id="469bf-426">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>
    - <span data-ttu-id="469bf-427">将邮箱置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="469bf-427">A hold is placed on a mailbox.</span></span>
    - <span data-ttu-id="469bf-428">邮箱将分配给合规性中心中的保留策略。</span><span class="sxs-lookup"><span data-stu-id="469bf-428">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="469bf-429">邮箱审核记录还计入 ["可恢复的项目"文件夹的文件夹限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。</span><span class="sxs-lookup"><span data-stu-id="469bf-429">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="469bf-430">审核记录中最多可 (300 万) 审核记录存储在"审核"子文件夹。</span><span class="sxs-lookup"><span data-stu-id="469bf-430">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="469bf-431">默认情况下启用的邮箱审核不太可能影响"可恢复的项目"文件夹的存储配额或文件夹限制。</span><span class="sxs-lookup"><span data-stu-id="469bf-431">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="469bf-432">可以在 PowerShell 中Exchange Online以下命令，以显示"可恢复的项目"文件夹中"审核"子文件夹中的项目大小和数量：</span><span class="sxs-lookup"><span data-stu-id="469bf-432">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="469bf-433">You can't directly access an 审核日志 record in the Recoverable Items folder;而是使用 **Search-MailboxAuditLog** cmdlet 或搜索审核日志查找和查看邮箱审核记录。</span><span class="sxs-lookup"><span data-stu-id="469bf-433">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="469bf-434">如果邮箱处于保留状态或分配到合规中心中的保留策略，审核日志 记录在默认情况下仍保留由邮箱 *的 AuditLogAgeLimit* 属性定义的持续时间 (90 天) 。</span><span class="sxs-lookup"><span data-stu-id="469bf-434">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="469bf-435">若要将审核日志保留的邮箱保留更长时间，需要增加邮箱的 *AuditLogAgeLimit* 值。</span><span class="sxs-lookup"><span data-stu-id="469bf-435">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>

- <span data-ttu-id="469bf-436">在多地理位置环境中，不支持跨地理位置邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="469bf-436">In a multi-geo environment, cross-geo mailbox auditing is not supported.</span></span> <span data-ttu-id="469bf-437">例如，如果为某用户分配了访问其他地理位置的共享邮箱的权限，此用户执行的邮箱操作不会记录在共享邮箱的邮箱审核日志中。</span><span class="sxs-lookup"><span data-stu-id="469bf-437">For example, if a user is assigned permissions to access a shared mailbox in a different geo location, mailbox actions performed by that user are not logged in the mailbox audit log of the shared mailbox.</span></span>
