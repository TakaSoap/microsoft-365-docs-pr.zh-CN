---
title: 在 Office 365 中隔离电子邮件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: 您可以在 Office 365 中为传入电子邮件设置隔离，在其中已被筛选为垃圾邮件、批量、网络钓鱼邮件和恶意软件的传入电子邮件可以保留下来供以后查看。
ms.openlocfilehash: f7669f69abb711d71362057f2019b0dd7e30443b
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021848"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="c0f17-103">在 Office 365 中隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="c0f17-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="c0f17-104">您可以在 Office 365 中为传入电子邮件设置隔离，其中已被筛选为垃圾邮件的邮件、批量邮件、网络钓鱼邮件、包含恶意软件的邮件以及与指定的邮件流规则匹配的邮件（也称为 trasport 规则）可供以后保留概述.</span><span class="sxs-lookup"><span data-stu-id="c0f17-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule (also known as a trasport rule) can be kept for later review.</span></span>
  
<span data-ttu-id="c0f17-105">默认情况下，为网络钓鱼、恶意软件和邮件流规则筛选的邮件将被发送到隔离，而被筛选为垃圾邮件和批量邮件的邮件将被发送到收件人的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c0f17-105">By default, messages that were filtered for phishing, malware, and mail flow rules are sent to quarantine, while messages that were filtered as spam and bulk mail are sent to the recipients' Junk Email folder.</span></span> <span data-ttu-id="c0f17-106">作为管理员，您可以设置垃圾邮件筛选器策略（也称为 "内容筛选器策略"），以便改为将垃圾邮件和批量邮件发送到隔离。</span><span class="sxs-lookup"><span data-stu-id="c0f17-106">As an admin, you can set up spam filter policies (also known as content filter policies) to send spam and bulk mail messages to quarantine instead.</span></span> <span data-ttu-id="c0f17-107">有关详细信息，请参阅“[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)”。</span><span class="sxs-lookup"><span data-stu-id="c0f17-107">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="c0f17-108">用户和管理员都可以使用隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="c0f17-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="c0f17-109">用户只能在隔离中处理自己的已筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="c0f17-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="c0f17-110">管理员可以搜索和管理所有用户的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="c0f17-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="c0f17-111">高可信度网络钓鱼邮件和通过邮件流规则操作隔离的邮件仅在管理员隔离区中可用。</span><span class="sxs-lookup"><span data-stu-id="c0f17-111">High confidence phish messages and messages quarantined by mail flow rule actions are only available in the admin quarantine.</span></span> <span data-ttu-id="c0f17-112">用户可以访问自己的网络钓鱼邮件、垃圾邮件和批量邮件。</span><span class="sxs-lookup"><span data-stu-id="c0f17-112">Users can access their own phish, spam, and bulk mail messages.</span></span> 
  
<span data-ttu-id="c0f17-113">了解有关使用隔离邮件的详细信息：</span><span class="sxs-lookup"><span data-stu-id="c0f17-113">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="c0f17-114">以管理员身份管理隔离邮件</span><span class="sxs-lookup"><span data-stu-id="c0f17-114">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="c0f17-115">以用户身份查找并释放隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="c0f17-115">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="c0f17-116">使用用户垃圾邮件通知释放和报告垃圾邮件隔离邮件</span><span class="sxs-lookup"><span data-stu-id="c0f17-116">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="c0f17-117">隔离常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c0f17-117">Quarantine FAQ</span></span>](quarantine-faq.md)
