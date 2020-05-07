---
title: 查看有关 Office 365 ATP 检测到的恶意文件的信息
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: 了解在何处可以查看有关在 SharePoint、OneDrive 或团队中检测到的恶意文件的信息，以及如何对这些文件执行操作。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47b1fea4b3b5713a8f69e8f4b2c0e2ad0f6dd6b8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036640"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="bb952-103">查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息</span><span class="sxs-lookup"><span data-stu-id="bb952-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="bb952-104">[适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](atp-for-spo-odb-and-teams.md)可保护您的组织免受文档库和工作组网站中的恶意文件的攻击。</span><span class="sxs-lookup"><span data-stu-id="bb952-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="bb952-105">检测到恶意文件时，将阻止该文件，以便在组织的安全团队执行进一步操作之前，任何人都无法打开、复制、移动或共享该文件。</span><span class="sxs-lookup"><span data-stu-id="bb952-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="bb952-106">阅读本文，了解如何查看有关检测到的文件以及要执行的操作的信息。</span><span class="sxs-lookup"><span data-stu-id="bb952-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="bb952-107">若要执行本文中所述的任务，您必须具有[针对安全&amp;合规中心](permissions-in-the-security-and-compliance-center.md)的必要权限。</span><span class="sxs-lookup"><span data-stu-id="bb952-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="bb952-108">查看包含检测到的文件的相关信息的报告</span><span class="sxs-lookup"><span data-stu-id="bb952-108">View reports with information about detected files</span></span>

<span data-ttu-id="bb952-109">若要查看 Office 365 ATP 检测到的文件的状态和详细信息，可以使用威胁防护状态报告。</span><span class="sxs-lookup"><span data-stu-id="bb952-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="bb952-110">在 "[安全&amp;合规性中心](https://protection.office.com)" 中，选择 "**报告** \> "**仪表板** \> **威胁防护状态**。</span><span class="sxs-lookup"><span data-stu-id="bb952-110">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="bb952-111">在报表的右上角，选择 "**查看详细信息表**"。</span><span class="sxs-lookup"><span data-stu-id="bb952-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="bb952-112">查看在报告中检测到的文件的列表。</span><span class="sxs-lookup"><span data-stu-id="bb952-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="bb952-113">选择列表中的项目以查看详细信息，包括执行的操作、文件名、文件路径等。</span><span class="sxs-lookup"><span data-stu-id="bb952-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="bb952-114">选择 "**高级分析**" 选项卡以查看信息，如观察到的行为和分析详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb952-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="bb952-115">查看隔离区中的文件并对其执行操作</span><span class="sxs-lookup"><span data-stu-id="bb952-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="bb952-116">在 "安全&amp;合规性中心" 中，选择 "**威胁管理** \> **检查** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="bb952-116">In the Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="bb952-117">（你也可以直接转到[https://protection.office.com/quarantine](https://protection.office.com/quarantine)。）</span><span class="sxs-lookup"><span data-stu-id="bb952-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="bb952-118">在左上角，将下拉菜单从**电子邮件**更改为**文件**。</span><span class="sxs-lookup"><span data-stu-id="bb952-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="bb952-119">如果结果列表中包含过多项目，请使用**筛选**功能缩小选定范围。</span><span class="sxs-lookup"><span data-stu-id="bb952-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="bb952-120">选择列表中的某一项，以查看详细信息，包括文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="bb952-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="bb952-121">选择可用操作。</span><span class="sxs-lookup"><span data-stu-id="bb952-121">Choose an available action.</span></span>
    
    - <span data-ttu-id="bb952-122">选择 "**释放文件**" 以取消阻止该文件。</span><span class="sxs-lookup"><span data-stu-id="bb952-122">Choose **Release file** to unblock the file.</span></span> 

      <span data-ttu-id="bb952-123">选择 "**将报告发送给 microsoft** " 以将该文件报告为 "误报到 microsoft"。</span><span class="sxs-lookup"><span data-stu-id="bb952-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 

    - <span data-ttu-id="bb952-124">选择 "**下载文件**" 以进一步调查文件。</span><span class="sxs-lookup"><span data-stu-id="bb952-124">Choose **Download file** to investigate the file further.</span></span> 

    - <span data-ttu-id="bb952-125">选择 "**从隔离区删除**" 以从隔离项目列表中删除该文件。</span><span class="sxs-lookup"><span data-stu-id="bb952-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="bb952-126">如果选择此选项，则还必须在 SharePoint Online、OneDrive for Business 或 Microsoft 团队中从其各自的库中删除文件。</span><span class="sxs-lookup"><span data-stu-id="bb952-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="bb952-127">此选项不会取消阻止打开或共享文件。</span><span class="sxs-lookup"><span data-stu-id="bb952-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="bb952-128">选择 "**关闭**" 以关闭所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb952-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

