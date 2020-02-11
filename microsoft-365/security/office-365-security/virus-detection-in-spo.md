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
description: 了解 SharePoint Online 中的防病毒保护。
ms.openlocfilehash: f22c2a3280148eb23f4ba53ff467a533186ed791
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887269"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="e04a0-103">SharePoint Online 中的病毒检测</span><span class="sxs-lookup"><span data-stu-id="e04a0-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="e04a0-104">通过检测用户上传到 SharePoint Online 的文件中的病毒，Office 365 可帮助保护您的环境免受恶意软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="e04a0-104">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="e04a0-105">上载文件后，可能会对其进行病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="e04a0-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="e04a0-106">如果发现文件感染了病毒，则会设置一个属性，以便用户无法下载或同步该文件。</span><span class="sxs-lookup"><span data-stu-id="e04a0-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e04a0-107">SharePoint Online 中的这些防病毒功能是包含病毒的一种方法。</span><span class="sxs-lookup"><span data-stu-id="e04a0-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="e04a0-108">它们不是为了抵御针对您的环境的恶意软件的单一防御点。</span><span class="sxs-lookup"><span data-stu-id="e04a0-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="e04a0-109">我们鼓励所有客户在各层评估和实施反恶意软件保护，并应用最佳做法来保护企业基础结构。</span><span class="sxs-lookup"><span data-stu-id="e04a0-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="e04a0-110">有关策略和最佳实践的详细信息，请参阅[安全路线图](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="e04a0-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="e04a0-111">将受感染的文件上载到 SharePoint Online 时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="e04a0-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="e04a0-112">Office 365 使用通用的病毒检测引擎。</span><span class="sxs-lookup"><span data-stu-id="e04a0-112">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="e04a0-113">引擎在 SharePoint Online 中以异步方式运行，并在上载文件后扫描这些文件。</span><span class="sxs-lookup"><span data-stu-id="e04a0-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="e04a0-114">试探法用于确定要扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="e04a0-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="e04a0-115">当发现文件包含病毒时，会对其进行标记，以便无法再次下载。</span><span class="sxs-lookup"><span data-stu-id="e04a0-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="e04a0-116">在4月2018，我们删除了扫描文件的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="e04a0-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="e04a0-117">以下是所发生的情况：</span><span class="sxs-lookup"><span data-stu-id="e04a0-117">Here's what happens:</span></span>

1. <span data-ttu-id="e04a0-118">用户将文件上传到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="e04a0-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="e04a0-119">SharePoint Online 决定文件是否符合扫描的条件。</span><span class="sxs-lookup"><span data-stu-id="e04a0-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="e04a0-120">病毒检测引擎将扫描文件。</span><span class="sxs-lookup"><span data-stu-id="e04a0-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="e04a0-121">如果发现了病毒，病毒引擎将对文件设置一个属性，表明它已被感染。</span><span class="sxs-lookup"><span data-stu-id="e04a0-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="e04a0-122">当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="e04a0-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="e04a0-123">如果文件受到感染，用户不能使用浏览器从 SharePoint Online 下载文件。</span><span class="sxs-lookup"><span data-stu-id="e04a0-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="e04a0-124">以下是所发生的情况：</span><span class="sxs-lookup"><span data-stu-id="e04a0-124">Here's what happens:</span></span>

1. <span data-ttu-id="e04a0-125">用户打开 web 浏览器并尝试从 SharePoint Online 下载感染病毒的文件。</span><span class="sxs-lookup"><span data-stu-id="e04a0-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="e04a0-126">向用户提供一条警告，指示已检测到病毒。</span><span class="sxs-lookup"><span data-stu-id="e04a0-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="e04a0-127">向用户提供下载文件的选项，并尝试使用自己的防病毒软件将其清除。</span><span class="sxs-lookup"><span data-stu-id="e04a0-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="e04a0-128">可以在 SharePoint Online PowerShell 中的[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet 上使用*DisallowInfectedFileDownload*参数，以防止用户下载感染病毒的文件，即使在反病毒警告窗口中也是如此。</span><span class="sxs-lookup"><span data-stu-id="e04a0-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="e04a0-129">OneDrive 同步客户端尝试同步受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="e04a0-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="e04a0-130">无论用户是使用新 OneDrive 同步客户端（OneDrive .exe）还是以前的 OneDrive for Business 同步客户端（Groove）同步文件，同步客户端也不会下载该病毒。</span><span class="sxs-lookup"><span data-stu-id="e04a0-130">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="e04a0-131">同步客户端将显示一条通知，指出文件无法同步。</span><span class="sxs-lookup"><span data-stu-id="e04a0-131">The sync client will display a notification that the file can't be synced.</span></span>
