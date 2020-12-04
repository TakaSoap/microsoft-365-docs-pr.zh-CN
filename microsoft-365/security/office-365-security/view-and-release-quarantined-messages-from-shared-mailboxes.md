---
title: 查看并释放共享邮箱中的隔离邮件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 用户可以了解如何查看和操作发送到他们有权访问的共享邮箱的隔离邮件。
ms.openlocfilehash: 0c165395edc3a3032ece603cb8d9aac875443d7d
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570929"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a><span data-ttu-id="84e86-103">查看并释放共享邮箱中的隔离邮件</span><span class="sxs-lookup"><span data-stu-id="84e86-103">View and release quarantined messages from shared mailboxes</span></span>

> [!NOTE]
> <span data-ttu-id="84e86-104">本文中所述的功能目前处于预览阶段，不可用于所有人，并且可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="84e86-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="84e86-105">如果隔离邮件是以 [EOP 中的用户的方式查找和释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)中所述的收件人之一，则用户可以对这些邮件进行管理。</span><span class="sxs-lookup"><span data-stu-id="84e86-105">Users can manage quarantined messages where they are one of the recipients as described in [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="84e86-106">但是，如果用户具有对邮箱的完全访问权限和 "代理发送" 或 "代表发送" 权限的共享邮箱，如 [Exchange Online 中的共享邮箱](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)中所述，则该怎么办？</span><span class="sxs-lookup"><span data-stu-id="84e86-106">But what about shared mailboxes where the user has Full Access and Send As or Send on Behalf permissions to the mailbox as described in [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?</span></span>

<span data-ttu-id="84e86-107">以前，用户可以管理发送到共享邮箱的隔离邮件。若要使自动映射为共享 (邮箱启用了邮箱，默认情况下，当管理员授予用户对另一个邮箱) 的访问权限时，默认情况下会启用该功能。</span><span class="sxs-lookup"><span data-stu-id="84e86-107">Previously, the ability for users to manage quarantined messages sent to a shared mailbox required admins to leave automapping enabled for the shared mailbox (it's enabled by default when an admin gives a user access to another mailbox).</span></span> <span data-ttu-id="84e86-108">但是，根据用户有权访问的邮箱的大小和数量，在 Outlooks 尝试打开用户有权访问的 *所有* 邮箱时，性能可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="84e86-108">However, depending on the size and number of mailboxes that the user has access to, performance can suffer as Outlooks tries to open *all* mailboxes that the user has access to.</span></span> <span data-ttu-id="84e86-109">因此，许多管理员选择 [删除共享邮箱的自动映射](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="84e86-109">For this reason, many admins choose to [remove automapping for shared mailboxes](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="84e86-110">现在，用户不再需要自动映射来管理发送到共享邮箱的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="84e86-110">Now, automapping is no longer required for users to manage quarantined messages that were sent to shared mailboxes.</span></span> <span data-ttu-id="84e86-111">它仅适用于工作。</span><span class="sxs-lookup"><span data-stu-id="84e86-111">It just works.</span></span> <span data-ttu-id="84e86-112">有两种不同的方法可用于访问发送到共享邮箱的隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="84e86-112">There are two different methods to access quarantined messages that were sent to a shared mailbox:</span></span>

- <span data-ttu-id="84e86-113">如果管理员已在反垃圾邮件策略中 [启用了最终用户垃圾邮件通知](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) ，则有权访问共享邮箱中的最终用户垃圾邮件通知的任何用户都可以单击通知中的 " **审阅** " 按钮，以转到安全 & 合规性中心中的 "隔离"。</span><span class="sxs-lookup"><span data-stu-id="84e86-113">If the admin has [enabled end-user spam notifications](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in anti-spam policies, any user that has access to the end-user spam notifications in the shared mailbox can click the **Review** button in the notification to go to quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="84e86-114">请注意，此方法仅允许用户管理发送到共享邮箱的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="84e86-114">Note that this method only allows users to manage quarantined messages that were sent to the shared mailbox.</span></span> <span data-ttu-id="84e86-115">用户无法在此上下文中管理自己的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="84e86-115">Users can't manage their own quarantine messages in this context.</span></span>

- <span data-ttu-id="84e86-116">用户可以 [转到 Security & 合规性中心中的隔离](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="84e86-116">The user can [go to the quarantine in the Security & Compliance Center](find-and-release-quarantined-messages-as-a-user.md).</span></span> <span data-ttu-id="84e86-117">默认情况下，仅显示发送给用户的邮件。</span><span class="sxs-lookup"><span data-stu-id="84e86-117">By default, only messages that were sent to the user are shown.</span></span> <span data-ttu-id="84e86-118">但是，用户可以更改 **邮件 ID 按钮** (的 **排序结果**，默认情况下) "**收件人电子邮件地址**"，输入共享邮箱电子邮件地址，然后单击 "**刷新**" 以查看发送到共享邮箱的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="84e86-118">However, the user can change the **Sort results** (the **Message ID button** by default) to **Recipient email address**, enter the shared mailbox email address, and then click **Refresh** to see the quarantined messages that were sent to the shared mailbox.</span></span>

  ![按收件人电子邮件地址对隔离邮件进行排序。](../../media/quarantine-sort-results-by-recipient-email-address.png)

<span data-ttu-id="84e86-120">无论采用哪种方法，用户都可以通过包含隔离邮件的 **收件人** 列来避免混淆。</span><span class="sxs-lookup"><span data-stu-id="84e86-120">Regardless of the method, users can avoid confusion by including the **Recipient** column for quarantined messages.</span></span> <span data-ttu-id="84e86-121">要显示的最大列数为7，因此用户需要单击 " **修改列**"，删除现有列 (例如，" **策略类型** " ") "，选择 " **收件人**"，然后单击 " **保存** " 或 " **另存为默认值**"。</span><span class="sxs-lookup"><span data-stu-id="84e86-121">The maximum number of columns to display is 7, so the user will need to click **Modify columns**, remove an existing column (for example, **Policy type**), select **Recipient**, and then click **Save** or **Save as default**.</span></span>

  ![删除 "策略类型" 列并将 "收件人" 列添加到 "隔离"。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a><span data-ttu-id="84e86-123">要记住的事项</span><span class="sxs-lookup"><span data-stu-id="84e86-123">Things to keep in mind</span></span>

- <span data-ttu-id="84e86-124">对隔离邮件进行操作的第一个用户为使用共享邮箱的每个人决定邮件的 fate。</span><span class="sxs-lookup"><span data-stu-id="84e86-124">The first user to act on the quarantined message decides the fate of the message for everyone who uses the shared mailbox.</span></span> <span data-ttu-id="84e86-125">例如，如果有10个用户访问共享邮箱，并且用户决定删除隔离邮件，则会删除所有10个用户的邮件。</span><span class="sxs-lookup"><span data-stu-id="84e86-125">For example, if a shared mailbox is accessed by 10 users, and a user decides to delete the quarantine message, the message is deleted for all 10 users.</span></span> <span data-ttu-id="84e86-126">同样，如果用户决定释放邮件，则会将其发布到共享邮箱，并可供共享邮箱的所有其他用户访问。</span><span class="sxs-lookup"><span data-stu-id="84e86-126">Likewise, if a user decides to release the message, it's released to the shared mailbox and is accessible by all other users of the shared mailbox.</span></span>

- <span data-ttu-id="84e86-127">目前，如果用户选择发送到共享邮箱的多个隔离邮件，则当用户单击 "**释放邮件**" 或 "删除 **批量操作**" 浮出控件中的 **邮件** 时，将返回以下误导性错误：</span><span class="sxs-lookup"><span data-stu-id="84e86-127">Currently, if a user selects multiple quarantined messages that were sent to the shared mailbox, the following misleading errors are returned when the user clicks **Release messages** or **Delete messages** in the **Bulk actions** flyout:</span></span>

  > <span data-ttu-id="84e86-128">您没有权限释放所有选定的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="84e86-128">You do not have permission to release all selected quarantined messages.</span></span>
  >
  > <span data-ttu-id="84e86-129">您没有删除所有选定的隔离邮件的权限。</span><span class="sxs-lookup"><span data-stu-id="84e86-129">You do not have permission to delete all selected quarantined messages.</span></span>

  <span data-ttu-id="84e86-130">无论错误是什么，都会对邮件执行操作，并且可以忽略该错误。</span><span class="sxs-lookup"><span data-stu-id="84e86-130">Regardless of the error, the action is taken on the messages, and the error can be ignored.</span></span>

  ![当批量释放或删除发送到共享邮箱的隔离邮件时，返回 False 错误。](../../media/quarantine-bulk-action-error.png)

- <span data-ttu-id="84e86-132">目前，" **阻止发件人** " 按钮在已发送到共享邮箱的隔离邮件的 " **详细信息** " 浮出控件中不可用。</span><span class="sxs-lookup"><span data-stu-id="84e86-132">Currently, the **Block sender** button is not available in the **Details** flyout for quarantined messages that were sent to the shared mailbox.</span></span>

- <span data-ttu-id="84e86-133">若要在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中管理共享邮箱的隔离邮件，最终用户需要将 [get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet 与共享邮箱电子邮件地址结合使用，以确定邮件的 _RecipientAddress_ 参数值。</span><span class="sxs-lookup"><span data-stu-id="84e86-133">To manage quarantined messages for the shared mailbox in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), the end-user will need to use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) cmdlet with shared mailbox email address for the value of the _RecipientAddress_ parameter to identify the messages.</span></span> <span data-ttu-id="84e86-134">例如：</span><span class="sxs-lookup"><span data-stu-id="84e86-134">For example:</span></span>

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  <span data-ttu-id="84e86-135">然后，最终用户可以从列表中选择隔离的邮件以进行查看或对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="84e86-135">Then, the end-user can select a quarantined message from the list to view or take action on.</span></span>

  <span data-ttu-id="84e86-136">本示例显示发送到共享邮箱的所有隔离邮件，然后从隔离区中释放列表中的第一封邮件， (列表中的第一条消息为0，第二个是1，依此类推) 。</span><span class="sxs-lookup"><span data-stu-id="84e86-136">This example shows all of the quarantined messages that were sent to the shared mailbox, and then releases the first message in the list from quarantine (the first message in the list is 0, the second is 1, and so on).</span></span>

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  <span data-ttu-id="84e86-137">有关语法和参数的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="84e86-137">For detailed syntax and parameter information, see the following topics:</span></span>

  - [<span data-ttu-id="84e86-138">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="84e86-138">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [<span data-ttu-id="84e86-139">QuarantineMessageHeader</span><span class="sxs-lookup"><span data-stu-id="84e86-139">Get-QuarantineMessageHeader</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [<span data-ttu-id="84e86-140">预览-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="84e86-140">Preview-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [<span data-ttu-id="84e86-141">发布-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="84e86-141">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
