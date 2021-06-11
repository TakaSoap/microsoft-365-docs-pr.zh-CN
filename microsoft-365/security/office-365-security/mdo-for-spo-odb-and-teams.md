---
title: 用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
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
description: 了解适用于 Office 365 Online、SharePoint、OneDrive for Business 和 Microsoft Teams 中的文件的 Microsoft Defender。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a74a75f12a758b9b116a3f752624df38f338d0d1
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878216"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="882e1-103">用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="882e1-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="882e1-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="882e1-104">**Applies to**</span></span>
- [<span data-ttu-id="882e1-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="882e1-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="882e1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="882e1-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="882e1-107">保险箱适用于 Office 365 的[Microsoft Defender](whats-new-in-defender-for-office-365.md) SharePoint、OneDrive 和 Microsoft Teams 的附件为已由 Microsoft 365 中的常见病毒检测引擎在上载时扫描的文件提供了一层额外的[保护](virus-detection-in-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="882e1-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="882e1-108">保险箱SharePoint、OneDrive 和 Microsoft Teams 的附件可帮助检测和阻止在团队网站和文档库中标识为恶意的现有文件。</span><span class="sxs-lookup"><span data-stu-id="882e1-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="882e1-109">保险箱默认情况下，SharePoint、OneDrive 和 Microsoft Teams 的附件不会启用。</span><span class="sxs-lookup"><span data-stu-id="882e1-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="882e1-110">若要打开它，请参阅打开保险箱[附件SharePoint、OneDrive和Microsoft Teams。](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="882e1-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="882e1-111">保险箱、OneDrive和SharePoint附件Microsoft Teams的工作原理</span><span class="sxs-lookup"><span data-stu-id="882e1-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="882e1-112">如果保险箱附件SharePoint、OneDrive 和 Microsoft Teams，并且将文件标识为恶意文件，则使用与文件存储的直接集成锁定该文件。</span><span class="sxs-lookup"><span data-stu-id="882e1-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="882e1-113">以下图像显示了库中检测到的恶意文件示例。</span><span class="sxs-lookup"><span data-stu-id="882e1-113">The following image shows an example of a malicious file detected in a library.</span></span>

![文件中OneDrive for Business一个被检测为恶意的文件](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="882e1-115">尽管阻止的文件仍在文档库和 Web、移动或桌面应用程序中列出，但用户无法打开、复制、移动或共享该文件。</span><span class="sxs-lookup"><span data-stu-id="882e1-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="882e1-116">但他们可以删除阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="882e1-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="882e1-117">下面是阻止的文件在移动设备上的外观示例：</span><span class="sxs-lookup"><span data-stu-id="882e1-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![从应用移动应用中删除OneDrive for Business阻止OneDrive文件](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="882e1-119">默认情况下，用户可以下载阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="882e1-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="882e1-120">下面是在移动设备上下载阻止的文件的外观：</span><span class="sxs-lookup"><span data-stu-id="882e1-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![下载阻止的文件OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="882e1-122">SharePoint联机管理员可以阻止用户下载恶意文件。</span><span class="sxs-lookup"><span data-stu-id="882e1-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="882e1-123">有关说明，请参阅[使用 SharePoint Online PowerShell 阻止用户下载恶意文件](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。</span><span class="sxs-lookup"><span data-stu-id="882e1-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="882e1-124">若要了解有关文件被检测为恶意文件时的用户体验，请参阅在 SharePoint Online、OneDrive 或 Microsoft Teams 中发现恶意文件时[Microsoft Teams。](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="882e1-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="882e1-125">查看有关附件中检测到的恶意保险箱文件SharePoint、OneDrive和Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="882e1-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="882e1-126">SharePoint、OneDrive 和 Microsoft Teams 的 保险箱 附件标识为恶意的文件将显示在[Microsoft Defender for Office 365](view-reports-for-mdo.md)的报告和资源管理器 (以及实时检测) [中](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="882e1-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="882e1-127">自 2018 年 5 月起，当 保险箱 Attachments for SharePoint、OneDrive 和 Microsoft Teams 识别为恶意文件时，该文件也可隔离。</span><span class="sxs-lookup"><span data-stu-id="882e1-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="882e1-128">有关详细信息，请参阅使用 Microsoft 365 Defender 门户管理 Defender for Office 365 中的[隔离Office 365。](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="882e1-128">For more information, see [Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="882e1-129">请记住以下几点</span><span class="sxs-lookup"><span data-stu-id="882e1-129">Keep these points in mind</span></span>

- <span data-ttu-id="882e1-130">Defender for Office 365不会扫描 SharePoint Online、OneDrive for Business 或 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="882e1-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="882e1-131">这是设计使然的。</span><span class="sxs-lookup"><span data-stu-id="882e1-131">This is by design.</span></span> <span data-ttu-id="882e1-132">以异步方式扫描文件。</span><span class="sxs-lookup"><span data-stu-id="882e1-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="882e1-133">此过程使用共享和来宾活动事件以及智能启发和威胁信号来识别恶意文件。</span><span class="sxs-lookup"><span data-stu-id="882e1-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="882e1-134">请确保你的SharePoint网站配置为使用新式[体验](/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="882e1-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="882e1-135">Defender for Office 365 保护适用于是否使用新式体验或经典视图;但是，文件被阻止的视觉指示器仅在新式体验中可用。</span><span class="sxs-lookup"><span data-stu-id="882e1-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="882e1-136">保险箱SharePoint、OneDrive 和 Microsoft Teams 的附件是组织的整体威胁防护策略的一部分，其中包括 Exchange Online Protection (EOP) 中的反垃圾邮件和反恶意软件保护，以及 microsoft Defender for Office 365 中的 保险箱 链接和 保险箱 附件。</span><span class="sxs-lookup"><span data-stu-id="882e1-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="882e1-137">若要了解更多信息，请参阅防止 Office 365 中[的威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="882e1-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
