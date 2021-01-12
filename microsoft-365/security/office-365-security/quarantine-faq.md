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
- m365initiative-defender-office365
description: 管理员可以查看有关 Exchange Online Protection 和 EOP (隔离邮件的常见问题和) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddb5847706aef3d2c3b8ea8cd9a96fd65a9b3d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794408"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="82b37-103">隔离邮件常见问题解答</span><span class="sxs-lookup"><span data-stu-id="82b37-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="82b37-104">本主题提供有关在 Exchange Online 中具有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的隔离电子邮件的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="82b37-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="82b37-105">有关反垃圾邮件保护的问题和解答，请参阅 [反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="82b37-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="82b37-106">有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="82b37-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="82b37-107">有关反欺骗保护的问题和解答，请参阅 [反欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="82b37-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="82b37-108">如何管理因恶意软件隔离的邮件？</span><span class="sxs-lookup"><span data-stu-id="82b37-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="82b37-109">只有管理员才能管理因恶意软件隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="82b37-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="82b37-110">有关详细信息，请参阅以管理员角色 [管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="82b37-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="82b37-111">如何隔离垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="82b37-111">How do I quarantine spam?</span></span>

<span data-ttu-id="82b37-112">默认情况下，通过垃圾邮件筛选被分类为垃圾邮件或批量电子邮件的邮件将传递到用户的邮箱，并移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="82b37-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="82b37-113">但是，您可以创建和配置反垃圾邮件策略来隔离垃圾邮件或批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="82b37-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="82b37-114">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="82b37-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="82b37-115">如何授予用户对隔离的访问权限？</span><span class="sxs-lookup"><span data-stu-id="82b37-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="82b37-116">用户必须具有有效的帐户，以访问自己的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="82b37-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="82b37-117">独立 EOP 要求在 EOP 中将用户表示为邮件用户 (通过目录同步邮箱手动创建或) 。</span><span class="sxs-lookup"><span data-stu-id="82b37-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="82b37-118">有关在独立 EOP 环境中管理用户的信息，请参阅["在 EOP 中管理邮件用户"。](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="82b37-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="82b37-119">最终用户可以在隔离中访问哪些邮件？</span><span class="sxs-lookup"><span data-stu-id="82b37-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="82b37-120">自 2020 年 4 (，用户可以访问垃圾邮件、批量) 电子邮件和邮件，包括收件人的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="82b37-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="82b37-121">最终用户无法访问隔离的恶意软件、高可信度网络钓鱼或因邮件流规则（也称为传输规则 (传输规则）中的托管隔离操作而隔离) 。</span><span class="sxs-lookup"><span data-stu-id="82b37-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="82b37-122">有关用户访问隔离邮件详细信息，请参阅"查找隔离邮件并作为用户[释放"。](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="82b37-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="82b37-123">邮件在隔离区中保留多久？</span><span class="sxs-lookup"><span data-stu-id="82b37-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="82b37-124">您可以使用反垃圾邮件策略配置垃圾邮件、网络钓鱼和批量电子邮件在隔离区中的保留时间。</span><span class="sxs-lookup"><span data-stu-id="82b37-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="82b37-125">默认值为 30 天，也是最大值。</span><span class="sxs-lookup"><span data-stu-id="82b37-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="82b37-126">有关详细信息，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="82b37-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="82b37-127">对于由邮件流规则操作 **"** 将邮件发送到托管隔离邮箱"隔离的邮件，这些邮件在隔离中保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="82b37-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="82b37-128">无法配置此持续时间。</span><span class="sxs-lookup"><span data-stu-id="82b37-128">You can't configure this duration.</span></span>

<span data-ttu-id="82b37-129">在时间段过期后，邮件将被删除且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="82b37-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="82b37-130">我能否一次释放或报告多个隔离邮件？</span><span class="sxs-lookup"><span data-stu-id="82b37-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="82b37-131">在安全&合规中心，一次可以选择并释放最多 100 条消息。</span><span class="sxs-lookup"><span data-stu-id="82b37-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="82b37-132">管理员可以使用 Exchange Online PowerShell 或独立 EOP PowerShell 中的 [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) 和 [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlet 批量查找并释放隔离邮件，并批量报告误报。</span><span class="sxs-lookup"><span data-stu-id="82b37-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="82b37-133">搜索隔离邮件时是否支持通配符？</span><span class="sxs-lookup"><span data-stu-id="82b37-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="82b37-134">我能否搜索特定域的隔离邮件？</span><span class="sxs-lookup"><span data-stu-id="82b37-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="82b37-135">安全与合规中心不支持通配符&通配符。</span><span class="sxs-lookup"><span data-stu-id="82b37-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="82b37-136">例如，在搜索发件人时，需要指定完整电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="82b37-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="82b37-137">但是，您可以在 Exchange Online PowerShell 或独立 EOP PowerShell 中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="82b37-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="82b37-138">例如，运行以下命令以查找来自域中所有发件人的垃圾邮件隔离contoso.com：</span><span class="sxs-lookup"><span data-stu-id="82b37-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="82b37-139">然后，运行以下命令以将这些邮件释放给所有原始收件人：</span><span class="sxs-lookup"><span data-stu-id="82b37-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="82b37-140">释放邮件后，你无法再次释放它。</span><span class="sxs-lookup"><span data-stu-id="82b37-140">After you release a message, you can't release it again.</span></span>
