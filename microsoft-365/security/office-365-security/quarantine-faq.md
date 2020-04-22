---
title: 隔离常见问题解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: 有关 Office 365 中的隔离的常见问题的解答。
ms.openlocfilehash: 3947fbed2a17380a18320a8bffd08a8178ad2b3f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634420"
---
# <a name="quarantine-faq"></a><span data-ttu-id="c4de1-103">隔离常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c4de1-103">Quarantine FAQ</span></span>

<span data-ttu-id="c4de1-104">本主题提供了 Microsoft 365 客户与 Exchange Online 或独立 Exchange Online Protection （EOP）客户（无 Exchange Online 邮箱）中的邮箱隔离的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="c4de1-104">This topic provides frequently asked questions and answers about quarantine for Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="c4de1-105">问：如何管理已隔离的恶意邮件？</span><span class="sxs-lookup"><span data-stu-id="c4de1-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="c4de1-106">只有管理员可以管理隔离的恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="c4de1-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="c4de1-107">有关详细信息，请参阅[在 Office 365 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="c4de1-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="c4de1-108">问：如何隔离垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="c4de1-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="c4de1-109">A.</span><span class="sxs-lookup"><span data-stu-id="c4de1-109">A.</span></span> <span data-ttu-id="c4de1-110">默认情况下，通过垃圾邮件筛选功能分类为垃圾邮件或批量电子邮件的邮件将被传递到用户的邮箱，并移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4de1-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="c4de1-111">但您可以创建并配置反垃圾邮件策略以隔离垃圾邮件或批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c4de1-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="c4de1-112">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c4de1-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="c4de1-113">问：如何向用户授予对隔离的访问权限？</span><span class="sxs-lookup"><span data-stu-id="c4de1-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="c4de1-114">A.</span><span class="sxs-lookup"><span data-stu-id="c4de1-114">A.</span></span> <span data-ttu-id="c4de1-115">用户必须具有有效的帐户才能访问其自己的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="c4de1-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="c4de1-116">独立 EOP 要求用户在 EOP 中表示为邮件用户（手动创建或通过目录同步创建）。</span><span class="sxs-lookup"><span data-stu-id="c4de1-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="c4de1-117">有关在独立 EOP 环境中管理用户的详细信息，请参阅[Manage mail users IN EOP](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="c4de1-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="c4de1-118">问：最终用户可以访问隔离区中的哪些邮件？</span><span class="sxs-lookup"><span data-stu-id="c4de1-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="c4de1-119">A.</span><span class="sxs-lookup"><span data-stu-id="c4de1-119">A.</span></span> <span data-ttu-id="c4de1-120">用户可以访问垃圾邮件、批量电子邮件，以及在他们是收件人的网络钓鱼邮件（如4月，2020）。</span><span class="sxs-lookup"><span data-stu-id="c4de1-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="c4de1-121">最终用户无法访问隔离的恶意软件、高可信度的网络钓鱼或因将邮件传递到邮件流规则中**的托管隔离**操作（也称为传输规则）而被隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="c4de1-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c4de1-122">有关访问隔离邮件的用户的详细信息，请参阅[在 Office 365 中查找并以用户的形式发布隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c4de1-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="c4de1-123">问：邮件在隔离中保存了多长时间？</span><span class="sxs-lookup"><span data-stu-id="c4de1-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="c4de1-124">A.</span><span class="sxs-lookup"><span data-stu-id="c4de1-124">A.</span></span> <span data-ttu-id="c4de1-125">您可以使用反垃圾邮件策略配置在隔离中保存垃圾邮件、网络钓鱼和批量电子邮件的时间长度。</span><span class="sxs-lookup"><span data-stu-id="c4de1-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="c4de1-126">默认值为30天，也是最大值。</span><span class="sxs-lookup"><span data-stu-id="c4de1-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="c4de1-127">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c4de1-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="c4de1-128">对于由邮件流规则操作隔离的邮件，会将**邮件传递到托管隔离**，并将邮件保留30天。</span><span class="sxs-lookup"><span data-stu-id="c4de1-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="c4de1-129">您不能配置此持续时间。</span><span class="sxs-lookup"><span data-stu-id="c4de1-129">You can't configure this duration.</span></span>

<span data-ttu-id="c4de1-130">时段到期后，邮件将被删除且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="c4de1-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="c4de1-131">问：我是否可以一次释放或报告多个隔离邮件？</span><span class="sxs-lookup"><span data-stu-id="c4de1-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="c4de1-132">A.</span><span class="sxs-lookup"><span data-stu-id="c4de1-132">A.</span></span> <span data-ttu-id="c4de1-133">在安全 & 合规性中心中，可以一次选择并发布最高100个邮件。</span><span class="sxs-lookup"><span data-stu-id="c4de1-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="c4de1-134">管理员可以使用 Exchange Online PowerShell 或独立 Exchange Online Protection PowerShell 中的[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)和[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet 来批量查找和释放隔离的邮件，并批量报告误报。</span><span class="sxs-lookup"><span data-stu-id="c4de1-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="c4de1-135">问：搜索隔离邮件时是否支持通配符？</span><span class="sxs-lookup"><span data-stu-id="c4de1-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="c4de1-136">是否可以搜索特定域的隔离邮件？</span><span class="sxs-lookup"><span data-stu-id="c4de1-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="c4de1-137">A.</span><span class="sxs-lookup"><span data-stu-id="c4de1-137">A.</span></span> <span data-ttu-id="c4de1-138">安全性 & 合规性中心不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="c4de1-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="c4de1-139">例如，在搜索发件人时，您需要指定完整的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c4de1-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="c4de1-140">不过，您可以在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c4de1-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="c4de1-141">例如，运行以下命令以查找来自域 contoso.com 中的所有发件人的垃圾邮件隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="c4de1-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="c4de1-142">然后，运行以下命令，将这些邮件释放到所有原始收件人：</span><span class="sxs-lookup"><span data-stu-id="c4de1-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="c4de1-143">释放邮件后，您将无法再次将其释放。</span><span class="sxs-lookup"><span data-stu-id="c4de1-143">After you release a message, you can't release it again.</span></span>
