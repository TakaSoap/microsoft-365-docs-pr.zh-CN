---
title: SharePoint Online、OneDrive 和 Microsoft Teams 中的内置病毒防护
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 了解 SharePoint Online 如何在用户上载的文件中检测到病毒，以及如何阻止用户下载或同步文件。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055118"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="216dd-103">SharePoint Online、OneDrive 和 Microsoft Teams 中的内置病毒防护</span><span class="sxs-lookup"><span data-stu-id="216dd-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="216dd-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="216dd-104">**Applies to**</span></span>
- [<span data-ttu-id="216dd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="216dd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="216dd-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="216dd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="216dd-107">Microsoft 365 使用常见的病毒检测引擎扫描用户上传到 SharePoint Online、OneDrive 和 Microsoft Teams 的文件。</span><span class="sxs-lookup"><span data-stu-id="216dd-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="216dd-108">此保护包含在包括 SharePoint Online、OneDrive 和 Microsoft Teams 的所有订阅中。</span><span class="sxs-lookup"><span data-stu-id="216dd-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="216dd-109">内置防病毒功能是一种帮助包含病毒的方法。</span><span class="sxs-lookup"><span data-stu-id="216dd-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="216dd-110">它们不能作为针对你的环境抵御恶意软件的单一防御点。</span><span class="sxs-lookup"><span data-stu-id="216dd-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="216dd-111">我们鼓励所有客户在各种层调查和实施反恶意软件保护，并应用最佳实践来保护其企业基础结构。</span><span class="sxs-lookup"><span data-stu-id="216dd-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="216dd-112">有关策略和最佳做法详细信息，请参阅安全 [路线图](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="216dd-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="216dd-113">如果将受感染的文件上传到 SharePoint Online 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="216dd-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="216dd-114">Microsoft 365 病毒检测引擎以异步方式运行， (与 SharePoint Online 中的文件) 无关。</span><span class="sxs-lookup"><span data-stu-id="216dd-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="216dd-115">**不会自动扫描所有文件**。</span><span class="sxs-lookup"><span data-stu-id="216dd-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="216dd-116">启发式方法确定要扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="216dd-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="216dd-117">当发现文件包含病毒时，将标记该文件。</span><span class="sxs-lookup"><span data-stu-id="216dd-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="216dd-118">2018 年 4 月，我们删除了扫描文件 25 MB 的限制。</span><span class="sxs-lookup"><span data-stu-id="216dd-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="216dd-119">下面是发生的情况：</span><span class="sxs-lookup"><span data-stu-id="216dd-119">Here's what happens:</span></span>

1. <span data-ttu-id="216dd-120">用户将文件上载到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="216dd-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="216dd-121">SharePoint Online 是病毒扫描过程的一部分，稍后将确定文件是否满足扫描条件。</span><span class="sxs-lookup"><span data-stu-id="216dd-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="216dd-122">如果文件满足扫描条件，病毒检测引擎将扫描该文件。</span><span class="sxs-lookup"><span data-stu-id="216dd-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="216dd-123">如果在扫描的文件中发现了病毒，则病毒引擎在文件上设置一个属性，指示它受到感染。</span><span class="sxs-lookup"><span data-stu-id="216dd-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="216dd-124">当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="216dd-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="216dd-125">如果文件受到感染，则用户无法通过使用浏览器从 SharePoint Online 下载文件。</span><span class="sxs-lookup"><span data-stu-id="216dd-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="216dd-126">下面是发生的情况：</span><span class="sxs-lookup"><span data-stu-id="216dd-126">Here's what happens:</span></span>

1. <span data-ttu-id="216dd-127">用户打开 Web 浏览器并尝试从 SharePoint Online 下载受感染的文件。</span><span class="sxs-lookup"><span data-stu-id="216dd-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="216dd-128">用户得到一条警告，指出已检测到病毒。</span><span class="sxs-lookup"><span data-stu-id="216dd-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="216dd-129">默认情况下，用户可以选择下载文件，并尝试在其自己的设备上使用防病毒软件进行清理。</span><span class="sxs-lookup"><span data-stu-id="216dd-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="216dd-130">管理员可以在 SharePoint Online PowerShell 中 [对 Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet 使用 *DisallowInfectedFileDownload* 参数，以防止用户下载受感染的文件，即使在防病毒警告窗口中也可以。</span><span class="sxs-lookup"><span data-stu-id="216dd-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="216dd-131">有关说明，请参阅 [使用 SharePoint Online PowerShell 阻止用户下载恶意文件](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="216dd-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="216dd-132">一旦启用 *DisallowInfectedFileDownload* 参数，用户和管理员将完全阻止访问检测到/阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="216dd-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="216dd-133">OneDrive 同步客户端尝试同步受感染的文件时会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="216dd-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="216dd-134">OneDrive 同步客户端不会下载包含病毒的文件。</span><span class="sxs-lookup"><span data-stu-id="216dd-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="216dd-135">同步客户端将显示文件无法同步的通知。</span><span class="sxs-lookup"><span data-stu-id="216dd-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="216dd-136">Microsoft Defender for Office 365 的扩展功能</span><span class="sxs-lookup"><span data-stu-id="216dd-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="216dd-137">订阅中包含 Microsoft Defender for Office 365 或作为加载项购买 Microsoft [365 的 Microsoft 365](defender-for-office-365.md) 组织可以启用 SharePoint、OneDrive 和 Microsoft Teams 的安全附件，以增强报告和保护。</span><span class="sxs-lookup"><span data-stu-id="216dd-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="216dd-138">有关详细信息，请参阅 [SharePoint、OneDrive](mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件。</span><span class="sxs-lookup"><span data-stu-id="216dd-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="216dd-139">相关文章</span><span class="sxs-lookup"><span data-stu-id="216dd-139">Related Articles</span></span>

[<span data-ttu-id="216dd-140">Microsoft 365 中的恶意软件和勒索软件保护</span><span class="sxs-lookup"><span data-stu-id="216dd-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="216dd-141">有关 SharePoint Online、OneDrive 和 Microsoft Teams 中的防病毒功能详细信息[](protect-against-threats.md)，请参阅防止威胁和启用[SharePoint、OneDrive](turn-on-mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件。</span><span class="sxs-lookup"><span data-stu-id="216dd-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
