---
title: 创建和编辑 AutoPilot 设备
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: 了解如何在设备上使用 AutoPilot Microsoft 365 商业高级版。 你可以将配置文件分配给设备或一组设备。
ms.openlocfilehash: 96034ca50da114adca60169ae29da5948793b498
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165552"
---
# <a name="create-and-edit-autopilot-devices"></a>创建和编辑 AutoPilot 设备

## <a name="upload-a-list-of-devices"></a>上传设备列表

可以使用分 [步](add-autopilot-devices-and-profile.md) 指南上传设备，但还可以在"设备"选项卡 **中上传** 设备。 
  
设备必须满足以下要求：
  
- Windows 10版本 1703 或更高版本
    
- 尚未体验全新Windows全新体验的新设备

1. In the Microsoft 365 管理中心， choose **Devices** \> **AutoPilot**.
  
2. 在 **AutoPilot 页面上**，选择 **"设备**"选项卡 \> **"添加设备"。**
    
    ![In the Devices tab, choose Add devices.](../../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 在添加 **设备面板** 上，浏览到你准备保存关闭的设备列表 [CSV](../misc/device-list.md) \>  \> **文件**。
    
    你可以从硬件供应商获取此信息，或者可以使用 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 脚本生成 CSV 文件。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>向单个设备或一组设备应用配置文件

1. 在"**准备Windows"** 页上，选择"设备"**选项卡，** 然后选中一个或多个设备旁边的复选框。 
    
2. 在" **设备**"面板中，从" **分配的配置文件**"下拉列表中选择一个配置文件。 
    
    如果还没有任何配置文件，请参阅[创建和编辑 AutoPilot 配置文件](create-and-edit-autopilot-profiles.md)，获取相关说明。 
