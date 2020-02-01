---
title: 准备通过 Microsoft 365 Business 部署 Office 客户端
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 了解如何在 Windows 10 计算机上自动安装32位 Office 应用并将其更新。
ms.openlocfilehash: fa5b2ce1852ebdb1e76c1fa844793fee56af3d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593611"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="1eb09-103">准备通过 Microsoft 365 Business 部署 Office 客户端</span><span class="sxs-lookup"><span data-stu-id="1eb09-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="1eb09-104">准备在客户端计算机上自动安装 Office 应用</span><span class="sxs-lookup"><span data-stu-id="1eb09-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="1eb09-105">您可以使用 Microsoft 365 Business 在 Windows 10 计算机上自动安装32位 Office 应用程序，并将更新保持最新。</span><span class="sxs-lookup"><span data-stu-id="1eb09-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="1eb09-106">如果最终用户的计算机在 Windows 10 商业版上，则自动安装最适用：</span><span class="sxs-lookup"><span data-stu-id="1eb09-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="1eb09-107">没有现有的 Office 桌面应用（Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive）。</span><span class="sxs-lookup"><span data-stu-id="1eb09-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="1eb09-108">或</span><span class="sxs-lookup"><span data-stu-id="1eb09-108">or</span></span>
    
- <span data-ttu-id="1eb09-109">安装了即点即用 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="1eb09-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="1eb09-110">若要确定是否拥有即点即用版本的 Office，请在任何 Office 应用中，转到" **文件**"\>" **帐户**"（如 Outlook 中的 **Office 帐户**。</span><span class="sxs-lookup"><span data-stu-id="1eb09-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="1eb09-111">如果看到如下图所示的**Office 更新**，则说明安装是通过即点即用完成的。</span><span class="sxs-lookup"><span data-stu-id="1eb09-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="1eb09-113">**拥有此功能的好处**</span><span class="sxs-lookup"><span data-stu-id="1eb09-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="1eb09-114">电脑属于以下情况的最终用户：</span><span class="sxs-lookup"><span data-stu-id="1eb09-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="1eb09-115">**具有** Windows 10 商业版用户许可证、处于活动状态的 Microsoft 365 商业版 许可证、Windows 10 创意者更新，并且加入了 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="1eb09-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="1eb09-116">**没有64位**Office 应用程序（例如： Word、Excel、PowerPoint）。</span><span class="sxs-lookup"><span data-stu-id="1eb09-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="1eb09-117">如果需要64位 Office 应用程序，则此功能不合适，因为不支持触发来自 Microsoft 365 Business 管理控制台的 64-位2016即点即用版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="1eb09-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="1eb09-118">**没有** 任何 2016 Windows Installer (MSI) 独立应用（如 Visio 或 Project）。</span><span class="sxs-lookup"><span data-stu-id="1eb09-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="1eb09-119">Microsoft 365 商业版将 Office 升级到 Office 2016 即点即用版，这不适用于 Office 2016 MSI 独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="1eb09-119">Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="1eb09-120">下表显示最终用户/管理员可能需要执行的操作（取决于其初始状态），以便从 Microsoft 365 商业版管理控制台成功运行32位即点即用版 Office 部署。</span><span class="sxs-lookup"><span data-stu-id="1eb09-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="1eb09-121">**启动 Office 安装状态**</span><span class="sxs-lookup"><span data-stu-id="1eb09-121">**Starting Office install status**</span></span>|<span data-ttu-id="1eb09-122">**Microsoft 365 商业版 Office 安装之前要执行的操作**</span><span class="sxs-lookup"><span data-stu-id="1eb09-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="1eb09-123">**结束状态**</span><span class="sxs-lookup"><span data-stu-id="1eb09-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1eb09-124">未安装任何 Office 套件</span><span class="sxs-lookup"><span data-stu-id="1eb09-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="1eb09-125">无</span><span class="sxs-lookup"><span data-stu-id="1eb09-125">None</span></span>  <br/> |<span data-ttu-id="1eb09-126">使用即点即用安装 Office 2016 32-bit</span><span class="sxs-lookup"><span data-stu-id="1eb09-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="1eb09-127">有 32 位即点即用版 Office（2016 或更低版本）且无独立应用</span><span class="sxs-lookup"><span data-stu-id="1eb09-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="1eb09-128">无</span><span class="sxs-lookup"><span data-stu-id="1eb09-128">None</span></span>  <br/> |<span data-ttu-id="1eb09-129">根据需要，升级到了最新的 32 位即点即用版 Office 2016 **\***</span><span class="sxs-lookup"><span data-stu-id="1eb09-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="1eb09-130">现有的即点即用32位版本的 Office 和即点即用的32位或64位独立 Office 应用程序（例如 Visio、Project）</span><span class="sxs-lookup"><span data-stu-id="1eb09-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="1eb09-131">无</span><span class="sxs-lookup"><span data-stu-id="1eb09-131">None</span></span>  <br/> |<span data-ttu-id="1eb09-132">独立应用不受影响。</span><span class="sxs-lookup"><span data-stu-id="1eb09-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="1eb09-133">套件升级到 32 位即点即用版 Office 2016</span><span class="sxs-lookup"><span data-stu-id="1eb09-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="1eb09-134">有 32 位即点即用版 Office 和任何 32 位/64 位（除 2016）MSI 独立 Office 应用</span><span class="sxs-lookup"><span data-stu-id="1eb09-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="1eb09-135">无</span><span class="sxs-lookup"><span data-stu-id="1eb09-135">None</span></span>  <br/> |<span data-ttu-id="1eb09-136">独立应用不受影响。</span><span class="sxs-lookup"><span data-stu-id="1eb09-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="1eb09-137">套件升级到 32 位即点即用版 Office 2016</span><span class="sxs-lookup"><span data-stu-id="1eb09-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="1eb09-138">有任何 64 位即点即用版 Office</span><span class="sxs-lookup"><span data-stu-id="1eb09-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="1eb09-139">卸载64位 Office 应用程序（如果可以使用32位 Office 应用替换它们）</span><span class="sxs-lookup"><span data-stu-id="1eb09-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="1eb09-140">如果删除了 Office 64 位应用，则安装 32 位即点即用版 Office 2016</span><span class="sxs-lookup"><span data-stu-id="1eb09-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="1eb09-141">安装有 MSI Office 2016，有/无独立应用</span><span class="sxs-lookup"><span data-stu-id="1eb09-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="1eb09-142">卸载 MSI Office 2016。</span><span class="sxs-lookup"><span data-stu-id="1eb09-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="1eb09-p106">安装了 32 位即点即用版 Office 2016。不更改独立应用</span><span class="sxs-lookup"><span data-stu-id="1eb09-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="1eb09-145">安装有 MSI Office 2013（或更低版本）和/或独立 Office 应用</span><span class="sxs-lookup"><span data-stu-id="1eb09-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="1eb09-146">无</span><span class="sxs-lookup"><span data-stu-id="1eb09-146">None</span></span>  <br/> |<span data-ttu-id="1eb09-147">32 位即点即用版 Office 2016 和预先存在的 MSI Office 安装（和独立应用）并存</span><span class="sxs-lookup"><span data-stu-id="1eb09-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="1eb09-148">**(\*) 注意：** 由于一个已知 bug，不升级到 32 位即点即用版 Office 2016。</span><span class="sxs-lookup"><span data-stu-id="1eb09-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="1eb09-149">正在进行修补。</span><span class="sxs-lookup"><span data-stu-id="1eb09-149">A fix is in progress.</span></span> 
  