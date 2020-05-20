---
title: Microsoft 365 中的最终用户垃圾邮件通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以在 Exchange Online Protection （EOP）中了解有关隔离邮件的最终用户垃圾邮件通知。
ms.openlocfilehash: 7d4cf21ade504e999dc5b53ad9062977369561c6
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294237"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="2722c-103">使用用户垃圾邮件通知释放和报告隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="2722c-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="2722c-104">在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online 保护（EOP）组织中具有邮箱的 Microsoft 365 组织中，隔离会保留可能有害或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="2722c-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="2722c-105">有关详细信息，请参阅[EOP 中的隔离邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2722c-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="2722c-106">默认情况下，在反垃圾邮件策略中禁用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="2722c-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="2722c-107">当管理员[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)后，收件人（包括共享邮箱）将收到有关被隔离为垃圾邮件、批量电子邮件或（截止到2020年4月）的网络钓鱼的定期通知。</span><span class="sxs-lookup"><span data-stu-id="2722c-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="2722c-108">被隔离为高可信度网络钓鱼、恶意软件或通过邮件流规则（也称为传输规则）的邮件仅适用于管理员。</span><span class="sxs-lookup"><span data-stu-id="2722c-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="2722c-109">有关详细信息，请参阅[在 EOP 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="2722c-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="2722c-110">最终用户垃圾邮件通知包含每个隔离邮件的以下信息：</span><span class="sxs-lookup"><span data-stu-id="2722c-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="2722c-111">**发件人**：隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2722c-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="2722c-112">**Subject**：隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="2722c-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="2722c-113">**日期**：邮件被隔离的日期和时间（以 UTC 为单位）。</span><span class="sxs-lookup"><span data-stu-id="2722c-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="2722c-114">**阻止发件人**：单击此链接可将发件人添加到阻止发件人列表。</span><span class="sxs-lookup"><span data-stu-id="2722c-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="2722c-115">有关详细信息，请参阅[在 Outlook 中阻止邮件发件人](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="2722c-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="2722c-116">**Release**：对于垃圾邮件（不是网络钓鱼）邮件，您可以在此处释放邮件，而无需隔离安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="2722c-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="2722c-117">**查看**：单击此链接可转到 Security & 合规性中心中的隔离，可在其中释放、删除或报告隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="2722c-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="2722c-118">有关详细信息，请参阅[在 EOP 中以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="2722c-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![最终用户垃圾邮件通知示例](../../media/end-user-spam-notification.png)
