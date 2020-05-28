---
title: Microsoft 365 for business for Office 客户端部署准备
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 了解如何在 Windows 10 计算机上自动安装32位 Office 应用并将其更新。
ms.openlocfilehash: 6f3a80be9729a3818607c0f42e2cc7ece66a07ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401314"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Microsoft 365 for business for Office 客户端部署准备

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>准备在客户端计算机上自动安装 Office 应用

您可以使用 Microsoft 365 for business 在 Windows 10 计算机上自动安装32位 Office 应用程序，并将更新保持最新。
  
如果最终用户的计算机在 Windows 10 商业版上，则自动安装最适用：
  
- 没有现有的 Office 桌面应用（Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access 和 OneDrive）。
    
    或
    
- 安装了即点即用 Office 版本。
    
若要确定是否拥有即点即用版本的 Office，请在任何 Office 应用中，转到" **文件**"\>" **帐户**"（如 Outlook 中的 **Office 帐户**。 如果看到如下图所示的**Office 更新**，则说明安装是通过即点即用完成的。 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **拥有此功能的好处**
  
电脑属于以下情况的最终用户：
  
- **具有**Windows 10 商业版用户许可证、适用于商业版许可证的活动 Microsoft 365、Windows 10 创意者更新和已加入 Azure active Directory。 
    
- **没有64位**Office 应用程序（例如： Word、Excel、PowerPoint）。 如果需要64位 Office 应用程序，则此功能不合适，因为不支持触发来自 Microsoft 365 for business 管理控制台的 64-位2016即点即用版本的 Office。 
    
- **没有** 任何 2016 Windows Installer (MSI) 独立应用（如 Visio 或 Project）。 Microsoft 365 for business 将 Office 升级到 Office 2016 即点即用版本，这不适用于 Office 2016 MSI 独立应用程序。 
    
下表显示最终用户/管理员可能需要执行的操作，具体取决于其开始状态，从 Microsoft 365 for business administration console 中获得成功的32位即点即用版本的 Office 部署。
  
|**启动 Office 安装状态**|**在 Microsoft 365 for business Office 安装之前要执行的操作**|**结束状态**|
|:-----|:-----|:-----|
|未安装任何 Office 套件  <br/> |无  <br/> |使用即点即用安装 Office 2016 32-bit  <br/> |
|有 32 位即点即用版 Office（2016 或更低版本）且无独立应用  <br/> |无  <br/> |根据需要，升级到了最新的 32 位即点即用版 Office 2016 **\*** <br/> |
|现有的即点即用32位版本的 Office 和即点即用的32位或64位独立 Office 应用程序（例如 Visio、Project）  <br/> |无  <br/> |独立应用不受影响。 套件升级到 32 位即点即用版 Office 2016  <br/> |
|有 32 位即点即用版 Office 和任何 32 位/64 位（除 2016）MSI 独立 Office 应用  <br/> |无  <br/> |独立应用不受影响。 套件升级到 32 位即点即用版 Office 2016  <br/> ||||
|有任何 64 位即点即用版 Office  <br/> |卸载64位 Office 应用程序（如果可以使用32位 Office 应用替换它们）  <br/> |如果删除了 Office 64 位应用，则安装 32 位即点即用版 Office 2016  <br/> |
|安装有 MSI Office 2016，有/无独立应用  <br/> |卸载 MSI Office 2016。  <br/> |安装了 32 位即点即用版 Office 2016。不更改独立应用  <br/> |
|安装有 MSI Office 2013（或更低版本）和/或独立 Office 应用  <br/> |无  <br/> |32 位即点即用版 Office 2016 和预先存在的 MSI Office 安装（和独立应用）并存  <br/> |
||||
   
 **(\*) 注意：** 由于一个已知 bug，不升级到 32 位即点即用版 Office 2016。 正在进行修补。 
  
