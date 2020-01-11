---
title: 隔离常见问题解答
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 本主题提供了关于托管隔离的常见问题及解答。
ms.openlocfilehash: d275a919e58d2a908fb10d4dff412ebe0859662f
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021838"
---
# <a name="quarantine-faq"></a><span data-ttu-id="68811-103">隔离常见问题解答</span><span class="sxs-lookup"><span data-stu-id="68811-103">Quarantine FAQ</span></span>

<span data-ttu-id="68811-p101">本主题提供了关于托管隔离的常见问题及解答。解答适用于 Microsoft Exchange Online 和 Exchange Online Protection 客户。</span><span class="sxs-lookup"><span data-stu-id="68811-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>

 <span data-ttu-id="68811-106">**问：如何在隔离中管理恶意软件隔离的邮件？**</span><span class="sxs-lookup"><span data-stu-id="68811-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>

<span data-ttu-id="68811-107">您需要使用安全 & 合规性中心，以便查看和处理发送到隔离的邮件，因为它们包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="68811-107">You need to use the Security & Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware.</span></span> <span data-ttu-id="68811-108">有关详细信息，请参阅[在 Office 365 中隔离电子邮件消息](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="68811-108">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

 <span data-ttu-id="68811-109">**问：如何将该服务配置为将垃圾邮件隔离的邮件发送到隔离邮箱？**</span><span class="sxs-lookup"><span data-stu-id="68811-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>

<span data-ttu-id="68811-p103">答：默认情况下，经过内容筛选的邮件将发送到收件人的垃圾邮件文件夹。但是，管理员可以将内容筛选器策略配置为将垃圾邮件隔离邮件转为发送到隔离邮箱。有关可以对内容筛选邮件执行的不同操作的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="68811-p103">A. By default, content-filtered messages are sent to the recipients Junk Email folder. However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead. For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="68811-114">**问：该服务具有对垃圾邮件隔离消息的管理员和最终用户管理吗？**</span><span class="sxs-lookup"><span data-stu-id="68811-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>

<span data-ttu-id="68811-115">A.</span><span class="sxs-lookup"><span data-stu-id="68811-115">A.</span></span> <span data-ttu-id="68811-116">作为管理员，你可以在安全与合规中心（SCC）中搜索和查看有关所有隔离电子邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="68811-116">As an admin, you can search for and view details about all quarantined email messages in the Security and Compliance Center (SCC).</span></span> <span data-ttu-id="68811-117">在查找邮件之后，您可以将其发布到特定用户，并根据需要将其报告为 Microsoft 垃圾邮件分析团队的误报（非垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="68811-117">After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="68811-118">有关详细信息，请参阅[在 Office 365 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="68811-118">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="68811-119">作为最终用户，您可以通过以下方式管理自己的垃圾邮件隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="68811-119">As an end user, you can manage your own spam-quarantined messages via:</span></span>

- <span data-ttu-id="68811-120">垃圾邮件隔离用户界面。</span><span class="sxs-lookup"><span data-stu-id="68811-120">The spam quarantine user interface.</span></span> <span data-ttu-id="68811-121">有关详细信息，请参阅[在 Office 365 中查找并以用户的方式释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="68811-121">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

 <span data-ttu-id="68811-122">**问：如何向最终用户授予对隔离的访问权限？**</span><span class="sxs-lookup"><span data-stu-id="68811-122">**Q. How do I grant access to quarantine for my end users?**</span></span>

<span data-ttu-id="68811-123">A.</span><span class="sxs-lookup"><span data-stu-id="68811-123">A.</span></span> <span data-ttu-id="68811-124">若要访问最终用户垃圾邮件隔离邮箱，最终用户必须具有有效 Office 365 用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="68811-124">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="68811-125">保护本地邮箱的 EOP 客户必须是通过目录同步或 EAC 创建的有效电子邮件用户。</span><span class="sxs-lookup"><span data-stu-id="68811-125">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="68811-126">有关管理用户的详细信息，EOP 管理员可以参阅[Manage mail users IN EOP](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="68811-126">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="68811-127">对于 EOP 独立客户，建议使用目录同步并启用基于目录的边缘阻止，有关详细信息，请参阅[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="68811-127">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

 <span data-ttu-id="68811-128">**问：最终用户可以访问隔离区中的哪些邮件？**</span><span class="sxs-lookup"><span data-stu-id="68811-128">**Q. What messages can end users access in quarantine?**</span></span>

<span data-ttu-id="68811-129">A.</span><span class="sxs-lookup"><span data-stu-id="68811-129">A.</span></span> <span data-ttu-id="68811-130">最终用户可以访问自己的网络钓鱼、垃圾邮件和批量邮件。</span><span class="sxs-lookup"><span data-stu-id="68811-130">End users can access their own phish, spam, and bulk mail.</span></span> <span data-ttu-id="68811-131">最终用户无法访问其自己的恶意软件、高可信度网络钓鱼或与邮件流规则匹配的邮件（也称为传输规则）;这些仅在管理员隔离区中可用。</span><span class="sxs-lookup"><span data-stu-id="68811-131">End users can't access their own malware, high confidence phish, or messages that matched a mail flow rule (also known as a transport rule); these are only available in the admin quarantine.</span></span> 

 <span data-ttu-id="68811-132">**问：邮件将在隔离邮箱中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="68811-132">**Q. For how long are messages kept in the quarantine?**</span></span>

<span data-ttu-id="68811-133">A.</span><span class="sxs-lookup"><span data-stu-id="68811-133">A.</span></span> <span data-ttu-id="68811-134">默认情况下，垃圾邮件隔离的邮件在隔离中保留30天，而与邮件流规则匹配的隔离邮件将在隔离中保留最长30天（基于默认内容筛选策略中设置的保留期）。</span><span class="sxs-lookup"><span data-stu-id="68811-134">By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for up to 30 days based on the retention period set in your default content filter policy.</span></span> <span data-ttu-id="68811-135">在此时间段后，邮件将被删除且不可检索。</span><span class="sxs-lookup"><span data-stu-id="68811-135">After this period of time the messages are deleted and are not retrievable.</span></span> <span data-ttu-id="68811-136">与邮件流规则匹配的隔离邮件的保留期不可配置。</span><span class="sxs-lookup"><span data-stu-id="68811-136">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="68811-137">但是，垃圾邮件隔离邮件的保留期可以通过内容筛选器策略中的 "**保留垃圾邮件（天）** " 设置来降低。</span><span class="sxs-lookup"><span data-stu-id="68811-137">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="68811-138">有关详细信息，请参阅“[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)”。</span><span class="sxs-lookup"><span data-stu-id="68811-138">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="68811-139">**问：可以一次释放或报告多个被隔离的邮件吗？**</span><span class="sxs-lookup"><span data-stu-id="68811-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>

<span data-ttu-id="68811-140">A.</span><span class="sxs-lookup"><span data-stu-id="68811-140">A.</span></span> <span data-ttu-id="68811-141">是的，在隔离门户中一次最多可以释放100封邮件。</span><span class="sxs-lookup"><span data-stu-id="68811-141">Yes, up to 100 messages can be released at one time in the Quarantine portal.</span></span> <span data-ttu-id="68811-142">此外，管理员还可以创建远程 Windows PowerShell 脚本来完成此任务。</span><span class="sxs-lookup"><span data-stu-id="68811-142">In addition, admins can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="68811-143">使用[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet 搜索邮件，并使用[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet 释放邮件。</span><span class="sxs-lookup"><span data-stu-id="68811-143">Use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for messages, and the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet to release them.</span></span>

 <span data-ttu-id="68811-144">**问：搜索被隔离邮件时是否支持通配符？是否可以搜索特定域的隔离邮件？**</span><span class="sxs-lookup"><span data-stu-id="68811-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>

<span data-ttu-id="68811-p110">答：在 Exchange 管理员中心指定搜索条件时，不支持通配符。例如，在搜索某个发件人时，必须指定完整的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="68811-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>

<span data-ttu-id="68811-148">通过远程 Windows PowerShell，管理员可以指定 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet 以搜索特定域的隔离邮件（例如 contoso.com）：</span><span class="sxs-lookup"><span data-stu-id="68811-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="68811-p111">可将结果传递给 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet。包括 -ReleaseToAll 参数以将邮件释放给所有收件人。邮件释放后，无法再次释放该邮件。</span><span class="sxs-lookup"><span data-stu-id="68811-p111">The results can be passed to the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
