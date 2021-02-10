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
description: 默认情况下，Microsoft 365 中启用邮箱审核日志记录 (默认情况下也称为默认邮箱审核或邮箱审核) 。 这意味着邮箱所有者、代理和管理员执行的某些操作会自动记录在邮箱审核日志，您可以在其中搜索对邮箱执行的活动。
ms.openlocfilehash: 8b97e18a6c5d24bd74bb04eecc91999c4aa61bb9
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175581"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="99f59-104">管理邮箱审核</span><span class="sxs-lookup"><span data-stu-id="99f59-104">Manage mailbox auditing</span></span>

<span data-ttu-id="99f59-105">从 2019 年 1 月开始，Microsoft 将默认启用所有组织的邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all organizations.</span></span> <span data-ttu-id="99f59-106">这意味着自动记录由邮箱所有者、代理和管理员执行的某些操作，当您在邮箱邮箱中搜索相应的邮箱审核记录时，这些记录审核日志。</span><span class="sxs-lookup"><span data-stu-id="99f59-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="99f59-107">默认情况下，在启用邮箱审核之前，您必须为组织的每个用户邮箱手动启用它。</span><span class="sxs-lookup"><span data-stu-id="99f59-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="99f59-108">默认情况下，邮箱审核的一些好处是：</span><span class="sxs-lookup"><span data-stu-id="99f59-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="99f59-109">创建新邮箱时将自动启用审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="99f59-110">无需为新用户手动启用它。</span><span class="sxs-lookup"><span data-stu-id="99f59-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="99f59-111">无需管理审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="99f59-112">默认情况下，会针对管理员、代理和所有者帐户的每个登录类型审核 (一组预定义的邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="99f59-113">当 Microsoft 发布新的邮箱操作时，该操作可能会自动添加到默认审核的邮箱操作列表中 (用户拥有相应的许可证) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-113">When Microsoft releases a new mailbox action, the action might be automatically added to the list of mailbox actions that are audited by default (subject to the user having the appropriate license).</span></span> <span data-ttu-id="99f59-114">这意味着无需监视对邮箱添加新操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="99f59-115">由于要审核组织中所有邮箱的相同 (，因此在组织中拥有一致的邮箱审核) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!NOTE]
>* <span data-ttu-id="99f59-116">默认情况下，关于发布邮箱审核时，需要记住的重要一点就是：无需执行任何操作来管理邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-116">The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="99f59-117">但是，若要了解更多信息、从默认设置自定义邮箱审核或完全关闭邮箱审核，本主题可以帮助您。</span><span class="sxs-lookup"><span data-stu-id="99f59-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span>
>- <span data-ttu-id="99f59-118">默认情况下，只有 E5 用户的邮箱审核事件在安全 审核日志 合规中心或 Office 365 管理活动 API 的 & 搜索中可用。</span><span class="sxs-lookup"><span data-stu-id="99f59-118">By default, only mailbox audit events for E5 users are available in audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span> <span data-ttu-id="99f59-119">有关详细信息，请参阅本主题 [中的](#more-information) "详细信息"部分。</span><span class="sxs-lookup"><span data-stu-id="99f59-119">For more information, see the [More information](#more-information) section in this topic.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="99f59-120">验证邮箱审核默认是否打开</span><span class="sxs-lookup"><span data-stu-id="99f59-120">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="99f59-121">若要验证默认情况下是否为组织启用邮箱审核，请运行 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中的以下命令：</span><span class="sxs-lookup"><span data-stu-id="99f59-121">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="99f59-122">值 **False** 表示默认情况下为组织启用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-122">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="99f59-123">默认情况下，组织值会覆盖特定邮箱上的邮箱审核设置。</span><span class="sxs-lookup"><span data-stu-id="99f59-123">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="99f59-124">例如，如果禁用邮箱 (则邮箱) 的 *AuditEnabled* 属性为 **False，** 则仍将审核邮箱的默认邮箱操作，因为默认情况下会为组织启用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-124">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="99f59-125">若要为特定邮箱禁用邮箱审核，请为邮箱所有者和已委派邮箱访问权限的其他用户配置邮箱审核绕过。</span><span class="sxs-lookup"><span data-stu-id="99f59-125">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="99f59-126">有关详细信息，请参阅本主题中的 ["绕过邮箱审核](#bypass-mailbox-audit-logging) 日志记录"部分。</span><span class="sxs-lookup"><span data-stu-id="99f59-126">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="99f59-127">当默认情况下为组织启用邮箱审核时，受影响邮箱的 *AuditEnabled* 属性不会从 **False** 更改为 **True。**</span><span class="sxs-lookup"><span data-stu-id="99f59-127">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="99f59-128">换句话说，默认情况下启用的邮箱审核将忽略邮箱上的 *AuditEnabled* 属性。</span><span class="sxs-lookup"><span data-stu-id="99f59-128">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="99f59-129">支持的邮箱类型</span><span class="sxs-lookup"><span data-stu-id="99f59-129">Supported mailbox types</span></span>

<span data-ttu-id="99f59-130">下表显示了默认情况下邮箱审核当前支持的邮箱类型：</span><span class="sxs-lookup"><span data-stu-id="99f59-130">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="99f59-131">**邮箱类型**</span><span class="sxs-lookup"><span data-stu-id="99f59-131">**Mailbox type**</span></span>|<span data-ttu-id="99f59-132">**支持**</span><span class="sxs-lookup"><span data-stu-id="99f59-132">**Supported**</span></span>|<span data-ttu-id="99f59-133">**不支持**</span><span class="sxs-lookup"><span data-stu-id="99f59-133">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="99f59-134">用户邮箱</span><span class="sxs-lookup"><span data-stu-id="99f59-134">User mailboxes</span></span>|![复选标记](../media/checkmark.png)||
|<span data-ttu-id="99f59-136">共享邮箱</span><span class="sxs-lookup"><span data-stu-id="99f59-136">Shared mailboxes</span></span>|![复选标记](../media/checkmark.png)||
|<span data-ttu-id="99f59-138">Microsoft 365 组邮箱</span><span class="sxs-lookup"><span data-stu-id="99f59-138">Microsoft 365 Group mailboxes</span></span>|![复选标记](../media/checkmark.png)||
|<span data-ttu-id="99f59-140">资源邮箱</span><span class="sxs-lookup"><span data-stu-id="99f59-140">Resource mailboxes</span></span>||![复选标记](../media/checkmark.png)|
|<span data-ttu-id="99f59-142">公用文件夹邮箱</span><span class="sxs-lookup"><span data-stu-id="99f59-142">Public folder mailboxes</span></span>||![复选标记](../media/checkmark.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="99f59-144">登录类型和邮箱操作</span><span class="sxs-lookup"><span data-stu-id="99f59-144">Logon types and mailbox actions</span></span>

<span data-ttu-id="99f59-145">登录类型对对邮箱执行审核操作的用户进行分类。</span><span class="sxs-lookup"><span data-stu-id="99f59-145">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="99f59-146">以下列表介绍了邮箱审核日志记录中使用的登录类型：</span><span class="sxs-lookup"><span data-stu-id="99f59-146">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="99f59-147">**所有者**：邮箱 (与邮箱邮箱关联的帐户) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-147">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="99f59-148">**委派**：</span><span class="sxs-lookup"><span data-stu-id="99f59-148">**Delegate**:</span></span>

  - <span data-ttu-id="99f59-149">已分配有对另一个邮箱的 SendAs、SendOnBehalf 或 FullAccess 权限的用户。</span><span class="sxs-lookup"><span data-stu-id="99f59-149">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="99f59-150">已分配有用户邮箱的 FullAccess 权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="99f59-150">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="99f59-151">**管理员**：</span><span class="sxs-lookup"><span data-stu-id="99f59-151">**Admin**:</span></span>

  - <span data-ttu-id="99f59-152">邮箱使用下列 Microsoft 电子数据展示工具之一进行搜索：</span><span class="sxs-lookup"><span data-stu-id="99f59-152">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="99f59-153">合规性中心的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="99f59-153">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="99f59-154">合规性中心中的电子数据展示或高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="99f59-154">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="99f59-155">In-Place Exchange Online 中的电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="99f59-155">In-Place eDiscovery in Exchange Online.</span></span>

  - <span data-ttu-id="99f59-156">通过使用 MAPI 编辑器Microsoft Exchange Server邮箱。</span><span class="sxs-lookup"><span data-stu-id="99f59-156">The mailbox is accessed by using the Microsoft Exchange Server MAPI Editor.</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="99f59-157">用户邮箱和共享邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="99f59-157">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="99f59-158">下表描述了在用户邮箱和共享邮箱的邮箱审核日志记录中可用的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-158">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="99f59-159">复选标记 (</span><span class="sxs-lookup"><span data-stu-id="99f59-159">A check mark (</span></span> ![复选标记](../media/checkmark.png)<span data-ttu-id="99f59-161">) 指示可以针对登录类型记录邮箱操作 (并非所有操作都可用于所有登录类型) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-161">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="99f59-162">在选中 () ，默认情况下会记录登录类型的邮箱操作后，使用星号 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="99f59-162">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="99f59-163">请记住，对邮箱具有完全访问权限的管理员被视为代理。</span><span class="sxs-lookup"><span data-stu-id="99f59-163">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="99f59-164">**邮箱操作**</span><span class="sxs-lookup"><span data-stu-id="99f59-164">**Mailbox action**</span></span>|<span data-ttu-id="99f59-165">**说明**</span><span class="sxs-lookup"><span data-stu-id="99f59-165">**Description**</span></span>|<span data-ttu-id="99f59-166">**管理员**</span><span class="sxs-lookup"><span data-stu-id="99f59-166">**Admin**</span></span>|<span data-ttu-id="99f59-167">**委派用户**</span><span class="sxs-lookup"><span data-stu-id="99f59-167">**Delegate**</span></span>|<span data-ttu-id="99f59-168">**所有者**</span><span class="sxs-lookup"><span data-stu-id="99f59-168">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="99f59-169">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="99f59-169">**AddFolderPermissions**</span></span>|<span data-ttu-id="99f59-170">**注意**：尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-170">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="99f59-171">换句话说，请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="99f59-171">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="99f59-172">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="99f59-172">**ApplyRecord**</span></span>|<span data-ttu-id="99f59-173">项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-173">An item is labeled as a record.</span></span>|<span data-ttu-id="99f59-174">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-174">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-175">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-175">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-176">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-176">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-177">**复制**</span><span class="sxs-lookup"><span data-stu-id="99f59-177">**Copy**</span></span>|<span data-ttu-id="99f59-178">已将某个邮件复制到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="99f59-178">A message was copied to another folder.</span></span>|![复选标记](../media/checkmark.png)|||
|<span data-ttu-id="99f59-180">**创建**</span><span class="sxs-lookup"><span data-stu-id="99f59-180">**Create**</span></span>|<span data-ttu-id="99f59-181">在邮箱邮箱的"日历"、"联系人"、"便笺"或"任务"文件夹中创建了 (例如，会创建一个新的会议) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-181">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="99f59-182">不会审核邮件的创建、发送或接收。</span><span class="sxs-lookup"><span data-stu-id="99f59-182">Creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="99f59-183">也不会审核邮箱文件夹的创建。</span><span class="sxs-lookup"><span data-stu-id="99f59-183">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="99f59-184">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-184">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-185">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-185">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="99f59-187">**默认**</span><span class="sxs-lookup"><span data-stu-id="99f59-187">**Default**</span></span>||![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="99f59-191">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="99f59-191">**FolderBind**</span></span>|<span data-ttu-id="99f59-192">已访问某个邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="99f59-192">A mailbox folder was accessed.</span></span> <span data-ttu-id="99f59-193">管理员或代理打开邮箱时也会记录此操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-193">This action is also logged when the admin or delegate opens the mailbox.</span></span> <br/><br/> <span data-ttu-id="99f59-194">**注意**：合并由代理执行的文件夹绑定操作审核记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-194">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="99f59-195">在 24 小时内为单个文件夹访问生成一条审核记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-195">One audit record is generated for individual folder access within a 24-hour period.</span></span>|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)||
|<span data-ttu-id="99f59-198">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="99f59-198">**HardDelete**</span></span>|<span data-ttu-id="99f59-199">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="99f59-199">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="99f59-200">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-200">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-201">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-201">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-202">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-202">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-203">**MailItemsAccessed**</span><span class="sxs-lookup"><span data-stu-id="99f59-203">**MailItemsAccessed**</span></span>|<span data-ttu-id="99f59-204">邮件协议和客户端可以访问邮件数据。</span><span class="sxs-lookup"><span data-stu-id="99f59-204">Mail data is accessed by mail protocols and clients.</span></span> <span data-ttu-id="99f59-205">此值仅适用于 E5 或 E5 合规性附加订阅用户。</span><span class="sxs-lookup"><span data-stu-id="99f59-205">This value is only available for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="99f59-206">有关详细信息，请参阅"[为用户设置高级审核"。](advanced-audit.md#set-up-advanced-audit-for-users)</span><span class="sxs-lookup"><span data-stu-id="99f59-206">For more information, see [Set up Advanced Audit for users](advanced-audit.md#set-up-advanced-audit-for-users).</span></span>|<span data-ttu-id="99f59-207">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-207">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-208">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-208">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-209">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-209">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-210">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="99f59-210">**MailboxLogin**</span></span>|<span data-ttu-id="99f59-211">用户登录到其邮箱。</span><span class="sxs-lookup"><span data-stu-id="99f59-211">The user signed into their mailbox.</span></span> |||![复选标记](../media/checkmark.png)|
|<span data-ttu-id="99f59-213">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="99f59-213">**MessageBind**</span></span>|<span data-ttu-id="99f59-214">邮件在预览窗格中查看或由管理员打开。注意：尽管此值被接受为邮箱操作，但不再记录这些操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-214">A message was viewed in the preview pane or opened by an admin. **Note**: Although this value is accepted as a mailbox action, these actions are no longer logged.</span></span>|![复选标记](../media/checkmark.png)|||
|<span data-ttu-id="99f59-216">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="99f59-216">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="99f59-217">**注意**：尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-217">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="99f59-218">换句话说，请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="99f59-218">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="99f59-219">**移动**</span><span class="sxs-lookup"><span data-stu-id="99f59-219">**Move**</span></span>|<span data-ttu-id="99f59-220">已将某个邮件移至另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="99f59-220">A message was moved to another folder.</span></span>|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="99f59-224">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="99f59-224">**MoveToDeletedItems**</span></span>|<span data-ttu-id="99f59-225">已删除邮件，并已将其移动到“已删除邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="99f59-225">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="99f59-226">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-226">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-227">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-227">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-228">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-228">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-229">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="99f59-229">**RecordDelete**</span></span>|<span data-ttu-id="99f59-230">标记为记录的项目被软删除， ("可恢复的项目"文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-230">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="99f59-231">从"可恢复的项目"文件夹 (无法永久删除标记为记录) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-231">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="99f59-235">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="99f59-235">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="99f59-236">**注意**：尽管此值被接受为邮箱操作，但它已包含在 **UpdateFolderPermissions** 操作中，并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-236">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="99f59-237">换句话说，请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="99f59-237">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="99f59-238">**Send**</span><span class="sxs-lookup"><span data-stu-id="99f59-238">**Send**</span></span>|<span data-ttu-id="99f59-239">用户发送电子邮件、答复电子邮件或转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-239">The user sends an email message, replies to an email message, or forwards an email message.</span></span> <span data-ttu-id="99f59-240">此值仅适用于 E5 或 E5 合规性附加订阅用户。</span><span class="sxs-lookup"><span data-stu-id="99f59-240">This value is only available for E5 or E5 Compliance add-on subscription users.</span></span> <span data-ttu-id="99f59-241">有关详细信息，请参阅"[为用户设置高级审核"。](advanced-audit.md#set-up-advanced-audit-for-users)</span><span class="sxs-lookup"><span data-stu-id="99f59-241">For more information, see [Set up Advanced Audit for users](advanced-audit.md#set-up-advanced-audit-for-users).</span></span>|<span data-ttu-id="99f59-242">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-242">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-243">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-243">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-244">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-244">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-245">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="99f59-245">**SendAs**</span></span>|<span data-ttu-id="99f59-246">已使用“发送方式”权限发送邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-246">A message was sent using the SendAs permission.</span></span> <span data-ttu-id="99f59-247">这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="99f59-247">This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="99f59-248">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-248">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-249">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-249">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="99f59-250">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="99f59-250">**SendOnBehalf**</span></span>|<span data-ttu-id="99f59-251">已使用“代表发送”权限发送邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-251">A message was sent using the SendOnBehalf permission.</span></span> <span data-ttu-id="99f59-252">这表示另一个用户代表邮箱所有者发送了邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-252">This means another user sent the message on behalf of the mailbox owner.</span></span> <span data-ttu-id="99f59-253">邮件将向收件人说明发送此邮件时使用的身份及实际发送者。</span><span class="sxs-lookup"><span data-stu-id="99f59-253">The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="99f59-254">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-254">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-255">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-255">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="99f59-256">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="99f59-256">**SoftDelete**</span></span>|<span data-ttu-id="99f59-257">已永久删除或已从“已删除邮件”文件夹中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-257">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="99f59-258">软删除的项目将移动到"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="99f59-258">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="99f59-259">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-259">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-260">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-260">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-261">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-261">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-262">**更新**</span><span class="sxs-lookup"><span data-stu-id="99f59-262">**Update**</span></span>|<span data-ttu-id="99f59-263">已更改邮件或其属性。</span><span class="sxs-lookup"><span data-stu-id="99f59-263">A message or its properties was changed.</span></span>|<span data-ttu-id="99f59-264">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-264">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-265">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-265">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-266">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-266">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-267">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="99f59-267">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="99f59-268">日历委派已分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="99f59-268">A calendar delegation was assigned to a mailbox.</span></span> <span data-ttu-id="99f59-269">日历代理为同一组织内的其他人授予管理邮箱所有者日历的权限。</span><span class="sxs-lookup"><span data-stu-id="99f59-269">Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="99f59-270">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-270">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||<span data-ttu-id="99f59-271">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-271">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-272">**UpdateComplianceTag**</span><span class="sxs-lookup"><span data-stu-id="99f59-272">**UpdateComplianceTag**</span></span>|<span data-ttu-id="99f59-273">将不同的保留标签应用于邮件项目 (一个项目只能分配有一个保留标签) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-273">A different retention label is applied to a mail item (an item can only have one retention label assigned to it).</span></span>|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|![复选标记](../media/checkmark.png)|
|<span data-ttu-id="99f59-277">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="99f59-277">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="99f59-278">文件夹权限已更改。</span><span class="sxs-lookup"><span data-stu-id="99f59-278">A folder permission was changed.</span></span> <span data-ttu-id="99f59-279">文件夹权限用于控制组织中的哪些用户可以访问邮箱中的文件夹以及位于这些文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-279">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="99f59-280">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-280">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-281">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-281">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-282">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-282">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-283">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="99f59-283">**UpdateInboxRules**</span></span>|<span data-ttu-id="99f59-284">已添加、删除或已更改收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="99f59-284">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="99f59-285">收件箱规则用于根据指定条件处理用户收件箱中的邮件，在满足规则条件时采取措施，例如将邮件移动到指定文件夹或删除邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-285">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="99f59-286">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-286">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-287">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-287">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-288">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-288">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|

> [!IMPORTANT]
> <span data-ttu-id="99f59-289">如果在组织中默认启用邮箱审核之前自定义了要审核的任何登录类型的邮箱操作，则自定义设置将保留在邮箱上，并且不会覆盖默认邮箱操作，如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="99f59-289">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="99f59-290">若要将审核邮箱操作还原到其默认值 (您随时都可以) ，请参阅本主题稍后的"还原默认邮箱操作"部分。 [](#restore-the-default-mailbox-actions)</span><span class="sxs-lookup"><span data-stu-id="99f59-290">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a><span data-ttu-id="99f59-291">Microsoft 365 组邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="99f59-291">Mailbox actions for Microsoft 365 Group mailboxes</span></span>

<span data-ttu-id="99f59-292">默认情况下启用邮箱审核将邮箱审核日志记录引入 Microsoft 365 组邮箱，但无法自定义所记录的内容 (无法添加或删除为任何登录类型) 记录的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-292">Mailbox auditing on by default brings mailbox audit logging to Microsoft 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="99f59-293">下表介绍了每个登录类型的 Microsoft 365 组邮箱上默认记录的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-293">The following table describes the mailbox actions that are logged by default on Microsoft 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="99f59-294">请记住，对 Microsoft 365 组邮箱具有完全访问权限的管理员将被视为代理。</span><span class="sxs-lookup"><span data-stu-id="99f59-294">Remember, an admin with Full Access permission to a Microsoft 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="99f59-295">**邮箱操作**</span><span class="sxs-lookup"><span data-stu-id="99f59-295">**Mailbox action**</span></span>|<span data-ttu-id="99f59-296">**说明**</span><span class="sxs-lookup"><span data-stu-id="99f59-296">**Description**</span></span>|<span data-ttu-id="99f59-297">**管理员**</span><span class="sxs-lookup"><span data-stu-id="99f59-297">**Admin**</span></span>|<span data-ttu-id="99f59-298">**委派用户**</span><span class="sxs-lookup"><span data-stu-id="99f59-298">**Delegate**</span></span>|<span data-ttu-id="99f59-299">**所有者**</span><span class="sxs-lookup"><span data-stu-id="99f59-299">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="99f59-300">**创建**</span><span class="sxs-lookup"><span data-stu-id="99f59-300">**Create**</span></span>|<span data-ttu-id="99f59-301">创建日历项目。</span><span class="sxs-lookup"><span data-stu-id="99f59-301">Creation of a calendar Item.</span></span> <span data-ttu-id="99f59-302">不会审核邮件的创建、发送或接收。</span><span class="sxs-lookup"><span data-stu-id="99f59-302">Creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="99f59-303">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-303">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-304">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-304">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="99f59-305">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="99f59-305">**HardDelete**</span></span>|<span data-ttu-id="99f59-306">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="99f59-306">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="99f59-307">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-307">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-308">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-308">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-309">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-309">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-310">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="99f59-310">**MoveToDeletedItems**</span></span>|<span data-ttu-id="99f59-311">已删除邮件，并已将其移动到“已删除邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="99f59-311">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="99f59-312">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-312">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-313">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-313">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-314">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-314">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-315">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="99f59-315">**SendAs**</span></span>|<span data-ttu-id="99f59-316">已使用“发送方式”权限发送邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-316">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="99f59-317">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-317">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-318">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-318">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="99f59-319">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="99f59-319">**SendOnBehalf**</span></span>|<span data-ttu-id="99f59-320">已使用“代表发送”权限发送邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-320">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="99f59-321">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-321">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-322">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-322">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="99f59-323">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="99f59-323">**SoftDelete**</span></span>|<span data-ttu-id="99f59-324">已永久删除或已从“已删除邮件”文件夹中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="99f59-324">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="99f59-325">软删除的项目将移动到"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="99f59-325">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="99f59-326">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-326">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-327">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-327">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-328">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-328">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="99f59-329">**更新**</span><span class="sxs-lookup"><span data-stu-id="99f59-329">**Update**</span></span>|<span data-ttu-id="99f59-330">已更改邮件或其属性。</span><span class="sxs-lookup"><span data-stu-id="99f59-330">A message or its properties was changed.</span></span>|<span data-ttu-id="99f59-331">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-331">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-332">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-332">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="99f59-333">![复选标记](../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="99f59-333">![Check mark](../media/checkmark.png)<sup>\*</sup></span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="99f59-334">验证是否正在针对每种登录类型记录默认邮箱操作</span><span class="sxs-lookup"><span data-stu-id="99f59-334">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="99f59-335">默认情况下启用的邮箱审核会向所有邮箱添加新 *的 DefaultAuditSet* 属性。</span><span class="sxs-lookup"><span data-stu-id="99f59-335">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="99f59-336">此属性的值指示是否正在审核由 Microsoft (管理的默认) 操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-336">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="99f59-337">若要在用户邮箱或共享邮箱上显示值，请替换为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名) ，然后运行 Exchange Online PowerShell 中的以下 \<MailboxIdentity\> 命令：</span><span class="sxs-lookup"><span data-stu-id="99f59-337">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="99f59-338">若要在 Microsoft 365 组邮箱上显示值，请替换为共享邮箱的名称、别名或电子邮件地址，然后运行 Exchange Online PowerShell 中的以下 \<MailboxIdentity\> 命令：</span><span class="sxs-lookup"><span data-stu-id="99f59-338">To display the value on Microsoft 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="99f59-339">值 `Admin, Delegate, Owner` 指示：</span><span class="sxs-lookup"><span data-stu-id="99f59-339">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="99f59-340">将审核所有三种登录类型的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-340">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="99f59-341">这是你将在 Microsoft 365 组邮箱上看到的唯一值。</span><span class="sxs-lookup"><span data-stu-id="99f59-341">This is the only value you'll see on Microsoft 365 Group mailboxes.</span></span>

- <span data-ttu-id="99f59-342">管理员 *未更改* 用户邮箱或共享邮箱上任何登录类型的审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-342">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="99f59-343">请注意，这是邮箱审核默认在组织中最初打开后的默认状态。</span><span class="sxs-lookup"><span data-stu-id="99f59-343">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="99f59-344">如果管理员曾经使用 **Set-Mailbox** cmdlet) 上的 *AuditAdmin、AuditDelegate* 或 *AuditOwner* 参数更改了审核登录类型 (的邮箱操作，属性值将有所不同。 </span><span class="sxs-lookup"><span data-stu-id="99f59-344">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="99f59-345">例如，用户 `Owner` 邮箱或共享邮箱 *的 DefaultAuditSet* 属性的值指示：</span><span class="sxs-lookup"><span data-stu-id="99f59-345">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="99f59-346">正在审核邮箱所有者的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-346">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="99f59-347">已根据默认操作更改了对 `Delegate` 和 `Admin` 登录类型的审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-347">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="99f59-348">*DefaultAuditSet* 属性的空值指示用户邮箱或共享邮箱上所有三种登录类型的邮箱操作已更改。</span><span class="sxs-lookup"><span data-stu-id="99f59-348">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="99f59-349">有关详细信息，请参阅本主题中的"[](#change-or-restore-mailbox-actions-logged-by-default)更改或还原默认记录的邮箱操作"</span><span class="sxs-lookup"><span data-stu-id="99f59-349">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="99f59-350">显示正在登录邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="99f59-350">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="99f59-351">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f59-351">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="99f59-352">尽管您可以为 Microsoft 365 组邮箱将开关添加到以下 `-GroupMailbox` **Get-Mailbox** 命令，但不要认为返回的值。</span><span class="sxs-lookup"><span data-stu-id="99f59-352">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Microsoft 365 Group mailboxes, don't believe the values that are returned.</span></span> <span data-ttu-id="99f59-353">本主题前面"Microsoft 365 组邮箱的邮箱操作"部分介绍了为 [Microsoft 365](#mailbox-actions-for-microsoft-365-group-mailboxes) 组邮箱审核的默认和静态邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-353">The default and static mailbox actions that are audited for Microsoft 365 Group mailboxes are described in the [Mailbox actions for Microsoft 365 Group mailboxes](#mailbox-actions-for-microsoft-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="99f59-354">所有者操作</span><span class="sxs-lookup"><span data-stu-id="99f59-354">Owner actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="99f59-355">委派操作</span><span class="sxs-lookup"><span data-stu-id="99f59-355">Delegate actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="99f59-356">管理员操作</span><span class="sxs-lookup"><span data-stu-id="99f59-356">Admin actions</span></span>

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="99f59-357">更改或还原默认情况下记录的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="99f59-357">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="99f59-358">如前所述，默认情况下启用邮箱审核的主要好处之一是：无需管理审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-358">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="99f59-359">Microsoft 会为此进行此操作，我们将在发布后自动添加新的邮箱操作，以在默认情况下审核这些操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-359">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="99f59-360">但是，您的组织可能需要审核用户邮箱和共享邮箱的不同邮箱操作集。</span><span class="sxs-lookup"><span data-stu-id="99f59-360">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="99f59-361">本节中的过程将向您展示如何更改针对每种登录类型审核的邮箱操作，以及如何还原回 Microsoft 管理的默认操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-361">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99f59-362">如果您使用以下过程自定义登录用户邮箱或共享邮箱的邮箱操作，Microsoft 发布的任何新的默认邮箱操作将不会在这些邮箱上自动审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-362">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="99f59-363">需要手动将任何新邮箱操作添加到自定义操作列表中。</span><span class="sxs-lookup"><span data-stu-id="99f59-363">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="99f59-364">更改要审核的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="99f59-364">Change the mailbox actions to audit</span></span>

<span data-ttu-id="99f59-365">可以使用 **Set-Mailbox** cmdlet 上的 *AuditAdmin、AuditDelegate* 或 *AuditOwner* 参数更改为用户邮箱和共享邮箱审核的邮箱操作 (无法自定义 Microsoft 365 组邮箱的审核操作) 。 </span><span class="sxs-lookup"><span data-stu-id="99f59-365">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Microsoft 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="99f59-366">可以使用两种不同的方法来指定邮箱操作：</span><span class="sxs-lookup"><span data-stu-id="99f59-366">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="99f59-367">*使用此* (替换) 现有邮箱操作。 `action1,action2,...actionN`</span><span class="sxs-lookup"><span data-stu-id="99f59-367">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="99f59-368">*使用此语法* 添加或删除邮箱操作，而不影响其他现有 `@{Add="action1","action2",..."actionN"}` 值：或 `@{Remove="action1","action2",..."actionN"}` 。</span><span class="sxs-lookup"><span data-stu-id="99f59-368">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="99f59-369">此示例通过用 SoftDelete 和 HardDelete 覆盖默认操作来更改名为"Gabriela Laureano"的邮箱的管理员邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-369">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="99f59-370">本示例将 MailboxLogin 所有者操作添加到邮箱laura@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="99f59-370">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="99f59-371">此示例删除工作组讨论邮箱的 MoveToDeletedItems 委派操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-371">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="99f59-372">无论您使用哪种方法，自定义用户邮箱或共享邮箱上的已审核邮箱操作都会获得以下结果：</span><span class="sxs-lookup"><span data-stu-id="99f59-372">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="99f59-373">对于自定义的登录类型，Microsoft 不再管理审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-373">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="99f59-374">自定义的登录类型不再显示在邮箱的 *DefaultAuditSet* 属性值中，如 [前面所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)。</span><span class="sxs-lookup"><span data-stu-id="99f59-374">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="99f59-375">还原默认邮箱操作</span><span class="sxs-lookup"><span data-stu-id="99f59-375">Restore the default mailbox actions</span></span>

<span data-ttu-id="99f59-376">如果自定义了在用户邮箱或共享邮箱上审核的邮箱操作，可以使用以下语法还原一种或所有登录类型的默认邮箱操作：</span><span class="sxs-lookup"><span data-stu-id="99f59-376">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="99f59-377">可以指定用逗号分隔的多个 *DefaultAuditSet* 值</span><span class="sxs-lookup"><span data-stu-id="99f59-377">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="99f59-378">**注意**：以下过程不适用于 Microsoft 365 组邮箱 (它们仅限于此处所述的 [默认) 。](#mailbox-actions-for-microsoft-365-group-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="99f59-378">**Note**: The following procedures don't apply to Microsoft 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-microsoft-365-group-mailboxes)).</span></span>

<span data-ttu-id="99f59-379">此示例还原邮箱邮箱上所有登录类型的默认审核mark@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="99f59-379">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="99f59-380">此示例还原邮箱 chris@contoso.onmicrosoft.com 上管理员登录类型的默认审核邮箱操作，但保留委派和所有者登录类型的自定义审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-380">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="99f59-381">还原登录类型的默认审核邮箱操作将具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="99f59-381">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="99f59-382">当前邮箱操作列表将替换为登录类型的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="99f59-382">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="99f59-383">Microsoft 发布的任何新邮箱操作都会自动添加到登录类型的审核操作列表中。</span><span class="sxs-lookup"><span data-stu-id="99f59-383">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="99f59-384">邮箱 *的 DefaultAuditSet* 属性值已更新为包含还原的登录类型。</span><span class="sxs-lookup"><span data-stu-id="99f59-384">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="99f59-385">默认情况下，为组织关闭邮箱审核</span><span class="sxs-lookup"><span data-stu-id="99f59-385">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="99f59-386">默认情况下，可以通过在 Exchange Online PowerShell 中运行以下命令来为整个组织关闭邮箱审核：</span><span class="sxs-lookup"><span data-stu-id="99f59-386">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="99f59-387">默认情况下关闭邮箱审核具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="99f59-387">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="99f59-388">为组织禁用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-388">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="99f59-389">在默认情况下禁用邮箱审核时，不会审核任何邮箱操作，即使对邮箱启用了审核 (邮箱的 *AuditEnabled* 属性为 **True**) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-389">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="99f59-390">不会为新邮箱启用邮箱审核，并且将新邮箱或现有邮箱的 *AuditEnabled* 属性设置为 **True** 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="99f59-390">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="99f59-391">使用 **Set-MailboxAuditBypassAssociation** cmdlet (配置的任何邮箱审核旁路关联设置) 忽略。</span><span class="sxs-lookup"><span data-stu-id="99f59-391">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="99f59-392">现有邮箱审核记录将一直保留到审核日志期限到期。</span><span class="sxs-lookup"><span data-stu-id="99f59-392">Existing mailbox audit records are retained until the audit log age limit for the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="99f59-393">默认情况下打开邮箱审核</span><span class="sxs-lookup"><span data-stu-id="99f59-393">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="99f59-394">若要为组织重新启用邮箱审核，请运行 Exchange Online PowerShell 中的以下命令：</span><span class="sxs-lookup"><span data-stu-id="99f59-394">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="99f59-395">绕过邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="99f59-395">Bypass mailbox audit logging</span></span>

<span data-ttu-id="99f59-396">目前，当组织中默认启用邮箱审核时，无法禁用特定邮箱的邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-396">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="99f59-397">例如，将 *AuditEnabled 邮箱属性* 设置为 **False** 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="99f59-397">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="99f59-398">但是，您仍可以使用 Exchange Online PowerShell 中的 **Set-MailboxAuditBypassAssociation** cmdlet 阻止记录指定用户的任何和所有邮箱操作，无论操作发生的位置如何。 </span><span class="sxs-lookup"><span data-stu-id="99f59-398">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="99f59-399">例如：</span><span class="sxs-lookup"><span data-stu-id="99f59-399">For example:</span></span>

- <span data-ttu-id="99f59-400">旁路用户执行的邮箱所有者操作不会记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-400">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="99f59-401">被绕过用户在其他用户的邮箱上执行的委派操作 (包括未) 共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="99f59-401">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="99f59-402">旁路用户执行的管理员操作不会记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-402">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="99f59-403">若要绕过特定用户的邮箱审核日志记录，请替换为该用户的名称、电子邮件地址、别名或用户主体名称 (用户名) 并运行 \<MailboxIdentity\> 以下命令：</span><span class="sxs-lookup"><span data-stu-id="99f59-403">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="99f59-404">若要验证是否绕过指定用户的审核，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="99f59-404">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="99f59-405">值为 **True** 表示已绕过用户的邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-405">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="99f59-406">详细信息</span><span class="sxs-lookup"><span data-stu-id="99f59-406">More information</span></span>

- <span data-ttu-id="99f59-407">尽管默认情况下会为所有组织启用邮箱审核日志记录，但只有拥有 E5 许可证的用户才能在安全 & 合规中心或通过 [Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)管理活动 API 在 审核日志 搜索中返回邮箱 [审核日志](search-the-audit-log-in-security-and-compliance.md)**事件**。</span><span class="sxs-lookup"><span data-stu-id="99f59-407">Although mailbox audit logging on by default is enabled for all organizations, only users with E5 licenses will return mailbox audit log events in [audit log searches in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md) or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) **by default**.</span></span>

  <span data-ttu-id="99f59-408">若要检索审核日志 E5 许可证的用户的邮箱邮箱条目，您可以：</span><span class="sxs-lookup"><span data-stu-id="99f59-408">To retrieve mailbox audit log entries for users without E5 licenses, you can:</span></span>

  - <span data-ttu-id="99f59-409">手动启用单个邮箱的邮箱审核 (运行命令 `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ，) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-409">Manually enable mailbox auditing on individual mailboxes (run the command, `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true`).</span></span> <span data-ttu-id="99f59-410">完成此操作后，可以使用安全审核日志合规中心& Office 365 管理活动 API 进行搜索。</span><span class="sxs-lookup"><span data-stu-id="99f59-410">After you do this, you can use audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="99f59-411">如果邮箱审核似乎已在邮箱上启用，但您的搜索未返回任何结果，请更改 _AuditEnabled_ 参数的值，然后再更改 `$false` 回 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="99f59-411">If mailbox auditing already appears to be enabled on the mailbox, but your searches return no results, change the value of the _AuditEnabled_ parameter to `$false` and then back to `$true`.</span></span>
  
  - <span data-ttu-id="99f59-412">在 Exchange Online PowerShell 中使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="99f59-412">Use the following cmdlets in Exchange Online PowerShell:</span></span>

    - <span data-ttu-id="99f59-413">[Search-MailboxAuditLog，](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) 用于搜索审核日志用户的邮箱邮箱。</span><span class="sxs-lookup"><span data-stu-id="99f59-413">[Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) to search the mailbox audit log for specific users.</span></span>

    - <span data-ttu-id="99f59-414">[New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) 可搜索审核日志用户的邮箱邮箱，并通过电子邮件将结果发送给指定收件人。</span><span class="sxs-lookup"><span data-stu-id="99f59-414">[New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxauditlogsearch) to search the mailbox audit log for specific users and to have the results sent via email to specified recipients.</span></span>

  - <span data-ttu-id="99f59-415">在 Exchange Online (EAC) Exchange 管理中心执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="99f59-415">Use the Exchange admin center (EAC) in Exchange Online to do the following actions:</span></span>

    - [<span data-ttu-id="99f59-416">导出邮箱审核日志</span><span class="sxs-lookup"><span data-stu-id="99f59-416">Export mailbox audit logs</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [<span data-ttu-id="99f59-417">运行非所有者邮箱访问报告</span><span class="sxs-lookup"><span data-stu-id="99f59-417">Run a non-owner mailbox access report</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- <span data-ttu-id="99f59-418">默认情况下，邮箱审核日志记录在删除前保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="99f59-418">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="99f59-419">您可以使用 Exchange Online PowerShell 中 **Set-Mailbox** cmdlet 上的 *AuditLogAgeLimit* 参数更改审核日志记录期限。</span><span class="sxs-lookup"><span data-stu-id="99f59-419">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="99f59-420">但是，如果增加此值，则不允许搜索超过 90 天的事件。审核日志。</span><span class="sxs-lookup"><span data-stu-id="99f59-420">However, increasing this value doesn't allow you to search for events that are older than 90 days in the audit log.</span></span>

  <span data-ttu-id="99f59-421">如果增加期限，则需要使用 Exchange Online PowerShell 中的 [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) cmdlet 在用户的邮箱 审核日志 中搜索超过 90 天的记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-421">If you increase the age limit, you need to use the [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="99f59-422">如果在默认情况下为组织启用邮箱审核之前更改了邮箱的 *AuditLogAgeLimit* 属性，则邮箱的现有 审核日志 期限不会更改。</span><span class="sxs-lookup"><span data-stu-id="99f59-422">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="99f59-423">换句话说，默认情况下启用的邮箱审核不会影响邮箱审核记录的当前期限。</span><span class="sxs-lookup"><span data-stu-id="99f59-423">In other words, mailbox auditing on by default doesn't affect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="99f59-424">若要更改 Microsoft 365 组邮箱上的 *AuditLogAgeLimit* 值，需要将开关包括在 `-GroupMailbox` **Set-Mailbox** 命令中。</span><span class="sxs-lookup"><span data-stu-id="99f59-424">To change the *AuditLogAgeLimit* value on a Microsoft 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="99f59-425">邮箱审核日志存储在每个用户邮箱的 ("可恢复的项目"文件夹中) "审核"子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="99f59-425">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="99f59-426">对于邮箱审核记录和"可恢复的项目"文件夹，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="99f59-426">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="99f59-427">邮箱审核记录计入"可恢复邮件"文件夹的存储配额，默认为 30 GB， (警告配额为 20 GB) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-427">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30 GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="99f59-428">当发生以下事件时，存储配额 (90 GB 警告配额) 达到 100 GB：</span><span class="sxs-lookup"><span data-stu-id="99f59-428">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="99f59-429">将邮箱置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="99f59-429">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="99f59-430">邮箱将分配给合规性中心中的保留策略。</span><span class="sxs-lookup"><span data-stu-id="99f59-430">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="99f59-431">邮箱审核记录还计入"可恢复的项目"文件夹 [的文件夹限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)。</span><span class="sxs-lookup"><span data-stu-id="99f59-431">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="99f59-432">审核记录中最多可 (300 万) 审核记录存储在"审核"子文件夹内。</span><span class="sxs-lookup"><span data-stu-id="99f59-432">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99f59-433">默认情况下，邮箱审核不太可能影响"可恢复的项目"文件夹的存储配额或文件夹限制。</span><span class="sxs-lookup"><span data-stu-id="99f59-433">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="99f59-434">您可以在 Exchange Online PowerShell 中运行以下命令，以显示"可恢复的项目"文件夹中"审核"子文件夹中的项目大小和数量：</span><span class="sxs-lookup"><span data-stu-id="99f59-434">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="99f59-435">You can't directly access an 审核日志 record in the Recoverable Items folder;而是使用 **Search-MailboxAuditLog** cmdlet 或搜索审核日志查找和查看邮箱审核记录。</span><span class="sxs-lookup"><span data-stu-id="99f59-435">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="99f59-436">如果邮箱处于保留状态或分配给合规中心中的保留策略，审核日志 记录在默认情况下仍保留由邮箱 *的 AuditLogAgeLimit* 属性定义的持续时间 (90) 。</span><span class="sxs-lookup"><span data-stu-id="99f59-436">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="99f59-437">若要将审核日志保留的邮箱保留更长时间，需要增加邮箱 *的 AuditLogAgeLimit* 值。</span><span class="sxs-lookup"><span data-stu-id="99f59-437">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>

- <span data-ttu-id="99f59-438">在多地理位置环境中，不支持跨地理位置邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="99f59-438">In a multi-geo environment, cross-geo mailbox auditing is not supported.</span></span> <span data-ttu-id="99f59-439">例如，如果为某用户分配了访问其他地理位置的共享邮箱的权限，此用户执行的邮箱操作不会记录在共享邮箱的邮箱审核日志中。</span><span class="sxs-lookup"><span data-stu-id="99f59-439">For example, if a user is assigned permissions to access a shared mailbox in a different geo location, mailbox actions performed by that user are not logged in the mailbox audit log of the shared mailbox.</span></span>
