---
title: 准备通过 Microsoft 365 商业版部署 Office 客户端
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 了解如何在 Windows 10 计算机上自动安装 32 位 Office 应用并保持更新。
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580046"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="afaec-103">准备通过 Microsoft 365 商业版部署 Office 客户端</span><span class="sxs-lookup"><span data-stu-id="afaec-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="afaec-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="afaec-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="afaec-105">准备在客户端计算机上自动安装 Office 应用</span><span class="sxs-lookup"><span data-stu-id="afaec-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="afaec-106">可以使用 Microsoft 365 商业高级版在 Windows 10 计算机上自动安装 32 位 Office 应用，并使它们具有最新更新。</span><span class="sxs-lookup"><span data-stu-id="afaec-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="afaec-107">如果最终用户的计算机在 Windows 10 商业计算机上并且：</span><span class="sxs-lookup"><span data-stu-id="afaec-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="afaec-108">没有现有的 Office 桌面应用（Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive）。</span><span class="sxs-lookup"><span data-stu-id="afaec-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="afaec-109">或</span><span class="sxs-lookup"><span data-stu-id="afaec-109">or</span></span>
    
- <span data-ttu-id="afaec-110">安装了即点即用 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="afaec-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="afaec-111">若要确定是否拥有即点即用版本的 Office，请在任何 Office 应用中，转到" **文件**"\>" **帐户**"（如 Outlook 中的 **Office 帐户**。</span><span class="sxs-lookup"><span data-stu-id="afaec-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="afaec-112">如果看到下图所示的 **Office** 更新，则使用即点即用完成安装。</span><span class="sxs-lookup"><span data-stu-id="afaec-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="afaec-114">**谁从拥有此功能中获益**</span><span class="sxs-lookup"><span data-stu-id="afaec-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="afaec-115">电脑属于以下情况的最终用户：</span><span class="sxs-lookup"><span data-stu-id="afaec-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="afaec-116">**拥有**  Windows 10 商业版用户许可证、活动的 Microsoft 365 商业版许可证、Windows 10 创意者更新，并且已加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="afaec-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="afaec-117">**没有 64** 位 Office 应用程序，例如 (Word、Excel、PowerPoint) 。</span><span class="sxs-lookup"><span data-stu-id="afaec-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="afaec-118">如果需要 64 位 Office 应用，则此功能不适合，因为不支持从 Microsoft 365 商业版管理控制台触发 64 位 2016 即点即用版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="afaec-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="afaec-119">**没有** 任何 2016 Windows Installer (MSI) 独立应用（如 Visio 或 Project）。</span><span class="sxs-lookup"><span data-stu-id="afaec-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="afaec-120">Microsoft 365 商业版将 Office 升级到 Office 2016 即点即用版本，它不能用于 Office 2016 MSI 独立应用。</span><span class="sxs-lookup"><span data-stu-id="afaec-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="afaec-121">下表显示了最终用户/管理员可能需要执行哪些操作，具体取决于其开始状态，才能从 Microsoft 365 商业版管理控制台成功部署 32 位即点即用版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="afaec-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="afaec-122">**启动 Office 安装状态**</span><span class="sxs-lookup"><span data-stu-id="afaec-122">**Starting Office install status**</span></span>|<span data-ttu-id="afaec-123">**在安装 Microsoft 365 商业版 Office 之前要执行的操作**</span><span class="sxs-lookup"><span data-stu-id="afaec-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="afaec-124">**结束状态**</span><span class="sxs-lookup"><span data-stu-id="afaec-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afaec-125">未安装任何 Office 套件</span><span class="sxs-lookup"><span data-stu-id="afaec-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="afaec-126">无</span><span class="sxs-lookup"><span data-stu-id="afaec-126">None</span></span>  <br/> |<span data-ttu-id="afaec-127">使用"单击运行"安装 Office 2016 32 位</span><span class="sxs-lookup"><span data-stu-id="afaec-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="afaec-128">有 32 位即点即用版 Office（2016 或更低版本）且无独立应用</span><span class="sxs-lookup"><span data-stu-id="afaec-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="afaec-129">无</span><span class="sxs-lookup"><span data-stu-id="afaec-129">None</span></span>  <br/> |<span data-ttu-id="afaec-130">根据需要，升级到了最新的 32 位即点即用版 Office 2016 **\***</span><span class="sxs-lookup"><span data-stu-id="afaec-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="afaec-131">现有的 32 位单击运行版本的 Office 和 32 位或 64 位的单击运行独立 Office 应用 (例如 Visio、Project) </span><span class="sxs-lookup"><span data-stu-id="afaec-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="afaec-132">无</span><span class="sxs-lookup"><span data-stu-id="afaec-132">None</span></span>  <br/> |<span data-ttu-id="afaec-133">独立应用不受影响。</span><span class="sxs-lookup"><span data-stu-id="afaec-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="afaec-134">套件升级到 32 位即点即用版 Office 2016</span><span class="sxs-lookup"><span data-stu-id="afaec-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="afaec-135">有 32 位即点即用版 Office 和任何 32 位/64 位（除 2016）MSI 独立 Office 应用</span><span class="sxs-lookup"><span data-stu-id="afaec-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="afaec-136">无</span><span class="sxs-lookup"><span data-stu-id="afaec-136">None</span></span>  <br/> |<span data-ttu-id="afaec-137">独立应用不受影响。</span><span class="sxs-lookup"><span data-stu-id="afaec-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="afaec-138">套件升级到 32 位即点即用版 Office 2016</span><span class="sxs-lookup"><span data-stu-id="afaec-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="afaec-139">有任何 64 位即点即用版 Office</span><span class="sxs-lookup"><span data-stu-id="afaec-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="afaec-140">卸载 64 位 Office 应用（如果可以将其替换为 32 位 Office 应用）</span><span class="sxs-lookup"><span data-stu-id="afaec-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="afaec-141">如果删除了 Office 64 位应用，则安装 32 位即点即用版 Office 2016</span><span class="sxs-lookup"><span data-stu-id="afaec-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="afaec-142">安装有 MSI Office 2016，有/无独立应用</span><span class="sxs-lookup"><span data-stu-id="afaec-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="afaec-143">卸载 MSI Office 2016。</span><span class="sxs-lookup"><span data-stu-id="afaec-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="afaec-p106">安装了 32 位即点即用版 Office 2016。不更改独立应用</span><span class="sxs-lookup"><span data-stu-id="afaec-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="afaec-146">安装有 MSI Office 2013（或更低版本）和/或独立 Office 应用</span><span class="sxs-lookup"><span data-stu-id="afaec-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="afaec-147">无</span><span class="sxs-lookup"><span data-stu-id="afaec-147">None</span></span>  <br/> |<span data-ttu-id="afaec-148">32 位即点即用版 Office 2016 和预先存在的 MSI Office 安装（和独立应用）并存</span><span class="sxs-lookup"><span data-stu-id="afaec-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="afaec-149">**(\*) 注意：** 由于一个已知 bug，不升级到 32 位即点即用版 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="afaec-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="afaec-150">正在修复。</span><span class="sxs-lookup"><span data-stu-id="afaec-150">A fix is in progress.</span></span> 
  
