---
title: 使用分步指南添加 Autopilot 设备和配置文件
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows AutoPilot 为你的企业设置新的 Windows 10 设备。
ms.openlocfilehash: e0802ddcc0964d0b8d102f7dbdb9116b33cdcf58
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277062"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>使用分步指南添加 Autopilot 设备和配置文件

可使用 Windows AutoPilot 为公司设置新的 Windows 10 设备，以便将设备提供给员工后，可立即用于工作。
  
## <a name="device-requirements"></a>设备要求

设备需要满足以下要求：
  
- Windows 10 版本 1703 或更高版本。
    
- 未获得过 Windows 现成体验的新设备。
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>使用设置指南创建设备和配置文件

如果尚未创建设备组或配置文件，最好首先使用分步指南，但也可在不使用指南的情况下，[添加设备](create-and-edit-autopilot-devices.md)和[分配配置文件](create-and-edit-autopilot-profiles.md)。 
  
1. 在 Microsoft 365 商业版 管理中心，定位" **设备操作**"卡，选择" **使用 Autopilot 部署 Windows**"。
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. 在" **准备 Windows**"页面，单击或点击" **启动指南**"。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. 在" **上传设备列表 .csv 文件**"页面，浏览到已准备好的 .CSV 文件所在位置，然后单击" **打开**"\>" **下一步**"。该文件应具有三个页眉：
    
  - 列 A：设备序列号
    
  - 列 B：Windows 产品 ID
    
  - 列 C：硬件哈希
    
    可从硬件供应商获取此信息，也可以使用将生成 CSV 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。 
    
    有关详细信息，请参阅[设备列表 CSV 文件](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。还可在" **上传设备列表 .csv 文件**"页面下载示例文件。 
    
4. 在" **分配配置文件**"页面上，可选择现有配置文件或新建配置文件。如果没有配置文件，系统会提示新建配置文件。 
    
    配置文件是可应用到单个设备或一组设备的一系列设置。
    
    默认功能是必需的且会自动设置。默认功能是：
    
  - 跳过 Cortana、OneDrive 和 OEM 注册。
    
  - 使用公司品牌创建登录体验。
    
  - 你的设备将连接到 Azure Active Directory 帐户，并自动注册以便由 Microsoft 365 商业版 托管。
    
    有关详细信息，请参阅
    
    [关于 AutoPilot 配置文件设置](autopilot-profile-settings.md) 。 
    
5. 其他设置是" **跳过隐私设置**"和" **不允许用户成为本地管理员**"。默认情况下，这两者设置为" **关**"。 
    
    选择" **下一步**"。
    
6. " **完成**"页面指示创建（或选择）的配置文件会应用到通过上传设备列表创建的设备组。这些设置将在设备用户下次登录时生效。选择" **关闭**"。
    