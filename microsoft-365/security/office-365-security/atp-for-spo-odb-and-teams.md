---
title: 适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 了解有关 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件的 Office 365 高级威胁防护。
ms.openlocfilehash: e4a711d6554ffcb8e291d5b2154120d078995e94
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815405"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e41a1-103">适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="e41a1-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="e41a1-104">SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP 概述</span><span class="sxs-lookup"><span data-stu-id="e41a1-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="e41a1-105">用户定期共享文件，并使用 SharePoint、OneDrive 和 Microsoft 团队进行协作。</span><span class="sxs-lookup"><span data-stu-id="e41a1-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="e41a1-106">使用[Office 365 高级威胁防护](office-365-atp.md)（ATP），您的组织可以更安全地进行协作。</span><span class="sxs-lookup"><span data-stu-id="e41a1-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="e41a1-107">ATP 可帮助检测和阻止在工作组网站和文档库中被标识为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>

## <a name="how-office-365-atp-operates"></a><span data-ttu-id="e41a1-108">如何运行 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="e41a1-108">How Office 365 ATP operates</span></span>

<span data-ttu-id="e41a1-109">如果 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件被标识为恶意，ATP 将直接与文件存储集成以锁定该文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="e41a1-110">下图显示了在库中检测到的恶意文件的示例。</span><span class="sxs-lookup"><span data-stu-id="e41a1-110">The following image shows an example of a malicious file detected in a library.</span></span>

![OneDrive for business 中一个检测为恶意的文件](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="e41a1-112">尽管阻止的文件仍在文档库和 web、移动设备或桌面应用程序中列出，但无法打开、复制、移动或共享被阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="e41a1-113">但是，用户可以删除被阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="e41a1-114">下面的示例展示了在用户的移动设备上显示的内容：</span><span class="sxs-lookup"><span data-stu-id="e41a1-114">Here's an example of what that looks like on a user's mobile device:</span></span>

![从 OneDrive 移动应用程序中删除 OneDrive for business 中的阻止文件](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="e41a1-116">根据 Microsoft 365 的配置方式，用户可能会或可能无法下载被阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-116">Depending on how Microsoft 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="e41a1-117">下面介绍了如何在用户的移动设备上下载被阻止的文件：</span><span class="sxs-lookup"><span data-stu-id="e41a1-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>

![在 OneDrive for Business 中下载阻止的文件](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="e41a1-119">有关详细信息，请参阅[开启适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e41a1-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="e41a1-120">记住这些要点</span><span class="sxs-lookup"><span data-stu-id="e41a1-120">Keep these points in mind</span></span>

- <span data-ttu-id="e41a1-121">ATP 将不会扫描 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的每个单个文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="e41a1-122">这是有意设计的。</span><span class="sxs-lookup"><span data-stu-id="e41a1-122">This is by design.</span></span> <span data-ttu-id="e41a1-123">通过使用共享和来宾活动事件的进程以及智能试探和威胁信号识别恶意文件，异步扫描文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="e41a1-124">确保您的 SharePoint 网站已配置为使用[新式体验](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="e41a1-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="e41a1-125">当文件被标识为恶意的且被阻止时，人们可以看到这种情况发生在新式体验中，而不是经典视图中。</span><span class="sxs-lookup"><span data-stu-id="e41a1-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="e41a1-126">ATP protection 适用于是否使用新式体验或经典视图;但是，仅在新式体验中，才会出现阻止文件的视觉指示器。</span><span class="sxs-lookup"><span data-stu-id="e41a1-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>

- <span data-ttu-id="e41a1-127">在 SharePoint Online、OneDrive for Business 或 Microsoft 团队中被标识为恶意的文件将显示在[Office 365 高级威胁防护](view-reports-for-atp.md)和[资源管理器（和实时检测）](threat-explorer.md)的报告中。</span><span class="sxs-lookup"><span data-stu-id="e41a1-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

- <span data-ttu-id="e41a1-128">ATP 是组织整体威胁防护策略的一部分，其中包括反垃圾邮件和反恶意软件保护，以及安全链接和安全附件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="e41a1-129">若要了解详细信息，请参阅[在 Office 365 中防御威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="e41a1-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="e41a1-130">SharePoint Online 管理员可以确定是否允许用户下载被检测为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="e41a1-131">这是通过使用 DisallowInfectedFileDownload 参数运行 Set-spotenant PowerShell cmdlet 来实现的（请参阅[打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)）。</span><span class="sxs-lookup"><span data-stu-id="e41a1-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="e41a1-132">SharePoint Online、OneDrive for Business 和 Microsoft 团队的 ATP 中的隔离</span><span class="sxs-lookup"><span data-stu-id="e41a1-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="e41a1-133">从后期开始可能为2018，安全合规中心中的[隔离](quarantine-email-messages.md)功能 &amp; 将扩展到 SharePoint Online、OneDrive For Business 和 MICROSOFT 团队的 ATP。</span><span class="sxs-lookup"><span data-stu-id="e41a1-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e41a1-134">当 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的文件被标识为恶意文件时，除了 ATP 阻止打开或共享该文件之外，该文件还包含在隔离项目的列表中。</span><span class="sxs-lookup"><span data-stu-id="e41a1-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="e41a1-135">（在安全 &amp;合规性中心，请转到 "**威胁管理**" \> **查看** \> **隔离**和筛选**文件**。）</span><span class="sxs-lookup"><span data-stu-id="e41a1-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Files**.)</span></span>

<span data-ttu-id="e41a1-136">如果你是组织的 Microsoft 365 企业安全团队的一部分，并且在[安全 &amp; 合规中心中分配](permissions-in-the-security-and-compliance-center.md)了必要的权限，则可以下载、发布、报告和删除从隔离区中的 ATP 检测为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-136">If you're part of your organization's Microsoft 365 for business security team and have the necessary [permissions assigned in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>

- <span data-ttu-id="e41a1-137">**释放和报告**文件将在 SharePoint、OneDrive 或 Microsoft 团队的相应团队网站或文档库中删除文件上的 ATP 块。</span><span class="sxs-lookup"><span data-stu-id="e41a1-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="e41a1-138">然后，用户可以打开、共享和下载文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="e41a1-139">当选择 "**向 Microsoft 发送报告**" 选项时，该文件将报告为 "误报到 microsoft"。</span><span class="sxs-lookup"><span data-stu-id="e41a1-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span>

- <span data-ttu-id="e41a1-140">**删除文件**会将文件从隔离区中删除。但是，仍阻止打开或共享文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="e41a1-141">此外，还必须在其各自的文档库或团队网站（SharePoint Online、OneDrive for Business 或 Microsoft 团队）中删除该文件。</span><span class="sxs-lookup"><span data-stu-id="e41a1-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span>

- <span data-ttu-id="e41a1-142">通过**下载文件**，您可以下载并分析文件，以查找任何误报。</span><span class="sxs-lookup"><span data-stu-id="e41a1-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e41a1-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e41a1-143">Next steps</span></span>

 - [<span data-ttu-id="e41a1-144">打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="e41a1-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

 - [<span data-ttu-id="e41a1-145">查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息</span><span class="sxs-lookup"><span data-stu-id="e41a1-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

