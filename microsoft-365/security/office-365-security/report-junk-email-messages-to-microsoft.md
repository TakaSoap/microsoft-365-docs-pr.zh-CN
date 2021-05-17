---
title: 向 Microsoft 报告垃圾邮件、非垃圾邮件和网络钓鱼邮件
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理员可以了解向 Microsoft 报告好坏消息和文件以进行分析的不同方法。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c87938a8716da36f027300d685f0caedcf69660
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291123"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="73f80-103">向 Microsoft 报告邮件和文件</span><span class="sxs-lookup"><span data-stu-id="73f80-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="73f80-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="73f80-104">**Applies to**</span></span>
- [<span data-ttu-id="73f80-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="73f80-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="73f80-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="73f80-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="73f80-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73f80-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="73f80-108">在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，用户和管理员都有几种不同的方法向 Microsoft 报告电子邮件和文件。</span><span class="sxs-lookup"><span data-stu-id="73f80-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

****

|<span data-ttu-id="73f80-109">方法</span><span class="sxs-lookup"><span data-stu-id="73f80-109">Method</span></span>|<span data-ttu-id="73f80-110">说明</span><span class="sxs-lookup"><span data-stu-id="73f80-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="73f80-111">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="73f80-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="73f80-112">对于拥有邮箱的组织中管理员Exchange Online报告 (在独立 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="73f80-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="73f80-113">启用报告邮件或报告钓鱼外接程序</span><span class="sxs-lookup"><span data-stu-id="73f80-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="73f80-114">适用于Outlook web Outlook上 (以前称为"Outlook Web App) "的 Outlook Web App) 。</span><span class="sxs-lookup"><span data-stu-id="73f80-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="73f80-115">根据你的订阅，用户通过外接程序报告的邮件可在管理员提交门户、自动调查和响应[](admin-submission.md) (AIR) [结果](air-view-investigation-results.md)、用户报告的邮件报告以及威胁资源管理器中[提供。](threat-explorer-views.md#email--submissions) [](view-email-security-reports.md#user-reported-messages-report)</span><span class="sxs-lookup"><span data-stu-id="73f80-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="73f80-116">可以将报告的邮件配置为复制或重定向到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="73f80-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="73f80-117">有关详细信息，请参阅用户 [提交策略](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="73f80-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="73f80-118">向报告误报和漏报Outlook</span><span class="sxs-lookup"><span data-stu-id="73f80-118">Report false positives and false negatives to Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="73f80-119">提交误报 (阻止或发送到垃圾邮件文件夹) 的误报 (以及使用"报告邮件"功能传递到收件箱) Exchange Online Protection (EOP) 的误报或钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="73f80-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="73f80-120">手动将邮件提交到 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="73f80-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="73f80-121">将附加邮件手动发送到特定 Microsoft 电子邮件地址，以发送垃圾邮件，而不是垃圾邮件和网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="73f80-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="73f80-122">使用邮件流规则来查看用户向 Microsoft 报告的内容</span><span class="sxs-lookup"><span data-stu-id="73f80-122">Use mail flow rules to see what your users are reporting to Microsoft</span></span>](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|<span data-ttu-id="73f80-123">了解如何创建邮件流规则 (也称为传输规则) 在用户向 Microsoft 报告邮件进行分析时通知您。</span><span class="sxs-lookup"><span data-stu-id="73f80-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="73f80-124">将恶意软件和非恶意软件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="73f80-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="73f80-125">使用 Microsoft 安全智能 网站提交附件和其他文件。</span><span class="sxs-lookup"><span data-stu-id="73f80-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|

<span data-ttu-id="73f80-126">如果垃圾邮件或网络钓鱼邮件被隔离而不是传递，则用户可以从安全与合规中心中的隔离门户& Microsoft。</span><span class="sxs-lookup"><span data-stu-id="73f80-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Security & Compliance Center.</span></span> <span data-ttu-id="73f80-127">有关详细信息，请参阅[Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="73f80-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="73f80-128">提交到 Microsoft 的数据位于北美数据中心Office 365合规性边界。</span><span class="sxs-lookup"><span data-stu-id="73f80-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="73f80-129">数据由工程团队的分析师审阅，以帮助提高筛选器的有效性。</span><span class="sxs-lookup"><span data-stu-id="73f80-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
