---
title: 创建和编辑 AutoPilot 设备
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 了解如何使用 Microsoft 365 商业版中的 AutoPilot 上传设备。 您可以将配置文件分配给一个或一组设备。
ms.openlocfilehash: 9ae94266f5a41d8d115fc92f0f080a6fdbdc9f15
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288007"
---
# <a name="create-and-edit-autopilot-devices"></a>创建和编辑 AutoPilot 设备

## <a name="upload-a-list-of-devices"></a>上传设备列表

可以使用[分步指南](add-autopilot-devices-and-profile.md)上传设备，还可通过" **设备**"选项卡上传设备。 
  
设备需要满足以下要求：
  
- Windows 10 版本 1703 或更高版本。
    
- 未获得过 Windows 现成体验的新设备。

1. 在 Microsoft 365 Business 管理中心中，选择 "**设备** \> " **AutoPilot**。
  
2. 在 " **AutoPilot** " 页上， **** 选择 " \>设备" 选项卡 "**添加设备**"。
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 在 "**添加设备**" 面板上，浏览到已准备好\> **保存** \> **** 的[设备列表 CSV 文件](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。
    
    可从硬件供应商获取此信息，也可以使用将生成 csv 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>向单个设备或一组设备应用配置文件

1. 在" **准备 Windows**"页面上，选择" **设备**"选项卡，并勾选一个或多个设备旁边的复选框。 
    
2. 在" **设备**"面板中，从" **分配的配置文件**"下拉列表中选择一个配置文件。 
    
    如果还没有任何配置文件，请参阅[创建和编辑 AutoPilot 配置文件](create-and-edit-autopilot-profiles.md)，获取相关说明。 
    
