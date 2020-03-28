---
title: 将垃圾邮件、非垃圾邮件和网络钓鱼邮件报告给 Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Microsoft Office Outlook 的 Microsoft 垃圾邮件报告加载项可以提供多种报告垃圾邮件的方式：
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033658"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="46d74-103">将邮件和文件报告给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="46d74-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="46d74-104">Office 365 中的用户和管理员使用 Exchange Online 中的邮箱的组织，或独立 Exchange Online Protection （EOP）组织（没有 Exchange Online 邮箱）来提交电子邮件。有几种不同的方法可用于报告邮件和文件到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="46d74-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes to submit email messages have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="46d74-105">**方法**</span><span class="sxs-lookup"><span data-stu-id="46d74-105">**Method**</span></span>|<span data-ttu-id="46d74-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="46d74-106">**Description**</span></span>|
|[<span data-ttu-id="46d74-107">使用管理员提交将可疑的垃圾邮件、网络钓鱼诈骗、Url 和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="46d74-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="46d74-108">对于具有 Exchange Online 邮箱的组织中的管理员，建议使用此报告方法（在独立 EOP 中不可用）。</span><span class="sxs-lookup"><span data-stu-id="46d74-108">This is the recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="46d74-109">在 Office 365 中启用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="46d74-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="46d74-110">适用于 Outlook、Outlook for Mac 和 web 上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="46d74-110">Works with Outlook, Outlook for Mac, and Outlook on the web.</span></span> <span data-ttu-id="46d74-111">这是推荐的加载项。</span><span class="sxs-lookup"><span data-stu-id="46d74-111">This is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="46d74-112">根据你的许可证，报告的邮件在[自动调查和响应（空中）结果](air-view-investigation-results.md)（[用户报告的邮件报告](view-email-security-reports.md#user-reported-messages-report)和[威胁浏览器](threat-explorer-views.md#email--submissions)）中可用。</span><span class="sxs-lookup"><span data-stu-id="46d74-112">Depending on your license, the reported messages are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report) and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="46d74-113">在 Office 365 中安装和使用 Microsoft Outlook 的垃圾邮件报告外接程序</span><span class="sxs-lookup"><span data-stu-id="46d74-113">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="46d74-114">仅在 Outlook 中有效。</span><span class="sxs-lookup"><span data-stu-id="46d74-114">Only works in Outlook.</span></span>|
|[<span data-ttu-id="46d74-115">在 Office 365 中的 Outlook 网页上报告垃圾邮件和网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="46d74-115">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="46d74-116">对于具有 Exchange Online 邮箱的组织，请在 web 上的 Outlook 中使用内置功能（在独立 EOP 中不可用）。</span><span class="sxs-lookup"><span data-stu-id="46d74-116">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="46d74-117">将恶意软件和非恶意软件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="46d74-117">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="46d74-118">使用 Microsoft 安全智能网站提交附件和其他文件。</span><span class="sxs-lookup"><span data-stu-id="46d74-118">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="46d74-119">如果已隔离垃圾邮件或网络钓鱼邮件，而不是进行传递，则用户可以从 Office 365 Security & 合规性中心中的隔离门户向 Microsoft 报告邮件。</span><span class="sxs-lookup"><span data-stu-id="46d74-119">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="46d74-120">有关详细信息，请参阅[在 Office 365 中查找并以用户的方式释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="46d74-120">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>