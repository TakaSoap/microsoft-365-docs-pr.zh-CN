---
title: 隔离邮件常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 管理员可以在 Exchange Online Protection 邮箱中查看有关隔离邮件的常见问题 (解) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826785"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="4069f-103">隔离邮件常见问题解答</span><span class="sxs-lookup"><span data-stu-id="4069f-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="4069f-104">本主题提供了有关 Exchange Online 中邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的隔离电子邮件的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="4069f-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="4069f-105">有关反垃圾邮件保护的问题和解答，请参阅"[反垃圾邮件保护常见问题解答"。](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="4069f-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="4069f-106">有关反恶意软件保护的问题和解答，请参阅"[反恶意软件保护常见问题解答"。](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="4069f-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="4069f-107">有关反欺骗保护的问题和解答，请参阅反 [欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="4069f-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="4069f-108">如何管理被恶意软件隔离的邮件？</span><span class="sxs-lookup"><span data-stu-id="4069f-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="4069f-109">只有管理员可以管理被隔离的恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="4069f-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="4069f-110">有关详细信息，请参阅 [以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="4069f-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="4069f-111">如何隔离垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="4069f-111">How do I quarantine spam?</span></span>

<span data-ttu-id="4069f-112">默认情况下，按垃圾邮件筛选分类为垃圾邮件或批量电子邮件的邮件会传递到用户邮箱，并移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="4069f-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="4069f-113">但是，您可以创建和配置反垃圾邮件策略来代封垃圾邮件或批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4069f-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="4069f-114">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4069f-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="4069f-115">如何授予用户访问隔离权限？</span><span class="sxs-lookup"><span data-stu-id="4069f-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="4069f-116">用户必须拥有有效帐户才能访问其自己的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="4069f-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="4069f-117">独立 EOP 要求用户在 EOP 中表示为邮件用户 (通过目录同步工具手动创建或) 。</span><span class="sxs-lookup"><span data-stu-id="4069f-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="4069f-118">有关在独立 EOP 环境中管理用户的详细信息，请参阅"在[EOP 中管理邮件用户"。](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="4069f-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="4069f-119">最终用户可以访问哪些隔离邮件？</span><span class="sxs-lookup"><span data-stu-id="4069f-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="4069f-120">从 2020 年 4 月起，用户在 (月起可以访问) 视为收件人的垃圾邮件、批量邮件和联系人联系人。</span><span class="sxs-lookup"><span data-stu-id="4069f-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="4069f-121">最终用户无法访问隔离的恶意软件、高可信度钓鱼或由于将邮件传递到邮件流规则 (也称为传输规则) 中托管隔离操作而被隔离的邮件。 **Deliver the message to the hosted quarantine**</span><span class="sxs-lookup"><span data-stu-id="4069f-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="4069f-122">有关访问隔离邮件的用户的详细信息，请参阅以用户 [身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="4069f-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="4069f-123">邮件会在隔离邮箱中保留多长时间？</span><span class="sxs-lookup"><span data-stu-id="4069f-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="4069f-124">您可以通过使用反垃圾邮件策略配置垃圾邮件、网络钓鱼和批量电子邮件在隔离邮箱中的保留时间。</span><span class="sxs-lookup"><span data-stu-id="4069f-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="4069f-125">默认值为 30 天，也是最大值。</span><span class="sxs-lookup"><span data-stu-id="4069f-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="4069f-126">有关详细信息，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4069f-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="4069f-127">对于被邮件流规则隔离的邮件， **操作 向托管隔离邮箱传递**邮件，邮件会在隔离区中保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="4069f-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="4069f-128">您无法配置此持续时间。</span><span class="sxs-lookup"><span data-stu-id="4069f-128">You can't configure this duration.</span></span>

<span data-ttu-id="4069f-129">此时间段到期后，将删除邮件且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="4069f-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="4069f-130">我可以一次释放或报告多个被隔离的邮件吗？</span><span class="sxs-lookup"><span data-stu-id="4069f-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="4069f-131">在安全与&中心内，一次最多可以选择并发布 100 个邮件。</span><span class="sxs-lookup"><span data-stu-id="4069f-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="4069f-132">管理员可以在 Exchange Online PowerShell 中使用 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 和 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets，从批量查找并释放隔离邮件并批量报告误报。</span><span class="sxs-lookup"><span data-stu-id="4069f-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="4069f-133">搜索隔离的邮件时是否支持通配符？</span><span class="sxs-lookup"><span data-stu-id="4069f-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="4069f-134">能否搜索特定域的隔离邮件？</span><span class="sxs-lookup"><span data-stu-id="4069f-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="4069f-135">安全与合规中心不支持通&通配符。</span><span class="sxs-lookup"><span data-stu-id="4069f-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="4069f-136">例如，搜索发件人时，需要指定完整的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4069f-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="4069f-137">但是，可以在 Exchange Online PowerShell 中使用通配符或独立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4069f-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="4069f-138">例如，运行以下命令，以查找来自域身份验证中所有发件人的垃圾邮件contoso.com：</span><span class="sxs-lookup"><span data-stu-id="4069f-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="4069f-139">然后，运行以下命令将这些邮件释放给所有原始收件人：</span><span class="sxs-lookup"><span data-stu-id="4069f-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="4069f-140">释放邮件后，则无法重新释放邮件。</span><span class="sxs-lookup"><span data-stu-id="4069f-140">After you release a message, you can't release it again.</span></span>
