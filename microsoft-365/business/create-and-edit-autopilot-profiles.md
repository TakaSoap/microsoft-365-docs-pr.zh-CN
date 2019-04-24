---
title: 创建和编辑 AutoPilot 配置文件
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: '了解如何创建、编辑、删除或删除 AutoPilot 配置文件。 '
ms.openlocfilehash: 85fc897b2f428afae8d55feeb577021adaa30f72
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277061"
---
# <a name="create-and-edit-autopilot-profiles"></a>创建和编辑 AutoPilot 配置文件

## <a name="create-a-profile"></a>创建配置文件

配置文件适用于单个设备或一组设备，
  
1. 在 Microsoft 365 Business 管理中心中, 选择 "**设备** \> " **AutoPilot**。
  
2. 在 " **AutoPilot** " 页上, 选择 "**配置文件**" 选项卡\> **创建配置文件**。
    
3. 在" **创建配置文件**"页面上，输入可帮助识别配置文件的文件名称，例如"市场营销"，启用所需设置（请参阅[关于"AutoPilot 配置文件"设置](autopilot-profile-settings.md)获取详细信息），并选择" **保存**"。
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>对设备应用配置文件

创建配置文件之后，可将其应用到一个或一组设备。可以选择[分步指南](add-autopilot-devices-and-profile.md)中的现有配置文件，然后将其应用于新设备，或可替换某个设备或一组设备的现有配置文件。 
  
1. 在" **准备 Windows**"页面上，选择" **设备**"选项卡。 
    
2. Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>编辑、删除或移除配置文件

将配置文件分配给一个设备后，便可以更新该文件，即使已将该设备提供给一个用户。如果设备连接了 internet，系统会在设置过程中下载最新版本的配置文件。如果用户将其设备恢复为出厂默认设置，设备将再次下载配置文件的最新更新。 
  
### <a name="edit-a-profile"></a>编辑配置文件

1. 在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。 
    
2. Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.
    
    如果在用户将设备连接到 internet 之前执行此操作，配置文件会应用于设置过程。
    
### <a name="delete-a-profile"></a>删除配置文件

1. 在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。 
    
2. Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.
    
    如果删除了配置文件，该文件会从之前分配到的一个或一组设备中移除。
    
### <a name="remove-a-profile"></a>移除配置文件

1. 在" **准备 Windows**"页面上，选择" **设备**"选项卡。 
    
2. Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.
    
