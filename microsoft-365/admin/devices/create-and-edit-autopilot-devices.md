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
ms.openlocfilehash: 784db256bb5dae16739722566b6f7a9c8511a678
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313883"
---
# <a name="create-and-edit-autopilot-devices"></a>创建和编辑 AutoPilot 设备

> [!NOTE]
> 从 2022 年 3 月 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 此产品/服务为设备提供其他安全功能。 [详细了解 Defender for Business](../../security/defender-business/mdb-overview.md)。

## <a name="upload-a-list-of-devices"></a>上传设备列表

可以使用分 [步](add-autopilot-devices-and-profile.md) 指南上传设备，但还可以在"设备"选项卡 **中上传** 设备。 
  
设备必须满足以下要求：
  
- Windows 10版本 1703 或更高版本
    
- 尚未体验全新体验Windows全新体验的新设备

1. In the Microsoft 365 管理中心， choose **Devices** \> **AutoPilot**.
  
2. 在 **AutoPilot 页面上**，选择 **"设备**"选项卡\>**"添加设备"**。
    
    ![In the Devices tab, choose Add devices.](../../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. 在"**添加设备"** 面板上，浏览到 [](../misc/device-list.md)已准备"保存""关闭"的设备列表 \> **CSV** \> **文件**。
    
    你可以从硬件供应商获取此信息，或者可以使用 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 脚本生成 CSV 文件。 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>向单个设备或一组设备应用配置文件

1. 在"**准备Windows**"页上，选择"设备 **"选项卡，** 然后选中一个或多个设备旁边的复选框。 
    
2. 在" **设备**"面板中，从" **分配的配置文件**"下拉列表中选择一个配置文件。 
    
    如果还没有任何配置文件，请参阅[创建和编辑 AutoPilot 配置文件](create-and-edit-autopilot-profiles.md)，获取相关说明。 

## <a name="see-also"></a>另请参阅

[保护业务Microsoft 365的十大方法](../security-and-compliance/secure-your-business-data.md)