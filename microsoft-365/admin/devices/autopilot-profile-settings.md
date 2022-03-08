---
title: 关于"AutoPilot 配置文件"设置
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1.keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
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
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 配置文件可帮助你控制Windows在用户设备上进行安装。 配置文件包含默认和可选设置，如 skip Cortana安装。
ms.openlocfilehash: d0b1a15ef8279234868b94ab5c16e449a54cf62f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313869"
---
# <a name="about-autopilot-profile-settings"></a>关于"AutoPilot 配置文件"设置

## <a name="autopilot-profile-settings"></a>AutoPilot 配置文件设置

> [!NOTE]
> 从 2022 年 3 月 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 此产品/服务为设备提供其他安全功能。 [详细了解 Defender for Business](../../security/defender-business/mdb-overview.md)。

可以使用 AutoPilot 配置文件来控制用户Windows安装方法。 配置文件包含以下设置。
  
 **AutoPilot 默认功能 (自动) 所需的功能：**
  
|**设置**|**说明**|
|:-----|:-----|
|跳过Cortana、OneDrive和 OEM 注册  <br/> |跳过安装消费者应用，如Cortana个人OneDrive。 只要用户是设备的本地管理员，设备用户就可以稍后安装它们。 将跳过原始制造商注册，因为设备由 Microsoft 365 商业高级版。  <br/> |
|使用公司品牌登录体验  <br/> |如果你的公司有"将公司品牌添加到Microsoft 365[登录](../setup/customize-sign-in-page.md)"页面，设备用户将在登录时获得该体验。  <br/> |
|使用已配置帐户的 MDM AAD注册。  <br/> |用户标识由用户Azure Active Directory，用户将登录到 Windows，Microsoft 365其Microsoft 365 商业高级版凭据。  <br/> |
   
 **可选设置：**
  
|**设置**|**说明**|
|:-----|:-----|
|默认情况下，跳过 ("关闭")   <br/> |如果此选项设置为 **"** 打开"，则设备用户将看不到设备的许可协议，并且Windows首次登录时将看不到该设备。  <br/> |
|不允许用户成为本地管理员  <br/> |如果此选项设置为 **"打开"**，则设备用户将无法安装任何个人应用，Cortana。<br/> |

## <a name="see-also"></a>另请参阅

[保护业务Microsoft 365的十大方法](../security-and-compliance/secure-your-business-data.md)