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
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>准备通过 Microsoft 365 商业版部署 Office 客户端

本文适用于 Microsoft 365 商业高级版。

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>准备在客户端计算机上自动安装 Office 应用

可以使用 Microsoft 365 商业高级版在 Windows 10 计算机上自动安装 32 位 Office 应用，并使它们具有最新更新。
  
如果最终用户的计算机在 Windows 10 商业计算机上并且：
  
- 没有现有的 Office 桌面应用（Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive）。
    
    或
    
- 安装了即点即用 Office 版本。
    
若要确定是否拥有即点即用版本的 Office，请在任何 Office 应用中，转到" **文件**"\>" **帐户**"（如 Outlook 中的 **Office 帐户**。 如果看到下图所示的 **Office** 更新，则使用即点即用完成安装。 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **谁从拥有此功能中获益**
  
电脑属于以下情况的最终用户：
  
- **拥有**  Windows 10 商业版用户许可证、活动的 Microsoft 365 商业版许可证、Windows 10 创意者更新，并且已加入 Azure Active Directory。 
    
- **没有 64** 位 Office 应用程序，例如 (Word、Excel、PowerPoint) 。 如果需要 64 位 Office 应用，则此功能不适合，因为不支持从 Microsoft 365 商业版管理控制台触发 64 位 2016 即点即用版本的 Office。 
    
- **没有** 任何 2016 Windows Installer (MSI) 独立应用（如 Visio 或 Project）。 Microsoft 365 商业版将 Office 升级到 Office 2016 即点即用版本，它不能用于 Office 2016 MSI 独立应用。 
    
下表显示了最终用户/管理员可能需要执行哪些操作，具体取决于其开始状态，才能从 Microsoft 365 商业版管理控制台成功部署 32 位即点即用版本的 Office。
  
|**启动 Office 安装状态**|**在安装 Microsoft 365 商业版 Office 之前要执行的操作**|**结束状态**|
|:-----|:-----|:-----|
|未安装任何 Office 套件  <br/> |无  <br/> |使用"单击运行"安装 Office 2016 32 位  <br/> |
|有 32 位即点即用版 Office（2016 或更低版本）且无独立应用  <br/> |无  <br/> |根据需要，升级到了最新的 32 位即点即用版 Office 2016 **\*** <br/> |
|现有的 32 位单击运行版本的 Office 和 32 位或 64 位的单击运行独立 Office 应用 (例如 Visio、Project)   <br/> |无  <br/> |独立应用不受影响。 套件升级到 32 位即点即用版 Office 2016  <br/> |
|有 32 位即点即用版 Office 和任何 32 位/64 位（除 2016）MSI 独立 Office 应用  <br/> |无  <br/> |独立应用不受影响。 套件升级到 32 位即点即用版 Office 2016  <br/> ||||
|有任何 64 位即点即用版 Office  <br/> |卸载 64 位 Office 应用（如果可以将其替换为 32 位 Office 应用）  <br/> |如果删除了 Office 64 位应用，则安装 32 位即点即用版 Office 2016  <br/> |
|安装有 MSI Office 2016，有/无独立应用  <br/> |卸载 MSI Office 2016。  <br/> |安装了 32 位即点即用版 Office 2016。不更改独立应用  <br/> |
|安装有 MSI Office 2013（或更低版本）和/或独立 Office 应用  <br/> |无  <br/> |32 位即点即用版 Office 2016 和预先存在的 MSI Office 安装（和独立应用）并存  <br/> |
||||
   
 **(\*) 注意：** 由于一个已知 bug，不升级到 32 位即点即用版 Office 2016。 正在修复。 
  
