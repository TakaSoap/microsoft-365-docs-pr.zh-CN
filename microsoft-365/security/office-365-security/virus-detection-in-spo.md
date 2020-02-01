---
title: SharePoint Online 中的病毒检测
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
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
description: 通过检测用户上传到 SharePoint Online 的文件中的病毒，Office 365 可帮助保护您的环境免受恶意软件的攻击。 上载文件后，将对其进行病毒扫描。 如果发现文件感染了病毒，则会设置一个属性，以便用户无法下载或同步该文件。
ms.openlocfilehash: 1a41c5bb00e7169878206be2db076af0b0745e30
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597999"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="dc8de-105">SharePoint Online 中的病毒检测</span><span class="sxs-lookup"><span data-stu-id="dc8de-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="dc8de-106">通过检测用户上传到 SharePoint Online 的文件中的病毒，Office 365 可帮助保护您的环境免受恶意软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="dc8de-106">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="dc8de-107">上载文件后，可能会对其进行病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="dc8de-107">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="dc8de-108">如果发现文件感染了病毒，则会设置一个属性，以便用户无法下载或同步该文件。</span><span class="sxs-lookup"><span data-stu-id="dc8de-108">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dc8de-109">SharePoint Online 中的这些防病毒功能是包含病毒的一种方法。</span><span class="sxs-lookup"><span data-stu-id="dc8de-109">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="dc8de-110">它们不是为了抵御针对您的环境的恶意软件的单一防御点。</span><span class="sxs-lookup"><span data-stu-id="dc8de-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="dc8de-111">我们鼓励所有客户在各层评估和实施反恶意软件保护，并应用最佳做法来保护企业基础结构。</span><span class="sxs-lookup"><span data-stu-id="dc8de-111">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="dc8de-112">有关策略和最佳实践的详细信息，请参阅[安全路线图](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="dc8de-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="dc8de-113">将受感染的文件上载到 SharePoint Online 时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="dc8de-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="dc8de-114">Office 365 使用通用的病毒检测引擎。</span><span class="sxs-lookup"><span data-stu-id="dc8de-114">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="dc8de-115">引擎在 SharePoint Online 中以异步方式运行，并在上载文件后扫描这些文件。</span><span class="sxs-lookup"><span data-stu-id="dc8de-115">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="dc8de-116">试探法用于确定要扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="dc8de-116">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="dc8de-117">当发现文件包含病毒时，会对其进行标记，以便无法再次下载。</span><span class="sxs-lookup"><span data-stu-id="dc8de-117">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="dc8de-118">在4月2018，我们删除了扫描文件的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="dc8de-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="dc8de-119">以下是所发生的情况：</span><span class="sxs-lookup"><span data-stu-id="dc8de-119">Here's what happens:</span></span>
  
1. <span data-ttu-id="dc8de-120">用户将文件上传到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="dc8de-120">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="dc8de-121">SharePoint Online 决定文件是否符合扫描的条件。</span><span class="sxs-lookup"><span data-stu-id="dc8de-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="dc8de-122">病毒检测引擎将扫描文件。</span><span class="sxs-lookup"><span data-stu-id="dc8de-122">The virus detection engine scans the file.</span></span>
    
4. <span data-ttu-id="dc8de-123">如果发现了病毒，病毒引擎将对文件设置一个属性，表明它已被感染。</span><span class="sxs-lookup"><span data-stu-id="dc8de-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="dc8de-124">当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="dc8de-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="dc8de-125">如果文件感染了病毒，用户将无法使用浏览器从 SharePoint Online 下载该文件。</span><span class="sxs-lookup"><span data-stu-id="dc8de-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="dc8de-126">以下是所发生的情况：</span><span class="sxs-lookup"><span data-stu-id="dc8de-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="dc8de-127">用户打开 web 浏览器并尝试从 SharePoint Online 下载感染病毒的文件。</span><span class="sxs-lookup"><span data-stu-id="dc8de-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="dc8de-128">向用户提供一条警告，指示已检测到病毒。</span><span class="sxs-lookup"><span data-stu-id="dc8de-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="dc8de-129">向用户提供下载文件的选项，并尝试使用自己的病毒软件对其进行清理。</span><span class="sxs-lookup"><span data-stu-id="dc8de-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="dc8de-130">您可以将 Set-spotenant cmdlet 与**DisallowInfectedFileDownload**参数一起使用，以禁止用户下载检测到的文件，即使在 "反病毒警告" 窗口中也是如此。</span><span class="sxs-lookup"><span data-stu-id="dc8de-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="dc8de-131">请参阅 [DisallowInfectedFileDownload]https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)（。</span><span class="sxs-lookup"><span data-stu-id="dc8de-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="dc8de-132">OneDrive 同步客户端尝试同步受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="dc8de-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="dc8de-133">无论用户是使用新 OneDrive 同步客户端（OneDrive .exe）还是以前的 OneDrive for Business 同步客户端（Groove）同步文件，同步客户端也不会下载该病毒。</span><span class="sxs-lookup"><span data-stu-id="dc8de-133">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="dc8de-134">同步客户端将显示一条通知，指出文件无法同步。</span><span class="sxs-lookup"><span data-stu-id="dc8de-134">The sync client will display a notification that the file can't be synced.</span></span>
  

