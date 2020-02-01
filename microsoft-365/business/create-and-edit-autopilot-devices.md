---
title: 创建和编辑 AutoPilot 设备
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 了解如何使用 Microsoft 365 商业版中的 AutoPilot 上传设备。 您可以将配置文件分配给一个或一组设备。
ms.openlocfilehash: 5a99f691b0325f511f34e3a6c3a20f08ee8d909f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594003"
---
# <a name="create-and-edit-autopilot-devices"></a>创建和编辑 AutoPilot 设备

## <a name="upload-a-list-of-devices"></a>上传设备列表

您可以使用分步[指南](add-autopilot-devices-and-profile.md)上载设备，但也可以在 "**设备**" 选项卡中上传设备。 
  
设备必须满足以下要求：
  
- Windows 10 版本1703或更高版本
    
- 尚未通过 Windows 开箱即用体验的新设备

1. 在 Microsoft 365 Business 管理中心中，选择 "**设备** \> " **AutoPilot**。
  
2. 在 " **AutoPilot** " 页上， **** 选择 " \>设备" 选项卡 "**添加设备**"。
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 在 "**添加设备**" 面板上，浏览到已准备好\> **保存** \> **** 的[设备列表 CSV 文件](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。
    
    您可以从您的硬件供应商处获取此信息，也可以使用[G-et-windowsautopilotinfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)生成 CSV 文件。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>向单个设备或一组设备应用配置文件

1. 在 "**准备 Windows** " 页面上，选择 "**设备**" 选项卡，然后选中一个或多个设备旁边的复选框。 
    
2. 在" **设备**"面板中，从" **分配的配置文件**"下拉列表中选择一个配置文件。 
    
    如果还没有任何配置文件，请参阅[创建和编辑 AutoPilot 配置文件](create-and-edit-autopilot-profiles.md)，获取相关说明。 
    
