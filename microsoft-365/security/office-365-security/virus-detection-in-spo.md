---
title: SharePoint Online、OneDrive 和 Microsoft 团队中的内置病毒防护
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 了解 SharePoint Online 如何检测用户上载的文件中的病毒并阻止用户下载或同步文件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327983"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="07a2a-103">SharePoint Online、OneDrive 和 Microsoft 团队中的内置病毒防护</span><span class="sxs-lookup"><span data-stu-id="07a2a-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="07a2a-104">Microsoft 365 使用通用的病毒检测引擎来扫描用户上载到 SharePoint Online、OneDrive 和 Microsoft 团队的文件。</span><span class="sxs-lookup"><span data-stu-id="07a2a-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="07a2a-105">此保护包括在所有订阅中，包括 SharePoint Online、OneDrive 和 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="07a2a-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07a2a-106">内置防病毒功能是一种帮助包含病毒的方法。</span><span class="sxs-lookup"><span data-stu-id="07a2a-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="07a2a-107">它们不是为了抵御针对您的环境的恶意软件的单一防御点。</span><span class="sxs-lookup"><span data-stu-id="07a2a-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="07a2a-108">我们鼓励所有客户在不同的层调查和实施反恶意软件保护，并应用最佳做法来保护其企业基础结构。</span><span class="sxs-lookup"><span data-stu-id="07a2a-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="07a2a-109">有关策略和最佳实践的详细信息，请参阅 [安全路线图](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="07a2a-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="07a2a-110">将受感染的文件上载到 SharePoint Online 时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="07a2a-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="07a2a-111">Microsoft 365 病毒检测引擎在 SharePoint Online 中异步运行。</span><span class="sxs-lookup"><span data-stu-id="07a2a-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="07a2a-112">**上载时不会自动扫描所有文件**。</span><span class="sxs-lookup"><span data-stu-id="07a2a-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="07a2a-113">启发式确定要扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="07a2a-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="07a2a-114">找到文件以包含病毒时，文件会被标记为无法再次下载。</span><span class="sxs-lookup"><span data-stu-id="07a2a-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="07a2a-115">在4月2018，我们删除了扫描文件的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="07a2a-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="07a2a-116">以下是所发生的情况：</span><span class="sxs-lookup"><span data-stu-id="07a2a-116">Here's what happens:</span></span>

1. <span data-ttu-id="07a2a-117">用户将文件上传到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="07a2a-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="07a2a-118">SharePoint Online 决定文件是否符合扫描的条件。</span><span class="sxs-lookup"><span data-stu-id="07a2a-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="07a2a-119">病毒检测引擎将扫描文件。</span><span class="sxs-lookup"><span data-stu-id="07a2a-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="07a2a-120">如果发现了病毒，病毒引擎将对文件设置一个属性，表明它已被感染。</span><span class="sxs-lookup"><span data-stu-id="07a2a-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="07a2a-121">当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="07a2a-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="07a2a-122">如果文件受到感染，用户不能使用浏览器从 SharePoint Online 下载文件。</span><span class="sxs-lookup"><span data-stu-id="07a2a-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="07a2a-123">以下是所发生的情况：</span><span class="sxs-lookup"><span data-stu-id="07a2a-123">Here's what happens:</span></span>

1. <span data-ttu-id="07a2a-124">用户打开 web 浏览器并尝试从 SharePoint Online 下载感染病毒的文件。</span><span class="sxs-lookup"><span data-stu-id="07a2a-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="07a2a-125">向用户提供一条警告，指示已检测到病毒。</span><span class="sxs-lookup"><span data-stu-id="07a2a-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="07a2a-126">默认情况下，会向用户提供下载文件的选项，并尝试使用防病毒软件在自己的设备上进行清理。</span><span class="sxs-lookup"><span data-stu-id="07a2a-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="07a2a-127">管理员可以在 SharePoint Online PowerShell 中使用[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet 上的*DisallowInfectedFileDownload*参数，以防止用户下载感染病毒的文件，即使在 "反病毒警告" 窗口中也是如此。</span><span class="sxs-lookup"><span data-stu-id="07a2a-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="07a2a-128">有关说明，请参阅 [使用 SharePoint Online PowerShell 防止用户下载恶意文件](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="07a2a-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="07a2a-129">一旦启用 *DisallowInfectedFileDownload* 参数，就会为用户和管理员完全阻止对已检测/被阻止文件的访问。</span><span class="sxs-lookup"><span data-stu-id="07a2a-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="07a2a-130">OneDrive 同步客户端尝试同步受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="07a2a-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="07a2a-131">OneDrive 同步客户端不会下载包含病毒的文件。</span><span class="sxs-lookup"><span data-stu-id="07a2a-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="07a2a-132">同步客户端将显示一条通知，指出文件无法同步。</span><span class="sxs-lookup"><span data-stu-id="07a2a-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a><span data-ttu-id="07a2a-133">具有 Office 365 高级威胁防护的扩展功能</span><span class="sxs-lookup"><span data-stu-id="07a2a-133">Extended capabilities with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="07a2a-134">包含 [Office 365 高级威胁防护 (ATP) ](office-365-atp.md) 包含在订阅中或作为加载项购买的 microsoft 365 组织可以为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP，以增强报告和保护功能。</span><span class="sxs-lookup"><span data-stu-id="07a2a-134">Microsoft 365 organizations that have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="07a2a-135">有关详细信息，请参阅 [适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="07a2a-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="07a2a-136">详细信息</span><span class="sxs-lookup"><span data-stu-id="07a2a-136">More information</span></span>

<span data-ttu-id="07a2a-137">有关 SharePoint Online、OneDrive 和 Microsoft 团队中的防病毒的详细信息，请参阅 [防止威胁](protect-against-threats.md) 并 [打开 SharePoint、OneDrive 和 MICROSOFT 团队的 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="07a2a-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
