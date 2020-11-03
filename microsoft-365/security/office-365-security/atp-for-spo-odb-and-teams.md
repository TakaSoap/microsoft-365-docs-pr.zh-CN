---
title: 适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 了解适用于 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件的 Microsoft Defender for Office 365。
ms.openlocfilehash: 7b007671a7fecb3ae074fd07ce38d17fb025f6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844328"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="90c11-103">适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="90c11-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90c11-104">[Microsoft Defender For Office 365](office-365-atp.md)中的 SharePoint、OneDrive 和 microsoft 团队的 ATP 为[microsoft 365 中的常见病毒检测引擎](virus-detection-in-spo.md)在上载时已扫描的文件提供了额外的保护层。</span><span class="sxs-lookup"><span data-stu-id="90c11-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="90c11-105">SharePoint、OneDrive 和 Microsoft 团队的 ATP 可帮助检测和阻止在工作组网站和文档库中标识为恶意的现有文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="90c11-106">默认情况下不启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP。</span><span class="sxs-lookup"><span data-stu-id="90c11-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="90c11-107">若要打开它，请参阅 [启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="90c11-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="90c11-108">SharePoint、OneDrive 和 Microsoft 团队的 ATP 的工作原理</span><span class="sxs-lookup"><span data-stu-id="90c11-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="90c11-109">如果启用了 SharePoint、OneDrive 和 Microsoft 团队的 ATP，并将文件标识为恶意文件，则会使用与文件存储区的直接集成来锁定文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="90c11-110">下图显示了在库中检测到的恶意文件的示例。</span><span class="sxs-lookup"><span data-stu-id="90c11-110">The following image shows an example of a malicious file detected in a library.</span></span>

![OneDrive for business 中一个检测为恶意的文件](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="90c11-112">尽管阻止的文件仍在文档库和 web、移动或桌面应用程序中列出，但用户无法打开、复制、移动或共享文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="90c11-113">但它们可以删除被阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="90c11-114">下面的示例展示了阻止的文件在移动设备上的显示效果：</span><span class="sxs-lookup"><span data-stu-id="90c11-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![从 OneDrive 移动应用程序中删除 OneDrive for business 中的阻止文件](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="90c11-116">默认情况下，用户可以下载被阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="90c11-117">下面介绍了如何在移动设备上下载被阻止的文件：</span><span class="sxs-lookup"><span data-stu-id="90c11-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![在 OneDrive for Business 中下载阻止的文件](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="90c11-119">SharePoint Online 管理员可以阻止用户下载恶意文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="90c11-120">有关说明，请参阅 [使用 SharePoint Online PowerShell 防止用户下载恶意文件](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="90c11-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="90c11-121">若要详细了解在将文件检测为恶意时的用户体验，请参阅在 [SharePoint Online、OneDrive 或 Microsoft 团队中找到恶意文件时应执行的操作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="90c11-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="90c11-122">查看有关由 SharePoint、OneDrive 和 Microsoft 团队的 ATP 检测到的恶意文件的信息</span><span class="sxs-lookup"><span data-stu-id="90c11-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="90c11-123">Microsoft Defender for Office 365 中被标识为恶意的文件将显示在 [Microsoft defender For office 365](view-reports-for-atp.md) 和资源管理器中的报告中， [ (和实时检测) ](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="90c11-123">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="90c11-124">到5月2018日，当 Microsoft Defender for Office 365 将某个文件标识为恶意文件时，该文件也在隔离区中可用。</span><span class="sxs-lookup"><span data-stu-id="90c11-124">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="90c11-125">有关详细信息，请参阅 [使用安全 & 合规性中心管理隔离的文件](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)。</span><span class="sxs-lookup"><span data-stu-id="90c11-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="90c11-126">记住这些要点</span><span class="sxs-lookup"><span data-stu-id="90c11-126">Keep these points in mind</span></span>

- <span data-ttu-id="90c11-127">适用于 Office 的 Defender 365 不会扫描 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的每一个文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-127">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="90c11-128">这是设计使然的。</span><span class="sxs-lookup"><span data-stu-id="90c11-128">This is by design.</span></span> <span data-ttu-id="90c11-129">异步扫描文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="90c11-130">此过程使用共享和来宾活动事件以及智能试探法和威胁信号来识别恶意文件。</span><span class="sxs-lookup"><span data-stu-id="90c11-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="90c11-131">确保您的 SharePoint 网站已配置为使用 [新式体验](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="90c11-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="90c11-132">适用于 Office 365 的 Defender 防护应用是否使用新式体验或经典视图;但是，阻止文件被阻止的视觉指示器仅适用于新式体验。</span><span class="sxs-lookup"><span data-stu-id="90c11-132">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="90c11-133">SharePoint、OneDrive 和 Microsoft 团队的 ATP 是组织的整体威胁防护策略的一部分，其中包括 Exchange Online Protection 中的反垃圾邮件和反恶意软件保护 (EOP) ，以及 Microsoft Defender for Office 365 中的安全链接和安全附件。</span><span class="sxs-lookup"><span data-stu-id="90c11-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="90c11-134">若要了解详细信息，请参阅 [在 Office 365 中防御威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="90c11-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
