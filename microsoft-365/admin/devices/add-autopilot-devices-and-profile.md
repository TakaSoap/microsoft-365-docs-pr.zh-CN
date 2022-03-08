---
title: 使用分步指南添加 Autopilot 设备和配置文件
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.localizationpriority: medium
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: 了解如何使用 Windows AutoPilot 为Windows 10设置新设备，以便员工可以使用这些设备。
ms.openlocfilehash: 12e86102633ddfc19960fb561b2a626da29f0560
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314009"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>使用分步指南添加 Autopilot 设备和配置文件

> [!NOTE]
> 从 2022 年 3 月 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 此产品/服务为设备提供其他安全功能。 [详细了解 Defender for Business](../../security/defender-business/mdb-overview.md)。

可以使用 Windows AutoPilot 为Windows 10设置新的 Windows 10 设备，以便当你将这些设备供员工使用时，这些设备可供使用。
  
## <a name="device-requirements"></a>设备要求

设备必须满足以下要求：
  
- Windows 10版本 1703 或更高版本
    
- 尚未体验全新体验Windows全新体验的新设备
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>使用设置指南创建设备和配置文件

如果你尚未创建设备组或配置文件，则开始使用最佳方法就是使用分步指南。 还可以添加[设备并](create-and-edit-autopilot-devices.md)[为其分配配置文件](create-and-edit-autopilot-profiles.md)，而无需使用指南。 
  
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。

2. 在左侧导航窗格中，选择 **设备** \> **AutoPilot**。

    ![在管理中心，选择"设备"，然后选择"AutoPilot"。](../../media/AutoPilot.png)
  
2. 在 **AutoPilot** 页面上，单击或点击"开始 **指南"**。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. On the **Upload .csv file with list of devices** page， browse to a location where you have the prepared .CSV file， then **Open** \> **Next**. 文件必须具有三个标头：
    
    - 列 A：设备序列号
    
    - 列 B：Windows 产品 ID
    
    - 列 C：硬件哈希
    
    你可以从硬件供应商获取此信息，或者可以使用 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 脚本生成 CSV 文件。 
    
    有关详细信息，请参阅 [设备列表 CSV 文件](../misc/device-list.md)。还可在" **上传设备列表 .csv 文件**"页面下载示例文件。 
    
> [!NOTE]
> 此脚本使用 WMI 检索客户在 Autopilot 中注册设备Windows所需的属性。 请注意，生成的 CSV 文件不收集 Windows 产品 ID (PKID) 值是正常的，因为注册设备不需要这样做，并且输出 CSV 中的 PKID 为 NULL 完全正常。 将仅填充序列号和硬件哈希。
    
4. 在 **"分配配置文件"** 页上，您可以选择现有配置文件或创建新配置文件。 如果还没有，系统将提示你创建一个。 
    
    配置文件是可应用到单个设备或一组设备的一系列设置。
    
    默认功能是必需的，并且会自动设置。 默认功能是：
    
    - 跳过Cortana、OneDrive和 OEM 注册。
    
    - 使用公司品牌创建登录体验。
    
    - 连接你的设备Azure Active Directory帐户，并自动注册它们以由 Microsoft 365 商业高级版。
    
    有关详细信息，请参阅关于 [AutoPilot 配置文件设置](autopilot-profile-settings.md)。 
    
5. 其他设置是" **跳过隐私设置**"和" **不允许用户成为本地管理员**"。默认情况下，这两者设置为" **关**"。 
    
    选择" **下一步**"。
    
6. **你已完成指示** 你创建 (或选择) 的配置文件将应用到通过上传设备列表创建的设备组。 设置将在设备用户下次登录时生效。 选择“关闭”。

## <a name="related-content"></a>相关内容

[有关 AutoPilot 配置文件设置 (](autopilot-profile-settings.md) 文章) \
[用于保护设备和](../devices/choose-device-security.md)应用数据的选项 (文章) 保护业务计划的 Microsoft 365 [方法](../security-and-compliance/secure-your-business-data.md)