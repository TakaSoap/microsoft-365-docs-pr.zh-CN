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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以查看有关 Exchange Online Protection 中的隔离邮件的常见问题和解答， (EOP) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 112f8a9f0714d962f8ea18ade5455178ba773858
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908838"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="f3e0f-103">隔离邮件常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f3e0f-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f3e0f-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="f3e0f-104">**Applies to**</span></span>
- [<span data-ttu-id="f3e0f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f3e0f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f3e0f-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="f3e0f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f3e0f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3e0f-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f3e0f-108">本主题提供有关在 Exchange Online 中拥有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的隔离电子邮件的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-108">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="f3e0f-109">有关反垃圾邮件保护的问题和解答，请参阅 [反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="f3e0f-110">有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="f3e0f-111">有关反欺骗保护的问题和解答，请参阅 [反欺骗保护常见问题解答](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="f3e0f-112">如何管理因恶意软件隔离的邮件？</span><span class="sxs-lookup"><span data-stu-id="f3e0f-112">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="f3e0f-113">只有管理员才能管理因恶意软件隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-113">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="f3e0f-114">有关详细信息，请参阅 [以管理员角色管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-114">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="f3e0f-115">如何隔离垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="f3e0f-115">How do I quarantine spam?</span></span>

<span data-ttu-id="f3e0f-116">默认情况下，被垃圾邮件筛选分类为垃圾邮件或批量电子邮件的邮件将传递到用户的邮箱，并移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-116">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="f3e0f-117">不过，您可以创建和配置反垃圾邮件策略，以隔离垃圾邮件或批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-117">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="f3e0f-118">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="f3e0f-119">如何授予用户对隔离的访问权限？</span><span class="sxs-lookup"><span data-stu-id="f3e0f-119">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="f3e0f-120">用户必须具有有效的帐户，以访问隔离中自己的邮件。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-120">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="f3e0f-121">独立 EOP 要求在 EOP 中将用户表示为邮件用户 (通过目录同步邮箱手动创建或) 。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-121">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="f3e0f-122">有关在独立 EOP 环境中管理用户的信息，请参阅 [在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-122">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="f3e0f-123">最终用户可以在隔离中访问哪些邮件？</span><span class="sxs-lookup"><span data-stu-id="f3e0f-123">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="f3e0f-124">自 2020 年 4 (，用户可以访问垃圾邮件、批量) 电子邮件和邮件。这些邮件是收件人。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-124">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="f3e0f-125">最终用户无法访问隔离的恶意软件、高可信度网络钓鱼或因邮件流规则中的"将邮件传递至托管隔离"操作而隔离 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-125">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="f3e0f-126">有关访问隔离邮件的用户详细信息，请参阅以用户模式查找并 [释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-126">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="f3e0f-127">邮件在隔离区中保留多久？</span><span class="sxs-lookup"><span data-stu-id="f3e0f-127">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="f3e0f-128">您可以使用反垃圾邮件策略配置垃圾邮件、网络钓鱼和批量电子邮件在隔离区中保留多久。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-128">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="f3e0f-129">默认值为 30 天，也是最大值。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-129">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="f3e0f-130">有关详细信息，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f3e0f-130">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="f3e0f-131">对于由邮件流规则操作 **"** 将邮件发送到托管隔离邮箱"隔离的邮件，这些邮件在隔离中保留 30 天。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-131">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="f3e0f-132">无法配置此持续时间。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-132">You can't configure this duration.</span></span>

<span data-ttu-id="f3e0f-133">时间段过期后，邮件将被删除且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-133">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="f3e0f-134">能否一次释放或报告多个隔离邮件？</span><span class="sxs-lookup"><span data-stu-id="f3e0f-134">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="f3e0f-135">在安全&合规中心，一次最多可以选择并释放 100 条消息。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-135">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="f3e0f-136">管理员可以使用 Exchange Online PowerShell 或独立 EOP PowerShell 中的 [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) 和 [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) cmdlet 批量查找并释放隔离邮件，并批量报告误报。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-136">Admins can use the the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="f3e0f-137">搜索隔离邮件时是否支持通配符？</span><span class="sxs-lookup"><span data-stu-id="f3e0f-137">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="f3e0f-138">能否搜索特定域的隔离邮件？</span><span class="sxs-lookup"><span data-stu-id="f3e0f-138">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="f3e0f-139">安全与合规中心不支持&通配符。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-139">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="f3e0f-140">例如，在搜索发件人时，需要指定完整的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-140">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="f3e0f-141">但是，您可以在 Exchange Online PowerShell 或独立 EOP PowerShell 中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-141">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="f3e0f-142">例如，将以下 PowerShell 代码复制到记事本，将文件另存为 .ps1，位置便于您查找 (例如，C:\Data\QuarantineRelease.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-142">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="f3e0f-143">然后，在连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 或 [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)后，运行以下命令以运行脚本：</span><span class="sxs-lookup"><span data-stu-id="f3e0f-143">Then, after you connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="f3e0f-144">该脚本执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f3e0f-144">The script does the following actions:</span></span>

- <span data-ttu-id="f3e0f-145">查找从 fabrikam 域中所有发件人隔离为垃圾邮件的未发布邮件。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-145">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="f3e0f-146">最大结果数为 50，000， (50 页（包含 1000 个结果) ）。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-146">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="f3e0f-147">将结果保存到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-147">Save the results to a CSV file.</span></span>
- <span data-ttu-id="f3e0f-148">将匹配的隔离邮件释放给所有原始收件人。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-148">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="f3e0f-149">释放邮件后，无法再次释放它。</span><span class="sxs-lookup"><span data-stu-id="f3e0f-149">After you release a message, you can't release it again.</span></span>