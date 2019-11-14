---
title: 使用分步指南添加 Autopilot 设备和配置文件
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows AutoPilot 为你的企业设置新的 Windows 10 设备。
ms.openlocfilehash: 5f40dac57285b83da57d4506bac58e562475522c
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323087"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>使用分步指南添加 Autopilot 设备和配置文件

您可以使用 Windows AutoPilot 为你的企业设置**新**的 Windows 10 设备，以便在你将其提供给员工时可以使用它们。
  
## <a name="device-requirements"></a>设备要求

设备必须满足以下要求：
  
- Windows 10 版本1703或更高版本
    
- 尚未通过 Windows 开箱即用体验的新设备
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>使用设置指南创建设备和配置文件

[![显示管理中心正在更改且你可在 aka.ms/aboutM365preview 找到更多详细信息的标签。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

如果尚未创建设备组或配置文件，最好的入门方式是使用分步指南。 您还可以[添加设备](create-and-edit-autopilot-devices.md)并[将配置文件分配](create-and-edit-autopilot-profiles.md)给它们，而无需使用指南。 
  
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。

2. 在左侧导航窗格中，选择 "**设备** \> " " **AutoPilot**"。

    ![在管理中心中，选择 "设备"，然后选择 "AutoPilot"。](media/AutoPilot.png)
  
2. 在 " **AutoPilot** " 页上，单击或点击 "**启动指南**"。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. 在 "**使用设备列表上载 .csv 文件**" 页上，浏览到已准备就绪的位置。CSV 文件，然后**打开** \> "**下一步**"。 该文件必须具有三个标头：
    
    - 列 A：设备序列号
    
    - 列 B：Windows 产品 ID
    
    - 列 C：硬件哈希
    
    您可以从您的硬件供应商处获取此信息，也可以使用[G-et-windowsautopilotinfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)生成 CSV 文件。 
    
    有关详细信息，请参阅[设备列表 CSV 文件](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e)。还可在" **上传设备列表 .csv 文件**"页面下载示例文件。 
    
4. 在 "**分配配置文件**" 页上，可以选择现有配置文件，也可以创建新的配置文件。 如果尚未安装，系统会提示您创建一个。 
    
    配置文件是可应用到单个设备或一组设备的一系列设置。
    
    默认功能是必需的，并会自动设置。 默认功能是：
    
    - 跳过 Cortana、OneDrive 和 OEM 注册。
    
    - 使用公司品牌创建登录体验。
    
    - 将设备连接到 Azure Active Directory 帐户，并自动注册以由 Microsoft 365 商业版管理。
    
    有关详细信息，请参阅[关于 AutoPilot 配置文件设置](autopilot-profile-settings.md)。 
    
5. 其他设置是" **跳过隐私设置**"和" **不允许用户成为本地管理员**"。默认情况下，这两者设置为" **关**"。 
    
    选择" **下一步**"。
    
6. **您已完成**指示您创建的配置文件（或选择的）将应用于您通过上载设备列表创建的设备组。 这些设置将在设备用户下次登录时生效。 选择****“关闭”。
    