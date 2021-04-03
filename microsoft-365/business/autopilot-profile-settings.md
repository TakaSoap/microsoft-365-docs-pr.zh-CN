---
title: 关于"AutoPilot 配置文件"设置
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 配置文件可帮助你控制如何在用户设备上安装 Windows。 配置文件包含默认和可选设置，如跳过 Cortana 安装。
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578499"
---
# <a name="about-autopilot-profile-settings"></a>关于"AutoPilot 配置文件"设置

## <a name="autopilot-profile-settings"></a>AutoPilot 配置文件设置

可以使用 AutoPilot 配置文件来控制如何在用户设备上安装 Windows。 配置文件包含以下设置。
  
 **AutoPilot 默认 (需要) 自动设置的功能：**
  
|**设置**|**说明**|
|:-----|:-----|
|跳过 Cortana、OneDrive 和 OEM 注册  <br/> |跳过 Cortana 和个人 OneDrive 等消费者应用的安装。 只要用户是设备的本地管理员，设备用户就可以稍后安装它们。 由于设备由 Microsoft 365 商业高级版管理，因此将跳过原始制造商注册。  <br/> |
|使用公司品牌登录体验  <br/> |如果你的公司有"将公司品牌添加到 [Microsoft 365](../admin/setup/customize-sign-in-page.md)登录"页，设备用户将在登录时获得该体验。  <br/> |
|使用已配置的 AAD 帐户自动注册 MDM。  <br/> |用户标识由 Azure Active Directory 管理，用户将使用其 Microsoft 365 商业高级版凭据登录 Windows 和 Microsoft 365。  <br/> |
   
 **可选设置：**
  
|**设置**|**说明**|
|:-----|:-----|
|默认情况下，跳过 ("关闭")   <br/> |如果此选项设置为 **"开"，** 则设备用户首次登录时将看不到设备和 Windows 的许可协议。  <br/> |
|不允许用户成为本地管理员  <br/> |如果此选项设置为 **"打开"，** 则设备用户将无法安装任何个人应用，例如 Cortana。<br/> |
