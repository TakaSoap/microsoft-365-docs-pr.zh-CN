---
title: 关于"AutoPilot 配置文件"设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 配置文件可帮助您控制 Windows 在用户设备上的安装方式。 配置文件包含 "跳过 Cortana 安装" 等默认和可选设置。
ms.openlocfilehash: d43a15e5f3dc83596b5c23dd0ceb416b24810298
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276933"
---
# <a name="about-autopilot-profile-settings"></a>关于"AutoPilot 配置文件"设置

## <a name="autopilot-profile-settings"></a>AutoPilot 配置文件设置

您可以使用 AutoPilot 配置文件控制 Windows 在用户设备上的安装方式。 配置文件包含以下设置。
  
 **自动设置的 AutoPilot 默认功能 (必需):**
  
|**设置**|**说明**|
|:-----|:-----|
|跳过 Cortana、OneDrive 和 OEM 注册  <br/> |跳过安装使用者应用程序, 如 Cortana 和个人 OneDrive。 只要他或她是设备上的本地管理员, 设备用户就可以在以后安装这些设备。 由于设备将由 Microsoft 365 商业版管理, 因此将跳过原始制造商注册。  <br/> |
|使用贵公司品牌登录体验  <br/> |如果您的公司[将公司商标添加到 Office 365 登录页面](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), 则设备用户将在登录时获得该体验。  <br/> |
|使用已配置的 AAD 帐户的 MDM 自动注册。  <br/> |用户标识将由 Azure Active directory 管理, 并且用户将使用其 Microsoft 365 商业版凭据登录 Windows 和 Office 365。  <br/> |
   
 **可选设置:**
  
|**设置**|**说明**|
|:-----|:-----|
|跳过隐私设置 (默认情况下禁用)  <br/> |如果此选项设置为 **"开**", 则在用户首次登录时, 设备用户将看不到设备和 Windows 的许可协议。  <br/> |
|不允许用户成为本地管理员  <br/> |如果此选项设置为 **"开**", 则设备用户将无法安装任何个人应用程序, 如 Cortana。  <br/> |
   
