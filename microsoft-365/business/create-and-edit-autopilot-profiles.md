---
title: 创建和编辑 AutoPilot 配置文件
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 了解如何创建 AutoPilot 配置文件并将其应用到设备，以及编辑或删除配置文件或从设备中删除配置文件。
ms.openlocfilehash: 6a8057969242d839ebbb4cbef8d26dd3f1858c59
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417328"
---
# <a name="create-and-edit-autopilot-profiles"></a>创建和编辑 AutoPilot 配置文件

## <a name="create-a-profile"></a>创建配置文件

配置文件适用于单个设备或一组设备，
  
1. 在 Microsoft 365 Business 管理中心中，选择 "**设备** \> " **AutoPilot**。
  
2. 在 " **AutoPilot** " 页上，选择 "**配置文件**" 选项卡\> **创建配置文件**。
    
3. 在 "**创建配置文件**" 页上，输入可帮助您识别它的配置文件的名称，例如 "营销"。 打开所需的设置，然后选择 "**保存**"。 有关 AutoPilot 配置文件设置的详细信息，请参阅[关于 AutoPilot 配置文件设置](autopilot-profile-settings.md)。
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>对设备应用配置文件

创建配置文件后，可以将其应用到一个或一组设备。 您可以在分步[指南](add-autopilot-devices-and-profile.md)中选取现有配置文件，并将其应用于新设备，或替换某个设备或设备组的现有配置文件。 
  
1. 在" **准备 Windows**"页面上，选择" **设备**"选项卡。 
    
2. 选中设备名称旁边的复选框，然后在 "**设备**" 面板中，从 "**分配的配置文件**" 下拉列表\> **中**选择一个配置文件。
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>编辑、删除或移除配置文件

将配置文件分配给一个设备后，便可以更新该文件，即使已将该设备提供给一个用户。如果设备连接了 internet，系统会在设置过程中下载最新版本的配置文件。如果用户将其设备恢复为出厂默认设置，设备将再次下载配置文件的最新更新。 
  
### <a name="edit-a-profile"></a>编辑配置文件

1. 在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。 
    
2. 选中设备名称旁边的复选框，然后在 "**配置文件**" 面板中，更新任何可用设置\> **保存**。
    
    如果在用户将设备连接到 internet 之前执行此操作，配置文件会应用于设置过程。
    
### <a name="delete-a-profile"></a>删除配置文件

1. 在" **准备 Windows**"页面上，选择" **配置文件**"选项卡。 
    
2. 选中设备名称旁边的复选框，然后在 "**配置文件**" 面板中选择 "**删除配置文件** \> **保存**"。
    
    如果删除了配置文件，该文件会从之前分配到的一个或一组设备中移除。
    
### <a name="remove-a-profile"></a>移除配置文件

1. 在" **准备 Windows**"页面上，选择" **设备**"选项卡。 
    
2. 选中设备名称旁边的复选框，然后在 "**设备**" 面板中，从 "分配的**配置文件**" \> **下拉列表中**选择 "**无**"。
    
