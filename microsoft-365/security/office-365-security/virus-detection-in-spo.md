---
title: SharePoint Online 中的病毒检测
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
ms.openlocfilehash: f6bfc23ca4120122ecfa44ad4d39795fed22af84
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429916"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="fae9b-103">SharePoint Online、OneDrive 和 Microsoft 团队中的病毒检测</span><span class="sxs-lookup"><span data-stu-id="fae9b-103">Virus detection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="fae9b-104">Microsoft 365 通过检测用户上传到 SharePoint Online、OneDrive 和 Microsoft 团队的文件中的病毒，帮助保护您的环境免受恶意软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="fae9b-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="fae9b-105">上载文件后，可能会对其进行病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="fae9b-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="fae9b-106">如果发现文件感染了病毒，则会设置一个属性，以便用户无法下载或同步该文件。</span><span class="sxs-lookup"><span data-stu-id="fae9b-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fae9b-107">SharePoint Online 中的这些防病毒功能是包含病毒的一种方法。</span><span class="sxs-lookup"><span data-stu-id="fae9b-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="fae9b-108">它们不是为了抵御针对您的环境的恶意软件的单一防御点。</span><span class="sxs-lookup"><span data-stu-id="fae9b-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="fae9b-109">我们鼓励所有客户在各层评估和实施反恶意软件保护，并应用最佳做法来保护企业基础结构。</span><span class="sxs-lookup"><span data-stu-id="fae9b-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="fae9b-110">有关策略和最佳实践的详细信息，请参阅[安全路线图](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="fae9b-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="fae9b-111">将受感染的文件上载到 SharePoint Online 时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="fae9b-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="fae9b-112">Microsoft 365 使用通用的病毒检测引擎。</span><span class="sxs-lookup"><span data-stu-id="fae9b-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="fae9b-113">引擎在 SharePoint Online 中以异步方式运行，并在上载文件后扫描这些文件。</span><span class="sxs-lookup"><span data-stu-id="fae9b-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="fae9b-114">试探法用于确定要扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="fae9b-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="fae9b-115">当发现文件包含病毒时，会对其进行标记，以便无法再次下载。</span><span class="sxs-lookup"><span data-stu-id="fae9b-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="fae9b-116">在4月2018，我们删除了扫描文件的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="fae9b-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="fae9b-117">以下是所发生的情况：</span><span class="sxs-lookup"><span data-stu-id="fae9b-117">Here's what happens:</span></span>

1. <span data-ttu-id="fae9b-118">用户将文件上传到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="fae9b-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="fae9b-119">SharePoint Online 决定文件是否符合扫描的条件。</span><span class="sxs-lookup"><span data-stu-id="fae9b-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="fae9b-120">病毒检测引擎将扫描文件。</span><span class="sxs-lookup"><span data-stu-id="fae9b-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="fae9b-121">如果发现了病毒，病毒引擎将对文件设置一个属性，表明它已被感染。</span><span class="sxs-lookup"><span data-stu-id="fae9b-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="fae9b-122">当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="fae9b-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="fae9b-123">如果文件受到感染，用户不能使用浏览器从 SharePoint Online 下载文件。</span><span class="sxs-lookup"><span data-stu-id="fae9b-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="fae9b-124">以下是所发生的情况：</span><span class="sxs-lookup"><span data-stu-id="fae9b-124">Here's what happens:</span></span>

1. <span data-ttu-id="fae9b-125">用户打开 web 浏览器并尝试从 SharePoint Online 下载感染病毒的文件。</span><span class="sxs-lookup"><span data-stu-id="fae9b-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="fae9b-126">向用户提供一条警告，指示已检测到病毒。</span><span class="sxs-lookup"><span data-stu-id="fae9b-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="fae9b-127">向用户提供下载文件的选项，并尝试使用自己的防病毒软件将其清除。</span><span class="sxs-lookup"><span data-stu-id="fae9b-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="fae9b-128">可以在 SharePoint Online PowerShell 中的[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet 上使用*DisallowInfectedFileDownload*参数，以防止用户下载感染病毒的文件，即使在反病毒警告窗口中也是如此。</span><span class="sxs-lookup"><span data-stu-id="fae9b-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>
> 
> <span data-ttu-id="fae9b-129">此外，请注意，只要您启用了*DisallowInfectedFileDownload*参数，就会完全阻止用户和管理员对检测到的/被阻止的文件的访问。</span><span class="sxs-lookup"><span data-stu-id="fae9b-129">Also keep in mind, that as soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completly blocked for users and administrators.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="fae9b-130">OneDrive 同步客户端尝试同步受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="fae9b-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="fae9b-131">用户是使用新 OneDrive 同步客户端（OneDrive.exe）还是以前的 OneDrive for Business 同步客户端（Groove.exe）同步文件，如果文件包含病毒，同步客户端不会下载它。</span><span class="sxs-lookup"><span data-stu-id="fae9b-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="fae9b-132">同步客户端将显示一条通知，指出文件无法同步。</span><span class="sxs-lookup"><span data-stu-id="fae9b-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-atp"></a><span data-ttu-id="fae9b-133">Office 365 ATP 的扩展功能</span><span class="sxs-lookup"><span data-stu-id="fae9b-133">Extended capabilities with Office 365 ATP</span></span>

<span data-ttu-id="fae9b-134">启用了 Office 365 ATP for Sharepoint、OneDrive 和 Microsoft 团队的客户[打开 sharepoint、onedrive 和 Microsoft 团队的 atp](turn-on-atp-for-spo-odb-and-teams.md) ，可以使用安全 & 合规性中心管理用于 AV 和 ATP 检测的隔离文件。</span><span class="sxs-lookup"><span data-stu-id="fae9b-134">Customers who enabled Office 365 ATP for Sharepoint, OneDrive, and Microsoft Teams [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) are able to use the Security & Compliance Center to manage quarantined files for AV and ATP detections.</span></span> <span data-ttu-id="fae9b-135">[仅 ATP：使用安全 & 合规性中心管理隔离的文件](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)。</span><span class="sxs-lookup"><span data-stu-id="fae9b-135">[ATP Only: Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="more-information"></a><span data-ttu-id="fae9b-136">更多信息</span><span class="sxs-lookup"><span data-stu-id="fae9b-136">More information</span></span>

<span data-ttu-id="fae9b-137">有关如何配置 SharePoint Online 防病毒的详细信息，请参阅[针对威胁进行保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements)和[打开有关 sharepoint、OneDrive 和 MICROSOFT 团队的 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) 。</span><span class="sxs-lookup"><span data-stu-id="fae9b-137">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


