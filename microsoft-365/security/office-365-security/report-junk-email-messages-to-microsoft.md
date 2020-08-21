---
title: 向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理员可以了解向 Microsoft 报告良好和不良消息与文件进行分析的不同方法。
ms.openlocfilehash: fabe28d084361041ae9e6a8d118dd8c43c2225f7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827637"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="f74c5-103">向 Microsoft 报告邮件和文件</span><span class="sxs-lookup"><span data-stu-id="f74c5-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="f74c5-104">在没有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，用户和管理员都有多种不同的方法向 Microsoft 报告电子邮件和文件。</span><span class="sxs-lookup"><span data-stu-id="f74c5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

****

|<span data-ttu-id="f74c5-105">方法</span><span class="sxs-lookup"><span data-stu-id="f74c5-105">Method</span></span>|<span data-ttu-id="f74c5-106">说明</span><span class="sxs-lookup"><span data-stu-id="f74c5-106">Description</span></span>|
|---|---|
|[<span data-ttu-id="f74c5-107">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="f74c5-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="f74c5-108">对于具有 Exchange Online 邮箱的组织中管理员，建议 (在独立 EOP 邮箱中不可用) 。</span><span class="sxs-lookup"><span data-stu-id="f74c5-108">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="f74c5-109">启用报告消息加载项</span><span class="sxs-lookup"><span data-stu-id="f74c5-109">Enable the Report Message add-in</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="f74c5-110">适用于 Outlook、Outlook for Mac 和 Outlook 网页版 (（以前称为 Outlook Web App) 版本 Outlook Web App) ，这是推荐的外接程序。</span><span class="sxs-lookup"><span data-stu-id="f74c5-110">Works with Outlook, Outlook for Mac, and Outlook on the web (formerly known as Outlook Web App), and is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="f74c5-111">根据您的订阅，用户报告的外接程序邮件位于[Admin Submissions 门户](admin-submission.md)、自动调查和[响应 (AIR) 结果、](air-view-investigation-results.md)[用户报告的消息报告](view-email-security-reports.md#user-reported-messages-report)和[威胁资源管理器中](threat-explorer-views.md#email--submissions)。</span><span class="sxs-lookup"><span data-stu-id="f74c5-111">Depending on your subscription, messages that users reported with the add-in are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span> <br/><br/> <span data-ttu-id="f74c5-112">您可以将报告的邮件配置为复制或重定向到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f74c5-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f74c5-113">有关详细信息，请参阅 [在 EOP 中指定提交用户收集垃圾邮件和网络钓鱼邮件的邮箱](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f74c5-113">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in EOP](user-submission.md).</span></span>|
|[<span data-ttu-id="f74c5-114">安装和使用 Microsoft Outlook 的垃圾邮件报告加载项</span><span class="sxs-lookup"><span data-stu-id="f74c5-114">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="f74c5-115">仅适用于 Outlook。</span><span class="sxs-lookup"><span data-stu-id="f74c5-115">Only works in Outlook.</span></span>|
|[<span data-ttu-id="f74c5-116">在 Outlook 网页版中报告垃圾和钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="f74c5-116">Report junk and phishing email in Outlook on the web</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="f74c5-117">对具有 Exchange Online 邮箱的组织使用 Outlook 网页版中的内置 (在独立 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="f74c5-117">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span> <br/><br/> <span data-ttu-id="f74c5-118">用户可在管理提交门户 [中显示用户报告的邮件](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f74c5-118">Messages that users report are available in [the Admin Submissions portal](admin-submission.md).</span></span> <br/><br/> <span data-ttu-id="f74c5-119">您可以将报告的邮件配置为复制或重定向到您指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f74c5-119">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f74c5-120">有关详细信息，请参阅 [指定一个邮箱以提交 Exchange Online 中垃圾邮件和网络钓鱼邮件](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f74c5-120">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange online](user-submission.md).</span></span>|
|[<span data-ttu-id="f74c5-121">手动将邮件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="f74c5-121">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="f74c5-122">将附加的邮件手动发送到特定的 Microsoft 垃圾邮件地址，而不是垃圾邮件和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="f74c5-122">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="f74c5-123">使用邮件流规则来查看用户向 Microsoft 报告的内容</span><span class="sxs-lookup"><span data-stu-id="f74c5-123">Use mail flow rules to see what your users are reporting to Microsoft</span></span>](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|<span data-ttu-id="f74c5-124">了解如何创建邮件流规则 (也称为传输规则，) 传输规则类型在用户向 Microsoft 报告邮件进行分析时会通知你。</span><span class="sxs-lookup"><span data-stu-id="f74c5-124">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>
|||
|[<span data-ttu-id="f74c5-125">将恶意软件和非恶意软件提交给 Microsoft 分析</span><span class="sxs-lookup"><span data-stu-id="f74c5-125">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="f74c5-126">使用 Microsoft 安全智能网站提交附件和其他文件。</span><span class="sxs-lookup"><span data-stu-id="f74c5-126">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="f74c5-127">如果垃圾邮件或网络钓鱼邮件被隔离而不是传递，则用户可以从安全 & 合规中心的"隔离"门户将邮件报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="f74c5-127">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f74c5-128">有关详细信息，请参阅 [在 Microsoft 365 中以用户身份查找和释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="f74c5-128">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>
