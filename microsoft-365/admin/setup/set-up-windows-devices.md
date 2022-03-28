---
title: 为Windows用户设置Microsoft 365 商业高级版设备
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 为Windows用户设置运行Windows 10 专业版的设备Microsoft 365 商业高级版，从而实现集中式管理和安全控制。
ms.openlocfilehash: f64114ac6a117ac3eacc9b6aa9de31366e847f33
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403580"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>为Windows用户设置Microsoft 365 商业高级版设备

## <a name="before-you-begin"></a>准备工作

在你可以为 Microsoft 365 商业高级版 用户设置 Windows 设备之前，请确保所有 Windows 设备都运行 Windows 10 专业版 版本 1703 (创意者更新) 或 Windows 11 专业版。 

Windows 10 专业版 (或Windows 11 专业版) 是部署 Windows 10 商业版 的先决条件，这是一组补充 Windows 10 专业版 和 Windows 11 专业版，并启用集中管理和安全Microsoft 365 商业高级版。

[详细了解有关Microsoft 365 商业高级版](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab)。

## <a name="windows-10-pro-and-windows-11-pro"></a>Windows 10 专业版 和 Windows 11 专业版

如果你有运行 Windows 早期版本的 Windows 设备（如 Windows 7 Pro、Windows 8 专业版 或 Windows 8.1 专业版）的 Microsoft 365 商业高级版 订阅，则你的 Microsoft 365 商业高级版 订阅授权你将这些设备升级到Windows 10 专业版 或 Windows 11 专业版。
  
若要详细了解如何升级Windows，请参阅以下文章：

- [将Windows家庭版升级到Windows Pro](https://support.microsoft.com/windows/upgrade-windows-home-to-windows-pro-ef34d520-e73f-3198-c525-d1a218cc2818)
- [升级到 Windows 10 专业版](https://support.microsoft.com/windows/upgrade-to-windows-10-pro-71ecc746-0f81-a4c0-bd4b-0db8559e0796)
  
升级后，请参阅验证[设备是否连接到](#verify-the-device-is-connected-to-azure-ad)Azure AD验证是否具有升级，或确保升级有效。

## <a name="join-windows-devices-to-your-organizations-azure-ad"></a>将Windows设备加入到组织的 Azure AD

当你的公司的所有 Windows 设备在 Windows 10 专业版 或 Windows 11 专业版 运行时，你可以将这些设备加入到组织的 Azure Active Directory (Azure AD) 。 

1. 在Windows设备上，选择Windows徽标，然后选择"设置图标。
  
2. In **设置**， go to **AccountsAccess**  >  work or school \> **连接**.
  
3. 键入您的电子邮件地址，然后选择"下一 **步"**。

4. 按照提示完成此过程。

## <a name="verify-the-device-is-connected-to-azure-ad"></a>验证设备是否连接到 Azure AD

若要验证同步状态，请在"访问工作或学校"页面上设置"**连接到** **_** \<organization name\> "区域以公开"信息"和"断开连接"**按钮**。 选择 **"** 信息"获取同步状态。 
  
在" **同步状态"** 页面上，选择 **"同步** "，获取电脑上的最新移动设备管理策略。  
  
## <a name="next-steps"></a>后续步骤

若要设置移动设备，请参阅为用户Microsoft 365 商业高级版[移动设备。](set-up-mobile-devices.md) 

若要增强保护，请参阅保护企业计划的 Microsoft 365 [10 种方法](../security-and-compliance/secure-your-business-data.md)。
  
