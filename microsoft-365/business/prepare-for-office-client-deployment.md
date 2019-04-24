---
title: 准备通过 Microsoft 365 Business 部署 Office 客户端
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 了解如何将32位 Office 应用自动安装到 Windows 10 计算机并将其更新。
ms.openlocfilehash: c8e93746b89925d6b6a928a474fe5736e2834987
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286635"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>准备通过 Microsoft 365 Business 部署 Office 客户端

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>准备在客户端计算机上自动安装 Office 应用

可以使用 Microsoft 365 商业版 将 32 位 Office 应用自动安装到 Windows 10 计算机，并确保始终使用最新版本。
  
这种方法最适用的情况是最终用户的计算机使用 Windows 10 商业版，而且：
  
- 没有现有的 Office 桌面应用（Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive）。
    
    或
    
- 安装了即点即用 Office 版本。
    
若要确定是否拥有即点即用版本的 Office，请在任何 Office 应用中，转到" **文件**"\>" **帐户**"（如 Outlook 中的 **Office 帐户**。如果看到"Office 更新"（如下图所示），则表示使用了即点即用进行安装。 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **谁可以从此功能受益**
  
电脑属于以下情况的最终用户：
  
- **具有** Windows 10 商业版用户许可证、处于活动状态的 Microsoft 365 商业版 许可证、Windows 10 创意者更新，并且加入了 Azure Active Directory。 
    
- **没有** 64 位 Office 应用（如：Word、Exce、Powerpoint）。如果需要 64 位 Office 应用，则不建议使用此功能，因为不支持从 Microsoft 365 商业版 管理控制台触发 64 位 Office 2016 即点即用版本。 
    
- **没有** 任何 2016 Windows Installer (MSI) 独立应用（如 Visio 或 Project）。Microsoft 365 商业版 将 Office 升级到 Office 2016 即点即用版，这不适用于 Office 2016 MSI 独立应用。 
    
下表详细说明了最终用户/管理员需要执行哪些操作才能从 Microsoft 365 商业版 管理控制台成功部署 32 位即点即用版 Office，具体取决于其开始时的状态。
  
|**启动 Office 安装状态**|**Microsoft 365 商业版 Office 安装之前要执行的操作**|**结束状态**|
|:-----|:-----|:-----|
|未安装任何 Office 套件  <br/> |无  <br/> |使用即点即用来安装 32 位 2016 Office  <br/> |
|有 32 位即点即用版 Office（2016 或更低版本）且无独立应用  <br/> |无  <br/> |根据需要，升级到了最新的 32 位即点即用版 Office 2016 **\*** <br/> |
|有 32 位即点即用版 Office 和 32 位/64 位即点即用独立 Office 应用（例如 Visio、Project）  <br/> |无  <br/> |独立应用不受影响。套件升级到 32 位即点即用版 Office 2016  <br/> |
|有 32 位即点即用版 Office 和任何 32 位/64 位（除 2016）MSI 独立 Office 应用  <br/> |无  <br/> |独立应用不受影响。套件升级到 32 位即点即用版 Office 2016  <br/> ||||
|有任何 64 位即点即用版 Office  <br/> |如果可将 64 位 Office 应用替换为 32 位 Office 应用，则卸载该 64 位应用  <br/> |如果删除了 Office 64 位应用，则安装 32 位即点即用版 Office 2016  <br/> |
|安装有 MSI Office 2016，有/无独立应用  <br/> |卸载 MSI Office 2016。  <br/> |安装了 32 位即点即用版 Office 2016。不更改独立应用  <br/> |
|安装有 MSI Office 2013（或更低版本）和/或独立 Office 应用  <br/> |无  <br/> |32 位即点即用版 Office 2016 和预先存在的 MSI Office 安装（和独立应用）并存  <br/> |
||||
   
 **(\*) 注意：** 由于一个已知 bug，不升级到 32 位即点即用版 Office 2016。正在修复该错误。 
  


